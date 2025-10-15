---
description: Scopri le differenze tra gli avvisi in Customer Journey Analytics e Adobe Analytics
title: Confronto delle funzioni degli avvisi tra Customer Journey Analytics e Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 9e07dfc84bc06aef987d99c225cefb4e0406f552
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 24%

---

# Confronto delle funzioni di avviso

Il processo di utilizzo degli avvisi in Customer Journey Analytics è quasi identico a quello degli avvisi in Adobe Analytics. Tuttavia, ci sono importanti differenze. Le sezioni seguenti descrivono le differenze principali.

## Gli avvisi orari non sono disponibili

Gli avvisi orari sono **non** disponibili in Customer Journey Analytics, mentre gli avvisi orari sono disponibili in Adobe Analytics. In Customer Journey Analytics, gli avvisi possono essere configurati come giornalieri, settimanali o mensili.

È possibile acquisire dati in Adobe Experience Platform in vari modi. Di conseguenza, la completezza e la disponibilità dei dati non possono essere raggiunte in modo affidabile entro i limiti di un’ora.  La flessibilità dell’acquisizione dei dati implica che gli avvisi orari non sono pratici a causa dell’elevato potenziale di dati incompleti. Per ulteriori informazioni, consulta [I tempi di acquisizione dei dati variano](#data-ingestion-times-vary-in-customer-journey-analytics).

## I tempi di acquisizione dei dati variano

Il tempo necessario prima che i dati siano completi e disponibili per essere segnalati in Customer Journey Analytics varia a seconda dell’organizzazione.

Ciò è dovuto ai seguenti motivi:

* Capacità di Platform di contenere tutti i tipi di schemi e tipi di dati

  A differenza di Adobe Analytics (che segnala solo i dati web), in Adobe Experience Platform[&#x200B; è possibile acquisire molti tipi diversi di dati da segnalare in Customer Journey Analytics e non tutti i tipi di dati possono essere inviati in sequenza e in tempo reale.](/help/data-ingestion/data-ingestion.md)

* Ritardo nella consegna dei dati batch ai set di dati di Platform

  Anche se alcuni dati potrebbero essere disponibili per creare rapporti prima, tutti i [dati batch vengono acquisiti in un set di dati di Platform](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), in genere nell&#39;intervallo da 3 a 9 ore oltre l&#39;ora dell&#39;evento dati. Affinché gli avvisi siano precisi, l’acquisizione dei dati deve essere completa, con tutti i dati batch disponibili nel set di dati. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Per questi motivi, l’acquisizione dei dati per i vari tipi di dati evento che possono essere acquisiti è completa solo dopo un certo ritardo, che in genere varia da 3 a 9 ore oltre l’ora dell’evento dei dati. Affinché gli avvisi siano precisi, i dati evento per un determinato intervallo di eventi devono essere completi, il che significa che Adobe non riceve più i dati evento per l’intervallo di eventi specificato.

Per tenere conto di questo ritardo nel tempo di acquisizione, gli avvisi hanno un ritardo predefinito di 9 ore prima di essere inviati.

Puoi impostare il ritardo predefinito di 9 ore su qualsiasi valore compreso tra 0 e 24 ore. Tuttavia, la riduzione del ritardo al di sotto di 9 ore può significare che stai eseguendo un rapporto con dati incompleti, il che si traduce in informazioni di avviso imprecise.

Per ulteriori informazioni su come regolare il ritardo e sui fattori da considerare quando lo si fa, vedere [Creare avvisi](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Creare un avviso

In Analysis Workspace in Adobe Analytics, puoi [creare avvisi da Analysis Workspace in più modi](https://experienceleague.adobe.com/en/docs/analytics/components/alerts/alert-builder). In Customer Journey Analytics, è possibile [creare un avviso](alert-builder.md) in Analysis Workspace solo da una selezione in una tabella a forma libera.

Sia Adobe Analytics che Customer Journey Analytics supportano la creazione di avvisi tramite [Gestione avvisi](alert-manager.md)
