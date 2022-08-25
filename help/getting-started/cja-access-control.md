---
title: Controllo degli accessi a CJA
description: Scopri come implementare il controllo degli accessi in CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: ccb13b9632433f2fcc9c765e9527f157dad632d4
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 16%

---

# Controllo degli accessi a CJA

Il Customer Journey Analytics (CJA) è governato da tre livelli di accesso o da tre ruoli: Ruolo di amministratore del prodotto, ruolo di amministratore del profilo di prodotto e accesso a livello di utente. Questo argomento spiega questi ruoli in modo più dettagliato.

## Ruolo di amministratore prodotto

Gli amministratori di prodotto dispongono delle autorizzazioni per completare qualsiasi attività necessaria all’interno di CJA. Devi essere aggiunto come amministratore di prodotto al **Profilo prodotto Customer Journey Analytics** in [Admin Console](https://adminconsole.adobe.com/enterprise/) sotto [!UICONTROL Customer Journey Analytics] > [!UICONTROL Admins] scheda > [!UICONTROL Add Admin]. Gli amministratori di prodotto dispongono delle seguenti autorizzazioni:

* Creare/aggiornare/eliminare connessioni o visualizzazioni dati
* Aggiornare/eliminare progetti, filtri, metriche calcolate, tipi di pubblico, annotazioni o filtri creati da altri utenti
* Condividere progetti Workspace con tutti gli utenti

Diventare amministratore di prodotto nel solo Customer Journey Analytics non è sufficiente per creare, aggiornare o eliminare un [connection](/help/connections/overview.md). Per creare una connessione a un set di dati di Experience Platform, è necessario disporre anche di autorizzazioni Experience Platform. In particolare, devi far parte di un **profilo di prodotto Experience Platform** che ti fornisca le seguenti autorizzazioni:

* Modellazione dati: visualizzare schemi, gestire schemi
* Gestione dati: visualizzare i set di dati, gestire i set di dati
* Acquisizione dei dati: gestisci origini
* Visualizzare gli spazi dei nomi delle identità

Per ulteriori informazioni sulle autorizzazioni di Experience Platform, consulta [Controllo degli accessi in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it).

## Ruolo amministratore del profilo di prodotto

Un profilo di prodotto è un insieme di autorizzazioni. Gli amministratori dei profili di prodotto possono

* Crea e gestisci singoli profili di prodotto, ad esempio l’aggiunta di nuovi utenti.

* In CJA, modifica le visualizzazioni dati che fanno parte di un profilo di prodotto che gestiscono. Non possono creare nuove visualizzazioni dati.

## Accesso a livello di utente

Gli utenti del Customer Journey Analytics non possono creare, modificare o visualizzare visualizzazioni dati o connessioni. Gli utenti possono creare filtri, progetti, tipi di pubblico e metriche calcolate con autorizzazioni speciali nell’Admin Console.

## Cura dei progetti Workspace

È possibile utilizzare un altro livello di controllo degli accessi a livello di reporting di Workspace. Puoi limitare l’accesso a componenti specifici per determinati utenti. Per ulteriori informazioni su come limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) a livello di progetto Workspace e come la cura è associata alle visualizzazioni dati, consulta [Cura progetti](/help/analysis-workspace/curate-share/curate.md).

## Consentire l’accesso a singole metriche o dimensioni

Non puoi concedere o negare autorizzazioni sulle singole metriche o dimensioni in Customer Journey Analytics, come invece puoi fare in Adobe Analytics. Le metriche e le dimensioni possono essere modificate in [visualizzazioni dati](/help/data-views/data-views.md) e sono pertanto soggetti a modifiche nella CJA. La modifica di tali rapporti comporta anche modifiche retroattive del reporting.

## Casi d’uso

Di seguito sono riportati alcuni casi d’uso che illustrano come il controllo degli accessi può essere utilizzato in scenari reali.

### Accesso di terze parti

Una terza parte con cui lavora la tua azienda dispone di un lead del team che può essere reso amministratore del profilo di prodotto. Questo amministratore può quindi aggiungere utenti del suo team a questo profilo di prodotto. Questo amministratore può dare accesso a visualizzazioni di dati specifiche e aggiungere altri utenti a questo profilo di prodotto. Possono anche modificare le visualizzazioni dati sulle quali hanno il controllo per adattarle alle esigenze del proprio team.

### Controllo dell’accesso a livello di riga

Supponiamo che tu voglia dare agli utenti l’accesso ai dati da un solo giorno. Ecco come limitare l’accesso a queste righe specifiche:

1. Crea un filtro in CJA dove **[!UICONTROL Day]** è uguale alla data a cui desideri che abbiano accesso ai dati.
1. In [!UICONTROL Data views] > [!UICONTROL Settings], aggiungi il filtro alla visualizzazione dati.
1. Salva la visualizzazione dati e applica automaticamente il filtro al set di dati. Tutte le righe che non rientrano nella definizione del filtro vengono ora escluse automaticamente dalla visualizzazione dati modificata.
1. Crea un nuovo profilo di prodotto in Admin Console, aggiungi gli utenti e limita il loro accesso a questa visualizzazione dati.

### Controllo dell&#39;accesso a livello di valore

Gli utenti che hanno accesso a una visualizzazione dati possono lavorare solo con le metriche e le dimensioni incluse dall’amministratore in questa visualizzazione dati. Gli amministratori possono utilizzare [Funzionalità di inclusione/esclusione](/help/data-views/component-settings/include-exclude-values.md) nelle visualizzazioni dati per, ad esempio, escludere determinati valori di dimensione da una visualizzazione dati.

Ecco un esempio relativo all&#39;assistenza sanitaria: Supponiamo che tu crei una metrica chiamata &quot;Ipertensione&quot; in una visualizzazione dati, da un set di dati che include questi dati. Il fatto che si tratti di una metrica vi permetterebbe di vedere il valore aggregato di questa metrica, ma non i singoli pazienti che vi rientrano.

## Autorizzazioni CJA

La **[!UICONTROL Permissions]** tab fa parte di ciascun profilo di prodotto in [Admin Console](https://adminconsole.adobe.com/enterprise/). Puoi aggiungere utenti a profili di prodotto specifici. Quindi assegni i diritti a visualizzazioni di dati specifiche e specifica quali autorizzazioni hanno gli utenti in un profilo di prodotto. Di seguito sono elencate le autorizzazioni specifiche per CJA:

![autorizzazioni di admin console](assets/permissions.png)

| Autorizzazione | Definizione |
| --- | --- |
| **[!UICONTROL Data Views]** | Se si attiva/disattiva **[!UICONTROL Auto-Include]** a **[!UICONTROL On]**, gli utenti che fanno parte di questo profilo di prodotto possono visualizzare tutte le visualizzazioni di dati esistenti e appena create. Se questa impostazione è impostata su **[!UICONTROL Off]**, puoi selezionare visualizzazioni dati specifiche a cui gli utenti hanno accesso. |
| **[!UICONTROL Reporting Tools]**: |  |
| **[!UICONTROL Audit Logs Access]** | Attualmente, [registri di controllo](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) sono disponibili solo tramite l’API . Questa autorizzazione è per una futura interfaccia utente in fase di sviluppo. |
| **[!UICONTROL Reporting Usage Admin]** | Consente agli utenti di visualizzare ed eliminare i rapporti in esecuzione nella propria azienda. La funzionalità di utilizzo dei rapporti non è ancora stata rilasciata. |
| **[!UICONTROL Reporting Usage View]** | Consente agli utenti di visualizzare tutte le richieste di reporting simultanee. La funzionalità di utilizzo dei rapporti non è ancora stata rilasciata. |
| **[!UICONTROL Calculated Metrics Creation]** | Consente agli utenti di creare [metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter Creation]** | Consente agli utenti di creare [filtri](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs Access]** | Consente agli utenti di accedere al [Labs](/help/labs/labs.md) in CJA. |
| **[!UICONTROL Annotation Creation]** | Consente agli utenti di creare [annotazioni](/help/components/annotations/overview.md). |
| **[!UICONTROL Audience Creation]** | Consente agli utenti di creare [pubblico](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Audience View]** | Consente agli utenti di visualizzare [pubblico](/help/components/audiences/audiences-overview.md). |