---
title: Utilizzare il connettore di origine Analytics esclusivamente per l’aggiornamento a Customer Journey Analytics
description: Scopri come creare il connettore di origine di Analytics e mappare i campi
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 94%

---

# Alternativa di aggiornamento: utilizzare solo il connettore di origine di Analytics per l’aggiornamento a Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Utilizzare unicamente il connettore di origine di Analytics"
>abstract="(Sconsigliato) Puoi utilizzare il connettore di origine Analytics come unico percorso di implementazione per Customer Journey Analytics. <br><br>Questa opzione riduce il tempo di implementazione inviando rapidamente i dati a Customer Journey Analytics. Tuttavia, presenta diverse lacune, come una latenza più elevata e difficoltà durante la migrazione ad Adobe Analytics in futuro."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Sebbene non sia consigliato, puoi utilizzare il connettore di origine Analytics come unico percorso di implementazione per Customer Journey Analytics. Tuttavia, a causa degli svantaggi intrinseci associati a questo tipo di aggiornamento, Adobe consiglia di utilizzare il connettore di origine Analytics insieme a una nuova implementazione di Experience Platform Web SDK. Per ulteriori informazioni su questo percorso di aggiornamento consigliato, consulta [Percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

## Vantaggi e svantaggi

Utilizza le informazioni nella tabella seguente per comprendere i vantaggi e gli svantaggi dell’utilizzo del connettore di origine esclusivamente durante l’aggiornamento a Customer Journey Analytics.

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>Percorso di aggiornamento meno impegnativo e dispendioso in termini di tempo. <p>La migrazione dei dati a Customer Journey Analytics avviene in modo semplice e rapido.</p></li></ul> | <ul><li>**I dati non vengono inviati a Edge Network**: <p>Ciò comporta i seguenti svantaggi:</p><ul><li>Livello più alto di [latenza](/help/technotes/guardrails.md#latencies) nella generazione di rapporti tra tutti i percorsi di aggiornamento; non ottimizzato per casi d’uso di personalizzazione in tempo reale.</li><li>I dati non possono essere condivisi con altre applicazioni Adobe Experience Platform; è limitato solo a Customer Journey Analytics</li><li>Si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento e così via)</li></ul><li>**Difficoltà di passare a Web SDK in futuro**: è probabile che, alla fine, vorrai accedere ai vantaggi offerti da Experience Platform Web SDK. Per iniziare a utilizzare Experience Platform Web SDK, dovrai eseguire una nuova implementazione.</li><li>**Utilizza il gruppo di campi evento esperienza di Analytics nello schema**: questo gruppo di campi aggiunge molti eventi Adobe Analytics che non sono necessari nello schema di Customer Journey Analytics.  Ciò può portare a uno schema più disordinato e complesso di quello altrimenti necessario per Customer Journey Analytics.</li><li>**Richiede licenze sia per Adobe Analytics che per Customer Journey Analytics**: l’utilizzo del connettore di origine Analytics prevede pagamenti sia per Adobe Analytics che per Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

## Passaggi di base

Se decidi di utilizzare il connettore di origine Analytics come unico percorso di implementazione per Customer Journey Analytics, segui i passaggi di implementazione descritti in [Acquisire e utilizzare i dati usufruendo dei connettori di origine](/help/data-ingestion/sources.md).

