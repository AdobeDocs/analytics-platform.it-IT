---
title: Guida utente di CJA per gli utenti di Adobe Analytics
description: Cosa considerare dal punto di vista di un utente quando l’azienda sposta i dati da Adobe Analytics al Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 755e554e3eb362d6e7149e5d3a4fbbcddebdd14d
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 24%

---


# Guida utente di CJA per gli utenti di Adobe Analytics

>[!NOTE]
>
>Questa pagina è in costruzione.

Congratulazioni, la tua azienda sta iniziando a lavorare con il Customer Journey Analytics! In qualità di utente che ha familiarità con Adobe Analytics, hai già un ottimo vantaggio. Lavorando con il Customer Journey Analytics, noterete alcune grandi differenze e alcune somiglianze. Questa pagina ha lo scopo di spiegare quelle cose che non sono cambiate, così come alcune delle principali differenze. Inoltre, ti spiegheremo come ottenere ulteriori informazioni sui nuovi concetti e ulteriori passaggi per rendere il tuo percorso cliente più semplice e di successo.

## Cosa non è cambiato

Molte delle cose che hai familiarità con il reporting non sono cambiate.

* È comunque possibile utilizzare la potenza di [Analysis Workspace](/help/analysis-workspace/home.md) per analizzare i dati.
* Hai anche la stessa versione di [Dashboard di Adobe Analytics](/help/mobile-app/home.md) a vostra disposizione. Workspace e dashboard funzionano allo stesso modo dei tradizionali Adobe Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) dispone di una nuova interfaccia ed è ora in esecuzione su PC, Mac e la versione Web di Excel.

Quando si tratta di reporting, la differenza è che si ha accesso a molti più dati cross-channel da analizzare. Ecco un esempio di alcune visualizzazioni multicanale che includono una serie di origini dati cross-channel:

![visualizzazioni multicanale](assets/cross-channel.png)

## Nuova architettura

Il Customer Journey Analytics ottiene i suoi dati da Adobe Experience Platform. L’Experience Platform ti consente di centralizzare e standardizzare i dati e i contenuti dei clienti da qualsiasi sistema o canale e applica la scienza dei dati e l’apprendimento automatico per migliorare la progettazione e la distribuzione di esperienze personalizzate.

In Platform i dati del cliente vengono memorizzati come set di dati, costituiti da uno schema e da un batch di dati. Per ulteriori informazioni su Platform, consulta [Panoramica dell’architettura di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=it).

Il tuo amministratore CJA ha stabilito [connessioni](/help/connections/create-connection.md) ai set di dati in Platform. Hanno poi costruito [visualizzazioni dati](/help/data-views/data-views.md) all&#39;interno di tali connessioni. Considera le visualizzazioni dati come simili alle suite di rapporti virtuali. Le visualizzazioni dati sono la base per la generazione di rapporti in Customer Journey Analytics.

## Nuovi concetti e terminologia

Diverse funzioni di CJA sono state rinominate e riarchitettate, se confrontate con il tradizionale Adobe Analytics, per allinearsi agli standard di settore. Alcuni termini aggiornati includono segmenti, suite di rapporti virtuali, classificazioni, attributi cliente e nomi di contenitori. Concetti familiari come eVar e prop non esistono più, insieme ai limiti imposti.

### eVar e proprietà

[!UICONTROL eVars], [!UICONTROL props] e [!UICONTROL events] nel senso tradizionale di Adobe Analytics non esistono più in [!UICONTROL Customer Journey Analytics]. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query.

### I segmenti sono ora &quot;Filtri&quot;

[!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi, utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. Inoltre, i &quot;segmenti&quot; sono stati rinominati &quot;filtri&quot;.

Al momento, non puoi condividere/pubblicare [!UICONTROL filters] ([!UICONTROL segments]) da [!DNL Customer Journey Analytics] ad Experience Platform Unified Profile o altre applicazioni Experience Cloud. Questa funzionalità è in fase di sviluppo.

### Metriche calcolate

[!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi, utilizza qualsiasi schema AEP. Ciò significa che nessuna delle metriche calcolate esistenti è compatibile con [!UICONTROL Customer Journey Analytics].

### Impostazioni di persistenza della sessione e della variabile

[!UICONTROL Customer Journey Analytics] applica tutte queste impostazioni al momento di creazione del rapporto ed esse si trovano ora in Data Views (Visualizzazioni dati). Le modifiche a queste impostazioni sono ora retroattive e si possono avere più versioni utilizzando più Data Views (Visualizzazioni dati).

### Le suite di rapporti virtuali ora sono &quot;visualizzazioni dati&quot;



### Le classificazioni sono ora &quot;Set di dati di ricerca&quot;

### Gli attributi del cliente sono ora &quot;Set di dati di profilo&quot;


### I contenitori Hit ora sono contenitori &quot;Evento&quot;

### I contenitori delle visite ora sono contenitori &quot;Sessione&quot;

### I contenitori dei visitatori ora sono contenitori &quot;Persona&quot;

### `Uniques Exceeded` limitazioni

[!UICONTROL Customer Journey Analytics] non ha limiti di valore univoci, quindi non è necessario preoccuparsene.
