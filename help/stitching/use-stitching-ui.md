---
title: Utilizzare l’unione
description: Come utilizzare l’unione
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: c4aea74807be15af56413522d9e6fbf5f18a37a0
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 4%

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


   Se selezioni **[!UICONTROL Identity Graph]** per l&#39;ID persona, devi selezionare uno spazio dei nomi.

   >[!NOTE]
   >
   >Devi essere autorizzato a utilizzare il grafo delle identità.
   >

   Prima di ciò, viene visualizzata una finestra di dialogo **[!UICONTROL Change to identity graph]** per verificare che [ abbia completato la configurazione del grafico delle identità per il set di dati](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) prima di utilizzare il grafico delle identità per l&#39;unione. Seleziona **[!UICONTROL Continue]** (Avanti) per continuare.

   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Namespace]**.


1. Selezionare un intervallo di lookback dal menu a discesa **[!UICONTROL Lookback window]**. Le opzioni disponibili dipendono dal pacchetto Customer Journey Analytics a cui hai diritto.

Dopo aver salvato una connessione contenente set di dati abilitati per l’unione di identità, il processo di unione per ciascun set di dati inizia all’avvio dell’acquisizione dei dati per tale set di dati.