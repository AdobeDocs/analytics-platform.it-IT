---
title: Configurazione manuale di Content Analytics
description: Come configurare manualmente l’analisi dei contenuti
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Configurazione manuale di Content Analytics

>[!WARNING]
>
>Questo articolo è una bozza preliminare non ufficiale di una versione finale di prossima pubblicazione e fa parte della documentazione di Content Analytics. Tutti i contenuti sono soggetti a modifiche e nessun obbligo legale può essere derivato dalla versione corrente di questo articolo.
>

{{release-limited-testing}}

Questo articolo descrive le azioni manuali necessarie per attivare o disattivare una configurazione di Content Analytics o per modificare l’implementazione di Content Analytics.

Sono disponibili le seguenti azioni di configurazione manuali:

## Attiva

Per attivare una nuova configurazione o le modifiche apportate a una configurazione esistente:

1. Devi seguire il [flusso di pubblicazione](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Pubblicazione della libreria per la proprietà Tags contenente la configurazione Content Analytics completata. Solo a questo punto vengono raccolti i dati di Content Analytics per i domini, le esperienze e le risorse configurati.

1. Devi [installare](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) il codice incorporato nell&#39;elemento `<head>` delle pagine nell&#39;ambiente di sviluppo, staging o pubblicazione, soggetto a Content Analytics.


## Disattiva

Per disattivare la raccolta dei dati di analisi dei contenuti:

1. Rimuovi il [codice incorporato](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) nell&#39;elemento `<head>` delle pagine nell&#39;ambiente di sviluppo, staging o produzione, soggetto a Content Analytics.
1. [Elimina](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) la proprietà Tag associata per la configurazione di Content Analytics.



## Modifica

È possibile apportare alcune modifiche minori a una configurazione implementata utilizzando la [configurazione guidata](guided.md). Ad esempio, modifica la visualizzazione dati.

Utilizza l&#39;estensione [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) nella proprietà Tags associata alla configurazione Content Analytics per apportare modifiche ai seguenti artefatti:

* [Sandbox e flusso di dati](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Verificare che la sandbox e lo stream di dati configurati nell&#39;estensione Adobe Content Analytics siano già configurati per Content Analytics utilizzando la [configurazione guidata](guided.md) in una fase precedente. Questa configurazione assicura la disponibilità di tutti gli artefatti richiesti.<br/><br/>Verificare inoltre che gli aggiornamenti per sandbox o flussi di dati non interferiscano con un&#39;altra configurazione di Content Analytics configurata per utilizzare la stessa sandbox o gli stessi flussi di dati.
  >

* [Filtro eventi](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  Puoi modificare le espressioni regolari per modificare il modo in cui filtri pagine e risorse.


Dopo aver apportato modifiche nell&#39;estensione Adobe Content Analytics, assicurati di utilizzare il [flusso di pubblicazione](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} per attivare le modifiche.



>[!MORELIKETHIS]
>
>[Configurazione guidata](guided.md)
>[Panoramica sulla pubblicazione dei tag di raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Controllo delle versioni

Se hai bisogno del controllo delle versioni delle esperienze Content Analytics, devi aggiungere una funzione `adobe.getContentExperienceVersion` globale nelle pagine che consideri esperienze da analizzare.

La funzione `adobe.getContentExperienceVersion` deve restituire una stringa come valore, che può essere qualsiasi cosa scelta, per identificare la versione. La versione viene aggiunta all&#39;[URL Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Se la funzione non è presente o non viene restituito alcun valore dalla funzione, il valore `NoVersion` viene utilizzato come predefinito.

### Esempio

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
