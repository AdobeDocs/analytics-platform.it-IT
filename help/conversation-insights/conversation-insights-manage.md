---
title: Gestione configurazione approfondimenti conversazione
description: Scopri come gestire le configurazioni di Informazioni sulla conversazione.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 6%
---
# Gestione configurazioni

Dopo aver [creato le configurazioni di Informazioni sulla conversazione](/help/conversation-insights/conversation-insights-configure.md), puoi visualizzare, modificare o eliminare queste configurazioni.

Solo gli amministratori di sistema possono gestire le configurazioni di Informazioni sulla conversazione.

Per informazioni su Informazioni sulla conversazione, vedere [Panoramica su Informazioni sulla conversazione](/help/conversation-insights/conversation-insights-overview.md).

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
1. Utilizza la finestra di dialogo [**[!UICONTROL Crea configurazione]**](./conversation-insights-configure.md) per configurare gli approfondimenti sulla conversazione.

## Modificare una configurazione

Per modificare una configurazione esistente di Informazioni sulla conversazione:

1. Esegui una delle operazioni seguenti:

   * Seleziona il nome della configurazione da modificare.
   * Seleziona la casella di controllo accanto alla configurazione da modificare, quindi seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]** dalla barra delle azioni blu.
   * Seleziona ![Altro](/help/assets/icons/More.svg) per la configurazione da modificare. Dal menu di scelta rapida selezionare ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica]**.

1. Utilizza la finestra di dialogo [**[!UICONTROL Configurazione / _nome della configurazione_]**](./conversation-insights-configure.md) per configurare gli approfondimenti sulla conversazione.

## Eliminare una configurazione

Per eliminare una configurazione esistente di Informazioni sulla conversazione:

1. Esegui una delle operazioni seguenti:

   * Seleziona la casella di controllo accanto alla configurazione da eliminare, quindi seleziona ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]** dalla barra blu delle azioni.
   * Seleziona ![Altro](/help/assets/icons/More.svg) per la configurazione da modificare. Dal menu di scelta rapida selezionare ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]**.

1. Nella finestra di dialogo **[!UICONTROL Elimina configurazione]**, seleziona **[!UICONTROL Elimina]** per eliminare la configurazione. Seleziona **[!UICONTROL Annulla]** per annullare.
