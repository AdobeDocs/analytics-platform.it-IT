---
title: Guida alla transizione
description: Scopri come passare da Customer Journey Analytics a Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
autotag-review: '2026-05-19T08:06:36.475Z'
TQID: 'https://experienceleague.adobe.com/vkf6272OwRu9B4ZgpiXKhc4J3WAqUAm8r-3iQLUgOKg'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 9c87ce4fb30c7d1d66ce88174443369ef44a7377
workflow-type: tm+mt
source-wordcount: 623
ht-degree: 3%

---

# Guida alla transizione

Questa guida illustra come passare da Customer Journey Analytics a B2B edition di Customer Journey Analytics.

L’articolo presuppone che tu utilizzi già Customer Journey Analytics in una certa misura:

* Sono presenti [connessioni](/help/connections/overview.md) che acquisiscono dati in Customer Journey Analytics.
* Sono presenti [visualizzazioni dati](/help/data-views/data-views.md) che utilizzano i dati di queste connessioni.
* Sono presenti [progetti](/help/analysis-workspace/home.md) con report e visualizzazioni che sfruttano queste visualizzazioni dati.

Se non hai mai utilizzato Customer Journey Analytics in precedenza, consulta la [Guida rapida di B2B edition](cja-b2b-quick-start-guide.md).

Se sei un utente di Adobe Analytics e prevedi di utilizzare Customer Journey Analytics B2B edition, consulta innanzitutto la documentazione sull&#39;[aggiornamento da Adobe Analytics a Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md).


## Implementazione esistente

L’implementazione esistente di Customer Journey Analytics non cambia affatto una volta che hai ottenuto la licenza e hai effettuato il provisioning per Customer Journey Analytics B2B edition.

Tutte le connessioni esistenti sono considerate [connessioni basate su persona](cja-b2b-concepts-features.md#connections-and-identifiers) e continuano a funzionare senza alcun aggiornamento. Tutto ciò che si basa sui dati di queste connessioni basate su persone, come visualizzazioni dati, progetti Workspace, segmenti, esportazioni pianificate, avvisi e altro ancora, continua a funzionare come previsto e pianificato in origine.

>[!IMPORTANT]
>
>Non è possibile modificare le connessioni personali esistenti in una connessione basata su account. Per utilizzare le funzioni di B2B edition è necessaria una nuova connessione basata su account.
>


## Implementare funzioni B2B

Per implementare le funzioni B2B nell’implementazione esistente, devi seguire questi passaggi:

1. Modellare i dati B2B. Puoi utilizzare [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) per standardizzare i dati B2B e definire schemi per i dati B2B.<br/>È possibile basare gli schemi sulle [classi standard fornite in Real-time CDP B2B edition](https://experienceleague.adobe.com/it/docs/experience-platform/rtcdp/schemas/b2b) oppure utilizzare classi e schemi personalizzati. Gli articoli [casi d&#39;uso](/help/use-cases/b2b/b2b-edition/use-cases-overview.md) utilizzano classi e schemi di Real-time CDP B2B edition. Tuttavia, per utilizzare le classi e gli schemi standard non è necessaria una licenza di Real-time CDP B2B edition. <br/>Customer Journey Analytics B2B edition presume almeno i dati evento della serie temporale basati sull&#39;account e trae vantaggio dai dati aggiuntivi del profilo o del record di ricerca. Ad esempio i dati dell’account, i dati del gruppo di acquisto, i dati delle opportunità, i dati dei membri dell’elenco di marketing e altro ancora.

   * Definisci quale identificatore desideri utilizzare come identificatore dell’account principale (ID account). Spesso un CRM esistente o un altro strumento (ad esempio: Demandbase) ti aiuta a determinare tale identificatore.
   * Identifica identificatori aggiuntivi per gli altri dati B2B che intendi utilizzare: identificatore globale dell’account, identificatore dell’opportunità, identificatore del gruppo di acquisto e identificatore della persona.

1. Prepara i dati B2B. Assicurati di aggiungere e raccogliere gli identificatori dell’account in tutte le serie temporali dei dati evento e dei record rilevanti. Allo stesso modo, assicurati che i dati evento della serie temporale e il record di ricerca contengano altri identificatori per gli eventi rilevanti. Ad esempio: un evento che segnala il passaggio a un’altra fase di vendita deve avere un identificatore di opportunità. E tale identificatore dovrebbe far parte dei dati di ricerca delle opportunità.

1. [Crea una nuova connessione basata su account](/help/connections/create-connection.md#account-based-connection). Seleziona i contenitori facoltativi da includere, [aggiungi set di dati](/help/connections/create-connection.md#add-datasets) e definisci le [impostazioni per ogni set di dati](/help/connections/create-connection.md#dataset-settings). Utilizza [corrispondenza per contenitore](cja-b2b-concepts-features.md#match-by-container) per i set di dati dei record di ricerca ogni volta che ciò sia possibile.

1. [Crea visualizzazioni dati](/help/data-views/create-dataview.md) in base alla nuova connessione.

   * Assicurati di aggiungere tutti i campi rilevanti come metriche o dimensioni dai dati che hai acquisito.
   * Se necessario, applica le impostazioni dei componenti (come persistenza, attribuzione e altro).
   * Se necessario, aggiungi ulteriori campi derivati.

1. [Crea progetti Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) per creare rapporti e ottenere informazioni sui tuoi dati B2B. Utilizza funzionalità B2B specifiche, come [container](cja-b2b-concepts-features.md#containers), per ottenere informazioni approfondite.

   È possibile combinare report e approfondimenti B2B (basati su persone) e B2B (basati su account) tramite l&#39;utilizzo di più [pannelli](/help/analysis-workspace/c-panels/panels.md) in un unico progetto Workspace.
