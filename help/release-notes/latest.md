---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a7636909c0570655ee6d3638e56828916044d2bd
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 66%

---

# Note sulla versione di Customer Journey Analytics (CJA) (ottobre/novembre 2022)

**Ultimo aggiornamento**: 19 ottobre 2022

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni principali e aggiornamenti

| Funzione | Descrizione | [Inizio del rollout](/help/release-notes/releases.md) | [Disponibilità generale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **[!UICONTROL Key metric summary]visualizzazione** | La visualizzazione [!UICONTROL Key metric summary] consente di vedere come si presenta una metrica importante in un singolo arco temporale. Consente inoltre di confrontare le prestazioni delle metriche in due intervalli di tempo. [Ulteriori informazioni](/help/analysis-workspace/visualizations/key-metric.md) | 5 ottobre 2022 | 19 ottobre 2022 |
| **Variabili multivalore senza distinzione tra maiuscole e minuscole** | Per le variabili multivalore senza distinzione tra maiuscole e minuscole, i valori memorizzati in `mvvar1` - `mvvar3` non verrà più abbassato automaticamente. Al contrario, i dati passati tramite il connettore di origine di Analytics a Adobe Experience Platform e CJA rifletteranno il caso originale passato dalla pagina. | N/D | 24 ottobre 2022 |
| **Registro di controllo CJA** | Il Customer Journey Analytics (CJA) consente di controllare l’attività dell’utente per vari servizi e funzionalità sotto forma di &quot;registri di controllo&quot;. Questi registri formano un percorso di audit che può aiutare a risolvere i problemi e aiutare la tua azienda a rispettare efficacemente le politiche di gestione dei dati aziendali e i requisiti normativi, come l&#39;Health Insurance Portability and Accountability Act (HIPAA). In precedenza questi registri erano disponibili solo tramite l’API Audit Logs. [Documentazione da seguire] | N/D | 26 ottobre 2022 |
| **Preparazione dell&#39;HIPAA** | Descrizione da seguire | N/D | 7 novembre 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni

* È stato risolto un problema a causa del quale le versioni recenti di MacOS venivano erroneamente denominate come &quot;Macintosh&quot;. Con questa correzione, la dimensione del sistema operativo inizierà a utilizzare la numerazione delle versioni &quot;MacOS&quot;, a partire da MacOS 11. (AN-301834)

### Altre correzioni apportate ad 

AN-302367; AN-302562

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Pagina di destinazione predefinita** | 29 settembre 2023 | La [nuova pagina di destinazione](/help/getting-started/landing.md) introdotta all’inizio di quest’anno diventerà l’esperienza predefinita per tutti gli utenti da **gennaio 2023**. La pagina corrente diventerà obsoleta e tutti dovranno utilizzare la nuova esperienza. |
| **Mappatura IP-geolocalizzazione migliorata** | 29 settembre 2022 | Il fornitore di Adobe per le ricerche IP, Digital Element, sta effettuando l’aggiornamento a un nuovo set di dati migliorato (NetAcuity Pulse) per la mappatura IP-geolocalizzazione. Per Adobe Analytics l’adozione di questo nuovo set di dati è stata posticipata a **gennaio 2023**. Il nuovo database sarà più accurato delle versioni precedenti. Quando il nuovo database verrà adottato, alcune mappature IP-geolocalizzazione verranno modificate/migliorate.<p> Anche i dati CJA forniti tramite [!UICONTROL Analytics Source Connector] sfrutteranno automaticamente le nuove mappature. |
| Condizioni per l’esecuzione automatica di **[!UICONTROL Anomaly detection]** | 29 settembre 2022 | Oggi, [!UICONTROL Anomaly detection] viene eseguito automaticamente su tutte le colonne delle tabelle a forma libera con serie temporale. Affinché i dati possano essere rapidamente disponibili per l’analisi e per velocizzare il caricamento dei progetti, Adobe cambierà il modo in cui funziona l’esecuzione automatica di [!UICONTROL Anomaly detection]. A partire dal **26 ottobre 2022**, il rilevamento delle anomalie viene eseguito automaticamente solo sulla prima colonna di metriche di una tabella. Se necessario, puoi configurare le impostazioni delle colonne per eseguire [!UICONTROL Anomaly detection] anche su altre colonne. |

{style=&quot;table-layout:auto&quot;}


## Risorse correlate

* [Note sulle versioni precedenti di CJA per il 2022](/help/release-notes/2022.md)

* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)

* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)

* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)

* [Customer Journey Analytics - Aggiornamenti della documentazione](/help/release-notes/doc-changes.md)
