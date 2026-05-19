---
title: Mancanza di autorizzazioni
description: Scopri come risolvere i problemi derivanti dalla mancanza di autorizzazioni
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
autotag-review: '2026-05-19T09:32:28.410Z'
TQID: 'https://experienceleague.adobe.com/qGrpX20MMcrjeEO75K2Ndoki4eiDmEvmaUCzED8jR1w'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 75%

---

# Mancanza di autorizzazioni

Customer Journey Analytics non funziona correttamente quando non sono presenti determinate autorizzazioni di Adobe Experience Platform.

Ad esempio, dopo la creazione di [Connessione](../connections/overview.md) e [Visualizzazione dati](../data-views/data-views.md), nella sezione [Componenti](/help/data-views/create-dataview.md#components), è possibile che venga visualizzato il seguente messaggio di errore:


>[!BEGINSHADEBOX]

*[!UICONTROL Si è verificato un errore durante il recupero dei criteri DULE. Verifica le autorizzazioni, i criteri o le etichette dell’account. Messaggio: Non consentito.]*

>[!ENDSHADEBOX]


1. Assicurati di disporre del controllo degli accessi corretto:

   * È necessario disporre dei privilegi di amministratore di sistema o di prodotto per un&#39;organizzazione che dispone di un prodotto Experience Platform. Per ulteriori informazioni, consulta [Panoramica sul controllo degli accessi](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it#platform-permissions).

   * Devi essere un utente nel profilo di prodotto AEP-Default-All-Users. Se non disponi delle autorizzazioni necessarie per aggiungerti a questo profilo, rivolgiti al tuo amministratore. Per ulteriori informazioni, consulta [Flusso di lavoro e gerarchia di controllo degli accessi](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it#access-control-hierarchy-and-workflow).


1. Passa all&#39;interfaccia utente di Adobe Experience Platfom.

1. Seleziona **[!UICONTROL Autorizzazioni]** dalla barra a sinistra.

1. Seleziona **[!UICONTROL Ruoli]**.

1. Passa al ruolo pertinente.

1. Seleziona ![Modifica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Modifica]** per modificare il ruolo.

1. Accertati che **[!UICONTROL Gestisci criteri utilizzo dati]** e **[!UICONTROL Visualizza criteri utilizzo dati]** siano aggiunti al contenitore **[!UICONTROL Governance dati]**.

1. Seleziona **[!UICONTROL Salva]** per salvare le modifiche.
