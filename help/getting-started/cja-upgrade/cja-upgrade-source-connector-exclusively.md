---
title: Utilizza il connettore di origine di Analytics esclusivamente per l’aggiornamento al Customer Journey Analytics
description: Scopri come creare il connettore di origine di Analytics e mappare i campi
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 07570641949e17d30b7f9f5b38eb95c29c5176c0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 27%

---

# Utilizza il connettore di origine di Analytics esclusivamente per l’aggiornamento al Customer Journey Analytics

>[!NOTE]
> 
>Usa le informazioni in questa pagina per rispondere alle domande nell&#39;elenco di controllo per l&#39;aggiornamento di [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Anche se non è consigliato, puoi utilizzare il connettore di origine Analytics come unico percorso di implementazione per il Customer Journey Analytics. Tuttavia, a causa degli svantaggi associati a questo tipo di aggiornamento, Adobe consiglia di utilizzare il connettore di origine di Analytics insieme a una nuova implementazione di Experience Platform Web SDK. Per ulteriori informazioni su questo percorso di aggiornamento consigliato, vedere [Percorso consigliato durante l&#39;aggiornamento da Adobe Analytics al Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Utilizza le seguenti informazioni per comprendere i vantaggi e gli svantaggi dell’utilizzo esclusivo del connettore di origine:

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>Percorso di aggiornamento meno lungo e impegnativo. <p>I dati vengono migrati al Customer Journey Analytics in modo rapido e semplice.</p></li></ul> | <ul><li>**I dati non vengono inviati a Edge Network**: <p>Ciò comporta i seguenti svantaggi:</p><ul><li>Livello massimo di [latenza](/help/technotes/guardrails.md#latencies) nel reporting per tutti i percorsi di aggiornamento; non ottimizzato per i casi di utilizzo di personalizzazione in tempo reale.</li><li>I dati non possono essere condivisi con altre applicazioni Adobe Experience Platform; è limitato solo a Customer Journey Analytics</li><li>Si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento e così via)</li></ul><li>**Difficoltà di passare al Web SDK in futuro**: probabilmente in seguito, avrai accesso ai vantaggi forniti dal Web SDK Experience Platform. Per iniziare a utilizzare l’SDK per web di Experience Platform, è necessario eseguire una nuova implementazione.</li><li>**Utilizza il gruppo di campi evento esperienza di Analytics nello schema**: questo gruppo di campi aggiunge molti eventi Adobe Analytics che non sono necessari nello schema di Customer Journey Analytics.  Ciò può portare a uno schema più disordinato e complesso di quello altrimenti necessario per Customer Journey Analytics.</li><li>**Richiede licenze sia per Adobe Analytics che per Customer Journey Analytics**: l&#39;utilizzo del connettore di origine di Analytics richiede il pagamento sia per Adobe Analytics che per Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}
