---
title: Unione delle identità basata su grafo
description: Spiega il concetto e il funzionamento dell’unione basata su grafico
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 90a285fcd96866974087c53d402e85b4a2d83ccf
workflow-type: tm+mt
source-wordcount: '1512'
ht-degree: 5%

---

# Unione delle identità basata su grafo

Nell’unione basata su grafico, specifica un set di dati evento, l’ID persistente (cookie) e lo spazio dei nomi dell’ID persona per tale set di dati. L’unione basata su grafico aggiunge una nuova colonna per l’ID dell’unione al set di dati dell’evento. Quindi utilizza l’ID persistente per eseguire query sul grafo delle identità dal servizio Experience Platform Identity, utilizzando lo spazio dei nomi specificato, per aggiornare l’ID unito.

>[!NOTE]
>
>Verificare che il set di dati sia [abilitato per Identity Service](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).
>


![Unione basata su grafico](/help/stitching/assets/gbs.png)

## IdentityMap

L&#39;unione basata su grafico supporta l&#39;utilizzo del gruppo di campi [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) nei seguenti scenari:

- Utilizzo dell&#39;identità primaria negli spazi dei nomi `identityMap` per definire l&#39;ID persistente:
   - Se più identità primarie si trovano in spazi dei nomi diversi, le identità negli spazi dei nomi vengono ordinate lessigraficamente e la prima identità viene selezionata.
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

- Utilizzo dello spazio dei nomi `identityMap` per definire l&#39;ID persistente:
   - Se in uno spazio dei nomi `identityMap` sono presenti più valori per persistentID, viene utilizzata la prima identità disponibile lessicografica.

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


## Funzionamento dell’unione basata su grafico

L’unione esegue almeno due passaggi sui dati in un determinato set di dati.

- **Unione live**: tenta di unire ogni hit (evento) nel momento in cui arriva, utilizzando l&#39;ID persistente per cercare l&#39;ID persona per lo spazio dei nomi selezionato eseguendo una query sul grafico delle identità. Se l’ID persona è disponibile dalla ricerca, viene immediatamente unito.

- **Unione ripetizioni**: *riproduce* i dati in base alle identità aggiornate dal grafico delle identità. In questa fase, gli hit da dispositivi precedentemente sconosciuti (ID persistenti) vengono uniti in quanto il grafo delle identità ha risolto l’identità per uno spazio dei nomi. La ripetizione è determinata da due parametri: **frequency** e **lookback window**. Adobe offre le seguenti combinazioni di questi parametri:
   - **Lookback giornaliero su una frequenza giornaliera**: i dati vengono ripetuti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le ripetizioni sono molto più frequenti, ma i profili non autenticati devono autenticarsi lo stesso giorno in cui visitano il sito.
   - **Lookback settimanale su una frequenza settimanale**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback settimanale (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di una settimana non vengono rielaborati fino alla successiva riproduzione settimanale.
   - **Lookback bisettimanale con frequenza settimanale**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback bisettimanale (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di due settimane non vengono rielaborati fino alla successiva riproduzione settimanale.
   - **Lookback mensile su una frequenza settimanale**: i dati vengono ripetuti ogni settimana con un intervallo di lookback mensile (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di un mese non vengono rielaborati fino alla successiva riproduzione settimanale.

- **Privacy**: quando vengono ricevute richieste relative alla privacy, oltre a rimuovere l&#39;identità richiesta dal set di dati di origine, è necessario annullare l&#39;unione di tale identità tra eventi non autenticati. Inoltre, l’identità deve essere rimossa dal grafo delle identità per evitare future unioni basate su grafo per tale identità specifica.

  >[!IMPORTANT]
  >
  >Il processo di separazione, come parte delle richieste di accesso a dati personali, cambia all’inizio del 2025. Il processo di rimozione delle unioni corrente riavvia gli eventi utilizzando la versione più recente delle identità note. Questa riassegnazione degli eventi a un’altra identità potrebbe avere conseguenze legali indesiderate. Per risolvere questi problemi, a partire dal 2025 il nuovo processo di rimozione delle unioni aggiorna gli eventi che sono oggetto della richiesta di privacy con l’ID persistente.
  > 

I dati oltre l’intervallo di lookback non vengono riprodotti. Un profilo deve eseguire l’autenticazione all’interno di un intervallo di lookback specificato affinché una visita non autenticata e una visita autenticata siano identificate insieme. Una volta riconosciuto, il dispositivo è live stitched da quel momento in poi.

Considera i due aggiornamenti del grafo delle identità seguenti nel tempo per il visitatore A (con ID persistente `246`) e il visitatore B (con ID persistente `3579`) e come questi aggiornamenti influiscono sui passaggi nell&#39;unione basata sul grafo.

![Grafico identità 3579](assets/identity-graphs.svg)

È possibile visualizzare un grafo delle identità nel tempo per un profilo specifico utilizzando [Visualizzatore grafo identità](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Consulta anche [Logica di collegamento del servizio Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) per comprendere meglio la logica utilizzata durante il collegamento delle identità.

### Passaggio 1: live stitching

L’unione live tenta di unire ogni evento, al momento della raccolta, alle informazioni note in quel momento provenienti dal grafico delle identità.

+++ Dettagli

| | Tempo | ID persistente<br/>`ECID` | Spazio dei nomi<br/>`Email` ![MappingDati](/help/assets/icons/DataMapping.svg) | ID unione (dopo unione live) |
|--:|---|---|---|---|
| 1 | 11/05/2023:00 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) *non definito* | `246` |
| 2 | 14/05/2023:00 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 15:00 12/05/2023 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 17/05/2023:00 | `3579` | `3579` ![Ramo1](/help/assets/icons/Branch1.svg) *non definito* | `3579` |
| 5 | 19:00 del 12/05/2023 | `3579` | `3579` ![Ramo1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 15:00 13/05/2023 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 16/05/2023:30 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Puoi vedere come viene risolto l’ID unione per ogni evento. In base al tempo, all’ID persistente e alla ricerca del grafico delle identità per lo spazio dei nomi specificato (nello stesso momento).
Quando la ricerca viene risolta in più ID uniti (come per l&#39;evento 7), viene selezionato il primo ID lessicografico restituito dal grafo delle identità (`a.b@yahoo.co.uk` nell&#39;esempio).

+++

### Passaggio 2: ripetere l’unione

A intervalli regolari (in base all’intervallo di lookback scelto), l’unione ripetuta ricalcola i dati storici in base alla versione più recente del grafico delle identità, al momento dell’intervallo.

+++ Dettagli

Con un&#39;unione di ripetizione che si verifica al 16:30 del 2023-05-2024, con una configurazione dell&#39;intervallo di lookback di 24 ore, alcuni eventi dell&#39;esempio vengono ricollegati (indicati da ![Ripetizione](/help/assets/icons/Replay.svg)).

| | Tempo | ID persistente<br/>`ECID` | Spazio dei nomi<br/>`Email` ![MappingDati](/help/assets/icons/DataMapping.svg) | ID unione<br/>(dopo unione live) | ID unione<br/>(dopo la ripetizione 24 ore) |
|---|---|---|---|---|---|
| 2 | 14/05/2023:00 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 15:00 12/05/2023 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Riproduci](/help/assets/icons/Replay.svg) 4 | 17/05/2023:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Riproduci](/help/assets/icons/Replay.svg) 5 | 19:00 del 12/05/2023 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Riproduci](/help/assets/icons/Replay.svg) 6 | 15:00 13/05/2023 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](/help/assets/icons/Replay.svg) 7 | 16/05/2023:30 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Con la ripetizione dell’unione che si verifica al 16:30 del 2023-05-2023, con una configurazione dell’intervallo di lookback di 7 giorni, tutti gli eventi dell’esempio vengono ricollegati.


| | Tempo | ID persistente<br/>`ECID` | Spazio dei nomi<br/>`Email` ![MappingDati](/help/assets/icons/DataMapping.svg) | ID unione<br/>(dopo unione live) | ID unione<br/>(dopo la ripetizione 7 giorni) |
|---|---|---|---|---|---|
| ![Riproduci](/help/assets/icons/Replay.svg) 1 | 11/05/2023:00 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) *non definito* | `246` | `a.b@yahoo.co.uk` |
| ![Riproduci](/help/assets/icons/Replay.svg) 2 | 14/05/2023:00 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](/help/assets/icons/Replay.svg) 3 | 15:00 12/05/2023 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](/help/assets/icons/Replay.svg) 4 | 17/05/2023:00 | `3579` | `3579` ![Ramo1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Riproduci](/help/assets/icons/Replay.svg) 5 | 19:00 del 12/05/2023 | `3579` | `3579` ![Ramo1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Riproduci](/help/assets/icons/Replay.svg) 6 | 15:00 13/05/2023 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](/help/assets/icons/Replay.svg) 7 | 16/05/2023:30 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Passaggio 3: richiesta di accesso a dati personali

Quando ricevi una richiesta di accesso a dati personali, l’ID unione viene eliminato in tutti i record relativi all’oggetto della richiesta di accesso a dati personali.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra l’effetto di una richiesta di accesso a dati personali (ad esempio al 2023-05-13 18:00) per gli eventi di esempio.

| | Tempo | ID persistente<br/>`ECID` | Spazio dei nomi<br/>`Email` ![MappingDati](/help/assets/icons/DataMapping.svg) | ID unione (dopo la richiesta di privacy) |
|--:|---|---|---|---|
| ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) 1 | 11/05/2023:00 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) 2 | 14/05/2023:00 | `246` | `246`![Ramo1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) 3 | 15:00 12/05/2023 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) 4 | 17/05/2023:00 | `3579` | `3579` ![Ramo1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) 5 | 19:00 del 12/05/2023 | `3579` | `3579` ![Ramo1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) 6 | 15:00 13/05/2023 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RimuoviCerchio](/help/assets/icons/RemoveCircle.svg) 7 | 16/05/2023:30 | `246` | `246` ![Ramo1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Ramo1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Prerequisiti

I seguenti prerequisiti si applicano in modo specifico all’unione basata su grafico:

- Il set di dati evento in Adobe Experience Platform, a cui si desidera applicare l&#39;unione, deve avere una colonna che identifica un profilo su ogni riga, l&#39;**ID persistente**. Ad esempio, un ID visitatore generato da una libreria AppMeasurement di Adobe Analytics o un ECID generato dal servizio Experience Platform Identity.
- Anche l&#39;ID persistente deve essere [definito come identità](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity) nello schema.
- Il grafo delle identità di Experience Platform Identity Service deve avere uno spazio dei nomi (ad esempio `Email` o `Phone`) da utilizzare durante l&#39;unione per risolvere il **ID persona**. Per ulteriori informazioni, consulta [Servizio Experience Platform Identity](https://experienceleague.adobe.com/it/docs/experience-platform/identity/home).

>[!NOTE]
>
>**not** richiede una licenza di Real-time Customer Data Platform per l&#39;unione basata su grafico. Il pacchetto **Prime** o versione successiva di Customer Journey Analytics include i diritti richiesti dal servizio Experience Platform Identity.


## Limitazioni

Le seguenti limitazioni si applicano in modo specifico all’unione basata su grafico:

- Le marche temporali non vengono prese in considerazione quando si esegue una query per l’ID della persona utilizzando lo spazio dei nomi specificato. Pertanto, è possibile che un ID persistente sia unito a un ID persona di un record che ha una marca temporale precedente.
- Negli scenari di dispositivi condivisi, in cui lo spazio dei nomi nel grafico contiene più identità, viene utilizzata la prima identità lessicografica. Se i limiti e le priorità dello spazio dei nomi sono configurati come parte del rilascio delle regole di collegamento del grafico, viene utilizzata l’identità dell’ultimo utente autenticato. Per ulteriori informazioni, vedere [Dispositivi condivisi](/help/use-cases/stitching/shared-devices.md).
- Esiste un limite rigido di tre mesi per la retrocompilazione delle identità nel grafico delle identità. Puoi utilizzare le identità di backfill nel caso in cui non utilizzi un’applicazione Experience Platform, come Real-time Customer Data Platform, per compilare il grafico delle identità.
- Si applicano le [protezioni del servizio Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails). Vedi, ad esempio, i seguenti [limiti statici](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Numero massimo di identità in un grafico: 50.
   - Numero massimo di collegamenti a un’identità per una singola acquisizione batch: 50.
   - Numero massimo di identità in un record XDM per l’acquisizione del grafico: 20.
   - Numero minimo di identità in un record XDM per l’acquisizione del grafico: 2.
