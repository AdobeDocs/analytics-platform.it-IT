---
title: Gestire l’utilizzo del Customer Journey Analytics
description: Come gestire l’utilizzo di Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 37%

---

# Gestire l’utilizzo del Customer Journey Analytics

>[!TIP]
>
>Utilizza l&#39;interfaccia [**[!UICONTROL Usage]**](/help/connections/manage-connections.md#usage) per** visualizzare **l&#39;utilizzo delle righe acquisite e segnalabili in tutte le connessioni in Customer Journey Analytics.



È possibile gestire l&#39;utilizzo di Customer Journey Analytics nell&#39;interfaccia [**[!UICONTROL Connections]**](/help/connections/create-connection.md). In questa interfaccia è possibile definire la conservazione dei dati di Customer Journey Analytics come finestra continua in mesi (1 mese, 3 mesi, 6 mesi, ecc.), a livello di connessione.

Il vantaggio principale consiste nell’archiviare o generare rapporti solo sui dati applicabili e utili, nonché nell’eliminare i dati meno recenti che non sono più utili. Ti aiuta a rispettare i limiti del tuo contratto e riduce il rischio di sovraccosti.

Se lasci l’impostazione predefinita (non selezionata), il periodo di conservazione dei dati verrà sostituito dall’impostazione di conservazione dei dati di Adobe Experience Platform. Se disponi di 25 mesi di dati in Experience Platform, Customer Journey Analytics riceverà 25 mesi di dati tramite backfill. Eliminando10 di questi mesi in Platform, Customer Journey Analytics mantiene i restanti 15 mesi.

La conservazione dei dati si basa su marche temporali e si applica solo ai set di dati evento e ai set di dati di riepilogo. Non esiste alcuna impostazione di finestra continua per i set di dati di profilo o di ricerca, in quanto non sono disponibili marche temporali applicabili. Se la connessione include qualsiasi profilo o set di dati di ricerca, poiché sono uniti con set di dati evento, i dati vengono conservati in Customer Journey Analytics in base alle impostazioni di conservazione dei dati sui timestamp del set di dati evento.


>[!MORELIKETHIS]
>
>[Visualizza utilizzo Customer Journey Analytics](/help/connections/manage-connections.md#usage)

