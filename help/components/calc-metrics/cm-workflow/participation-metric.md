---
description: Con il generatore di metriche calcolate, chiunque può creare una metrica di partecipazione.
title: Metrica di partecipazione
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 5fbffb01c08b5f8069b2670742f7ae3836ad8357
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 0%

---

# Creare una metrica di &quot;partecipazione&quot;

Le informazioni seguenti spiegano come creare una metrica che mostra quali pagine hanno contribuito (o partecipato) alle visite che contenevano un ordine.

Questo tipo di informazioni potrebbe essere utile per qualsiasi proprietario di contenuto.

>[!NOTE]
>
>Puoi abilitare le metriche di partecipazione negli Strumenti di amministrazione, ma solo per gli eventi personalizzati da 1 a 100.

1. Inizia a creare una metrica, come descritto in [Creare metriche](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Nel generatore di metriche calcolate, denomina la metrica &quot;Partecipazione&quot; o qualcosa di simile.
1. Trascina l’evento di successo &quot;Ordini&quot; nell’area di lavoro Definizione.
1. Modificare il [modello di attribuzione](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) di tale evento a **[!UICONTROL Participation]** sotto **[!UICONTROL Settings]** ingranaggio. Seleziona **[!UICONTROL Visit]** lookback. La definizione deve essere simile alla seguente:

   ![](assets/participation.png)

1. Seleziona [!UICONTROL **Salva**] per salvare la metrica.
1. Utilizzare la metrica calcolata in una **[!UICONTROL Pages]** rapporto.

   ![](assets/participation-pages.png)

1. (Facoltativo) Condividi la metrica con altri utenti dell’organizzazione.
