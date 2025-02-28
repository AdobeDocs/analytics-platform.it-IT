---
title: Configurazione manuale di Content Analytics
description: Come configurare manualmente l’analisi dei contenuti
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
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

Per attivare una nuova configurazione o le modifiche apportate a una configurazione esistente, è necessario [pubblicare](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} la proprietà Tag associata. Solo quando pubblichi la proprietà Tag di analisi del contenuto, i dati di analisi del contenuto vengono raccolti per i domini, l’esperienza e le risorse configurati.


## Disattiva

Per disattivare la raccolta dei dati di analisi del contenuto, [annulla la pubblicazione](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} della proprietà Tag associata per la configurazione di Analisi del contenuto.



## Modifica

In generale, è necessario utilizzare la [procedura guidata di configurazione](guided.md) per apportare modifiche all&#39;implementazione.

In alternativa, puoi utilizzare l’estensione Adobe Content Analytics nella proprietà Tag associata alla configurazione di Content Analytics per apportare modifiche ai seguenti artefatti:

* [Sandbox e flusso di dati](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >È necessario verificare che la sandbox e lo stream di dati configurati nell&#39;estensione Adobe Content Analytics siano già configurati per Content Analytics utilizzando la [configurazione guidata](guided.md) in una fase precedente. Questa configurazione assicura la disponibilità di tutti gli artefatti richiesti.<br/><br/>È inoltre necessario verificare che gli aggiornamenti per sandbox o flussi di dati non interferiscano con un&#39;altra configurazione di Content Analytics configurata per utilizzare gli stessi flussi di dati sandbox o.
  >

* [Filtro eventi](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}.

  Puoi modificare le espressioni regolari per modificare il modo in cui filtri pagine e risorse.


Dopo aver apportato modifiche nell&#39;estensione Adobe Content Analytics, assicurati di [attivare](#activate) le modifiche.



>[!MORELIKETHIS]
>
>[Configurazione guidata](guided.md)
>[Panoramica sulla pubblicazione dei tag di raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>