---
description: Scopri le differenze tra gli avvisi e il Customer Journey Analytics di Adobe Analytics
title: Customer Journey Analytics di confronto delle funzioni degli avvisi e Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 5%

---

# Confronto delle funzioni di avviso

Il processo di utilizzo degli avvisi in Customer Journey Analytics è quasi identico a quello degli avvisi in Adobe Analytics. Tuttavia, ci sono importanti differenze. Le sezioni seguenti descrivono le differenze principali.

## Gli avvisi orari non sono disponibili nel Customer Journey Analytics

Gli avvisi orari non sono disponibili nel Customer Journey Analytics come in Adobe Analytics. In Customer Journey Analytics, gli avvisi possono essere configurati come giornalieri, settimanali o mensili.

Ciò è dovuto ai vari modi in cui i dati possono essere acquisiti in Adobe Experience Platform, prima che vengano segnalati in Customer Journey Analytics. La completezza e la disponibilità dei dati non possono essere raggiunte in modo affidabile entro un’ora, rendendo gli avvisi orari poco pratici a causa dell’elevato potenziale di dati incompleti. Per ulteriori informazioni, consulta [I tempi di acquisizione dei dati variano](#data-ingestion-times-vary-in-customer-journey-analytics).

## I tempi di acquisizione dei dati variano a seconda del Customer Journey Analytics

Il tempo necessario prima che i dati siano completi e disponibili per essere segnalati nel Customer Journey Analytics varia a seconda dell&#39;organizzazione.

Ciò è dovuto ai seguenti motivi:

* Capacità di Platform di contenere tutti i tipi di schemi e tipi di dati

  A differenza di Adobe Analytics (che segnala solo i dati web), [molti tipi diversi di dati possono essere acquisiti in Adobe Experience Platform](/help/data-ingestion/data-ingestion.md) per essere segnalati in Customer Journey Analytics e non tutti i tipi di dati possono essere inviati in sequenza e in tempo reale.

* Ritardo nella consegna dei dati batch ai set di dati di Platform

  Anche se alcuni dati potrebbero essere disponibili per creare rapporti prima, tutti i [dati batch vengono acquisiti in un set di dati di Platform](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.), in genere nell&#39;intervallo da 3 a 9 ore oltre l&#39;ora dell&#39;evento dati. Affinché gli avvisi siano precisi, l’acquisizione dei dati deve essere completa, con tutti i dati batch disponibili nel set di dati. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

Per questi motivi, l’acquisizione dei dati per i vari tipi di dati evento che possono essere acquisiti è completa solo dopo un certo ritardo, che in genere varia da 3 a 9 ore oltre l’ora dell’evento dei dati. Affinché gli avvisi siano precisi, i dati evento per un determinato intervallo di eventi devono essere completi, il che significa che Adobe non riceve più i dati evento per l’intervallo di eventi specificato.

Per tenere conto di questo ritardo nel tempo di acquisizione, gli avvisi hanno un ritardo predefinito di 9 ore prima di essere inviati.

Puoi impostare il ritardo predefinito di 9 ore su un valore compreso tra 0 e 24 ore. Tuttavia, la riduzione del ritardo al di sotto di 9 ore può significare che stai eseguendo la segnalazione di dati incompleti, il che si traduce in informazioni di avviso imprecise.

Per ulteriori informazioni su come regolare il ritardo e sui fattori da considerare quando lo si fa, vedere [Creare avvisi](/help/components/c-intelligent-alerts/alert-builder.md).

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## L’opzione per creare un avviso da Analysis Workspace non è disponibile

In Analysis Workspace in Adobe Analytics, puoi creare avvisi da Analysis Workspace in uno dei modi descritti di seguito. In Customer Journey Analytics, le opzioni per la creazione di avvisi da Analysis Workspace non sono ancora disponibili. Accedere al Generatore di avvisi come descritto in [Creare avvisi](/help/components/c-intelligent-alerts/alert-builder.md).

In Adobe Analytics sono disponibili le seguenti opzioni:

* Selezionare uno o più elementi in una tabella a forma libera, quindi fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Create alert from selection]**.

  Questo precompila immediatamente il generatore di avvisi per creare un avviso con le metriche e i filtri corretti.

* Apri un progetto in Analysis Workspace, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.

* Apri un progetto in Analysis Workspace, quindi utilizza la seguente scelta rapida:

  `ctrl (or cmd) + shift + a`






