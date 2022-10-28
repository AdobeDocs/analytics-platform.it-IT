---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fbfc7113aef8857e11ccfba5e5e557eed16c2465
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 71%

---

# Note sulla versione di Customer Journey Analytics (CJA) (ottobre/novembre 2022)

**Ultimo aggiornamento**: 25 ottobre 2022

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni principali e aggiornamenti

| Funzione | Descrizione | [Inizio del rollout](/help/release-notes/releases.md) | [Disponibilità generale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **[!UICONTROL Key metric summary]visualizzazione** | La visualizzazione [!UICONTROL Key metric summary] consente di vedere come si presenta una metrica importante in un singolo arco temporale. Consente inoltre di confrontare le prestazioni delle metriche in due intervalli di tempo. [Ulteriori informazioni](/help/analysis-workspace/visualizations/key-metric.md) | 5 ottobre 2022 | 19 ottobre 2022 |
| **Variabili con più valori senza distinzione tra maiuscole e minuscole** | Per le variabili con più valori senza distinzione tra maiuscole e minuscole, i valori memorizzati in `mvvar1` - `mvvar3` non verranno più convertiti automaticamente in minuscole. Al contrario, i dati trasmessi dal connettore di origine di Analytics ad Adobe Experience Platform e CJA manterranno le maiuscole e minuscole originali trasmesse dalla pagina. Colonne ASC/CJA `_experience.analytics.customDimensions.lists.list1.list[]` - `_experience.analytics.customDimensions.lists.list3.list[]` sono influenzati da questo cambiamento. | N/D | 24 ottobre 2022 |
| **Registro di controllo CJA** | Il Customer Journey Analytics (CJA) consente di controllare l’attività dell’utente per vari servizi e funzionalità sotto forma di &quot;registri di controllo&quot;. Questi rappresentano una traccia di audit (o audit trail) che risulta utile per risolvere eventuali problemi, nonché per rispettare i criteri aziendali relativi alla gestione dei dati e i requisiti normativi, come l’Health Insurance Portability and Accountability Act (HIPAA). In precedenza questi registri erano disponibili solo tramite l’API Audit Logs. [Ulteriori informazioni](/help/privacy/audit-log.md) | N/D | 26 ottobre 2022 |
| **Preparazione dell&#39;HIPAA** | L&#39;Adobe ora supporta la ricezione, l&#39;utilizzo, la manutenzione o la trasmissione di informazioni sulla salute protette in Customer Journey Analytics e in altre applicazioni basate su Experienci Platform solo per i clienti Healthcare Shield. Healthcare Shield è per i clienti sanitari che sono un&#39;entità coperta o un&#39;associazione commerciale solo negli Stati Uniti. [Ulteriori informazioni](https://www.adobe.com/trust/compliance/hipaa-ready.html) | N/D | 7 novembre 2022 |
| **Protezione tramite password per progetti pianificati** | Questa funzione fa parte della preparazione all&#39;HIPAA e si applica solo ai clienti dello Healthcare Shield. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#password) | N/D/ | 7 novembre 2022. |

{style=&quot;table-layout:auto&quot;}

## Correzioni

* È stato risolto un problema a causa del quale le versioni recenti di MacOS venivano erroneamente denominate come &quot;Macintosh&quot;. Con questa correzione, la dimensione del sistema operativo inizierà a utilizzare la numerazione delle versioni &quot;MacOS&quot;, a partire da MacOS 11. (AN-301834)

### Altre correzioni apportate ad 

AN-302367; AN-302562; AN-304036

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
