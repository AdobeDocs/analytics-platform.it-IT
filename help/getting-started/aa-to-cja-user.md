---
title: Guida per utenti di Adobe Analytics
description: Aspetti da considerare dal punto di vista dell’utente quando l’azienda trasferisce i dati da Adobe Analytics a Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '1417'
ht-degree: 94%

---

# Guida per utenti di Adobe Analytics

Se la tua organizzazione inizia a utilizzare Customer Journey Analytics (CJA), noterai alcune somiglianze e differenze tra l’applicazione Analytics tradizionale e CJA. Questa pagina illustra tali differenze per facilitare il passaggio alla nuova implementazione e al nuovo flusso di lavoro di reporting. Inoltre, fornisce alcune risorse aggiuntive sui nuovi concetti e ulteriori passaggi affinché il percorso dell’analista risulti più semplice ed efficace.

Rispetto alla soluzione Adobe Analytics tradizionale, diverse funzioni di CJA sono state rinominate e riprogettate, in base agli standard di settore. Alcuni termini che sono stati aggiornati includono segmenti, suite di rapporti virtuali, classificazioni, attributi cliente e nomi di contenitori. Le limitazioni di eVar e prop sono state superate grazie a dimensioni e metriche personalizzate flessibili.

## Cosa non è cambiato

Molte delle funzioni di reporting che conosci restano invariate.

* Puoi continuare a usare la potenza di [Analysis Workspace](/help/analysis-workspace/home.md) per analizzare i dati. Workspace funziona ancora come nell’ambiente Adobe Analytics tradizionale.
* È disponibile la stessa versione delle [dashboard di Adobe Analytics](/help/mobile-app/home.md), che funziona in modo simile in CJA e Analytics tradizionale.
* [Report Builder](/help/report-builder/report-buider-overview.md) ha una nuova interfaccia e funziona su MS Windows, MacOS e la versione web di Excel. (Prima di questa versione di Report Builder, non era possibile utilizzarlo su Mac, se non veniva eseguito su VMware.) Questa versione non supporta ancora la richiesta di dati AA tradizionale.

## Modifiche alle funzioni di reporting

Puoi accedere a molti più dati cross-channel da analizzare. Ad esempio, puoi creare un progetto Workspace che analizza le prestazioni di più canali, purché questi set di dati vengano acquisiti dalla tua organizzazione e inclusi nelle visualizzazioni dati utilizzate da CJA (vedi “Modifiche all’architettura dei dati”, di seguito).

![multi-channel-visualizations](assets/cross-channel.png)

## Modifiche all’architettura dei dati {#architecture}

CJA ottiene i dati da Adobe Experience Platform. Experience Platform permette di centralizzare e standardizzare i dati e i contenuti dei clienti da qualsiasi sistema o canale, e applica la data science e l’apprendimento automatico al fine di migliorare la progettazione e l’erogazione di esperienze personalizzate.

In Experience Platform, i dati dei clienti vengono memorizzati come set di dati, costituiti da uno [schema](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=it) e da batch di dati. Per ulteriori informazioni su Platform, consulta [Panoramica dell’architettura di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=it).

L’amministratore di CJA stabilisce [connessioni](/help/connections/create-connection.md) ai set di dati in Experience Platform. Quindi, utilizzando tali connessioni, crea delle [visualizzazioni dati](/help/data-views/data-views.md). Le visualizzazioni dati sono concettualmente simili alle suite di rapporti virtuali e rappresentano la base delle funzioni di reporting di CJA. Poiché tutti i dati originano da Experience Platform, non serve più ricorrere alle suite di rapporti come contenitori di dati.

Mediante una connessione, l’amministratore di Analytics integra i set di dati da Adobe Experience Platform in CJA, come illustrato nel seguente video:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe offre diversi modi per inserire i dati in Adobe Experience Platform, inclusi quelli delle suite di rapporti tramite il connettore di origini di Adobe Analytics e Web SDK. È possibile combinare in Experience Platform le implementazioni esistenti da diverse suite di rapporti. Le connessioni e le visualizzazioni dati basate su questi set di dati possono combinare dati che in precedenza esistevano in suite di rapporti separate.

## Modifiche al concetto di suite di rapporti virtuali {#data-views}

La funzione [!UICONTROL Data views] riprende il concetto delle attuali suite di rapporti virtuali e lo espande per [abilitare ulteriori controlli sui dati](/help/data-views/create-dataview.md), grazie alle connessioni. Con queste modifiche, impostazioni generali quali fuso orario e intervalli di timeout della sessione diventano configurabili e retroattive. A livello di report o di visualizzazione dati, inoltre, è possibile personalizzare singole impostazioni di variabili, come attribuzione e scadenza. Queste impostazioni sono retroattive e non distruttive.

Il selettore delle suite di rapporti, in alto a destra, ora consente di scegliere tra le visualizzazioni dati disponibili:

![data-view-selector](assets/data-views.png)

Per ulteriori informazioni su questo concetto, consulta [Casi d’uso per le visualizzazioni dati](/help/use-cases/data-views/data-views-usecases.md).

## Modifiche al concetto di eVar e prop

I concetti di [!UICONTROL eVars], [!UICONTROL props] e [!UICONTROL events] in Adobe Analytics tradizionale non esistono più in [!UICONTROL Customer Journey Analytics]. In Adobe Analytics, si utilizzano eVar e prop per memorizzare descrizioni di contenuti, clienti, campagne e così via, mentre con gli eventi si possono contare elementi quali ricavi, iscrizioni o lead generati. In Customer Journey Analytics è possibile accedere a entrambi questi tipi di dati, dalla barra a sinistra di Analysis Workspace, rispettivamente da Dimensioni o Metriche.

In CJA sono disponibili elementi schema illimitati, tra cui dimensioni, metriche e campi elenco. Questi sono mappati su elementi schema illimitati, tra cui dimensioni, metriche e campi elenco, in Experience Platform. Tutte le impostazioni relative a visite e attribuzione applicate dopo le regole di elaborazione in Adobe Analytics ora vengono applicate al momento della query in Customer Journey Analytics.

Grazie a questa flessibilità, puoi trovarti in situazioni in cui un singolo campo di schema può essere utilizzato sia come dimensione che come metrica, per supportare diverse esigenze di tracciamento.

## Modifiche al concetto di segmenti

Adobe ha rinominato il componente “segmenti” in “filtri” per allinearlo meglio agli standard di settore e per distinguerlo dai segmenti di Adobe Experience Platform.

[!UICONTROL Customer Journey Analytics] non utilizza più eVar, prop o eventi. Utilizza invece il nome del campo dello schema di Experience Platform su cui sono stati mappati. Ciò significa che i segmenti esistenti in Adobe Analytics non sono compatibili con [!UICONTROL Customer Journey Analytics]. Per trasferire a Customer Journey Analytics i segmenti esistenti di Adobe Analytics, guarda il video seguente:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

Non è ancora possibile condividere o pubblicare i [!UICONTROL filters] ([!UICONTROL segments]) da [!DNL Customer Journey Analytics] ad Experience Platform Unified Profile; questa funzionalità è attualmente in fase di sviluppo.

Oltre al cambiamento nel concetto di segmenti, sono stati aggiornati anche i contenitori di segmenti.

* **I contenitori Hit sono diventati contenitori [!UICONTROL Event]**. Il [!UICONTROL Event] Il contenitore consente di suddividere le informazioni sulla persona in base ai singoli eventi.
* **I contenitori Visite sono diventati contenitori [!UICONTROL Session]**. Il contenitore [!UICONTROL Session] consente di identificare le interazioni con pagine, campagne o conversioni per una specifica sessione.
* **I contenitori Visitatori sono diventati contenitori [!UICONTROL Person]**. Il [!UICONTROL Person] il contenitore include ogni sessione ed evento di una persona entro l’intervallo di tempo specificato.

## Modifiche al concetto di metriche calcolate

Le metriche calcolate hanno un nome simile in Analytics tradizionale e CJA. Tuttavia, al posto di eVar, prop o eventi, [!UICONTROL Customer Journey Analytics] utilizza qualsiasi elemento schema di Experience Platform. Di conseguenza, le metriche calcolate esistenti non sono compatibili con [!UICONTROL Customer Journey Analytics]. Per trasferire le metriche calcolate di Adobe Analytics a Customer Journey Analytics, guarda il video seguente:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Modifiche alle impostazioni di attribuzione e scadenza delle variabili

[!UICONTROL Customer Journey Analytics] applica tutte le impostazioni di variabile, incluse l’attribuzione e la scadenza, al momento della generazione del rapporto. Queste impostazioni ora risiedono in [visualizzazioni dati](/help/data-views/component-settings/persistence.md), e alcune impostazioni di variabili (come l’attribuzione) possono essere modificate nei progetti Workspace.

Una stessa visualizzazione dati può contenere più versioni della stessa variabile. Ad esempio, puoi avere una dimensione Codice di tracciamento che scade dopo 30 giorni, e un’altra che scade alla fine di una sessione. Entrambe queste dimensioni Codice di tracciamento utilizzano gli stessi dati di origine, ma impostazioni di attribuzione diverse.

Inoltre, più visualizzazioni dati possono essere basate sulla stessa connessione. Ad esempio, puoi avere una visualizzazione dati con un timeout di sessione di 30 minuti, e un’altra con un timeout di sessione di 15 minuti. Entrambe vengono elencate nel selettore in alto a destra per consentirti di passare facilmente dall’una all’altra.

## Modifiche al concetto di classificazione

Le classificazioni sono diventate “Set di dati di ricerca”. I set di dati di ricerca vengono utilizzati per cercare valori o chiavi presenti nei dati Evento o Profilo. Ad esempio, puoi caricare dati ricerca per mappare gli ID numerici presenti nei dati evento sui nomi dei prodotti. Per un caso d’uso di esempio, vedi [Aggiungere dati a livello di account come set di dati di ricerca](/help/use-cases/b2b/b2b.md).

## Modifiche al concetto di attributi cliente

Gli “attributi cliente” sono diventati “Set di dati profilo”. I set di dati profilo contengono dati applicati alle persone, agli utenti o ai clienti in [!UICONTROL Event] dati. Ad esempio, consentono di caricare dati riguardanti i tuoi clienti dal sistema CRM aziendale. Puoi scegliere l’ID persona da includere. Per ogni set di dati definito in [!DNL Experience Platform] viene definito anche uno specifico set di uno o più ID persona.

## Modifiche al modo in cui Adobe identifica i visitatori

CJA estende i concetti di identità oltre gli ECID per includere qualsiasi ID che tu voglia utilizzare: ID cliente, ID cookie, ID di unione, ID utente, codice di tracciamento e così via. Utilizzando un ID con uno spazio dei nomi comune nei diversi set di dati, oppure utilizzando l’[Analisi cross-channel](/help/cca/overview.md), diventa più facile collegare le persone tra diversi set di dati. Chiunque imposti un progetto Workspace in CJA deve comprendere gli ID utilizzati nei diversi set di dati. Il seguente video evidenzia l’uso delle identità in CJA:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Modifiche al concetto di elemento dimensione a traffico ridotto

In Adobe Analytics tradizionale, una variabile che riceve troppi valori univoci inizia a raccogliere gli elementi dimensionali definendoli [!UICONTROL Low-Traffic]. CJA presenta meno limitazioni relativamente ai campi a elevata cardinalità. Le modifiche apportate all’architettura di reporting consentono ad Analysis Workspace di fornire informazioni su molti più elementi di dimensione univoci. Per ulteriori informazioni su come CJA ottimizza il reporting per le dimensioni con numerosi valori univoci, Vedi [Long tail](../analysis-workspace/workspace-faq/long-tail.md).
