---
title: Unione basata sui campi
description: Spiegazione dell’unione basata sui campi
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1705'
ht-degree: 15%

---

# Unione basata sui campi

Nell’unione basata sui campi puoi specificare un set di dati evento, nonché l’ID persistente (cookie) e l’ID transitorio (ID persona) per tale set di dati. L’unione basata sui campi crea una nuova colonna ID unita nel nuovo set di dati uniti e aggiorna questa colonna ID unita in base alle righe che hanno un ID transitorio per quello specifico ID persistente. <br/>È possibile utilizzare l&#39;unione basata sui campi quando si utilizza il Customer Journey Analytics come soluzione autonoma (non avendo accesso al servizio Experience Platform Identity e al grafo delle identità associato). Oppure, quando non desideri utilizzare il grafico delle identità disponibile.

![Unione basata sui campi](/help/stitching/assets/fbs.png)

## Funzionamento dell’unione basata sui campi

L’unione esegue almeno due passaggi sui dati in un determinato set di dati.

- **Unione live**: tenta di unire ogni hit (evento) nel momento in cui arriva. Gli hit da dispositivi che sono &quot;nuovi&quot; al set di dati (non sono mai stati autenticati) in genere non vengono uniti a questo livello. Gli hit da dispositivi già riconosciuti vengono uniti immediatamente.

- **Unione ripetizioni**: &quot;riproduce&quot; i dati in base a identificatori univoci (ID transitori) appresi. In questa fase vengono uniti gli hit da dispositivi precedentemente sconosciuti (ID persistenti) (a ID transitori). La ripetizione è determinata da due parametri: **frequency** e **lookback window**. Adobe offre le seguenti combinazioni di questi parametri:
   - **Lookback giornaliero su una frequenza giornaliera**: i dati vengono ripetuti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le ripetizioni sono molto più frequenti, ma i visitatori non autenticati devono autenticarsi lo stesso giorno in cui visitano il sito.
   - **Lookback settimanale su una frequenza settimanale**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback settimanale (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di una settimana non vengono rielaborati fino alla successiva riproduzione settimanale.
   - **Lookback bisettimanale con frequenza settimanale**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback bisettimanale (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di due settimane non vengono rielaborati fino alla successiva riproduzione settimanale.
   - **Lookback mensile su una frequenza settimanale**: i dati vengono ripetuti ogni settimana con un intervallo di lookback mensile (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di un mese non vengono rielaborati fino alla successiva riproduzione settimanale.

- **Privacy**: quando vengono ricevute richieste relative alla privacy, oltre a rimuovere l&#39;identità richiesta, è necessario annullare l&#39;unione di tale identità tra eventi non autenticati.

  >[!IMPORTANT]
  >
  >Il processo di separazione, come parte delle richieste di accesso a dati personali, cambia all’inizio del 2025. Il processo di rimozione delle unioni corrente riavvia gli eventi utilizzando la versione più recente delle identità note. Questa riassegnazione degli eventi a un’altra identità potrebbe avere conseguenze legali indesiderate. Per risolvere questi problemi, a partire dal 2025 il nuovo processo di rimozione delle unioni aggiorna gli eventi che sono oggetto della richiesta di privacy con l’ID persistente.
  > 


I dati oltre l’intervallo di lookback non vengono riprodotti. Un visitatore deve effettuare l’autenticazione all’interno di un intervallo di lookback specificato affinché una visita non autenticata e una visita autenticata siano identificate insieme. Una volta riconosciuto, il dispositivo è live stitched da quel momento in poi.

### Passaggio 1: live stitching

L’unione live tenta di unire ogni evento al momento della raccolta su dispositivi e canali noti.

+++ Dettagli

Prendi in considerazione l’esempio seguente, in cui Bob registra eventi diversi come parte di un set di dati evento.

*Dati visualizzati il giorno in cui vengono raccolti:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 dispositivi** | | **4 persone**:<br/>`246`, `Bob`, `3579`, `81911` |

Gli eventi non autenticati e autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente). Gli eventi non autenticati sui dispositivi riconosciuti sono live stitched.

L’attribuzione funziona quando la variabile personalizzata di identificazione è associata a un dispositivo. Nell&#39;esempio precedente, tutti gli eventi ad eccezione di 1, 8, 9 e 10 sono live stitched (utilizzano tutti l&#39;identificatore `Bob`). L’unione live &quot;risolve&quot; l’ID unione per gli eventi 4, 6 e 12.

I dati ritardati (dati con una marca temporale di oltre 24 ore) vengono gestiti in base al massimo impegno, dando priorità all’unione dei dati correnti per ottenere la massima qualità.

+++

### Passaggio 2: ripetere l’unione

A intervalli regolari (una volta alla settimana o una volta al giorno, a seconda dell’intervallo di lookback scelto), la ripetizione dell’unione ricalcola i dati storici in base ai dispositivi riconosciuti. Se un dispositivo invia inizialmente i dati mentre non è autenticato e poi effettua l’accesso, la ripetizione dell’unione collega tali eventi non autenticati alla persona corretta.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla ripetizione dei dati.

*Gli stessi dati dopo la ripetizione:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) | ID unione (dopo la riproduzione) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Freccia Su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Freccia Su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 dispositivi** | | **4 persone**:<br/>`246`, `Bob`, `3579`, `81911` | **2 persone**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

L’attribuzione funziona quando la variabile personalizzata di identificazione è associata a un dispositivo. Nell’esempio precedente, l’evento 1 e 10 vengono uniti in seguito alla ripetizione, lasciando separati solo gli eventi 8 e 9. E riducendo la metrica delle persone (cumulativa) a 2.

+++

### Passaggio 3: richiesta di accesso a dati personali

Quando ricevi una richiesta di accesso a dati personali, l’ID unione viene eliminato in tutti i record relativi all’oggetto della richiesta di accesso a dati personali.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra l’effetto che una richiesta di privacy per Bob ha sui dati dopo l’elaborazione. Le righe in cui Bob è autenticato vengono rimosse (2, 3, 5, 7 e 11) insieme alla rimozione di Bob come ID transitorio per altre righe.

*Gli stessi dati dopo una richiesta di accesso a dati personali per Bob:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) | ID unione (dopo la riproduzione) | ID transitorio (ID accesso) | ID unione (dopo la richiesta di privacy) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Freccia Su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Freccia Su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 dispositivi** | | **4 persone**:<br/>246, `Bob`, `3579`, `81911` | **2 persone**:<br/>Bob, `3579` |  | **3 persone**:<br/>`246`, `3579`, `81911` |

+++

## Prerequisiti

I seguenti prerequisiti si applicano in modo specifico all’unione basata sui campi:

- Il set di dati dell’evento in Adobe Experience Platform, a cui desideri applicare l’unione, deve avere due colonne che aiutino a identificare i visitatori:

   - Un **ID persistente**, un identificatore disponibile su ogni riga. Ad esempio, un ID visitatore generato da una libreria di AppMeasurement Adobe Analytics o un ECID generato dal servizio Adobe Experience Platform Identity.
   - Un **ID transitorio**, un identificatore disponibile solo su alcune righe. Ad esempio, un nome utente o un indirizzo e-mail con hash quando un visitatore si autentica. Puoi utilizzare virtualmente qualsiasi identificatore che ti piace. L’unione considera questo campo come contenente le informazioni dell’ID persona effettivo. Per risultati di unione migliori, un ID transitorio deve essere inviato all’interno degli eventi del set di dati almeno una volta per ogni ID persistente. Se prevedi di includere questo set di dati all’interno di una connessione di Customer Journey Analytics, è preferibile che anche gli altri set di dati abbiano un identificatore comune simile.

- Entrambe le colonne (ID persistente e ID transitorio) devono essere definite come un campo di identità con uno spazio dei nomi identità nello schema per il set di dati da unire. Quando si utilizza l&#39;unione delle identità in Real-time Customer Data Platform, utilizzando il gruppo di campi [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), è comunque necessario aggiungere campi di identità con uno spazio dei nomi di identità. Questa identificazione dei campi di identità è necessaria in quanto l&#39;unione di Customer Journey Analytics non supporta il gruppo di campi `identityMap`. Quando si aggiunge un campo di identità nello schema, ma si utilizza anche il gruppo di campi `identityMap`, non impostare il campo di identità aggiuntivo come identità primaria. L&#39;impostazione di un campo di identità aggiuntivo come identità primaria interferisce con il gruppo di campi `identityMap` utilizzato per Real-time Customer Data Platform.

## Limitazioni

Le seguenti limitazioni si applicano in modo specifico all’unione basata sui campi:

- Le attuali funzionalità di rekeying sono limitate a un solo passaggio (ID persistente a ID transitorio). La reimpostazione in più passaggi (ad esempio, ID persistente in un ID transitorio e quindi in un altro ID transitorio) non è supportata.
- Se un dispositivo è condiviso da più persone e il numero totale di transizioni tra gli utenti supera le 50.000, il Customer Journey Analytics non unisce più i dati per tale dispositivo.
- Le mappe ID personalizzate utilizzate nell’organizzazione non sono supportate.
- L’unione distingue tra maiuscole e minuscole. Per i set di dati generati tramite il connettore di origine di Analytics, Adobe consiglia di rivedere eventuali regole VISTA o regole di elaborazione applicabili al campo ID transitorio. Questa revisione assicura che nessuna di queste regole introduca nuove forme dello stesso ID. Ad esempio, assicurati che le regole VISTA o di elaborazione non introducano lettere minuscole nel campo ID transitorio solo per una parte degli eventi.
- L’unione non combina o concatena i campi.
- Il campo ID transitorio deve contenere un singolo tipo di ID (ID da un singolo spazio dei nomi). Ad esempio, il campo ID transitorio non deve contenere una combinazione di ID di accesso e ID e-mail.
- Se si verificano più eventi con la stessa marca temporale per lo stesso ID persistente, ma con valori diversi nel campo ID transitorio, l’unione seleziona l’ID in base all’ordine alfabetico. Quindi, se l’ID persistente A ha due eventi con la stessa marca temporale e uno degli eventi specifica Bob e l’altro specifica Ann, l’unione seleziona Ann.
- Presta attenzione agli scenari in cui gli ID transitori contengono valori segnaposto, ad esempio `Undefined`. Per ulteriori informazioni, consulta le [domande frequenti](faq.md).
