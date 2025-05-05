---
title: Comprendere le funzioni univoche di Customer Journey Analytics
description: Informazioni sulle funzioni univoche di Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 78%

---

# Comprendere le funzioni univoche di Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Collegare dati di origini diverse"
>abstract="(Consigliato) Collega dati da varie proprietà web, dispositivi mobili e offline per creare una singola vista consolidata del comportamento della clientela. Questa possibilità di combinare dati di analisi provenienti da altri canali è il caso d’uso principale per Customer Journey Analytics."

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
>title="Contatta l’Assistenza clienti di Adobe per generare un set di dati uniti"
>abstract="Se un campo contiene un identificatore che esiste in più set di dati ma non è l’identificatore principale, puoi utilizzarlo per generare un nuovo set di dati con un identificatore coerente."

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
>abstract="Adobe consiglia di eseguire l’integrazione con Adobe Journey Optimizer per i casi di utilizzo di personalizzazione. L’integrazione con Adobe Target è possibile, ma è una soluzione temporanea."

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
>abstract="Adobe consiglia di eseguire l’integrazione con Adobe Real-time CDP per i casi d’uso basati sul pubblico. L’integrazione con Audience Manager è possibile, ma è una soluzione temporanea."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Nell’elenco seguente vengono illustrate solo le funzioni di Customer Journey Analytics che devono essere considerate durante il processo di aggiornamento. Per un elenco completo delle funzionalità di Adobe Analytics completamente supportate, parzialmente supportate o non supportate in Customer Journey Analytics, consulta [Supporto delle funzionalità di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Considera quali delle seguenti funzioni di Customer Journey Analytics desideri adottare quando effettui l’aggiornamento a Customer Journey Analytics:

| Funzione di Customer Journey Analytics | Funzione |
|---------|----------|
| [Collegare dati Web con dati provenienti da altri canali, ad esempio dati di call center](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics è combinato con la capacità di Experience Platform di contenere tutti i tipi e schemi di dati. Utilizzando [Experience Data Model (XDM)](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home.html?lang=it) i dati possono essere rappresentati e organizzati in modo uniforme e sono pronti per essere combinati ed esaminati. Adobe Analytics si concentra principalmente sui dati di analisi del web e dei dispositivi mobili con alcune funzionalità per [importare i dati](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=it). |
| [Unire gli hit provenienti da altri set di dati utilizzando una dimensione personalizzata](https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics consente di [combinare dati](/help/connections/combined-dataset.md) provenienti da più suite di rapporti come se si trattasse di una singola suite di rapporti in Adobe Analytics. |
| [Integrare con Adobe Real-time CDP](/help/components/audiences/audiences-overview.md) | Puoi [creare e pubblicare i tipi di pubblico](/help/components/audiences/audiences-overview.md) rilevati in Customer Journey Analytics su Real-Time Customer Profile in Adobe Experience Platform per la personalizzazione e il targeting dei clienti. |
| [Integrare con Adobe Target (A4T)](/help/integrations/at.md) | Il reporting di Target in Customer Journey Analytics consente di [misurare e creare rapporti sulle attività di Adobe Target](/help/integrations/at.md) direttamente in Customer Journey Analytics. Tuttavia, Adobe consiglia di eseguire l’integrazione con Adobe Journey Optimizer per i casi di utilizzo di personalizzazione. |
| [Integrare con Adobe Journey Optimizer](/help/integrations/ajo.md) | È possibile configurare i dati generati da Journey Optimizer per [eseguire analisi avanzate in Customer Journey Analytics](/help/integrations/ajo.md). |
| [Integrare con Adobe Audience Manager](https://experienceleague.adobe.com/it/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | È possibile [condividere caratteristiche e segmenti di Audience Manager in Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). Tuttavia, Adobe consiglia di eseguire l’integrazione con Adobe Real-time CDP per i casi d’uso basati sul pubblico. |
