---
title: Metodi alternativi per l'aggiornamento a Customer Journey Analytics
description: Scopri i metodi alternativi per l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
TQID: https://experienceleague.adobe.com/86uAMXhpBXaVnjA8Zh2G7Ail-XKR2HjrYNyge5BRMRc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 14557a59902110b1768d61e621adfb3f76ee9930
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 54%

---

# Alternativa di aggiornamento: inviare il livello dati a Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Inviare il livello di dati ad Adobe"
>abstract="Invece di inviare dati tramite un oggetto XDM, è possibile inviare l’intero livello dati ad Adobe tramite l’oggetto dati.<br><br>Questa opzione consente di risparmiare tempo di implementazione effettuando la mappatura del livello dati su XDM, anziché popolare un oggetto XDM da zero. Tuttavia, tale mappatura può essere laborioso, a causa di una quantità significativa di dati che potrebbero non essere facilmente interpretati da Adobe. Inoltre, questa opzione introduce nel tempo ulteriori complessità, in quanto qualsiasi campo aggiunto ai dati in un secondo momento dovrà essere mappato su XDM nello stream di dati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="Inviare il livello dati ad Adobe"
>abstract="Configura l’implementazione per inviare i dati ad Adobe al momento desiderato e configura il payload JSON affinché corrisponda all’intero livello di dati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="Assegnare ogni elemento del livello dati a XDM"
>abstract="Mappa ogni elemento del livello dati sul campo XDM desiderato. Tutti gli elementi del livello dati che non sono mappati su un campo XDM vengono eliminati in modo permanente, in quanto Adobe non sa dove o come memorizzare tali dati."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Durante l’aggiornamento a Customer Journey Analytics, Adobe [consiglia una nuova implementazione di Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Tuttavia, a seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi per l’aggiornamento consigliati potrebbero non essere pratici per la tua organizzazione.

Puoi inviare l’intero livello dati a Customer Journey Analytics invece di raccogliere i dati con l’oggetto XDM. Tuttavia, questa alternativa introduce una complessità aggiuntiva nel tempo.

## Vantaggi e svantaggi

Questo metodo si esclude a vicenda con [utilizzando la logica di raccolta dati di AppMeasurement con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), poiché entrambi i metodi eseguono la stessa attività.

Di seguito sono riportati i vantaggi e gli svantaggi dell&#39;utilizzo di questa alternativa di aggiornamento:

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidamento dell&#39;implementazione per la raccolta dati Adobe CX Enterprise tra altri prodotti CX Enterprise (AJO, RTCDP e così via)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)</li></ul><li>**Utilizza la logica del livello dati corrente**: questo metodo utilizza la logica del livello dati corrente al posto di un&#39;implementazione convenzionale di Web SDK. Anche se questo approccio richiede una certa configurazione, non richiede un’implementazione completamente nuova da zero e non richiede il popolamento di elementi di dati o regole di tag. Consente di mappare i dati dal livello dati a XDM, anziché popolare un oggetto XDM da zero.</li></ul> | <ul><li>**Richiede la mappatura per inviare i dati a Platform**: quando l’organizzazione è pronta per utilizzare Customer Journey Analytics, devi inviare i dati a un set di dati in Adobe Experience Platform. <p>Poiché questa opzione consente di inserire l’intero livello dati lato client nell’oggetto dati e inviarlo ad Adobe, si ottiene una quantità significativa di dati che Adobe non è in grado di interpretare facilmente. Per consentire ad Adobe di interpretare i dati, devi utilizzare la mappatura dello stream di dati per mappare ogni singolo campo al campo XDM desiderato.</p></li><li>**Implementazione rigida**: l&#39;implementazione è vincolata a ciò che fornisce il livello dati al momento dell&#39;invio dell&#39;hit. Questo potrebbe essere accettabile per le organizzazioni con esigenze di dati di base, ma la maggior parte delle organizzazioni dovrebbe evitare questo tipo di implementazione rigida a favore di un’implementazione più flessibile che consenta di popolare gli elementi di dati.</li><li>**Le modifiche future sono più difficili da implementare**: qualsiasi campo aggiunto ai dati in un secondo momento deve essere mappato a XDM nello stream di dati.</li></ul> |

{style="table-layout:auto"}

## Passaggi di base

I passaggi di base per inviare l’intero livello dati a Customer Journey Analytics sono i seguenti:

1. Configura l’implementazione per inviare i dati ad Adobe al momento desiderato e configura il payload JSON affinché corrisponda all’intero livello di dati.

1. Mappa ogni elemento del livello dati sul campo XDM desiderato.

   Tutti gli elementi del livello dati che non sono mappati su un campo XDM vengono eliminati in modo permanente, in quanto Adobe non sa dove o come memorizzare tali dati.
