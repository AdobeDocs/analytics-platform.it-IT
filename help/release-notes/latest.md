---
title: Note sulla versione di Customer Journey Analytics
description: Ultime note sulla versione del Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 806bcaa72479c3e871e12fd1c4802bac97eda439
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 27%

---

# Note sulla versione corrente di Adobe Customer Journey Analytics (gennaio 2025)

**Ultimo aggiornamento**: giovedì 22 gennaio 2025

Queste note sulla versione coprono il periodo dal 23 ottobre 2024 al 30 gennaio 2025. I rilasci di Adobe Customer Journey Analytics funzionano su un [modello di consegna continua](releases.md) che consente un approccio più scalabile e graduale alla distribuzione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Esperienza di utilizzo connessioni aggiornata** | La scheda **[!UICONTROL Usage]** in Connessione fornisce ora visualizzazioni migliorate per questi tipi di righe da segnalare: dati di base, acquisiti e storici. Puoi anche visualizzare e suddividere i dati di utilizzo per connessione, set di dati, sandbox o tag. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage) |  | giovedì 15 gennaio 2025 |
| **API per la migrazione dei progetti Adobe Analytics ed eventuali componenti inclusi nel Customer Journey Analytics** | È ora disponibile un’API per la migrazione dei progetti Adobe Analytics e dei componenti inclusi al Customer Journey Analytics. In precedenza, la migrazione di progetti e componenti era disponibile solo tramite l’interfaccia utente di. [Ulteriori informazioni](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=CJA%20Migration%20APIs). Seleziona **API di migrazione CJA** dal menu a discesa. |  | giovedì 15 gennaio 2025 |
| **Utilizza modelli personalizzati del Customer Journey Analytics nella pagina Rapporti di Journey Optimizer** | Ora puoi personalizzare la nuova interfaccia di reporting in Adobe Journey Optimizer creando o modificando un modello in Customer Journey Analytics, quindi salvando il modello da utilizzare nella pagina Rapporti in Journey Optimizer. In precedenza, non era possibile personalizzare la nuova interfaccia di reporting in Adobe Journey Optimizer. <p>Per ulteriori informazioni, vedere &quot;Creare un modello&quot; o &quot;Modificare o eliminare un modello&quot; in [Creare e gestire modelli](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/create-templates).  |  | giovedì 15 gennaio 2025 |
| **Modelli in Analysis Workspace** | I modelli sono ora disponibili in Customer Journey Analytics.<ul><li>**Modelli predefiniti**: è disponibile una vasta selezione di modelli predefiniti. Puoi utilizzare questi modelli per ottenere informazioni rapide sugli scenari di reporting più comuni. I modelli predefiniti possono essere utilizzati così come sono. In alternativa, possono essere utilizzati come punto di partenza per un progetto, che può quindi essere personalizzato per soddisfare meglio uno scopo specifico. [Ulteriori informazioni](/help/analysis-workspace/templates/use-templates.md)</li><li>**Modelli aziendali**: gli amministratori possono creare modelli aziendali per soddisfare le esigenze dei casi d&#39;uso specifici della propria organizzazione. I modelli aziendali creati dagli amministratori sono disponibili per gli utenti della propria organizzazione. [Ulteriori informazioni](/help/analysis-workspace/templates/create-templates.md)</li></ul> | Gennaio 15 | venerdì 30 gennaio 2025 |
| **Utilizzo prodotto** | Scopri come la tua organizzazione utilizza Customer Journey Analytics. Abilitando questa funzione viene creato un set di dati in Adobe Experience Platform che raccoglie dati quando un utente dell’organizzazione utilizza Analysis Workspace. Vengono inoltre create automaticamente una connessione e una visualizzazione dati, che consentono di accedere a dimensioni quali i principali tipi di progetto, gli utenti più attivi e i componenti più popolari utilizzati nei progetti. [Ulteriori informazioni](/help/tools/product-usage/usage-overview.md) | 23 ottobre 2024 | 22 gennaio 2025 |
| **Didascalie intelligenti v2** | I sottotitoli intelligenti sono ora supportati per le seguenti visualizzazioni: Multiriga, Barra, Barra orizzontale, Anello, Area, Flusso e Abbandono. È possibile scegliere di mostrare tutte le didascalie intelligenti contemporaneamente in una visualizzazione espansa oppure di mostrare singole didascalie intelligenti in una visualizzazione singola. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) |  | 22 gennaio 2025 |
| **Aggiungere analisi guidate ai progetti da Analisi guidata** | Consente di aggiungere analisi guidate ai progetti Workspace dall’interno di Analisi guidata. Puoi anche aggiungere analisi guidate direttamente in Analysis Workspace. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/guided-analysis/overview) |  | 22 gennaio 2025 |
| **Media Collection: aggiornamenti del connettore Source di Adobe per il nuovo XDM per Media Reporting** | Il connettore Source di Analytics mapperà automaticamente i dati multimediali in streaming in Adobe Analytics agli stessi campi utilizzati dal Web SDK. Attualmente, i dati vengono mappati sia sulle vecchie che sulle nuove posizioni, ma solo la nuova posizione verrà utilizzata in futuro. Il link alla documentazione seguirà a breve. |  | venerdì 30 gennaio 2025 |

## Correzioni in Customer Journey Analytics

Avvisi: AN-363263; AN-364880; AN-365029; AN-365960
Pubblico: AN-362564; AN-363254;
Acquisizione dei dati: AN-362359; AN-362751
Visualizzazioni dati: AN-362089; AN-365213; AN-365770; AN-366171; AN-366681
Campi derivati: AN-359711; AN-362496
Posizioni di esportazione: AN-363999
Esportazione di tabelle complete: AN-363055
Report Builder: AN-362937
Workspace: AN-359012; AN-359145; AN-359914; AN-361455; AN-361934; AN-362469; AN-363460; AN-364714; AN-364918; AN-366277;


## Avvisi importanti per gli amministratori di Customer Journey Analytics

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| N/D | | |

## Risorse correlate

* [Note sulle versioni precedenti di Customer Journey Analytics per il 2024](/help/release-notes/2024.md)
* [Note sulla versione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it)
* [Aggiornamenti della documentazione di Customer Journey Analytics](/help/release-notes/doc-changes.md)
