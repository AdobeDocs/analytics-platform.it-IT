---
title: Gestione configurazione approfondimenti conversazione
description: Scopri come gestire le configurazioni di Informazioni sulla conversazione.
solution: Customer Journey Analytics
feature: AI Tools
role: Admin, User
autotag-review: '2026-10-02T07:03:36.851Z'
TQID: 'https://experienceleague.adobe.com/D2nrhtN2SaHoAw0PU7yJtabvx-q0L5FHtBFu1sORfaI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: d7a261eb-f9ac-4dd6-bd60-1637efcd3d36
    internal-label: ''
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: b58d1768aef87f01bb3c20b01102d08a17e973ef
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 6%
---
# Gestione configurazioni

Dopo aver [creato le configurazioni di Informazioni sulla conversazione](/help/conversation-insights/configure.md), puoi visualizzare, modificare o eliminare queste configurazioni.

Solo gli amministratori di sistema possono gestire le configurazioni di Informazioni sulla conversazione.

Per informazioni su Informazioni sulla conversazione, vedere [Panoramica su Informazioni sulla conversazione](/help/conversation-insights/overview.md).


## Visualizzare e filtrare le configurazioni esistenti

Per visualizzare le configurazioni esistenti di Informazioni sulla conversazione:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Configurazione approfondimenti conversazione]**.

   ![Panoramica sulle configurazioni di Informazioni sulla conversazione](assets/conversation-insights-configurations.png)

   Per ogni configurazione sono disponibili le seguenti colonne di informazioni:

   * **[!UICONTROL Nome]**: nome della configurazione di Informazioni sulla conversazione.
   * **[!UICONTROL Creato da]**: utente che ha creato la configurazione.

   * **[!UICONTROL Sandbox]**: la sandbox di Experience Platform che contiene il set di dati del profilo aggiunto alla connessione.

   * **[!UICONTROL Connessione]**: la connessione aggiunta alla configurazione.

   * **[!UICONTROL Data di creazione]**: la data e l&#39;ora di creazione della configurazione.

   * **[!UICONTROL Ultima modifica]**: data dell&#39;ultima modifica della configurazione.

   * **[!UICONTROL Stato]**: lo stato della configurazione. I valori possibili sono:
     ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**, ![StatusBlue](/help/assets/icons/StatusBlue.svg) **[!UICONTROL Pending]** o ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Non riuscito]**.

   Per configurare le colonne da visualizzare nella tabella, selezionare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). Nella finestra di dialogo **[!UICONTROL Personalizza tabella]**, seleziona le colonne da visualizzare. Quindi selezionare **[!UICONTROL Applica]**.

1. (Facoltativo) Per filtrare l&#39;elenco delle configurazioni, selezionare ![Filtra](/help/assets/icons/Filter.svg), quindi filtrare in base a uno dei seguenti criteri:

   * **[!UICONTROL Connessione]**

   * **[!UICONTROL Creato da]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Stato]**

## Creare una configurazione

Per creare una nuova configurazione di Informazioni sulla conversazione:

1. Selezionare **[!UICONTROL Crea configurazione]**.
1. Utilizza la finestra di dialogo [**[!UICONTROL Crea configurazione]**](./configure.md) per configurare gli approfondimenti sulla conversazione.

## Modificare una configurazione

Per modificare una configurazione esistente di Informazioni sulla conversazione:

1. Esegui una delle operazioni seguenti:

   * Seleziona il nome della configurazione da modificare.
   * Seleziona la casella di controllo accanto alla configurazione da modificare, quindi seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]** dalla barra delle azioni blu.
   * Seleziona ![Altro](/help/assets/icons/More.svg) per la configurazione da modificare. Dal menu di scelta rapida selezionare ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]**.

1. Utilizza la finestra di dialogo [**[!UICONTROL Configurazione / _nome della configurazione_]**](./configure.md) per gestire gli approfondimenti sulla conversazione.

## Eliminare una configurazione

Per eliminare una configurazione esistente di Informazioni sulla conversazione:

1. Esegui una delle operazioni seguenti:

   * Seleziona la casella di controllo accanto alla configurazione da eliminare, quindi seleziona ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]** dalla barra blu delle azioni.
   * Seleziona ![Altro](/help/assets/icons/More.svg) per la configurazione da modificare. Dal menu di scelta rapida selezionare ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]**.

1. Nella finestra di dialogo **[!UICONTROL Elimina configurazione]**, seleziona **[!UICONTROL Elimina]** per eliminare la configurazione. Seleziona **[!UICONTROL Annulla]** per annullare.
