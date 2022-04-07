---
title: Guida utente di CJA per gli utenti di Adobe Analytics
description: Cosa considerare dal punto di vista di un utente quando l’azienda sposta i dati da Adobe Analytics al Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 570fb36de0ed81f001ed6115e73d1d4347f368ec
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 17%

---

# Guida utente di CJA per gli utenti di Adobe Analytics

La tua azienda sta iniziando ad assumere un Customer Journey Analytics. In qualità di utente che ha familiarità con Adobe Analytics, hai già un ottimo vantaggio. Lavorando con il Customer Journey Analytics, noterete alcune somiglianze e alcune grandi differenze. Questa pagina ha lo scopo di spiegare quelle cose che non sono cambiate, così come alcune delle principali differenze. Inoltre, ti spiegheremo come ottenere ulteriori informazioni sui nuovi concetti e ulteriori passaggi per rendere il tuo percorso cliente più semplice e di successo.

Diverse funzioni di CJA sono state rinominate e riarchitettate, se confrontate con il tradizionale Adobe Analytics, per allinearsi agli standard di settore. Alcuni termini aggiornati includono segmenti, suite di rapporti virtuali, classificazioni, attributi cliente e nomi di contenitori. Concetti familiari come eVar e prop non esistono più, insieme ai limiti imposti.

## Cosa non è cambiato

Molte delle cose che hai familiarità con il reporting non sono cambiate.

* È comunque possibile utilizzare la potenza di [Analysis Workspace](/help/analysis-workspace/home.md) per analizzare i dati. Workspace funziona come in Adobe Analytics tradizionale.
* Hai anche la stessa versione di [Dashboard di Adobe Analytics](/help/mobile-app/home.md) a vostra disposizione. Le dashboard (anche come app Mobile) funzionano allo stesso modo di Adobe Analytics tradizionale.
* [Report Builder](/help/report-builder/report-buider-overview.md) dispone di una nuova interfaccia ed è ora in esecuzione su PC, Mac e la versione Web di Excel.

Quando si tratta di reporting, **cosa è diverso** è che hai accesso a molti più dati cross-channel da analizzare. Ecco un esempio di alcune visualizzazioni che includono origini dati cross-channel:

![visualizzazioni multicanale](assets/cross-channel.png)

## Nuova architettura {#architecture}

Il Customer Journey Analytics ottiene i suoi dati da Adobe Experience Platform. L’Experience Platform ti consente di centralizzare e standardizzare i dati e i contenuti dei clienti da qualsiasi sistema o canale e applica la scienza dei dati e l’apprendimento automatico per migliorare la progettazione e la distribuzione di esperienze personalizzate.

In Platform i dati del cliente vengono memorizzati come set di dati, costituiti da uno schema e da un batch di dati. Per ulteriori informazioni su Platform, consulta [Panoramica dell’architettura di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=it).

Il tuo amministratore CJA ha stabilito [connessioni](/help/connections/create-connection.md) ai set di dati in Platform. Hanno poi costruito [visualizzazioni dati](/help/data-views/data-views.md) all&#39;interno di tali connessioni. Considera le visualizzazioni dati come simili alle suite di rapporti virtuali. Le visualizzazioni dati sono la base per la generazione di rapporti in Customer Journey Analytics. Il concetto di suite di rapporti non esiste più.

## Connessioni

Una connessione consente all’amministratore di Analytics di integrare i set di dati da [!DNL Adobe Experience Platform] in [!UICONTROL Workspace]. Per creare rapporti sui set di dati [!DNL Experience Platform] bisogna prima stabilire una connessione tra i set di dati in [!DNL Experience Platform] e [!UICONTROL Workspace].

Panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Suite di rapporti {#report-suites}

I dati della suite di rapporti possono essere inseriti in Experience Platform tramite il connettore origine Adobe Analytics o l’SDK per web, se l’organizzazione è ancora sulla piattaforma Adobe Analytics e se aggiungi CJA/AEP. In genere, i set di dati sorgente specifici per le suite di rapporti vengono creati utilizzando lo schema di Analytics.

Tuttavia, le suite di rapporti non sono più la base per la generazione di rapporti in CJA - [visualizzazioni dati](/help/data-views/data-views.md) sono. Per ulteriori informazioni sulle visualizzazioni dati, consulta la sezione seguente.

Le implementazioni esistenti da più set di dati possono essere combinate in Experience Platform. Le connessioni e le visualizzazioni dati basate su questi set di dati possono combinare i dati esistenti in precedenza in suite di rapporti separate.

## (Virtuale) le suite di rapporti ora sono &quot;visualizzazioni dati&quot; {#data-views}

[!UICONTROL Data views] prendi il concetto di suite di rapporti virtuali così come sono oggi ed espandilo per [abilitare controlli aggiuntivi sui dati](/help/data-views/create-dataview.md) reso disponibile tramite connessioni. Questo rende configurabili intervalli di timeout e timeout della sessione. Puoi anche applicare dinamicamente le proprietà di attribuzione e scadenza per le singole dimensioni. Tieni presente che questi vengono applicati retroattivamente su tutti i dati.

**Cosa devi fare**:

* In Workspace, il selettore suite di rapporti a cui sei abituato ti consente di scegliere tra le visualizzazioni dati condivise dall’amministratore:

   ![data-view-selector](assets/data-views.png)

* Familiarizza con i molti [casi di utilizzo intorno alle visualizzazioni dati](/help/data-views/data-views-usecases.md).

## eVar e proprietà

[!UICONTROL eVars], [!UICONTROL props] e [!UICONTROL events] nel senso tradizionale di Adobe Analytics non esistono più in [!UICONTROL Customer Journey Analytics]. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query.

**Cosa devi fare**:

* Acquisisci familiarità con i diversi modi in cui questi elementi dello schema possono essere utilizzati per eseguire il drill-down dei dati.

## I segmenti sono ora &quot;Filtri&quot;

[!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi, utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. Inoltre, i &quot;segmenti&quot; sono stati rinominati &quot;filtri&quot;.

Al momento, non puoi condividere/pubblicare [!UICONTROL filters] ([!UICONTROL segments]) da [!DNL Customer Journey Analytics] ad Experience Platform Unified Profile o altre applicazioni Experience Cloud. Questa funzionalità è in fase di sviluppo.

**Cosa devi fare**:

* Se desideri spostare i segmenti Adobe Analytics esistenti sul Customer Journey Analytics, visualizza [questo video](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=it).
* In caso contrario, ricreate i filtri nel Customer Journey Analytics.

## Metriche calcolate

[!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi, utilizza qualsiasi schema AEP. Ciò significa che nessuna delle metriche calcolate esistenti è compatibile con [!UICONTROL Customer Journey Analytics].

**Cosa devi fare**:

* Se desideri spostare le metriche calcolate di Adobe Analytics sul Customer Journey Analytics, visualizza [questo video](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=it).
* In caso contrario, ricreate le metriche calcolate in Customer Journey Analytics.

## Impostazioni di persistenza della sessione e della variabile

[!UICONTROL Customer Journey Analytics] applica tutte queste impostazioni al momento del report e queste impostazioni ora risiedono in [visualizzazioni dati](/help/data-views/component-settings/persistence.md). Le modifiche a queste impostazioni sono ora retroattive e puoi avere più versioni utilizzando più visualizzazioni dati!

## Le classificazioni sono ora &quot;Set di dati di ricerca&quot;

I set di dati di ricerca vengono utilizzati per cercare i valori o le chiavi presenti nei dati evento o profilo. Ad esempio, puoi caricare dati ricerca che mappano ID numerici nei dati evento ai nomi dei prodotti. Consulta [questo caso d’uso](/help/use-cases/b2b.md) per un esempio.

## Gli attributi del cliente sono ora &quot;Set di dati di profilo&quot;

I set di dati del profilo contengono dati applicati a visitatori, utenti o clienti nella [!UICONTROL Event] dati. Ad esempio, ti consente di caricare dati CRM sui tuoi clienti. Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] presenta un proprio set di uno o più ID persona definiti, ad esempio Cookie ID (ID cookie), Stitched ID (ID di unione), User ID (ID utente), Tracking Code (Codice di tracciamento) e così via.

## Identità

CJA espande i concetti di identità oltre gli ECID per includere qualsiasi ID che desideri utilizzare, inclusi ID cliente, ID cookie, ID unione, ID utente, codice di tracciamento e così via. Utilizzo di un ID namespace comune nei set di dati o utilizzo di [Analisi cross-channel](/help/connections/cca/overview.md) aiuta a collegare le persone tra loro tra diversi set di dati. Qualsiasi utente che imposti un progetto Workspace in CJA deve comprendere gli ID utilizzati nei set di dati.

Ecco un video che evidenzia l&#39;uso delle identità nel Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## I contenitori sono stati rinominati

Specifica un contenitore per [ogni visualizzazione dati creata](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).

* **I contenitori Hit ora sono contenitori &quot;Evento&quot;**. La [!UICONTROL Person] Il contenitore include ogni sessione e evento per i visitatori entro l’intervallo di tempo specificato.
* **I contenitori delle visite ora sono contenitori &quot;Sessione&quot;**. La [!UICONTROL Session] Il contenitore ti consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica.
* **I contenitori dei visitatori ora sono [!UICONTROL Person] contenitori**. La [!UICONTROL Person] Il contenitore include ogni sessione e evento per i visitatori entro l’intervallo di tempo specificato.

**Cosa devi fare**:

Puoi rinominare qualsiasi contenitore in base alle esigenze della tua organizzazione.

## `Uniques Exceeded` limitazioni

[!UICONTROL Customer Journey Analytics] non ha limiti di valore univoci, quindi non è necessario preoccuparsene.
