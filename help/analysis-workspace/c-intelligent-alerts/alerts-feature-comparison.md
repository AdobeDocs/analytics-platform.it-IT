---
description: Scopri le differenze tra gli avvisi intelligenti e il Customer Journey Analytics di Adobe Analytics
title: Customer Journey Analytics di confronto delle funzioni degli avvisi intelligenti e Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: 74ad39f6ccc6436f7c8540b7d8b69b20b93d2b5c
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Confronto delle funzioni di avvisi intelligenti: Customer Journey Analytics e Adobe Analytics

{{release-limited-testing}}

Il processo di utilizzo degli avvisi intelligenti in Customer Journey Analytics è quasi identico a quello degli avvisi intelligenti in Adobe Analytics. Tuttavia, ci sono importanti differenze.

Le sezioni seguenti descrivono le differenze principali.

## Gli avvisi orari non sono disponibili nel Customer Journey Analytics

Gli avvisi orari non sono disponibili nel Customer Journey Analytics come in Adobe Analytics. In Customer Journey Analytics, gli avvisi possono essere configurati per giornaliero, settimanale o mensile.

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

Per ulteriori informazioni su come regolare il ritardo e sui fattori da tenere in considerazione quando si esegue questa operazione, vedere <!--add link -->.

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->





