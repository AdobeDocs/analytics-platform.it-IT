---
title: Configurazione manuale di Content Analytics
description: Come configurare manualmente Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 100%

---

# Configurazione manuale di Content Analytics

Questo articolo descrive le azioni manuali necessarie per avviare o interrompere la raccolta dati di una configurazione di Content Analytics o per modificare l’implementazione di Content Analytics.

Sono disponibili le seguenti configurazioni manuali:

## Avviare la raccolta dati

Per avviare la raccolta dati per una configurazione di Content Analytics implementata:

1. Segui il [flusso di pubblicazione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview){target="_blank"}. Pubblica correttamente la libreria per la proprietà Tag contenente la configurazione di Content Analytics.

1. [Installa](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/environments/environments#installation) il codice incorporato nell’elemento `<head>` delle pagine dell’ambiente di sviluppo, di staging o di pubblicazione, soggetto a Content Analytics.


## Interrompere la raccolta dati

Per interrompere la raccolta dati per una configurazione di Content Analytics implementata:

1. Rimuovi il [codice incorporato](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/environments/environments) dell’elemento `<head>` delle pagine dell’ambiente di sviluppo, di staging o di produzione, soggetto a Content Analytics.
1. [Elimina](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview) la proprietà Tag associata per la configurazione di Content Analytics.



## Modificare la raccolta dati

La [configurazione guidata](guided.md) consente di apportare alcune modifiche minori a una configurazione implementata. Ad esempio, puoi cambiare la visualizzazione dati oppure abilitare o disabilitare alcune esperienze.

Utilizza l’[estensione Adobe Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview) nella proprietà Tag associata alla configurazione di Content Analytics per apportare modifiche ai seguenti artefatti:

* [Sandbox e stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Verifica che la sandbox e lo stream di dati configurati nell’estensione Adobe Content Analytics siano già stati configurati per Content Analytics in precedenza seguendo la [configurazione guidata](guided.md). Questa configurazione assicura la disponibilità di tutti gli artefatti richiesti.<br/><br/>Inoltre, verifica che eventuali aggiornamenti per sandbox o stream di dati non interferiscano con un’altra configurazione di Content Analytics impostata per la stessa sandbox o gli stessi stream di dati.
  >

* [Acquisizione e definizione delle esperienze](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=it#configure-experience-capture-and-definition)

  Puoi abilitare o disabilitare le esperienze e modificare le combinazioni di espressioni regolari e parametri di query per determinare come riprodurre i contenuti sul tuo sito web.

* [Segmentazione degli eventi](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Puoi modificare le espressioni regolari per specificare come segmentare pagine e risorse.


Dopo aver apportato modifiche all’estensione Adobe Content Analytics, assicurati di utilizzare il [flusso di pubblicazione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview){target="_blank"} per avviare la raccolta dati in base alle modifiche apportate.



>[!MORELIKETHIS]
>
>[Configurazione guidata](guided.md)
>>[Panoramica sulla pubblicazione dei tag di raccolta dati](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview)
>


## Controllo delle versioni

Se desideri raccogliere esperienze Content Analytics, con l’implementazione del controllo delle versioni puoi assicurarti che le nuove esperienze (modifiche alla pagina web) vengano raccolte correttamente.

Per implementare il controllo delle versioni, aggiungi una funzione `adobe.getContentExperienceVersion` globale alle pagine che consideri esperienze da analizzare.

La funzione `adobe.getContentExperienceVersion` deve restituire un valore di tipo stringa, a tua scelta, che consenta di identificare la versione. La versione viene aggiunta all’[URL dell’ID esperienza](/help/content-analytics/report/components.md#experience-metadata).

Se la funzione non è presente o non restituisce alcun valore, viene utilizzato il valore predefinito `NoVersion`.

### Esempio

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

## Identità

Content Analytics gestisce le identità nel modo seguente:

* ECID viene popolato automaticamente nella porzione `identityMap` dello schema Content Analytics.
* Se sono necessari altri valori di identità in `identityMap`, è necessario impostare questi valori nel callback `onBeforeEventSend` all’interno dell’estensione Web SDK.
* L’unione identità basata sui campi non è supportata perché lo schema è di proprietà del sistema. Pertanto, non è possibile aggiungere un altro campo allo schema per supportare l’unione identità basata sui campi


Per garantire che i dati di identità di Content Analytics e di Adobe Experience Platform Web SDK siano uniti correttamente a livello di campo, è necessario apportare modifiche al callback di Web SDK [prima dell’invio dell’evento](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"}.

1. Passa alla proprietà **[!UICONTROL Tags]** che contiene le estensioni Adobe Experience Platform Web SDK e Adobe Content Analytics.
1. Seleziona ![ il plug-in **[!UICONTROL Extensions]** ](/help/assets/icons/Plug.svg).
1. Seleziona l’estensione **[!UICONTROL Adobe Experience Platform Web SDK]**.
1. Seleziona **[!UICONTROL Configure]**.
1. Nella sezione **[!UICONTROL SDK instances]**, scorri verso il basso fino a **[!UICONTROL Data collection]** - **[!UICONTROL On before event send callback]**.

   ![Callback prima dell’invio dell’evento](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Seleziona **[!UICONTROL </> Provide on before event send callback code]**.
1. Aggiungi il seguente codice:

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Callback prima dell’invio dell’evento](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Seleziona **[!UICONTROL Save]** per salvare il codice.
1. Seleziona **[!UICONTROL Save]** per salvare l’estensione.
1. [Pubblica](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview) gli aggiornamenti per la proprietà Tag.





