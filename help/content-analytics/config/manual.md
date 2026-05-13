---
title: Configurazione manuale Content Analytics
description: Scopri come configurare Content Analytics manualmente.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
TQID: https://experienceleague.adobe.com/McecE-5AGq-IVw-rdkZpV5WgTvax-gubrpQk0ow4JJc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 720
ht-degree: 62%

---


# Configurazione manuale di Content Analytics

Questo articolo descrive le azioni manuali necessarie per avviare o interrompere la raccolta dati di una configurazione di Content Analytics o per modificare l’implementazione di Content Analytics.

Sono disponibili le seguenti configurazioni manuali:

## Avviare la raccolta dati

Per avviare la raccolta dati per una configurazione di Content Analytics implementata:

1. Segui il [flusso di pubblicazione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview){target="_blank"}. La libreria per le proprietà Tags contenente la configurazione Content Analytics è stata pubblicata.

1. In base ai canali configurati:

   * Per **web**: [Installa](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/environments/environments#installation) il codice incorporato nell&#39;elemento `<head>` delle pagine nell&#39;ambiente di sviluppo, staging o pubblicazione, soggetto a Content Analytics.
   * Per **mobile**: consulta la [guida all&#39;estensione per Adobe Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) specifica della soluzione nella [documentazione di Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/) su come configurare e dotare l&#39;app mobile di Content Analytics.

## Interrompere la raccolta dati

Per interrompere la raccolta dati per una configurazione di Content Analytics implementata, in base ai canali configurati:

* Per **web**:

   1. Rimuovi il [codice incorporato](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/environments/environments) dell’elemento `<head>` delle pagine dell’ambiente di sviluppo, di staging o di produzione, soggetto a Content Analytics.
   1. Elimina la proprietà dei tag web associati per la configurazione Content Analytics.

* Per **mobile**:

   1. Rimuovi l&#39;estensione [Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) dall&#39;app.
   1. Elimina la proprietà dei tag mobili associata per la configurazione di Content Analytics.

Segui il [flusso di pubblicazione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview){target="_blank"} per applicare le modifiche.


## Modificare la raccolta dati

La [configurazione guidata](guided.md) consente di apportare alcune modifiche minori a una configurazione implementata. Ad esempio, puoi cambiare la visualizzazione dati oppure abilitare o disabilitare alcune esperienze.


### Web

Utilizza l&#39;estensione Web [Adobe Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview) nella proprietà Tags associata alla configurazione Content Analytics per apportare modifiche ai seguenti artefatti:

* [Sandbox e stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Verifica che la sandbox e lo stream di dati configurati nell’estensione Adobe Content Analytics siano già stati configurati per Content Analytics in precedenza seguendo la [configurazione guidata](guided.md). Questa configurazione assicura la disponibilità di tutti gli artefatti richiesti.<br/><br/>Inoltre, verifica che eventuali aggiornamenti per sandbox o stream di dati non interferiscano con un’altra configurazione di Content Analytics impostata per la stessa sandbox o gli stessi stream di dati.
  >

* [Acquisizione e definizione dell’esperienza](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=it#configure-experience-capture-and-definition)

  Puoi abilitare o disabilitare le esperienze e modificare le combinazioni di espressioni regolari e parametri di query per determinare come riprodurre i contenuti sul tuo sito web.

* [Segmentazione degli eventi](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  Puoi modificare le espressioni regolari per specificare come segmentare pagine e risorse.


Dopo aver apportato le modifiche nell&#39;estensione Web Adobe Content Analytics, utilizza il [flusso di pubblicazione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview){target="_blank"} per iniziare a raccogliere i dati.


### Mobile

Utilizza l&#39;[estensione per dispositivi mobili Adobe Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) nella proprietà Tags associata alla configurazione Content Analytics per apportare ulteriori modifiche.

Dopo aver apportato le modifiche nell&#39;estensione Web Adobe Content Analytics, utilizza il [flusso di pubblicazione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview){target="_blank"} per iniziare a raccogliere i dati.


## Controllo delle versioni

>[!NOTE]
>
>Questa sezione si applica solo a Content Analytics per il canale web.


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

>[!MORELIKETHIS]
>
>[Configurazione guidata](guided.md)
>[Panoramica sulla pubblicazione dei tag di raccolta dati](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview)
>
