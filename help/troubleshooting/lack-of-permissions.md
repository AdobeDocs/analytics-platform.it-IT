---
title: Mancanza di autorizzazioni
description: Scopri come risolvere i problemi derivanti dalla mancanza di autorizzazioni
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 1905e37b76843a7622af4e874a2d74aceff55384
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 10%

---


# Mancanza di autorizzazioni

Il Customer Journey Analytics non funziona correttamente quando non sono presenti determinate autorizzazioni Adobe Experience Platform.

Ad esempio, dopo aver creato un’ [Connessione](../connections/overview.md) e [Visualizzazione dati](../data-views/data-views.md), è possibile che venga visualizzato il seguente messaggio di errore nel [Componenti](/help/data-views/create-dataview.md#components) sezione:


>[!BEGINSHADEBOX]

*[!UICONTROL Something went wrong and we couldn't load schema fields. Please try again.]*

>[!ENDSHADEBOX]


Per correggere questo errore, è necessario disporre dei privilegi di amministratore di sistema o di prodotto per un&#39;organizzazione che dispone di un prodotto di Experience Platform. Consulta [Panoramica sul controllo degli accessi](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) per ulteriori informazioni.

1. Passa all’interfaccia utente di Adobe Experience Platform.

1. Seleziona **[!UICONTROL Permissions]** (Flusso di pubblicazione) nella barra a sinistra.

1. Seleziona **[!UICONTROL Roles]**.

1. Passa al ruolo pertinente.

1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Edit]** per modificare il ruolo.

1. Assicurare **[!UICONTROL Manage Data Usage Policies]** e **[!UICONTROL View Data Usage Policies]** sono aggiunti al **[!UICONTROL Data Governance]** contenitore.

1. Seleziona **[!UICONTROL Save]** per salvare le modifiche.


