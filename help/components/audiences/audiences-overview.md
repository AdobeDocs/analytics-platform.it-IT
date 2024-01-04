---
title: Scopri la panoramica sulla pubblicazione di tipi di pubblico di Customer Journey Analytics
description: Scopri il concetto di pubblicazione di tipi di pubblico in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 50%

---

# Panoramica sulla pubblicazione di tipi di pubblico di Customer Journey Analytics

Ora puoi creare e pubblicare i tipi di pubblico rilevati nel Customer Journey Analytics in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) in Adobe Experience Platform per il targeting e la personalizzazione dei clienti.

La pubblicazione di tipi di pubblico offre un modo chiaro di attivarsi e di agire sulle informazioni presenti nel Customer Journey Analytics. Tali azioni possono includere:

* Utilizzo del pubblico per un percorso in Adobe Journey Optimizer.
* Esportazione del pubblico a terzi tramite una destinazione di Experience Platform.
* Arricchimento di Real-time Customer Profile con attributi utili derivati dai dati basati su eventi nel Customer Journey Analytics.
* Tutto questo con latenza minima dopo la pubblicazione del pubblico. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=it#latency)
* Pubblicazione di tipi di pubblico una tantum o ricorrenti.

I tipi di pubblico creati nel Customer Journey Analytics non devono necessariamente essere basati su set di dati abilitati per il profilo. Puoi acquisire dati storici in Experienci Platform senza abilitare set di dati e schemi associati per il profilo. Quindi utilizza questi set di dati per scoprire i tipi di pubblico rilevanti nel Customer Journey Analytics e pubblicarli in Real-time Customer Profile in Experienci Platform a scopo di attivazione.

## Terminologia chiave

**Pubblico**: un insieme o un elenco di identità con uno spazio dei nomi e un ID specifico correlati a tale spazio dei nomi. I tipi di pubblico sono trasportabili dal Adobe Experience Platform e dalle applicazioni che lo compongono (come il Customer Journey Analytics). I tipi di pubblico possono contenere spazi dei nomi misti.

**Filtro**: un insieme di regole che, se valutate in un insieme di dati per un periodo di tempo, produce un sottoinsieme di dati. Un filtro può essere utilizzato nel processo di creazione di un pubblico quando è associato ad altri servizi di supporto. I filtri sono definiti e mantenuti nel Customer Journey Analytics.

**Filtri** rispetto a **Segmenti**: il Customer Journey Analytics non utilizza il concetto di &quot;segmenti&quot;, utilizza invece i &quot;filtri&quot;. Sebbene siano entrambi un insieme di regole che possono contenere una logica simile, producono output diversi. Un filtro viene utilizzato per limitare un set di dati a scopo di analisi. Un segmento viene utilizzato per generare un elenco di identità che possono essere utilizzate per l’attivazione. I segmenti producono tipi di pubblico in Real-time Customer Profile, mentre i filtri (da soli) no. La pubblicazione di tipi di pubblico di Customer Journey Analytics è il processo mediante il quale utilizziamo un filtro di Customer Journey Analytics per creare un pubblico che può essere utilizzato da Real-time Customer Profile.

## Autorizzazioni

* Gli amministratori ricevono automaticamente l’autorizzazione **[!UICONTROL Audience Publishing]** in Adobe Admin Console.

* Gli amministratori possono concedere questa autorizzazione a singoli utenti.

* Gli amministratori richiedono inoltre l’autorizzazione **[!UICONTROL Manage Profiles]** in Adobe Experience Platform.

## Governance dei dati e consenso

Quando pubblichi un pubblico in un Customer Journey Analytics, vengono registrate le etichette e i criteri di governance dei dati allegati ai campi utilizzati nel pubblico.  Quando il pubblico viene attivato in una qualsiasi app di Adobe Experience, tutte le etichette e i criteri di governance dei dati associati sono disponibili per quel pubblico e possono essere applicati gli opportuni provvedimenti di implementazione. [Ulteriori informazioni sul consenso](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=it#consent-policy).

## Passaggi successivi

* [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md)
* [Gestire i tipi di pubblico](/help/components/audiences/manage.md)
