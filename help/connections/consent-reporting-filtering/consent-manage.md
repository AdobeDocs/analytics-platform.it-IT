---
title: Gestire le configurazioni di reporting e filtro del consenso
description: Scopri come visualizzare, modificare ed eliminare le configurazioni di reporting e filtro del consenso e come il set di dati di ricerca dei criteri di consenso rimane sincronizzato in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# Gestione delle configurazioni di reporting e filtro del consenso

Dopo aver [creato una configurazione di reporting e filtro del consenso](/help/connections/consent-reporting-filtering/consent-configure.md), puoi visualizzarla, modificarla o eliminarla.

Solo gli amministratori di sistema possono gestire le configurazioni di reporting e filtro del consenso.

Per informazioni generali, consulta [Panoramica sui rapporti di consenso e filtri](/help/connections/consent-reporting-filtering/consent-overview.md).

## Visualizza configurazioni esistenti

Per visualizzare le configurazioni esistenti:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Generazione rapporti di consenso e filtro]**.

   Per ogni configurazione sono disponibili le seguenti colonne di informazioni:

   * **[!UICONTROL Creato da]**: utente che ha creato la configurazione.

   * **[!UICONTROL Sandbox]**: la sandbox di Experience Platform che contiene il set di dati profilo.

   * **[!UICONTROL Connessione]**: la connessione a cui è applicata la configurazione.

   * **[!UICONTROL Filtro]**: azioni di marketing per le quali è abilitato il filtro, se presenti.

   * **[!UICONTROL Data di creazione]**: la data di creazione della configurazione.

   * **[!UICONTROL Ultima modifica]**: data dell&#39;ultima modifica della configurazione.

   * **[!UICONTROL Stato]**: lo stato della configurazione.

   È possibile nascondere le colonne selezionando l&#39;icona Colonna ![icona Colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), deselezionando le colonne che si desidera nascondere, quindi selezionando **[!UICONTROL Applica]**.

1. (Facoltativo) Per filtrare l&#39;elenco delle configurazioni, selezionare l&#39;icona **Filtro** ![Filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), quindi filtrare in base a uno dei criteri seguenti:

   * **[!UICONTROL Connessione]**

   * **[!UICONTROL Creato da]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Stato]**

## Modificare una configurazione

>[!IMPORTANT]
>
>Le modifiche apportate al filtro interessano solo i dati acquisiti dopo il salvataggio delle modifiche apportate alla configurazione. L’abilitazione del filtro non rimuove i dati dei visitatori non consenzienti acquisiti prima della modifica e la disabilitazione del filtro non recupera i dati esclusi durante l’abilitazione del filtro.

Per modificare una configurazione esistente:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Generazione rapporti di consenso e filtro]**.

1. Seleziona il nome della configurazione da modificare.

   Oppure

   Seleziona la casella di controllo accanto alla configurazione da modificare, quindi seleziona **[!UICONTROL Modifica]**.

1. Apporta le modifiche, quindi seleziona **[!UICONTROL Salva]**.

## Eliminare una configurazione

Per eliminare una configurazione esistente:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Generazione rapporti di consenso e filtro]**.

1. Selezionare la casella di controllo accanto alla configurazione da eliminare, quindi selezionare **[!UICONTROL Elimina]**.

## Come il set di dati di ricerca dei criteri di consenso rimane sincronizzato

Customer Journey Analytics mantiene automaticamente sincronizzato il set di dati di ricerca dei criteri di consenso con Experience Platform. Quando un criterio di consenso viene creato, aggiornato, rinominato o eliminato in Experience Platform, il nome del criterio e la descrizione corrispondenti nel set di dati di ricerca vengono aggiornati.

Considera quanto segue:

* Esiste un massimo di un set di dati di ricerca dei criteri di consenso per sandbox. Più configurazioni nello stesso set di dati di ricerca condividono tale set di dati.
* Poiché i nomi e le descrizioni dei criteri provengono da Experience Platform, aggiorna i metadati dei criteri in Experience Platform anziché modificare direttamente il set di dati di ricerca.
