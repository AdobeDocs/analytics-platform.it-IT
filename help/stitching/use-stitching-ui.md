---
title: Utilizzare l’unione
description: Come utilizzare l’unione
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 4bca14492374939cd1ea6508c774720db61a6283
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 5%

---

# Utilizzare l’unione

Puoi abilitare l’unione su uno o più set di dati evento configurati come parte della connessione. Il numero di set di dati evento che puoi abilitare per l’unione è determinato dal pacchetto Customer Journey Analytics per il quale hai concesso la licenza.

Puoi abilitare l&#39;unione come parte delle [impostazioni del set di dati](/help/connections/create-connection.md#dataset-settings) per un set di dati evento quando [crei una connessione](/help/connections/create-connection.md) o quando [modifichi una connessione](/help/connections/manage-connections.md#edit-a-connection).

Per abilitare l&#39;unione, nella sezione del set di dati evento della finestra di dialogo **[!UICONTROL Add datasets]** o **[!UICONTROL Edit dataset]**:

![Opzioni di unione identità quando si abilita l&#39;unione identità](assets/identity-stitching-ui.png)

1. Seleziona **[!UICONTROL Enable identity stitching]**.

   Se abiliti l&#39;unione per un set di dati evento esistente, la finestra di dialogo **[!UICONTROL Change Person ID]** mostra le implicazioni di una modifica dell&#39;ID persona dovuta all&#39;utilizzo dell&#39;unione. Seleziona **[!UICONTROL Continue]** (Avanti) per continuare.

   La finestra di dialogo **[!UICONTROL Enable identity stitching]** riepiloga le conseguenze dell&#39;unione di identità. Seleziona **[!UICONTROL Continue]** (Avanti) per continuare.

1. Selezionare un ID persistente dal menu a discesa **[!UICONTROL Persistent ID]**.

   Se si seleziona **[!UICONTROL Identity Map]** per l&#39;ID persistente, è necessario selezionare uno spazio dei nomi. Sono disponibili due opzioni:

   * Consenti a **[!UICONTROL Use primary identity namespace]** di utilizzare lo spazio dei nomi dell&#39;identità primaria.
   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Namespace]**.

1. Selezionare un ID persona dal menu a discesa **[!UICONTROL Person ID]**.

   Se selezioni **[!UICONTROL Identity Map]** per l&#39;ID persona, devi selezionare uno spazio dei nomi. Sono disponibili due opzioni:

   * Consenti a **[!UICONTROL Use primary identity namespace]** di utilizzare lo spazio dei nomi dell&#39;identità primaria.
   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Namespace]**.

   Se selezioni **[!UICONTROL Identity Graph]** per l&#39;ID persona, devi selezionare uno spazio dei nomi. In precedenza, veniva visualizzata una finestra di dialogo **[!UICONTROL Change to identity graph]** per verificare di aver completato la configurazione del grafo delle identità prima di utilizzare il grafo delle identità per l&#39;unione. Seleziona **[!UICONTROL Continue]** (Avanti) per continuare.

   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Namespace]**.


1. Selezionare un intervallo di lookback dal menu a discesa **[!UICONTROL Lookback window]**. Le opzioni sono **[!UICONTROL 1 day]**, **[!UICONTROL 7 days]**, **[!UICONTROL 14 days]** o **[!UICONTROL 30 days]**.
