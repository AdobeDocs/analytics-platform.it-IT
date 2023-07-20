---
title: AAID, ECID, AACUSTOMID e il connettore di origine di Analytics
description: Scopri in che modo il connettore di origine di Analytics si occupa dei campi di identità di Adobe Analytics.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 73%

---

# AAID, ECID, AACUSTOMID e il connettore di origine di Analytics

I dati di Adobe Analytics contengono più campi di identità. Tre importanti campi di identità sono trattati in modo particolare [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it): AAID, ECID, AACUSTOMID.

## AAID

Adobe Analytics ID (AAID) è l’identificatore primario del dispositivo in Adobe Analytics e la sua esistenza è garantita su ogni evento trasmesso attraverso il connettore di origine di Analytics. AAID viene talvolta indicato come “ID legacy di Analytics” o ID cookie `s_vi`. Tuttavia, viene creato un AAID anche se il cookie `s_vi` non è presente. AAID è rappresentato dalle colonne `post_visid_high/post_visid_low` nei [feed dati di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it#columns%2C-descriptions%2C-and-data-types).

Nel connettore di origine di Analytics, AAID viene trasformato in `HEX(post_visid_high) + "-" + HEX(post_visid_low)`. Il campo AAID di un dato evento contiene una singola identità che può corrispondere a uno dei diversi tipi descritti in [Ordine delle operazioni per gli ID di Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=it%5B%5D). All’interno di un’intera suite di rapporti, AAID può contenere diversi tipi in tutti gli eventi. Il tipo di ogni evento è indicato nella `post_visid_type` nei feed dati di Analytics.) Vedi anche [Data column reference](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it) (Riferimento delle colonne di dati).

## ECID

ECID (Experience Cloud ID), talvolta indicato anche come MCID (Marketing Cloud ID), è un campo separato dell’identificatore del dispositivo che viene popolato in Adobe Analytics quando Analytics viene implementato utilizzando il [servizio Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=it). ECID è rappresentato dalla colonna `mcvisid` nei feed dati di Adobe Analytics.

Se su un evento esiste un ECID, AAID può essere basato su ECID a seconda che il [periodo di tolleranza](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=it) di Analytics sia configurato o meno. Vedi anche [Richieste Analytics ed Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=it).

## AACUSTOMID

AACUSTOMID è un campo separato dell’identificatore che viene popolato in Adobe Analytics in base all’utilizzo della variabile `s.VisitorID` nell’implementazione di Analytics. AACUSTOMID è rappresentato dalla colonna `cust_visid` nei feed dati di Adobe Analytics. Se AACUSTOMID è presente, AAID sarà basato su AACUSTOMID. AACUSTOMID surclassa tutti gli altri identificatori come definito dall’ordine delle operazioni menzionato in precedenza.

## Trattamento delle identità da parte del connettore di origine di Analytics

Il connettore di origine di Analytics trasmette queste identità a Adobe Experience Platform in formato XDM come:

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

Questi campi non sono contrassegnati come identità. Le stesse identità vengono invece copiate in **_identityMap_** di XDM come coppie di valori chiave come segue:

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

Gli elementi tra parentesi &lt;> rappresentano i luoghi in cui apparirebbero i valori effettivi.

All’interno di identityMap:

* Se ECID è presente, viene contrassegnato come identità primaria dell’evento. In questo caso AAID può essere basato su ECID come da spiegazione precedente.
In caso contrario, AAID è contrassegnato come identità primaria dell’evento.
* AACUSTOMID non viene mai contrassegnato come ID primario dell’evento. Tuttavia, se AACUSTOMID è presente, AAID è basato su AACUSTOMID come da spiegazione precedente.

## ID Customer Journey Analytics e primario

Per quanto riguarda il Customer Journey Analytics, la definizione dell’ID primario è importante solo se decidi di utilizzare l’ID primario come ID persona. Tuttavia, non è obbligatorio: puoi scegliere un’altra colonna di identità come ID persona.
