---
title: Controllo degli accessi in Customer Journey Analytics
description: Scopri come implementare il controllo degli accessi nel Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 7280bd21882e2baa31e76dbb6f983ccaf1af8633
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 52%

---

# Controllo degli accessi in Customer Journey Analytics

Il Customer Journey Analytics è gestito da tre livelli di accesso o da tre ruoli: amministratore prodotto, amministratore profilo prodotto e accesso a livello di utente. Questo argomento spiega nel dettaglio questi ruoli.

Inoltre, vengono descritti modi più granulari per limitare l’accesso, come la cura di Workspace e il controllo dell’accesso a livello di riga o di valore.

## Ruolo di amministratore di prodotto

Per impostazione predefinita, gli utenti a cui è assegnato il ruolo di amministratore prodotto dispongono delle autorizzazioni necessarie per eseguire la maggior parte delle attività all’interno del Customer Journey Analytics. Tuttavia, alcune attività richiedono autorizzazioni aggiuntive.

Per aggiungere un utente come amministratore di prodotto:

1. Vai a [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Seleziona [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Amministratori**] scheda > [!UICONTROL **Aggiungi amministratore**].

   Agli utenti aggiunti viene assegnato il [Autorizzazioni predefinite per l’amministratore del prodotto](#product-admin-default-permissions). Puoi anche concederli [autorizzazioni aggiuntive](#product-admin-additional-permissions) se necessario.

### Autorizzazioni predefinite per l’amministratore del prodotto

Gli amministratori di prodotto dispongono delle autorizzazioni per completare la maggior parte delle attività all’interno del Customer Journey Analytics.

Gli amministratori di prodotto dispongono delle autorizzazioni necessarie per eseguire le attività seguenti per impostazione predefinita:

* Creare, aggiornare ed eliminare visualizzazioni dati
* Aggiornare ed eliminare progetti, filtri, metriche calcolate, pubblico, annotazioni o filtri creati da altri utenti
* Condividere progetti Workspace con tutti gli utenti
* Gestire l’attività di reporting in [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Esporta tabelle complete](/help/analysis-workspace/export/export-cloud.md) da Analysis Workspace

### Autorizzazioni aggiuntive per l’amministratore di prodotto

Oltre ad essere aggiunto come amministratore di prodotto nella **Profilo prodotto Customer Journey Analytics** nel [Admin Console](https://adminconsole.adobe.com/enterprise/), sono necessarie autorizzazioni aggiuntive per completare le seguenti attività in Customer Journey Analytics:

* Creare, aggiornare ed eliminare dati [Connessioni](/help/connections/overview.md)

  Per eseguire questa attività, gli utenti devono far parte di un **Profilo prodotto di Experience Platform** che fornisce le seguenti autorizzazioni:
   * Modellazione dati: visualizzare schemi, gestire schemi
   * Gestione dati: visualizzare i set di dati, gestire i set di dati
   * Acquisizione dei dati: gestisci origini
   * Visualizzare gli spazi dei nomi delle identità

     Per ulteriori informazioni sulle autorizzazioni di Experience Platform, consulta [Controllo degli accessi in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it).

* Esportare i set di dati nel cloud [Destinazioni](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=it)

  Per eseguire questa attività, gli utenti devono disporre delle seguenti autorizzazioni di Experience Platform:
   * Gestire le destinazioni
   * Attivare le destinazioni

     Per ulteriori informazioni sulle autorizzazioni di Experienci Platform Destinations, consulta [Panoramica sulle destinazioni](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html#access-controls).

## Ruolo di amministratore del profilo di prodotto

Un profilo di prodotto è un set di autorizzazioni. Gli amministratori dei profili di prodotto possono:

* Creare e gestire singoli profili di prodotto, ad esempio l’aggiunta di nuovi utenti o la gestione di gruppi di utenti e dei relativi profili di prodotto associati.

* In Customer Journey Analytics, modifica le visualizzazioni dati che fanno parte di un profilo di prodotto che gestiscono. Non possono creare nuove visualizzazioni dati.

## Accesso a livello di utente

La matrice seguente illustra le autorizzazioni di accesso principali per diverse funzionalità di Customer Journey Analytics per gli amministratori di prodotti diversi da e gli amministratori di prodotti CJA. Comprendere queste autorizzazioni consente agli utenti di navigare e utilizzare CJA in modo efficace in base al loro ruolo e alle loro responsabilità all’interno dell’organizzazione.

| Funzionalità del prodotto CJA | Amministratori non di prodotto (utenti) | Amministratori di prodotto |
| --- | --- | --- |
| **Visualizzazioni dati** | Impossibile visualizzare/aggiornare/creare/eliminare | Può creare/aggiornare/eliminare |
| **Connessioni** | Impossibile visualizzare/aggiornare/creare/eliminare | Può creare/aggiornare/eliminare |
| **Filtri** | Può creare | Può creare |
| **Progetti** | Può creare | Può creare/aggiornare/eliminare |
| **Tipi di pubblico** | Creazione consentita con autorizzazioni speciali in Admin Console | Può creare |
| **Metriche calcolate** | Creazione consentita con autorizzazioni speciali in Admin Console | Può creare |

{style="table-layout:auto"}

## Cura dei progetti Workspace

È possibile utilizzare un altro livello di controllo degli accessi a livello di reporting di Workspace. Puoi limitare l’accesso a componenti specifici per determinati utenti. Per ulteriori informazioni su come limitare i componenti (dimensioni, metriche, filtri, intervalli di date) a livello di progetto Workspace e come la cura è associata alle visualizzazioni dati, consulta [Cura progetti](/help/analysis-workspace/curate-share/curate.md).

## Consentire l’accesso a singole metriche o dimensioni

Non puoi concedere o negare autorizzazioni per singole metriche o dimensioni in Customer Journey Analytics, come invece puoi fare in Adobe Analytics. Le metriche e le dimensioni possono essere modificate in [visualizzazioni dati](/help/data-views/data-views.md) e sono quindi soggetti a modifiche di Customer Journey Analytics. La relativa modifica comporta anche modifiche retroattive del reporting.

## Casi d’uso

Di seguito sono riportati alcuni casi d’uso che illustrano come il controllo degli accessi può essere utilizzato in scenari reali.

### Accesso di terze parti

Un responsabile di team presso una terza parte con cui collabora la tua azienda può diventare amministratore di un profilo di prodotto. Tale amministratore può quindi aggiungere utenti del suo team a questo profilo di prodotto. Tale amministratore può concedere l’accesso a specifiche visualizzazioni di dati e aggiungere altri utenti a questo profilo di prodotto. Può anche modificare le visualizzazioni dati che gestisce per adattarle alle esigenze del proprio team.

### Controllo dell’accesso a livello di riga

Supponiamo che tu voglia permettere agli utenti di accedere ai dati di un solo giorno. Ecco come limitare l’accesso a queste righe specifiche:

1. Crea un filtro nel Customer Journey Analytics in cui **[!UICONTROL Day]** è uguale alla data alla quale desideri che abbiano accesso ai dati.
1. In [!UICONTROL Data views] > [!UICONTROL Settings], aggiungi tale filtro alla visualizzazione dati.
1. Salva la visualizzazione dati; il filtro verrà applicato automaticamente al set di dati. Tutte le righe che non rientrano nella definizione del filtro verrano escluse automaticamente dalla visualizzazione dati modificata.
1. Crea un nuovo Profilo di prodotto in Admin Console, aggiungi gli utenti e limita il loro accesso a questa visualizzazione dati.

### Controllo dell’accesso a livello di valore

Gli utenti che hanno accesso a una visualizzazione dati possono lavorare solo con le metriche e le dimensioni incluse dall’amministratore in questa visualizzazione dati. Gli amministratori possono utilizzare la [funzionalità Inclusione/Esclusione](/help/data-views/component-settings/include-exclude-values.md) nelle visualizzazioni dati per, ad esempio, escludere determinati valori di dimensione da una visualizzazione dati.

Ecco un esempio per il settore dell’assistenza sanitaria: supponiamo di creare una metrica chiamata “Ipertensione” in una visualizzazione dati, da un set di dati che include questi dati. Il fatto che si tratti di una metrica permetterebbe di vedere il valore aggregato di questa metrica, ma non i singoli pazienti che vi rientrano.

## Autorizzazioni di Customer Journey Analytics in Admin Console

La **[!UICONTROL Permissions]** scheda fa parte di ciascun profilo di prodotto in [Admin Console](https://adminconsole.adobe.com/enterprise/). Puoi aggiungere utenti a profili di prodotto specifici. Dopodiché dovrai assegnare i diritti a visualizzazioni di dati specifiche e specificare quali autorizzazioni hanno gli utenti in un profilo di prodotto. Di seguito sono elencate le autorizzazioni specifiche per il Customer Journey Analytics:

![autorizzazioni di admin console](assets/permissions.png)

| Autorizzazione | Definizione |
| --- | --- |
| **[!UICONTROL Data Views]** | Se si attiva **[!UICONTROL Auto-Include]** a **[!UICONTROL On]**, gli utenti che fanno parte di questo profilo di prodotto possono visualizzare tutte le visualizzazioni di dati esistenti e appena create. Se questa impostazione è impostata su **[!UICONTROL Off]**, puoi selezionare visualizzazioni dati specifiche a cui gli utenti hanno accesso. |
| **[!UICONTROL Reporting Tools]**: |   |
| **[!UICONTROL Audit Logs Access]** | Questa autorizzazione applica il controllo delle autorizzazioni all’[API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) e all’interfaccia utente dei registri di controllo. |
| **[!UICONTROL Analysis Workspace Access]** | Consente agli utenti di accedere ad Analysis Workspace in Customer Journey Analytics. |
| [!UICONTROL **Accesso guidato alle analisi**] | Consente agli utenti di creare [Progetti di analisi guidata](/help/guided-analysis/overview.md). |
| [!UICONTROL **Previsione**] | Consente agli utenti di accedere alla funzione di previsione in Analysis Workspace |
| **[!UICONTROL Reporting Usage Admin]** | Consente agli utenti di visualizzare ed eliminare tutti i rapporti in esecuzione nella propria azienda. |
| **[!UICONTROL Reporting Usage View]** | Consente agli utenti di visualizzare tutte le richieste di reporting simultanee. |
| [!UICONTROL **Esportazione tabella completa**] | Consente agli utenti di [esportare tabelle complete nel cloud](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Calculated Metrics Creation]** | Consente agli utenti di creare [metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter Creation]** | Consente agli utenti di creare [filtri](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs Access]** | Consente agli utenti di accedere a [Labs](/help/labs/labs.md) nel Customer Journey Analytics. |
| **[!UICONTROL Annotation Creation]** | Consente agli utenti di creare [annotazioni](/help/components/annotations/overview.md). |
| **[!UICONTROL Audience Creation]** | Consente agli utenti di creare [segmenti di pubblico](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Audience View]** | Consente agli utenti di visualizzare [i segmenti di pubblico](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL **Condividere Collegamenti Al Progetto Con Chiunque**] | Consente agli utenti di [condividere progetti con chiunque.](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html#share-public-link) |
| **[!UICONTROL Data View Tools]**: |   |
| [!UICONTROL **Esportazione tabella completa**] | Consente agli utenti di [esportare tabelle complete nel cloud](/help/analysis-workspace/export/export-cloud.md). |
| [!UICONTROL **Accesso a SQL Query Service**] | Consente agli utenti di accedere [Servizio query in AEP](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=it). |

{style="table-layout:auto"}
