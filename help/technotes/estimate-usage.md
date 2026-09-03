---
title: Gestire l’utilizzo del Customer Journey Analytics
description: Come gestire l’utilizzo di Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
autotag-review: '2026-05-19T09:30:13.855Z'
TQID: 'https://experienceleague.adobe.com/SWjkycY-YwNFMXRXwBypDtTL2ffFn40-Fp88vSxv-74'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: b3197353-f189-4932-8378-3f3bc40e6071id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 37%

---

# Gestire l’utilizzo del Customer Journey Analytics

>[!TIP]
>
>Utilizza l&#39;interfaccia [**[!UICONTROL Usage ]**](/help/connections/manage-connections.md#usage) per** visualizzare **l&#39;utilizzo delle righe acquisite e segnalabili in tutte le connessioni in Customer Journey Analytics.



Puoi gestire l&#39;utilizzo di Customer Journey Analytics nell&#39;interfaccia [**[!UICONTROL Connessioni ]**](/help/connections/create-connection.md). In questa interfaccia è possibile definire la conservazione dei dati di Customer Journey Analytics come finestra continua in mesi (1 mese, 3 mesi, 6 mesi, ecc.), a livello di connessione.

Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.

Se lasci l’impostazione predefinita (non selezionata), il periodo di conservazione dei dati verrà sostituito dall’impostazione di conservazione dei dati di Adobe Experience Platform. Se disponi di 25 mesi di dati in Experience Platform, Customer Journey Analytics riceverà 25 mesi di dati tramite backfill. Eliminando10 di questi mesi in Platform, Customer Journey Analytics mantiene i restanti 15 mesi.

La conservazione dei dati si basa su marche temporali e si applica solo ai set di dati evento e ai set di dati di riepilogo. Non esiste alcuna impostazione di finestra continua per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Se la connessione include qualsiasi profilo o set di dati di ricerca, poiché sono uniti con set di dati evento, i dati vengono conservati in Customer Journey Analytics in base alle impostazioni di conservazione dei dati sui timestamp del set di dati evento.


>[!MORELIKETHIS]
>
>[Visualizza utilizzo Customer Journey Analytics](/help/connections/manage-connections.md#usage)

