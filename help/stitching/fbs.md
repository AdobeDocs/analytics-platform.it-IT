---
title: Unione basata sui campi
description: Spiega il concetto e il funzionamento dell’unione basata sui campi.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: 2e2620bdc6875b13492013f4ec108bae0302a25a
workflow-type: tm+mt
source-wordcount: '1797'
ht-degree: 9%

---

# Unione delle identità basata sui campi

Nell’unione basata sui campi, specifica un set di dati evento, nonché l’ID persistente (cookie) e l’ID persona per tale set di dati. L’unione basata sui campi tenta di rendere le informazioni dell’ID persona disponibili per l’analisi dei dati di Customer Journey Analytics, su qualsiasi evento anonimo fornito con un ID persistente specifico.  Tali informazioni vengono recuperate dalle righe che hanno un ID persona per tale ID persistente specifico.

Se non è possibile recuperare le informazioni sull&#39;ID persona per un evento, viene utilizzato l&#39;ID persistente per l&#39;evento *unstitched*. Di conseguenza, in una [visualizzazione dati](/help/data-views/data-views.md) associata a una [connessione](/help/connections/overview.md) che contiene il set di dati abilitato per l&#39;unione, il componente ID persona contiene il valore ID persona o il valore ID persistente a livello di evento.

È possibile utilizzare l’unione basata sui campi quando si utilizza Customer Journey Analytics come soluzione indipendente (senza avere accesso al servizio Experience Platform Identity e al grafo delle identità associato). Oppure, quando non desideri utilizzare il grafico delle identità disponibile.

![Unione delle identità basata sui campi](/help/stitching/assets/fbs.svg)


## IdentityMap

L&#39;unione basata sui campi supporta l&#39;utilizzo del gruppo di campi [`identityMap`](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition#identity) nei seguenti scenari:

- Utilizzo dell&#39;identità primaria negli spazi dei nomi `identityMap` per definire l&#39;ID persistente:
   - Se più identità primarie si trovano in spazi dei nomi diversi, le identità negli spazi dei nomi vengono ordinate lessicograficamente e la prima identità viene selezionata.
   - Se più identità primarie si trovano in un singolo spazio dei nomi, viene selezionata la prima identità primaria disponibile lessicografica.

  Nell’esempio seguente, gli spazi dei nomi e le identità restituiscono un elenco di identità primarie ordinato e, infine, l’identità selezionata.

  <table style="table-layout:auto">
     <tr>
       <th>Spazi dei nomi</th>
       <th>Elenco identità</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Elenco identità ordinate</th>
      <th>Identità selezionata</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>


- Utilizzo dello spazio dei nomi `identityMap` per definire l&#39;ID persistente o l&#39;ID persona o entrambi:
   - Se in uno spazio dei nomi `identityMap` sono presenti più valori per l&#39;ID persistente o l&#39;ID persona, viene utilizzato il primo valore disponibile lessicografico.
   - Gli spazi dei nomi per l’ID persistente e l’ID persona devono escludersi a vicenda.

  Nell’esempio seguente, hai selezionato ECID come namespace da utilizzare. La selezione determina un elenco di identità ordinate e, infine, l’identità selezionata.

  <table style="table-layout:auto">
     <tr>
       <th>Spazi dei nomi</th>
       <th>Elenco identità</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Elenco identità ordinate</th>
      <th>Identità selezionata</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>

## Funzionamento dell’unione basata sui campi

L’unione esegue almeno due passaggi sui dati in un determinato set di dati.

- **Unione live**: tenta di unire ogni hit (evento) nel momento in cui arriva. Gli hit da dispositivi che sono *nuovi* per il set di dati (non sono mai stati autenticati) in genere non vengono uniti a questo livello. Gli hit da dispositivi già riconosciuti vengono uniti immediatamente.

- **Unione ripetizioni**: *riproduce* dati in base a identificatori univoci (ID persona). In questa fase vengono uniti gli hit da dispositivi precedentemente sconosciuti (ID persistenti) (agli ID persona). Due parametri determinano la ripetizione: **frequenza** e **intervallo di lookback**. Adobe offre le seguenti combinazioni di questi parametri:
   - **Lookback giornaliero su una frequenza giornaliera**: i dati vengono ripetuti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le ripetizioni sono molto più frequenti, ma i profili non autenticati devono autenticarsi lo stesso giorno in cui visitano il sito.
   - **Lookback settimanale su una frequenza settimanale**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback settimanale (vedi [opzioni](overview.md#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di una settimana non vengono rielaborati fino alla successiva riproduzione settimanale.
   - **Lookback bisettimanale con frequenza settimanale**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback bisettimanale (vedi [opzioni](overview.md#)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di due settimane non vengono rielaborati fino alla successiva riproduzione settimanale.
   - **Lookback mensile su una frequenza settimanale**: i dati vengono ripetuti ogni settimana con un intervallo di lookback mensile (vedi [opzioni](overview.md#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di un mese non vengono rielaborati fino alla successiva riproduzione settimanale.

- **Privacy**: quando vengono ricevute richieste relative alla privacy, oltre a rimuovere l&#39;identità richiesta, è necessario annullare l&#39;unione di tale identità tra eventi non autenticati.

  >[!IMPORTANT]
  >
  >Il processo di separazione, come parte delle richieste di accesso a dati personali, cambia all’inizio del 2025. Il processo di rimozione delle unioni corrente riavvia gli eventi utilizzando la versione più recente delle identità note. Questa riassegnazione degli eventi a un’altra identità potrebbe avere conseguenze legali indesiderate. Per risolvere questi problemi, a partire dal 2025 il nuovo processo di rimozione delle unioni aggiorna gli eventi che sono oggetto della richiesta di privacy con l’ID persistente.
  > 


I dati oltre l’intervallo di lookback non vengono riprodotti. Affinché una visita non autenticata e una visita autenticata siano identificate insieme, un profilo deve essere autenticato all’interno di un determinato intervallo di lookback. Una volta riconosciuto un dispositivo, quest’ultimo viene unito in tempo reale da quel momento in poi.

### Passaggio 1: live stitching

L’unione live tenta di unire ogni evento al momento della raccolta su dispositivi e canali noti.

+++ Dettagli

Prendi in considerazione l’esempio seguente, in cui Bob registra eventi diversi come parte di un set di dati evento.

*Dati visualizzati il giorno in cui vengono raccolti:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID persona | ID risultante (dopo unione live) |
|---|---|---|---|---|
| 1 | 12/05/2023:01 | `246` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 12/05/2023:02 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 12/05/2023:03 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` ![FrecciaGiù](/help/assets/icons/ArrowDown.svg) |
| 4 | 12/05/2023:04 | `246` | - | **`Bob`** |
| 5 | 12/05/2023:05 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 12/05/2023:06 | `246` | - | **`Bob`** |
| 7 | 12/05/2023:07 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 12/05/2023:03 | `3579` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 12/05/2023:09 | `3579` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 12/05/2023:02 | `81911` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 12/05/2023:05 | `81911` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` ![FrecciaGiù](/help/assets/icons/ArrowDown.svg) |
| 12 | 12/05/2023:12 | `81911` | - | **`Bob`** |
| | | **3 dispositivi** | | **4 persone**:<br/>`246`, `Bob`, `3579`, `81911` |

Gli eventi non autenticati e autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente). Gli eventi non autenticati sui dispositivi riconosciuti sono live stitched.

L’attribuzione funziona quando la variabile personalizzata di identificazione è associata a un dispositivo. Nell&#39;esempio precedente, tutti gli eventi ad eccezione di 1, 8, 9 e 10 sono live stitched (utilizzano tutti l&#39;identificatore `Bob`). L’unione live &quot;risolve&quot; l’ID risultante per gli eventi 4, 6 e 12.

I dati ritardati (dati con una marca temporale di oltre 24 ore) vengono gestiti in base al massimo impegno, dando priorità all’unione dei dati correnti per ottenere la massima qualità.

+++ 

### Passaggio 2: ripetere l’unione

A intervalli regolari (una volta alla settimana o una volta al giorno, a seconda dell’intervallo di lookback scelto), la ripetizione dell’unione ricalcola i dati storici in base ai dispositivi riconosciuti. Se un dispositivo invia inizialmente i dati mentre non è autenticato e poi effettua l’accesso, la ripetizione dell’unione collega tali eventi non autenticati alla persona corretta.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla ripetizione dei dati.

*Gli stessi dati dopo la ripetizione:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID persona | ID risultante (dopo unione live) | ID risultante (dopo la riproduzione) |
|---|---|---|---|---|---|
| 1 | 12/05/2023:01 | `246` | - | `246` | **`Bob`** |
| 2 | 12/05/2023:02 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![FrecciaSu](/help/assets/icons/ArrowUp.svg) |
| 3 | 12/05/2023:03 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 12/05/2023:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 12/05/2023:05 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` ![FrecciaGiù](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 12/05/2023:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 12/05/2023:07 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 12/05/2023:03 | `3579` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 12/05/2023:09 | `3579` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 12/05/2023:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 12/05/2023:05 | `81911` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` ![FrecciaGiù](/help/assets/icons/ArrowDown.svg) | `Bob` ![FrecciaSu](/help/assets/icons/ArrowUp.svg) |
| 12 | 12/05/2023:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 dispositivi** | | **4 persone**:<br/>`246`, `Bob`, `3579`, `81911` | **2 persone**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

L’attribuzione funziona quando la variabile personalizzata di identificazione è associata a un dispositivo. Nell’esempio precedente, l’evento 1 e 10 vengono uniti in seguito alla ripetizione, lasciando separati solo gli eventi 8 e 9. E riducendo la metrica delle persone (cumulativa) a 2.

+++ 

### Passaggio 3: richiesta di accesso a dati personali

Quando ricevi una richiesta di accesso a dati personali, tutte le informazioni sull’identificatore impostate dal processo di unione sul valore ID persona vengono aggiornate in tutti i record in un valore ID persistente per l’oggetto utente della richiesta di accesso a dati personali.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra l’effetto che una richiesta di privacy per Bob ha sui dati dopo l’elaborazione. Le righe in cui Bob è autenticato vengono rimosse (2, 3, 5, 7 e 11) insieme alla rimozione di Bob come ID persona per altre righe.

*Gli stessi dati dopo una richiesta di accesso a dati personali per Bob:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID persona | ID risultante (dopo unione live) | ID risultante (dopo la riproduzione) | ID persona | ID risultante (dopo la richiesta di accesso a dati personali) |
|---|---|---|---|---|---|---|---|
| 1 | 12/05/2023:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 12/05/2023:02 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Freccia Su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 12/05/2023:03 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![FrecciaGiù](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 12/05/2023:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 12/05/2023:05 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![FrecciaGiù](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 12/05/2023:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 12/05/2023:07 | `246` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 12/05/2023:03 | `3579` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 12/05/2023:09 | `3579` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 12/05/2023:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 12/05/2023:05 | `81911` | `Bob` ![FrecciaDestra](/help/assets/icons/ArrowRight.svg) | `Bob` ![FrecciaGiù](/help/assets/icons/ArrowDown.svg) | `Bob` ![FrecciaSu](/help/assets/icons/ArrowUp.svg) | ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 12/05/2023:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 dispositivi** | | **4 persone**:<br/>246, `Bob`, `3579`, `81911` | **2 persone**:<br/>Bob, `3579` |  | **3 persone**:<br/>`246`, `3579`, `81911` |

+++ 

## Prerequisiti

I seguenti prerequisiti si applicano in modo specifico all’unione basata sui campi:

- Il set di dati evento in Adobe Experience Platform, a cui desideri applicare l’unione, deve avere due colonne che aiutino a identificare i profili:

   - Un **ID persistente**, un identificatore disponibile su ogni riga. Ad esempio, un ID visitatore generato da una libreria AppMeasurement di Adobe Analytics o un ECID generato dal servizio Adobe Experience Platform Identity.
   - Un **ID persona**, un identificatore disponibile solo su alcune righe. Ad esempio, un nome utente o un indirizzo e-mail con hash una volta che un profilo si autentica. Puoi utilizzare virtualmente qualsiasi identificatore che ti piace. L’unione considera questo campo come contenente le informazioni dell’ID persona effettivo. Per risultati di unione migliori, un ID persona deve essere inviato all’interno degli eventi del set di dati almeno una volta per ogni ID persistente. Se prevedi di includere questo set di dati all’interno di una connessione Customer Journey Analytics, è preferibile che anche gli altri set di dati abbiano un identificatore comune simile.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## Limitazioni

Le seguenti limitazioni si applicano in modo specifico all’unione basata sui campi:

- Le attuali funzionalità di rekeying sono limitate a un solo passaggio (ID persistente a ID persona). La reimpostazione in più passaggi (ad esempio, ID persistente in un ID persona e quindi in un altro ID persona) non è supportata.
- Se più persone condividono un dispositivo e il numero totale di transizioni tra gli utenti supera le 50.000, Customer Journey Analytics non unisce più i dati per tale dispositivo.
- Le mappe ID personalizzate utilizzate nell’organizzazione non sono supportate.
- L’unione distingue tra maiuscole e minuscole. Per i set di dati generati tramite il connettore di origine di Analytics, Adobe consiglia di rivedere eventuali regole VISTA o regole di elaborazione applicabili al campo ID persona. Questa revisione assicura che nessuna di queste regole introduca nuove forme dello stesso ID. Ad esempio, assicurati che le regole VISTA o di elaborazione non introducano lettere minuscole nel campo ID persona solo per una parte degli eventi.
- L’unione non combina o concatena i campi.
- Il campo ID persona deve contenere un singolo tipo di ID (ID da un singolo spazio dei nomi). Ad esempio, il campo ID persona non deve contenere una combinazione di ID di accesso e ID e-mail.
- Se si verificano più eventi con la stessa marca temporale per lo stesso ID persistente, ma con valori diversi nel campo ID persona, l’unione seleziona l’ID in base all’ordine alfabetico. Quindi, se l’ID persistente A ha due eventi con la stessa marca temporale e uno degli eventi specifica Bob e l’altro specifica Ann, l’unione seleziona Ann.
- Presta attenzione agli scenari in cui gli ID persona contengono valori segnaposto, ad esempio `Undefined`. Per ulteriori informazioni, consulta le [domande frequenti](faq.md).
- Non è possibile utilizzare lo stesso spazio dei nomi sia per l’ID persistente che per l’ID persona, poiché gli spazi dei nomi devono escludersi a vicenda.
