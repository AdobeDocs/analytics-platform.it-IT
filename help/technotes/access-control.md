---
title: Controllo degli accessi in Customer Journey Analytics
description: Scopri come implementare il controllo degli accessi in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 3b0c182bbf4e7a0880287a9a95ea848e6b633430
workflow-type: tm+mt
source-wordcount: '1386'
ht-degree: 17%

---

# Controllo degli accessi

Customer Journey Analytics è gestito da tre livelli di accesso o da tre ruoli: amministratore di prodotto, amministratore del profilo di prodotto e accesso a livello di utente. Questo argomento spiega nel dettaglio questi ruoli.

Inoltre, questo articolo illustra modi più granulari per limitare l’accesso, come la cura di Workspace e il controllo dell’accesso a livello di riga o di valore.

## Controllo degli accessi basato sul ruolo

Sono disponibili i seguenti livelli di controllo degli accessi basati su ruoli.

### Ruolo di amministratore del prodotto

Per impostazione predefinita, gli utenti a cui è assegnato il ruolo di amministratore prodotto dispongono delle autorizzazioni necessarie per eseguire la maggior parte delle attività all’interno di Customer Journey Analytics. Tuttavia, alcune attività richiedono autorizzazioni aggiuntive.

Per aggiungere un utente come amministratore di prodotto:

1. Vai a [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Seleziona [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Scheda Amministratori**] > [!UICONTROL **Aggiungi amministratore**].

   Agli utenti aggiunti vengono assegnate le [autorizzazioni predefinite per l&#39;amministratore del prodotto](#product-admin-default-permissions). Se necessario, puoi anche concedere loro [ulteriori autorizzazioni](#product-admin-additional-permissions).

#### Autorizzazioni predefinite per l’amministratore del prodotto

Gli amministratori di prodotto dispongono delle autorizzazioni per completare la maggior parte delle attività in Customer Journey Analytics.

Per impostazione predefinita, gli amministratori di prodotto dispongono delle autorizzazioni necessarie per eseguire le attività seguenti:

* Aggiornare ed eliminare progetti, segmenti, metriche calcolate, tipi di pubblico, annotazioni o segmenti creati da altri utenti
* Condividere progetti Workspace con tutti gli utenti
* Gestisci attività di reporting in [Gestione attività di reporting](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Esporta tabelle complete](/help/analysis-workspace/export/export-cloud.md) da Analysis Workspace

#### Autorizzazioni aggiuntive per l’amministratore del prodotto

Oltre a essere stato aggiunto come amministratore di prodotto nel **profilo di prodotto Customer Journey Analytics** in [Admin Console](https://adminconsole.adobe.com/enterprise/), sono necessarie autorizzazioni aggiuntive per completare le seguenti attività in Customer Journey Analytics:

* Crea, aggiorna ed elimina [visualizzazioni dati](/help/data-views/data-views.md).
* Crea, aggiorna ed elimina [connessioni](/help/connections/overview.md)

  Per eseguire questa attività, gli utenti devono far parte di un **profilo di prodotto Experience Platform** che fornisce le seguenti autorizzazioni:

  | Categoria | Autorizzazione | Descrizione |
  |---|---|---|
  | [!UICONTROL Sandboxes] | [!UICONTROL At least one] | Accesso alle sandbox pertinenti per le connessioni. |
  | [!UICONTROL Data Modeling] | [!UICONTROL View Schemas] | Accesso in sola lettura agli schemi e alle risorse correlate. |
  | [!UICONTROL Data Modeling] | [!UICONTROL Manage Schemas] | Accesso per leggere, creare, modificare ed eliminare schemi e risorse correlate. |
  | [!UICONTROL Data Management] | [!UICONTROL View Datasets] | Accesso in sola lettura per set di dati e schemi. |
  | [!UICONTROL Identity Management] | [!UICONTROL View Identity Namespaces] | Accesso in sola lettura per gli spazi dei nomi delle identità. |

  Per ulteriori informazioni sulle autorizzazioni di Experience Platform, vedere [Gestione delle autorizzazioni per un profilo di prodotto](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).


* Se Journey Optimizer è integrato con Customer Journey Analytics in cui sono presenti connessioni Journey Optimizer, è necessario aggiungere anche le autorizzazioni di Percorso per accedere alle connessioni:

  | Categoria | Autorizzazione | Descrizione |
  |---|---|---|
  | [!UICONTROL Journeys] | [!UICONTROL View Journeys Events, Data Sources and Actions] | Accesso in sola lettura a eventi di percorso, azioni personalizzate di percorso e origini dati di percorso. |
  | [!UICONTROL Journeys] | [!UICONTROL Manage Journeys Events, Data Sources and Actions] | Leggi, crea, modifica ed elimina eventi, origini o azioni. |
  | [!UICONTROL Journeys] | [!UICONTROL View Journeys] | Accesso in sola lettura ai percorsi. |
  | [!UICONTROL Journeys] | [!UICONTROL Manage Journeys] | Lettura, creazione, modifica ed eliminazione di percorsi. |

* Esporta set di dati in [destinazioni](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/export-datasets)

  Per eseguire questa attività, gli utenti devono far parte di un **profilo di prodotto Experience Platform** che fornisce le seguenti autorizzazioni:

  | Categoria | Autorizzazione | Descrizione |
  |---|---|---|
  | [!UICONTROL Destinations] | [!UICONTROL Manage Destinations] | Accesso per leggere, creare ed eliminare connessioni di destinazione e account di destinazione. |
  | [!UICONTROL Destinations] | [!UICONTROL Activate Destinations] | Consente agli utenti di attivare i segmenti nelle destinazioni esistenti. Abilita il passaggio di mappatura nel flusso di lavoro di attivazione. Questa autorizzazione richiede anche che l’autorizzazione Visualizza destinazioni sia concessa all’utente che desidera attivare i dati nelle destinazioni. |

  Per ulteriori informazioni sulle autorizzazioni di Experience Platform, vedere [Gestione delle autorizzazioni per un profilo di prodotto](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

* Utilizza l&#39;estensione [BI](../data-views/bi-extension.md)

  Per consentire agli utenti di utilizzare l’estensione BI, un amministratore di prodotto

   * deve garantire che le autorizzazioni Experience Platform per l’utente includano un ruolo che disponga della risorsa Servizio query con le opzioni Gestisci query e Gestisci integrazione Servizio query. Per ulteriori informazioni sulle autorizzazioni di Experience Platform, vedere [Gestione delle autorizzazioni per un profilo di prodotto](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).

     | Categoria | Autorizzazione | Descrizione |
     |---|---|---| 
     | [!UICONTROL Query Service] | [!UICONTROL Manage Queries] | Accesso per leggere, creare, modificare ed eliminare query SQL strutturate per i dati di Platform. |
     | [!UICONTROL Query Service] | [!UICONTROL Manage Query Service Integration] | Accesso per creare, aggiornare ed eliminare credenziali senza scadenza per l’accesso a Query Service. |

   * deve garantire le autorizzazioni Customer Journey Analytics appropriate per l’utente:
      * l’autorizzazione ad accedere alle visualizzazioni dati pertinenti. Vedi [!UICONTROL Data Views] in [Accesso a livello utente](#user-level-access).
      * autorizzazione per accedere all’estensione Customer Journey Analytics BI. Vedi [!UICONTROL Data View Tools] in [Accesso a livello utente](#user-level-access).

### Ruolo di amministratore del profilo di prodotto

Un profilo di prodotto è un set di autorizzazioni. Gli amministratori di prodotto creano profili di prodotto e possono assegnarli per gestire uno o più profili di prodotto. Un amministratore del profilo di prodotto può quindi:

* Gestisci i profili di prodotto assegnati. Ad esempio, aggiungendo o rimuovendo utenti o gruppi di utenti e modificando le autorizzazioni per i profili di prodotto.

* In Customer Journey Analytics, modifica le visualizzazioni dati che fanno parte di un profilo di prodotto assegnato. Gli amministratori dei profili di prodotto non possono creare nuove visualizzazioni dati.

### Accesso a livello di utente

La tabella seguente illustra le autorizzazioni di accesso principali per diverse funzionalità di Customer Journey Analytics che puoi configurare per gli utenti rilevanti. Puoi gestire diversi livelli di accesso utente tramite i profili di prodotto. Un profilo di prodotto combina una serie di autorizzazioni che puoi quindi assegnare a singoli utenti o gruppi di utenti.

La scheda **[!UICONTROL Permissions]** fa parte di ogni profilo di prodotto in [Admin Console](https://adminconsole.adobe.com/enterprise/).

![autorizzazioni di admin console](assets/permissions.png)

| Categoria | Autorizzazione | Descrizione |
| --- | --- | ---|
| [!UICONTROL Data Views] | *nome visualizzazione dati* | Se si attiva **[!UICONTROL Auto-Include]** a **[!UICONTROL On]**, gli utenti che fanno parte di questo profilo di prodotto possono visualizzare tutte le visualizzazioni di dati esistenti e appena create. Se questa impostazione è impostata su **[!UICONTROL Off]**, puoi selezionare visualizzazioni dati specifiche a cui gli utenti hanno accesso. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Analysis Workspace Access] | Consenti agli utenti di accedere a [Analysis Workspace](/help/analysis-workspace/home.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Guided Analysis Access] | Consenti agli utenti di accedere a [Analisi guidata](/help/guided-analysis/overview.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Calculated Metrics Creation] | Consenti agli utenti di creare [metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md). Gli utenti possono assegnare tag, condividere, eliminare, rinominare, approvare e non approvare solo le metriche calcolate create o condivise con esse. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Segment Creation] | Consenti agli utenti di creare [segmenti](/help/components/segments/seg-overview.md). Gli utenti possono assegnare tag, condividere, eliminare, rinominare, approvare o annullare l’approvazione solo ai segmenti creati o a quelli condivisi con loro. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Labs Access] | Consenti agli utenti di accedere alla scheda [Labs](/help/labs/labs.md) in Customer Journey Analytics. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Annotation Creation] | Consenti agli utenti di creare [annotazioni](/help/components/annotations/overview.md). Gli utenti possono assegnare tag, condividere, eliminare e rinominare solo alle annotazioni create o condivise con esse. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audience View] | Consenti agli utenti di visualizzare [tipi di pubblico](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audience Creation] | Consenti agli utenti di creare [audience](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Reporting Tools] | [!UICONTROL Audit Logs Access] | Applica il controllo delle autorizzazioni all&#39;API [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) e all&#39;interfaccia utente dei registri di controllo. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Share Project Links With Anyone] | Consenti agli utenti [di condividere i progetti con chiunque.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Reporting Tools] | [!UICONTROL Forecasting] | Consenti agli utenti di accedere alla funzionalità [Previsione](../analysis-workspace/c-forecast/forecasting.md) in Analysis Workspace |
| [!UICONTROL Reporting Tools] | [!UICONTROL AI Assistant: Product Knowledge] | Consenti agli utenti di accedere all&#39;[Assistente AI](../ai-assistant.md) per conoscere il prodotto. |
| [!UICONTROL Reporting Tools] | [!UICONTROL Intelligent Captions] | Consenti agli utenti di accedere a [Didascalie intelligenti](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL Data View Tools] | [!UICONTROL Full Table Export] | Consenti agli utenti di [esportare tabelle complete nel cloud](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL Data View Tools] | [!UICONTROL CJA BI Extension] | Consenti agli utenti di utilizzare l&#39;estensione [BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}

<!-- add this:  [!UICONTROL Reporting Tools] -[!UICONTROL Data storytelling] - Let users [generate slide presentations based on Workspace projects.](/help/analysis-workspace/curate-share/generate-slides.md) -  -->

## Cura dei progetti Workspace

È possibile utilizzare un altro livello di controllo degli accessi a livello di reporting di Workspace. Puoi limitare l’accesso a componenti specifici per determinati utenti. Per ulteriori informazioni su come limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) a livello di progetto Workspace e come la cura è associata alle visualizzazioni dati, consulta [Curare i progetti](/help/analysis-workspace/curate-share/curate.md).

## Consentire l’accesso a singole metriche o dimensioni

Non puoi concedere o negare autorizzazioni per singole metriche o dimensioni in Customer Journey Analytics, come invece puoi fare in Adobe Analytics. Le metriche e le dimensioni possono essere modificate in [visualizzazioni dati](/help/data-views/data-views.md) e sono quindi soggette a modifiche in Customer Journey Analytics. La relativa modifica comporta anche modifiche retroattive del reporting.

## Casi d’uso

Di seguito sono riportati alcuni casi d’uso che illustrano come il controllo degli accessi può essere utilizzato in scenari reali.

### Accesso di terze parti

Puoi fornire l’accesso all’amministrazione del profilo di prodotto a un responsabile del team di una terza parte con cui lavora la tua azienda. Questo amministratore può aggiungere al profilo di prodotto gli utenti del team dell’azienda. Questo amministratore del profilo di prodotto può concedere l’accesso a specifiche visualizzazioni di dati e aggiungere altri utenti di terze parti a questo profilo di prodotto. L’amministratore del profilo di prodotto può modificare le visualizzazioni dati in base ai requisiti del team di terze parti.

### Controllo dell’accesso a livello di riga

Desideri consentire agli utenti di accedere ai dati da un solo giorno. Ecco come limitare l’accesso a queste righe specifiche:

1. Creare un segmento in [!UICONTROL Settings] di una visualizzazione dati specifica, dove [!UICONTROL Day] è uguale alla data alla quale desideri che abbiano accesso ai dati. Per ulteriori informazioni, vedere [Crea visualizzazione dati](/help/data-views/create-dataview.md#settings-filters).
1. Salva la visualizzazione dati, che applica il segmento alla parte di dati dei set di dati nella connessione sottostante. Tutte le righe che non rientrano nella definizione del segmento vengono automaticamente escluse dalla visualizzazione dati e non sono disponibili in Analysis Workspace quando si utilizza questa visualizzazione dati.
1. Crea un nuovo [profilo di prodotto](#product-profile-admin-role) in Admin Console, aggiungi gli utenti al profilo di prodotto e includi solo questa visualizzazione dati specifica nel profilo di prodotto.

### Controllo dell’accesso a livello di valore

Gli utenti che hanno accesso a una visualizzazione dati possono lavorare solo con le metriche e le dimensioni incluse dall’amministratore in questa visualizzazione dati. Gli amministratori possono utilizzare le impostazioni del componente [Includi/Escludi funzionalità](/help/data-views/component-settings/include-exclude-values.md) o [Bucket di valori](../data-views/component-settings/value-bucketing.md) in una visualizzazione dati per escludere o aggregare determinati valori di dimensione da una visualizzazione dati.

Ad esempio: puoi creare una metrica denominata *Ipertensione* in una visualizzazione dati da un componente che contiene i dati dei singoli pazienti del set di dati. La bucket dei valori consente di accedere solo ai valori a bucket, pertanto gli utenti dei dati non visualizzano i dati dei singoli pazienti.
