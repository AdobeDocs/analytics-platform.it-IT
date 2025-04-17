---
title: Configurazione manuale di Content Analytics
description: Come configurare manualmente l’analisi dei contenuti
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 981cd0c01d775acbd71cada7efed4911b4bcb157
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Configurazione manuale di Content Analytics

{{release-limited-testing}}


Questo articolo descrive le azioni manuali necessarie per avviare o arrestare la raccolta di dati di una configurazione di Content Analytics o per modificare l’implementazione di Content Analytics.

Sono disponibili le seguenti azioni di configurazione manuali:

## Avviare la raccolta dati

Per avviare la raccolta dati per una configurazione di Content Analytics implementata:

1. Segui il [flusso di pubblicazione](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Pubblicazione della libreria per la proprietà Tags contenente la configurazione Content Analytics completata.

1. [Installa](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) il codice incorporato nell&#39;elemento `<head>` delle pagine nell&#39;ambiente di sviluppo, gestione temporanea o pubblicazione, soggetto a Content Analytics.


## Interrompi raccolta dati

Per interrompere la raccolta dati per una configurazione di Content Analytics implementata:

1. Rimuovi il [codice incorporato](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) nell&#39;elemento `<head>` delle pagine nell&#39;ambiente di sviluppo, staging o produzione, soggetto a Content Analytics.
1. [Elimina](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) la proprietà Tag associata per la configurazione di Content Analytics.



## Modificare la raccolta dati

È possibile apportare alcune modifiche minori a una configurazione implementata utilizzando la [configurazione guidata](guided.md). Ad esempio, modifica la visualizzazione dati oppure abilita o disabilita le esperienze.

Utilizza l&#39;estensione [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) nella proprietà Tags associata alla configurazione Content Analytics per apportare modifiche ai seguenti artefatti:

* [Sandbox e flusso di dati](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Verificare che la sandbox e lo stream di dati configurati nell&#39;estensione Adobe Content Analytics siano già configurati per Content Analytics utilizzando la [configurazione guidata](guided.md) in una fase precedente. Questa configurazione assicura la disponibilità di tutti gli artefatti richiesti.<br/><br/>Verificare inoltre che gli aggiornamenti per sandbox o flussi di dati non interferiscano con un&#39;altra configurazione di Content Analytics configurata per utilizzare la stessa sandbox o gli stessi flussi di dati.
  >

* [Acquisizione e definizione dell&#39;esperienza](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Puoi abilitare o disabilitare le esperienze e modificare le combinazioni di espressioni regolari e parametri di query per determinare come viene eseguito il rendering del contenuto sul sito web.

* [Filtro eventi](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  Puoi modificare le espressioni regolari per modificare il modo in cui filtri pagine e risorse.


Dopo aver apportato modifiche all&#39;estensione Adobe Content Analytics, assicurati di utilizzare [flusso di pubblicazione](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} per avviare la raccolta di dati in base alle modifiche apportate.



>[!MORELIKETHIS]
>
>[Configurazione guidata](guided.md)
>[Panoramica sulla pubblicazione dei tag di raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Controllo delle versioni

Se desideri raccogliere esperienze Content Analytics, prendi in considerazione l’implementazione del controllo delle versioni per garantire che le nuove esperienze (modifiche alla pagina web) vengano raccolte correttamente.

Per implementare il controllo delle versioni, aggiungere una funzione `adobe.getContentExperienceVersion` globale nelle pagine che si considerano esperienze da analizzare.

La funzione `adobe.getContentExperienceVersion` deve restituire una stringa come valore, che può essere qualsiasi cosa scelta, per identificare la versione. La versione viene aggiunta all&#39;[URL Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Se la funzione non è presente o non viene restituito alcun valore dalla funzione, il valore `NoVersion` viene utilizzato come predefinito.

### Esempio

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
