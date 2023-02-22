---
title: Controllo degli accessi in Customer Journey Analytics
description: Scopri come implementare il controllo degli accessi in CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 34ee7954329d7dc8520031a977bb83d6e1bf3d3d
workflow-type: ht
source-wordcount: '885'
ht-degree: 100%

---

# Controllo degli accessi in Customer Journey Analytics

Customer Journey Analytics (CJA) è gestito da tre livelli di accesso o da tre ruoli: amministratore di prodotto, amministratore del profilo di prodotto e accesso a livello di utente. Questo argomento spiega nel dettaglio questi ruoli.

Inoltre, vengono descritti modi più granulari per limitare l’accesso, come la cura di Workspace e il controllo dell’accesso a livello di riga o di valore.

## Ruolo di amministratore di prodotto

Gli amministratori di prodotto sono autorizzati a completare qualsiasi attività necessaria all’interno di CJA. Per diventare amministratore di prodotto devi essere aggiunto al **Profilo prodotto Customer Journey Analytics** in [Admin Console](https://adminconsole.adobe.com/enterprise/) in [!UICONTROL Customer Journey Analytics] > scheda [!UICONTROL Admins] > [!UICONTROL Add Admin]. Gli amministratori di prodotto dispongono delle seguenti autorizzazioni:

* Creare/aggiornare/eliminare connessioni o visualizzazioni dati
* Aggiornare o eliminare progetti, filtri, metriche calcolate, tipi di pubblico, annotazioni o filtri creati da altri utenti
* Condividere progetti Workspace con tutti gli utenti

Per poter creare, aggiornare o eliminare una [connessione](/help/connections/overview.md), non è sufficiente diventare amministratore di prodotto in Customer Journey Analytics. Per creare una connessione a un set di dati di Experience Platform, è necessario disporre anche di autorizzazioni Experience Platform. In particolare, devi far parte di un **profilo di prodotto Experience Platform** che ti fornisca le seguenti autorizzazioni:

* Modellazione dati: visualizzare schemi, gestire schemi
* Gestione dati: visualizzare i set di dati, gestire i set di dati
* Acquisizione dei dati: gestisci origini
* Visualizzare gli spazi dei nomi delle identità

Per ulteriori informazioni sulle autorizzazioni di Experience Platform, consulta [Controllo degli accessi in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it).

## Ruolo di amministratore del profilo di prodotto

Un profilo di prodotto è un set di autorizzazioni. Gli amministratori dei profili di prodotto possono:

* Creare e gestire singoli profili di prodotto, ad esempio l’aggiunta di nuovi utenti o la gestione di gruppi di utenti e dei relativi profili di prodotto associati.

* Modificare le visualizzazioni dati che fanno parte di un profilo di prodotto che gestiscono in CJA. Non possono creare nuove visualizzazioni dati.

## Accesso a livello di utente

Gli utenti di Customer Journey Analytics non possono creare, modificare o visualizzare conenssioni o visualizzazioni dati. Gli utenti possono creare filtri, progetti, tipi di pubblico e metriche calcolate con autorizzazioni speciali in Admin Console.

## Cura dei progetti Workspace

È possibile utilizzare un altro livello di controllo degli accessi a livello di reporting di Workspace. Puoi limitare l’accesso a componenti specifici per determinati utenti. Per ulteriori informazioni su come limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) a livello di progetto Workspace e come la cura è associata alle visualizzazioni dati, consulta [Curare i progetti](/help/analysis-workspace/curate-share/curate.md).

## Consentire l’accesso a singole metriche o dimensioni

Non puoi concedere o negare autorizzazioni per singole metriche o dimensioni in Customer Journey Analytics, come invece puoi fare in Adobe Analytics. Le metriche e le dimensioni possono essere modificate nelle [visualizzazioni dati](/help/data-views/data-views.md) e sono quindi soggette a modifiche in CJA. La relativa modifica comporta anche modifiche retroattive del reporting.

## Casi d’uso

Di seguito sono riportati alcuni casi d’uso che illustrano come il controllo degli accessi può essere utilizzato in scenari reali.

### Accesso di terze parti

Un responsabile di team presso una terza parte con cui collabora la tua azienda può diventare amministratore di un profilo di prodotto. Tale amministratore può quindi aggiungere utenti del suo team a questo profilo di prodotto. Tale amministratore può concedere l’accesso a specifiche visualizzazioni di dati e aggiungere altri utenti a questo profilo di prodotto. Può anche modificare le visualizzazioni dati che gestisce per adattarle alle esigenze del proprio team.

### Controllo dell’accesso a livello di riga

Supponiamo che tu voglia permettere agli utenti di accedere ai dati di un solo giorno. Ecco come limitare l’accesso a queste righe specifiche:

1. Crea un filtro in CJA dove **[!UICONTROL Day]** è uguale alla data i cui dati desideri siano accessibili agli utenti.
1. In [!UICONTROL Data views] > [!UICONTROL Settings], aggiungi tale filtro alla visualizzazione dati.
1. Salva la visualizzazione dati; il filtro verrà applicato automaticamente al set di dati. Tutte le righe che non rientrano nella definizione del filtro verrano escluse automaticamente dalla visualizzazione dati modificata.
1. Crea un nuovo Profilo di prodotto in Admin Console, aggiungi gli utenti e limita il loro accesso a questa visualizzazione dati.

### Controllo dell’accesso a livello di valore

Gli utenti che hanno accesso a una visualizzazione dati possono lavorare solo con le metriche e le dimensioni incluse dall’amministratore in questa visualizzazione dati. Gli amministratori possono utilizzare la [funzionalità Inclusione/Esclusione](/help/data-views/component-settings/include-exclude-values.md) nelle visualizzazioni dati per, ad esempio, escludere determinati valori di dimensione da una visualizzazione dati.

Ecco un esempio per il settore dell’assistenza sanitaria: supponiamo di creare una metrica chiamata “Ipertensione” in una visualizzazione dati, da un set di dati che include questi dati. Il fatto che si tratti di una metrica permetterebbe di vedere il valore aggregato di questa metrica, ma non i singoli pazienti che vi rientrano.

## Autorizzazioni di CJA in Admin Console

La **[!UICONTROL Permissions]** scheda fa parte di ciascun profilo di prodotto in [Admin Console](https://adminconsole.adobe.com/enterprise/). Puoi aggiungere utenti a profili di prodotto specifici. Dopodiché dovrai assegnare i diritti a visualizzazioni di dati specifiche e specificare quali autorizzazioni hanno gli utenti in un profilo di prodotto. Di seguito sono elencate le autorizzazioni specifiche per CJA:

![autorizzazioni di admin console](assets/permissions.png)

| Autorizzazione | Definizione |
| --- | --- |
| **[!UICONTROL Data Views]** | Se si attiva **[!UICONTROL Auto-Include]** a **[!UICONTROL On]**, gli utenti che fanno parte di questo profilo di prodotto possono visualizzare tutte le visualizzazioni di dati esistenti e appena create. Se questa impostazione è impostata su **[!UICONTROL Off]**, puoi selezionare visualizzazioni dati specifiche a cui gli utenti hanno accesso. |
| **[!UICONTROL Reporting Tools]**: |  |
| **[!UICONTROL Audit Logs Access]** | Questa autorizzazione applica il controllo delle autorizzazioni all’[API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) e all’interfaccia utente dei registri di controllo. |
| **[!UICONTROL Reporting Usage Admin]** | Consente agli utenti di visualizzare ed eliminare tutti i rapporti in esecuzione nella propria azienda. |
| **[!UICONTROL Reporting Usage View]** | Consente agli utenti di visualizzare tutte le richieste di reporting simultanee. |
| **[!UICONTROL Calculated Metrics Creation]** | Consente agli utenti di creare [metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter Creation]** | Consente agli utenti di creare [filtri](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs Access]** | Consente agli utenti di accedere alla scheda [Labs](/help/labs/labs.md) in CJA. |
| **[!UICONTROL Annotation Creation]** | Consente agli utenti di creare [annotazioni](/help/components/annotations/overview.md). |
| **[!UICONTROL Audience Creation]** | Consente agli utenti di creare [segmenti di pubblico](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Audience View]** | Consente agli utenti di visualizzare [i segmenti di pubblico](/help/components/audiences/audiences-overview.md). |

{style=&quot;table-layout:auto&quot;}
