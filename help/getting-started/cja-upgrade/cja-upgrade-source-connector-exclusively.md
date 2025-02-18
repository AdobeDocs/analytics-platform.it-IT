---
title: Utilizzare il connettore di origine di Analytics esclusivamente per l’aggiornamento a Customer Journey Analytics
description: Scopri come creare il connettore di origine di Analytics e mappare i campi
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 39%

---

# Utilizzare il connettore di origine di Analytics esclusivamente per l’aggiornamento a Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Utilizzare unicamente il connettore di origine di Analytics"
>abstract="(Non consigliato) Non è possibile eseguire l’integrazione con altri servizi Adobe Experience Platform o uscire da Adobe Analytics con il connettore di origine di Analytics. È probabile che per collegare i dati da altre origini sia necessario eseguire l’unione. Per selezionare questa opzione, è necessario soddisfare tutti i requisiti nel questionario."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Usa le informazioni in questa pagina per rispondere alle domande nell&#39;[elenco di controllo per l&#39;aggiornamento di Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Anche se non è consigliato, puoi utilizzare il connettore di origine Analytics come unico percorso di implementazione per Customer Journey Analytics. Tuttavia, a causa degli svantaggi associati a questo tipo di aggiornamento, Adobe consiglia di utilizzare il connettore di origine di Analytics insieme a una nuova implementazione di Experience Platform Web SDK. Per ulteriori informazioni su questo percorso di aggiornamento consigliato, vedere [Percorso consigliato durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Utilizza le informazioni nella tabella seguente per comprendere i vantaggi e gli svantaggi dell’utilizzo esclusivo del connettore di origine.

Se decidi di utilizzare il connettore di origine di Analytics come unico percorso di implementazione per Customer Journey Analytics, segui i passaggi di implementazione descritti in [Acquisire e utilizzare dati utilizzando i connettori di origine](/help/data-ingestion/sources.md).

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>Percorso di aggiornamento meno lungo e impegnativo. <p>I dati vengono migrati a Customer Journey Analytics in modo rapido e semplice.</p></li></ul> | <ul><li>**I dati non vengono inviati a Edge Network**: <p>Ciò comporta i seguenti svantaggi:</p><ul><li>Livello massimo di [latenza](/help/technotes/guardrails.md#latencies) nel reporting per tutti i percorsi di aggiornamento; non ottimizzato per i casi di utilizzo di personalizzazione in tempo reale.</li><li>I dati non possono essere condivisi con altre applicazioni Adobe Experience Platform; è limitato solo a Customer Journey Analytics</li><li>Si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento e così via)</li></ul><li>**Difficoltà di passare al Web SDK in futuro**: è probabile che si desideri accedere ai vantaggi offerti da Experience Platform Web SDK. Per iniziare a utilizzare Experience Platform Web SDK, è necessario eseguire una nuova implementazione.</li><li>**Utilizza il gruppo di campi evento esperienza di Analytics nello schema**: questo gruppo di campi aggiunge molti eventi Adobe Analytics che non sono necessari nello schema di Customer Journey Analytics.  Ciò può portare a uno schema più disordinato e complesso di quello altrimenti necessario per Customer Journey Analytics.</li><li>**Richiede licenze sia per Adobe Analytics che per Customer Journey Analytics**: l&#39;utilizzo del connettore di origine di Analytics richiede il pagamento di Adobe Analytics e Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}
