---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: ddba0cdee1956048ba1875b49e8f2b77085c46da
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 40%

---

# Note sulla versione del Customer Journey Analytics corrente (CJA) (gennaio 2023)

**Ultimo aggiornamento**: 24 gennaio 2023

I rilasci di Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni principali e aggiornamenti

| Funzione | Descrizione | [Inizio del rollout](/help/release-notes/releases.md) | [Disponibilità generale](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Supporto array di oggetti per i set di dati di profilo e di ricerca** | I set di dati di profilo e i set di dati di ricerca ora supportano gli array di oggetti da utilizzare in CJA. | 11 gennaio 2023 | 19 gennaio 2023 |
| **Cartelle in Workspace** | Le cartelle consentono di organizzare e classificare i progetti per un migliore recupero e accesso. Inoltre, un **[!UICONTROL Company]** Questa cartella consente agli amministratori di creare e condividere facilmente il contenuto con tutti gli utenti di Workspace. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html?lang=it) | N/D | 11 gennaio 2023 |
| **Pagina di destinazione predefinita** | La [nuova pagina di destinazione](/help/getting-started/landing.md) introdotta in precedenza nel 2022 diventerà l’esperienza predefinita per tutti gli utenti su **11 gennaio 2023**. La pagina di destinazione precedente diventerà obsoleta e tutti dovranno utilizzare la nuova esperienza. | N/D | 11 gennaio 2023 |
| **Pagina di Project Manager obsoleta** | Con il rilascio della nuova pagina di destinazione, la funzione **[!UICONTROL Project Manager]** come indicato in **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Components]**. La nuova pagina di destinazione dispone di tutte le funzionalità della vecchia pagina di Project Manager e di altro ancora. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | N/D | 11 gennaio 2023 |
| **Pianifica cartelle di lavoro in Report Builder** | Al Customer Journey Analytics, è possibile creare pianificazioni per l&#39;invio di cartelle di lavoro a intervalli regolari. Ora i destinatari possono ricevere regolarmente gli ultimi aggiornamenti alle cartelle di lavoro. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | N/D | 11 gennaio 2023 |
| **Salvataggio automatico di nuovi progetti** | Analysis Workspace ora salva automaticamente i progetti appena creati. Se per qualsiasi motivo perdi inaspettatamente l’accesso a un nuovo progetto creato prima di salvarlo manualmente, è ora disponibile una versione di ripristino del progetto. In precedenza, i progetti venivano salvati automaticamente solo dopo essere stati inizialmente salvati manualmente. [Ulteriori informazioni](/help/analysis-workspace/build-workspace-project/save-projects.md) | N/D | 11 gennaio 2023 |
| **Preferenze utente ottimizzate** | È ora possibile configurare preferenze aggiuntive a livello di utente (in [!UICONTROL Components] > [!UICONTROL Preferences]). Quando imposti le preferenze utente, le selezioni si estendono su progetti, tabelle e visualizzazioni. La pagina Preferenze ora contiene le seguenti nuove schede, ciascuna contenente molte nuove opzioni di configurazione:<ul><li>Tabella a forma libera</li><li>Visualizzazioni>/li></ul>. Inoltre, sono ora disponibili ulteriori preferenze nella **[!UICONTROL General]** e **[!UICONTROL Project]** schede.<p>In precedenza, molte di queste preferenze erano configurabili solo per singoli progetti, tabelle e visualizzazioni. [Ulteriori informazioni](/help/analysis-workspace/user-preferences.md) | N/D | 11 gennaio 2023 |

{style=&quot;table-layout:auto&quot;}

## Correzioni

AN-287349; AN-301684; AN-305491; AN-305769; AN-307912

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Mappatura IP-geolocalizzazione migliorata** | 29 settembre 2022 | Il fornitore di Adobe per le ricerche IP, Digital Element, sta effettuando l’aggiornamento a un nuovo set di dati migliorato (NetAcuity Pulse) per la mappatura IP-geolocalizzazione. Adobe Analytics ha posticipato l&#39;adozione di questo nuovo set di dati a **11 gennaio 2023**. Il nuovo database sarà più accurato delle versioni precedenti. Quando il nuovo database verrà adottato, alcune mappature IP-geolocalizzazione verranno modificate/migliorate.<p> Anche i dati CJA forniti tramite [!UICONTROL Analytics Source Connector] sfrutteranno automaticamente le nuove mappature. |

{style=&quot;table-layout:auto&quot;}


## Risorse correlate

* [Note sulle versioni precedenti di CJA per il 2022](/help/release-notes/2022.md)

* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)

* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)

* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)

* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
