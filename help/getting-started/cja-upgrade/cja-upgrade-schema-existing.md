---
title: Scegliere lo schema per Customer Journey Analytics
description: Scopri le opzioni disponibili per la scelta di uno schema per Customer Journey Analytics e i vantaggi e gli svantaggi di ciascuna
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---

# Scegliere lo schema per Customer Journey Analytics {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="Utilizzare uno schema personalizzato"
>abstract="(Consigliato) La personalizzazione dello schema consente alla tua organizzazione di tenere traccia solo di ciò che serve e di evitare il sovraccarico legato a campi disordinati e non necessari. Questa opzione include i gruppi di campi aggiunti dal Web SDK e quelli personalizzati per la tua organizzazione."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="Utilizzare lo schema predefinito"
>abstract="(Non consigliato) Lo schema di Adobe Analytics contiene più di mille campi e questo può comportare schemi complessi e disordinati. La tua organizzazione sarebbe costretta a continuare ad aderire al concetto di prop ed eVar, che è un concetto legacy non utilizzato in Customer Journey Analytics. L’integrazione con altri servizi Adobe Experience Platform è più difficile."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Durante l’aggiornamento a Customer Journey Analytics, Adobe consiglia di creare uno schema Experience Data Model (XDM) personalizzato per allinearlo meglio alle esigenze della tua organizzazione quando inizi a utilizzare altri servizi Platform. In alternativa, puoi scegliere di utilizzare lo schema Adobe Analytics esistente.

Valuta i vantaggi e gli svantaggi di ciascuno.

## Creare uno schema personalizzato su misura per la tua organizzazione (scelta consigliata)

Adobe consiglia di creare uno schema personalizzato durante l’aggiornamento a Customer Journey Analytics.

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><p>I vantaggi dell’aggiornamento al proprio schema personalizzato includono:</p><ul><li>Uno schema semplificato personalizzato in base alle esigenze dell’organizzazione e alle specifiche applicazioni di Platform che utilizzi.</li><p>Quando sono necessarie delle modifiche allo schema, non è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></ul> | <p>Gli svantaggi dell’aggiornamento al proprio schema personalizzato includono:</p><ul><li>L’aggiornamento dello schema è un processo dispendioso in termini di tempo, necessario prima di iniziare a inviare i dati a Platform.</li></ul> |

## Utilizzarte lo schema Adobe Analytics esistente

L’opzione di utilizzare lo schema Adobe Analytics esistente con Customer Journey Analytics è disponibile solo se l’implementazione Adobe Analytics è configurata con Adobe Experience Platform Web SDK. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Vantaggi | Svantaggi |
|----------|---------|
| <p>I vantaggi derivanti dall’utilizzo dello schema di Adobe Analytics includono:</p><ul><li>Facilità di aggiornamento<p>Se stai già inviando dati ad Adobe Analytics con Adobe Experience Platform Web SDK, puoi aggiungere un servizio aggiuntivo allo stream di dati per inviare dati ad Adobe Experience Platform (che potrà quindi essere utilizzato nella configurazione di Customer Journey Analytics).</p></li></ul> | <p>Gli svantaggi dell’utilizzo dello schema di Adobe Analytics includono:</p><ul><li>Sebbene l’utilizzo dello schema di Adobe Analytics non limiti in termini di come può essere utilizzato con altre applicazioni di Platform, risulta in uno schema più complesso di quanto potrebbe essere altrimenti. Questo perché lo schema di Adobe Analytics contiene molti oggetti specifici di Adobe Analytics che difficilmente verranno utilizzati dall’organizzazione.<p>Quando sono necessarie delle modifiche allo schema, è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the Customer Journey Analytics Upgrade Guide.

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
