---
title: Selezionare Una Visualizzazione Dati In Report Builder
description: Scopri come selezionare una visualizzazione dati in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
TQID: https://experienceleague.adobe.com/auDJxQ6x6fqNVbDuN9reSffP9iUISZ7QgEflGWApc8A
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 1%

---

# Selezionare una visualizzazione dati

Puoi selezionare una visualizzazione dati dal menu a discesa o selezionare una visualizzazione dati da una cella e aggiornare automaticamente il blocco dati con una nuova visualizzazione dati.

## Selezionare una visualizzazione dati da una cella

La selezione di una visualizzazione dati da una cella semplifica l’aggiornamento dei blocchi di dati utilizzando diverse visualizzazioni dati. Invece di creare rapporti completamente nuovi con blocchi di dati separati, puoi aggiornare i blocchi di dati con una visualizzazione dati selezionata da una cella.

La selezione di una visualizzazione dati da una cella è utile quando:

* Visualizzazioni dati multiple simili o identiche nella struttura.
* Formati di blocchi di dati complessi che includono componenti e layout personalizzati.

Per selezionare una visualizzazione dati da una cella, crea innanzitutto un blocco di dati e assegna più visualizzazioni dati a una cella all’esterno del blocco di dati. Quindi, utilizza la **[!UICONTROL visualizzazione dati dalla cella]** per aggiornare i blocchi di dati da diverse visualizzazioni dati.

1. Crea un blocco di dati. Per informazioni sulla creazione di un blocco di dati, vedere [Creare un blocco di dati](/help/report-builder/create-a-data-block.md).

1. Selezionare ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) in **[!UICONTROL Visualizzazioni dati]**.

1. Selezionare una cella utilizzando ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) all&#39;esterno del blocco di dati.

1. Aggiungere una o più visualizzazioni dati da **[!UICONTROL Selezionare le visualizzazioni dati da aggiungere alla visualizzazione dati dalla cella]** tramite trascinamento della selezione. In alternativa, puoi selezionare due volte una visualizzazione dati per aggiungerla all&#39;elenco **[!UICONTROL Visualizzazioni dati incluse]**.

   * Puoi usare ![Cerca](/help/assets/icons/Search.svg) **[!UICONTROL _Seleziona visualizzazioni dati_]** per cercare le visualizzazioni dati.
   * Utilizza ![MoreSmall](/help/assets/icons/MoreSmall.svg) per aprire un menu di scelta rapida in modo da poter spostare le visualizzazioni dati verso l&#39;alto o verso il basso nell&#39;elenco **[!UICONTROL Visualizzazioni dati incluse]**.
   * Utilizza ![CrossSize75](/help/assets/icons/CrossSize75.svg) per eliminare una visualizzazione dati dall&#39;elenco **[!UICONTROL Visualizzazioni dati incluse]**.

   ![Seleziona visualizzazione dati da una cella](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Selezionare **[!UICONTROL Applica]** per applicare le visualizzazioni dati selezionate alla cella selezionata.


## Modificare la visualizzazione dati da una cella

1. Selezionare la posizione della cella della visualizzazione dati nel foglio.
1. Nell&#39;hub Report Builder, selezionare il collegamento **[!UICONTROL Visualizzazioni dati dalla cella]** in **[!UICONTROL Modifica rapida]**.
1. Selezionare una visualizzazione dati dal menu a discesa **[!UICONTROL Visualizzazione dati]**.

   ![Modifica visualizzazione dati da una cella](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Facoltativo, selezionare **[!UICONTROL Aggiorna blocchi di dati in caso di modifica]**.

1. Seleziona **[!UICONTROL Applica]**. Report Builder aggiorna il blocco di dati in base alla visualizzazione dati selezionata.
