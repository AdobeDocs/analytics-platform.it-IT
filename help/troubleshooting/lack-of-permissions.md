---
title: Mancanza di autorizzazioni
description: Scopri come risolvere i problemi derivanti dalla mancanza di autorizzazioni
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '160'
ht-degree: 100%

---

# Mancanza di autorizzazioni

Customer Journey Analytics non funziona correttamente quando non sono presenti determinate autorizzazioni di Adobe Experience Platform.

Ad esempio, dopo la creazione di [Connessione](../connections/overview.md) e [Visualizzazione dati](../data-views/data-views.md), nella sezione [Componenti](/help/data-views/create-dataview.md#components), è possibile che venga visualizzato il seguente messaggio di errore:


>[!BEGINSHADEBOX]

*[!UICONTROL Something went wrong retrieving DULE policies. Please verify account permissions, policies, or labels. Message: Forbidden.]*

>[!ENDSHADEBOX]


1. Assicurati di disporre del controllo degli accessi corretto:

   * È necessario disporre dei privilegi di amministratore di sistema o di prodotto per un&#39;organizzazione che dispone di un prodotto Experience Platform. Per ulteriori informazioni, consulta [Panoramica sul controllo degli accessi](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it#platform-permissions).

   * Devi essere un utente nel profilo di prodotto AEP-Default-All-Users. Se non disponi delle autorizzazioni necessarie per aggiungerti a questo profilo, rivolgiti al tuo amministratore. Per ulteriori informazioni, consulta [Flusso di lavoro e gerarchia di controllo degli accessi](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it#access-control-hierarchy-and-workflow).


1. Passa all&#39;interfaccia utente di Adobe Experience Platfom.

1. Seleziona **[!UICONTROL Permissions]** nella barra a sinistra.

1. Seleziona **[!UICONTROL Roles]**.

1. Passa al ruolo pertinente.

1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** per modificare il ruolo.

1. Assicurati che **[!UICONTROL Manage Data Usage Policies]** e **[!UICONTROL View Data Usage Policies]** siano aggiunti al contenitore di **[!UICONTROL Data Governance]**.

1. Seleziona **[!UICONTROL Save]** per salvare le modifiche.
