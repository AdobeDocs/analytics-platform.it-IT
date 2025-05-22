---
title: Configurazione manuale di Content Analytics
description: Come configurare manualmente Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 96%

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

* [Segmentazione eventi](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Puoi modificare le espressioni regolari per modificare il modo in cui segmentate pagine e risorse.


Dopo aver apportato modifiche all’estensione Adobe Content Analytics, assicurati di utilizzare il [flusso di pubblicazione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview){target="_blank"} per avviare la raccolta dati in base alle modifiche apportate.



>[!MORELIKETHIS]
>
>[Configurazione guidata](guided.md)
>[Panoramica sulla pubblicazione dei tag di raccolta dati](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview)
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
