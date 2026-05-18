---
title: Comprendere le funzioni univoche di Customer Journey Analytics
description: Informazioni sulle funzioni univoche di Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
TQID: https://experienceleague.adobe.com/8yBVFyHrc31-ac8XLV-aW-SWBfDZodlIXirICmdzpkY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 591
ht-degree: 100%

---

# Comprendere le funzioni univoche di Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Collegare dati di origini diverse"
>abstract="(Consigliato) Collega dati da varie proprietà web, mobili e offline per creare una singola vista consolidata del comportamento della clientela. La possibilità di combinare dati di analisi provenienti da altri canali è il caso d’uso principale per Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Unire gli hit da più set di dati"
>abstract="Se un set di dati non condivide un identificatore principale (ad esempio, un ID Experience Cloud), puoi comunque combinare i dati utilizzando un’altra dimensione, ad esempio il nome utente o l’indirizzo e-mail di accesso."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Abilita l’unione delle identità per i set di dati pertinenti"
>abstract="Se un campo contiene un identificatore che esiste in più set di dati ma non è l’identificatore primario, puoi utilizzare l’unione delle identità per migliorare i dati in uno o più di questi set di dati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Integrare con Real-time CDP"
>abstract="Combina i dati di profilo da più origini per generare tipi di pubblico e segmenti in base alle caratteristiche degli utenti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Integrare temporaneamente con Adobe Target"
>abstract="Adobe consiglia di eseguire l’integrazione con Adobe Journey Optimizer per i casi di utilizzo di personalizzazione. L’integrazione con Adobe Target è possibile, ma si tratta di una soluzione temporanea."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Integrare con Journey Optimizer"
>abstract="Fornisci alla clientela esperienze connesse, contestuali e personalizzate."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Integrare temporaneamente con Adobe Audience Manager"
>abstract="Adobe consiglia di eseguire l’integrazione con Adobe Real-time CDP per i casi d’uso basati sul pubblico. L’integrazione con Audience Manager è possibile, ma si tratta di una soluzione temporanea."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Nell’elenco seguente vengono illustrate solo le funzioni di Customer Journey Analytics che devono essere considerate durante il processo di aggiornamento. Per un elenco completo delle funzionalità di Adobe Analytics completamente supportate, parzialmente supportate o non supportate in Customer Journey Analytics, consulta [Supporto delle funzionalità di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Considera quali delle seguenti funzioni di Customer Journey Analytics desideri adottare quando effettui l’aggiornamento a Customer Journey Analytics:

| Funzione di Customer Journey Analytics | Funzione |
|---------|----------|
| [Collegare dati Web con dati provenienti da altri canali, ad esempio dati di call center](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics è combinato con la capacità di Experience Platform di contenere tutti i tipi e schemi di dati. Utilizzando [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) i dati possono essere rappresentati e organizzati in modo uniforme e sono pronti per essere combinati ed esaminati. Adobe Analytics si concentra principalmente sui dati di analisi del web e dei dispositivi mobili con alcune funzionalità per [importare i dati](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=it). |
| [Unire gli hit provenienti da altri set di dati utilizzando una dimensione personalizzata](https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics consente di [combinare dati](/help/connections/combined-dataset.md) provenienti da più suite di rapporti come se si trattasse di una singola suite di rapporti in Adobe Analytics. |
| [Integrare con Adobe Real-time CDP](/help/components/audiences/audiences-overview.md) | Puoi [creare e pubblicare i tipi di pubblico](/help/components/audiences/audiences-overview.md) rilevati in Customer Journey Analytics sul profilo cliente in tempo reale in Adobe Experience Platform a scopo di personalizzazione e targeting della clientela. |
| [Integrare con Adobe Target (A4T)](/help/integrations/at.md) | Il reporting di Target in Customer Journey Analytics consente di [misurare e creare rapporti sulle attività di Adobe Target](/help/integrations/at.md) direttamente in Customer Journey Analytics. Tuttavia, per i casi d’uso di personalizzazione, Adobe consiglia di eseguire l’integrazione con Adobe Journey Optimizer. |
| [Integrare con Adobe Journey Optimizer](/help/integrations/ajo.md) | Puoi configurare i dati generati da Journey Optimizer per [eseguire analisi avanzate in Customer Journey Analytics](/help/integrations/ajo.md). |
| [Integrare con Adobe Audience Manager](https://experienceleague.adobe.com/it/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Puoi [condividere caratteristiche e segmenti di Audience Manager in Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). Tuttavia, per i casi d’uso basati sul pubblico, Adobe consiglia di eseguire l’integrazione con Adobe Real-time CDP. |
