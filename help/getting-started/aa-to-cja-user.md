---
title: Guida utente di CJA per gli utenti di Adobe Analytics
description: Cosa considerare dal punto di vista di un utente quando l’azienda sposta i dati da Adobe Analytics al Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: eeb56599c81dd9cd20bf91c864aa57a783ef13fd
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 38%

---


# Guida utente di CJA per gli utenti di Adobe Analytics

Congratulazioni, la tua azienda ha trasferito almeno alcuni dei suoi dati al Customer Journey Analytics! Iniziando a lavorare con il Customer Journey Analytics, noterete alcune grandi differenze e alcune somiglianze. Questa pagina ha lo scopo di spiegare quelle cose che non sono cambiate, così come alcune delle principali differenze.

Inoltre, ti spiegheremo come ottenere ulteriori informazioni sui nuovi concetti e ulteriori passaggi per rendere il tuo percorso cliente più semplice e di successo.

## Cosa non è cambiato

Molte delle cose che hai familiarità con il reporting non sono cambiate. Puoi comunque utilizzare la potenza di Analysis Workspace per analizzare i tuoi dati, oltre alle dashboard di Adobe Analytics e a una nuova versione del Report Builder. Workspace e dashboard funzionano essenzialmente come nelle tradizionali Adobe Analytics. Il Report Builder dispone di una nuova interfaccia ed è ora in esecuzione su PC, computer Mac e la versione Web di Excel. Dal punto di vista del reporting, la differenza è che si ha accesso a molti più dati cross-channel da analizzare. Ecco un esempio di Workspace di

## Nuova architettura

Dal punto di vista architetturale, Customer Journey Analytics ottiene i propri dati da Adobe Experience Platform. L’Experience Platform ti consente di centralizzare e standardizzare i dati e i contenuti dei clienti da qualsiasi sistema o canale e applica la scienza dei dati e l’apprendimento automatico per migliorare la progettazione e la distribuzione di esperienze personalizzate.

In Platform i dati del cliente vengono memorizzati come set di dati, costituiti da uno schema e da un batch di dati. Per ulteriori informazioni su Platform, consulta [Panoramica dell’architettura di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=it).

L’amministratore CJA stabilisce le connessioni ai dati in Platform e crea le visualizzazioni dati all’interno di tali connessioni. Considera le visualizzazioni dati come simili alle suite di rapporti virtuali. Le visualizzazioni dati sono la base per la generazione di rapporti in Customer Journey Analytics.

## Nuovi concetti e terminologia

Diverse funzioni di CJA sono state rinominate e riarchitettate, se confrontate con il tradizionale Adobe Analytics, per allinearsi agli standard di settore. Alcuni termini aggiornati includono segmenti, suite di rapporti virtuali, classificazioni, attributi cliente e nomi di contenitori. Concetti familiari come eVar e prop non esistono più, insieme ai limiti imposti.

### I segmenti sono ora &quot;Filtri&quot;


### Le suite di rapporti virtuali ora sono &quot;visualizzazioni dati&quot;


### Le classificazioni sono ora &quot;Set di dati di ricerca&quot;

### Gli attributi del cliente sono ora &quot;Set di dati di profilo&quot;


### I contenitori Hit ora sono contenitori &quot;Evento&quot;

### I contenitori delle visite ora sono contenitori &quot;Sessione&quot;

### I contenitori dei visitatori ora sono contenitori &quot;Persona&quot;

## Domande frequenti sui componenti di Adobe Analytics

| Domanda | Risposta |
| --- | --- |
| Posso condividere/pubblicare [!UICONTROL filters] ([!UICONTROL segments]) da [!DNL Customer Journey Analytics] a Experience Platform Unified Profile o altre applicazioni Experience Cloud? | Non ancora, ma stiamo mettendo a punto questa funzionalità. |
| Cos’è successo alla mia vecchia impostazione [!UICONTROL eVar]? | [!UICONTROL eVars], [!UICONTROL props] e [!UICONTROL events] nel senso tradizionale di Adobe Analytics non esistono più in [!UICONTROL Customer Journey Analytics]. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query. |
| Dove sono ora tutte le impostazioni di persistenza relative alla sessione e alle variabili? | [!UICONTROL Customer Journey Analytics] applica tutte queste impostazioni al momento di creazione del rapporto ed esse si trovano ora in Data Views (Visualizzazioni dati). Le modifiche a queste impostazioni sono ora retroattive e si possono avere più versioni utilizzando più Data Views (Visualizzazioni dati). |
| Cosa succede ai segmenti o alle metriche calcolate esistenti? | [!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi, utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti o delle metriche calcolate esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. |
| In che modo [!UICONTROL Customer Journey Analytics] gestisce i limiti di `Uniques Exceeded`? | [!UICONTROL Customer Journey Analytics] non ha limiti di valore univoci, quindi non è necessario preoccuparsene. |
| Se sono già un cliente [!DNL Data Workbench], posso passare subito a [!UICONTROL Customer Journey Analytics] | Dipende dal tuo caso d’uso: collabora con il team del tuo account Adobe. I tuoi casi d’uso attuali potrebbero già essere gestiti con Customer Journey Analytics! |
