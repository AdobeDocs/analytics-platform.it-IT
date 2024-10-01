---
description: A seconda delle autorizzazioni, puoi condividere le metriche con l’intera organizzazione, i gruppi o i singoli utenti.
title: Condividere le metriche calcolate
feature: Calculated Metrics
exl-id: b2a3e4e3-f0aa-4505-b3f5-7d9f14dc1640
source-git-commit: e07197325e992cd85b852899c2f7cef60637f532
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 6%

---

# Condividere le metriche calcolate

In [Gestione metriche calcolate](cm-manager.md) è possibile condividere le metriche calcolate. A seconda delle autorizzazioni, puoi condividere le metriche calcolate con l’intera organizzazione, i gruppi o i singoli utenti:

* **Amministratori**: gli amministratori possono condividere le metriche calcolate con l&#39;intera organizzazione, con i gruppi all&#39;interno di un&#39;organizzazione e con i singoli utenti. Consulta la [documentazione di Admin Console](https://helpx.adobe.com/it/enterprise/using/manage-products.html) per maggiori informazioni.
* **Non amministratori**: i non amministratori possono condividere solo la metrica calcolata creata e solo con singoli utenti. |

Per condividere una o più metriche calcolate:

1. In [Gestione metriche calcolate](cm-manager.md), selezionare una o più delle metriche calcolate che si desidera condividere.
1. Dalla barra delle azioni, seleziona ![Condividi](/help/assets/icons/ShareLight.svg) **[!UICONTROL Share]**.
1. Nella finestra di dialogo **[!UICONTROL Share Calculated metric]** (Crea elemento dati):

   ![Finestra di dialogo Condividi metriche calcolate](assets/share-calculated-metrics-dialog.png)

   1. (facoltativamente) utilizzare ![Cerca](/help/assets/icons/Search.svg) per *Cerca singoli utenti o gruppi* e limita l&#39;elenco di gruppi o singoli utenti con cui si desidera condividere le metriche calcolate.

   1. Selezionare una o più opzioni dalla sezione **[!UICONTROL Organization]** o **[!UICONTROL Groups]** oppure cercare e selezionare uno o più utenti. Le opzioni disponibili dipendono dal ruolo.

   1. Selezionare **[!UICONTROL Save]** per condividere le metriche calcolate. Selezionare **[!UICONTROL Cancel]** per annullare.

## Best practice

Di seguito sono riportate alcune best practice per condividere le metriche calcolate e con chi condividerle.

* In qualità di amministratore, condividi una metrica calcolata con tutti solo se sei certo che gli utenti dell’organizzazione abbiano familiarità con l’utilizzo di tale metrica. Puoi anche valutare la possibilità di favorire queste metriche calcolate. Per ulteriori informazioni, vedere [Contrassegnare una metrica calcolata come preferita](cm-favorite.md).

* In qualità di amministratore, condividi una metrica calcolata con un gruppo specifico se tale metrica fornisce valore aziendale per la parte utenti di tale gruppo.

* In qualità di amministratore o di singolo utente, condividi una metrica calcolata con uno o più utenti singoli per convalidarne una. Se i filtri non si rivelano utili, puoi eliminare la metrica calcolata.


<!--

Depending on your permissions, you can share metrics with your whole organization, groups, or individual users.

|  Role | Permissions |
|---|---|
|  Administrator  | Can share metrics with All, with Groups, and with Users. Groups are set up as permission groups in the Admin console.  |
|  Non-Administrator  | Can share metrics only with individual users.  |

To share a calculated metric:

1. In the Calculated metrics manager, mark the checkbox next to the metric you want to share.

   ![Calculated metrics manager showing the available icons across the top of the window including Hide Filters, Tag, Share, Delete, and Copy.](assets/cm_task_bar.png)

1. Select the **[!UICONTROL Share]** icon. ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

   The Share Calculated metric dialog box displays.

   ![Share Calculated metric window with All selected for the Organization.](assets/cm_share.png)

1. Select **[!UICONTROL Share]**.

1. Choose who you want to share with:

   * **[!UICONTROL All]** (Administrators only): Shares with all users in the organization.

     Consider sharing with all only if it's of use to the entire company and everyone is comfortable using it. In this case, you should also consider making it an [approved metric](/help/components/calc-metrics/cm-workflow/cm-approving.md).
   
   * **[!UICONTROL Groups]** (Administrators only): Select any groups you want to share with.

     Consider sharing with a group if the metric provides good business value for that team.
   
   * **[!UICONTROL Individual users]**: Search for and select the individual users you want to share with.

      This is the only share option available to all users. Administrators might want to use this option to vet and validate a metric prior to making it available to a group or to everyone. If the metric isn't useful, it can be discarded. Administrators should not officially approve this type of metric.

1. Select **[!UICONTROL Share]**.

   The Shared icon appears next to the metric: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg).

1. You can filter on metrics shared with you by going to **[!UICONTROL Filters]** > **[!UICONTROL Other Filters]** > **[!UICONTROL Shared with Me]**.

1. (Optional) To filter the list of calculated metrics in the Calculated metrics manager to show only metrics that are shared with you, select the **Filter** icon, expand **[!UICONTROL Other filters]**, then select **[!UICONTROL Shared with me]**.

-->