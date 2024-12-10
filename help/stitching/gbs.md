---
title: Unione basata su grafico
description: Spiegazione dell’unione basata su grafico
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 7%

---

# Unione basata su grafico


Nell’unione basata su grafico, specifica un set di dati evento, nonché l’ID persistente (cookie) e lo spazio dei nomi dell’ID transitorio (ID persona) per tale set di dati. L’unione basata su grafico crea una nuova colonna per l’ID unione nel nuovo set di dati uniti. Quindi utilizza l’ID persistente per eseguire query sul grafo delle identità dal servizio Identity di Experience Platform, utilizzando lo spazio dei nomi specificato, per aggiornare l’ID unito.

![Unione basata su grafico](/help/stitching/assets/gbs.png)

## Funzionamento dell’unione basata su grafico

L’unione esegue almeno due passaggi sui dati in un determinato set di dati.

- **Unione in tempo reale**: tenta di unire ogni hit (evento) nel momento in cui arriva, utilizzando l&#39;ID persistente per cercare l&#39;ID transitorio per lo spazio dei nomi selezionato eseguendo una query sul grafo delle identità. Se l’ID transitorio è disponibile dalla ricerca, viene immediatamente unito.

- **Unione ripetizioni**: *riproduce* i dati in base alle identità aggiornate dal grafico delle identità. In questa fase, gli hit da dispositivi precedentemente sconosciuti (ID persistenti) vengono uniti in quanto il grafo delle identità ha risolto l’identità per uno spazio dei nomi. La ripetizione è determinata da due parametri: **frequency** e **lookback window**. Adobe offre le seguenti combinazioni di questi parametri:
   - **Lookback giornaliero su una frequenza giornaliera**: i dati vengono ripetuti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le ripetizioni sono molto più frequenti, ma i visitatori non autenticati devono autenticarsi lo stesso giorno in cui visitano il sito.
   - **Lookback settimanale su una frequenza settimanale**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback settimanale (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di una settimana non vengono rielaborati fino alla successiva riproduzione settimanale.
   - **Lookback bisettimanale con frequenza settimanale**: i dati vengono ripetuti una volta alla settimana con un intervallo di lookback bisettimanale (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di due settimane non vengono rielaborati fino alla successiva riproduzione settimanale.
   - **Lookback mensile su una frequenza settimanale**: i dati vengono ripetuti ogni settimana con un intervallo di lookback mensile (vedi [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di un mese non vengono rielaborati fino alla successiva riproduzione settimanale.

- **Privacy**: quando vengono ricevute richieste relative alla privacy, oltre a rimuovere l&#39;identità richiesta dal set di dati di origine, è necessario annullare l&#39;unione di tale identità tra eventi non autenticati. Inoltre, l’identità deve essere rimossa dal grafo delle identità per evitare future unioni basate su grafo per tale identità specifica.

  >[!IMPORTANT]
  >
  >Il processo di separazione, come parte delle richieste di accesso a dati personali, cambia all’inizio del 2025. Il processo di rimozione delle unioni corrente riavvia gli eventi utilizzando la versione più recente delle identità note. Questa riassegnazione degli eventi a un’altra identità potrebbe avere conseguenze legali indesiderate. Per risolvere questi problemi, a partire dal 2025 il nuovo processo di rimozione delle unioni aggiorna gli eventi che sono oggetto della richiesta di privacy con l’ID persistente.
  > 

I dati oltre l’intervallo di lookback non vengono riprodotti. Un visitatore deve effettuare l’autenticazione all’interno di un intervallo di lookback specificato affinché una visita non autenticata e una visita autenticata siano identificate insieme. Una volta riconosciuto, il dispositivo è live stitched da quel momento in poi.

Considera i due grafici delle identità seguenti per l&#39;ID persistente `246` e `3579`, il modo in cui questi grafici vengono aggiornati nel tempo e come questi aggiornamenti influiscono sui passaggi nell&#39;unione basata su grafico.

![Grafico identità 246](assets/identity-graph-246.svg)
![Grafico identità 3579](assets/identity-graph-3579.svg)

È possibile visualizzare un grafo delle identità nel tempo per un profilo specifico utilizzando [Visualizzatore grafo identità](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Consulta anche [Logica di collegamento del servizio Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) per comprendere meglio la logica utilizzata durante il collegamento delle identità.

### Passaggio 1: live stitching

L’unione live tenta di unire ogni evento, al momento della raccolta, alle informazioni note in quel momento provenienti dal grafico delle identità.

+++ Dettagli

| | Tempo | ID persistente<br/>`ECID` | Spazio Dei Nomi<br/>`Email` ![Grafico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID unione (dopo unione live) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non definito* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non definito* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Puoi vedere come viene risolto l’ID unione per ogni evento. In base al tempo, all’ID persistente e alla ricerca del grafico delle identità per lo spazio dei nomi specificato (nello stesso momento).
Quando la ricerca viene risolta in più ID uniti (come per l&#39;evento 7), viene selezionato il primo ID lessicografico restituito dal grafo delle identità (`a.b@yahoo.co.uk` nell&#39;esempio).

+++

### Passaggio 2: ripetere l’unione

A intervalli regolari (in base all’intervallo di lookback scelto), l’unione ripetuta ricalcola i dati storici in base alla versione più recente del grafico delle identità, al momento dell’intervallo.

+++ Dettagli

Con un&#39;unione di ripetizione che si verifica alle 16:30 del 2023-05-13, con una configurazione dell&#39;intervallo di lookback di 24 ore, alcuni eventi dell&#39;esempio vengono ricollegati (indicati da ![Ripetizione](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Tempo | ID persistente<br/>`ECID` | Spazio Dei Nomi<br/>`Email` ![Grafico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID unione<br/>(dopo unione live) | ID unione<br/>(dopo la ripetizione 24 ore) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Con la ripetizione dell’unione che si verifica alle 16:30 23-05-13, con una configurazione dell’intervallo di lookback di 7 giorni, tutti gli eventi dell’esempio vengono ricollegati.


| | Tempo | ID persistente<br/>`ECID` | Spazio Dei Nomi<br/>`Email` ![Grafico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID unione<br/>(dopo unione live) | ID unione<br/>(dopo la ripetizione 7 giorni) |
|---|---|---|---|---|---|
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non definito* | `246` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Passaggio 3: richiesta di accesso a dati personali

Quando ricevi una richiesta di accesso a dati personali, l’ID unione viene eliminato in tutti i record relativi all’oggetto della richiesta di accesso a dati personali.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra l’effetto che ha una richiesta di accesso a dati personali (ad esempio alle 18:00 del 5 maggio 2023) per gli eventi di esempio.

| | Tempo | ID persistente<br/>`ECID` | Spazio Dei Nomi<br/>`Email` ![Grafico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID unione (dopo la richiesta di privacy) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Prerequisiti

I seguenti prerequisiti si applicano in modo specifico all’unione basata su grafico:

- Il set di dati dell&#39;evento in Adobe Experience Platform, a cui si desidera applicare l&#39;unione, deve avere una colonna che identifica un visitatore su ogni riga, l&#39;**ID persistente**. Ad esempio, un ID visitatore generato da una libreria Adobe Analytics AppMeasurement o un ECID generato dal servizio Experience Platform Identity.
- Anche l&#39;ID persistente deve essere [definito come identità](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity) nello schema.
- Il grafo delle identità di Experience Platform Identity Service deve avere uno spazio dei nomi (ad esempio `Email` o `Phone`) da utilizzare durante l&#39;unione per risolvere il **ID transitorio**. Per ulteriori informazioni, consulta [Experience Platform Identity Service](https://experienceleague.adobe.com/it/docs/experience-platform/identity/home).

>[!NOTE]
>
>**not** richiede una licenza Real-time Customer Data Platform per l&#39;unione basata su grafico. Il pacchetto **Prime** o versione successiva del Customer Journey Analytics include i diritti Experienci Platform richiesti per il servizio Identity.


## Limitazioni

Le seguenti limitazioni si applicano in modo specifico all’unione basata su grafico:

- Le marche temporali non vengono prese in considerazione quando si esegue una query per l’ID transitorio utilizzando lo spazio dei nomi specificato. Pertanto, è possibile che un ID persistente sia unito a un ID transitorio di un record che ha una marca temporale precedente.
- Nessun supporto per dispositivi condivisi. Quando vengono restituite più identità, eseguendo una query sul grafico delle identità utilizzando uno spazio dei nomi, viene utilizzata la prima identità lessicografica.
- Esiste un limite rigido di tre mesi per la retrocompilazione delle identità nel grafico delle identità. Puoi utilizzare le identità di backfill nel caso in cui non utilizzi un’applicazione di Experience Platform, come Real-time Customer Data Platform, per compilare il grafico delle identità.
- Si applicano le [protezioni del servizio Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails). Vedi, ad esempio, i seguenti [limiti statici](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Numero massimo di identità in un grafico: 50.
   - Numero massimo di collegamenti a un’identità per una singola acquisizione batch: 50.
   - Numero massimo di identità in un record XDM per l’acquisizione del grafico: 20.
   - Numero minimo di identità in un record XDM per l’acquisizione del grafico: 2.
