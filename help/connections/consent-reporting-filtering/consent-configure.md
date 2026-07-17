---
title: Configurare reporting e filtro del consenso
description: Scopri come utilizzare la procedura guidata di provisioning per abilitare i rapporti sul consenso e i filtri facoltativi in fase di acquisizione per una connessione in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 728
ht-degree: 1%

---

# Configurare i rapporti e i filtri di consenso

Gli amministratori di sistema possono abilitare la segnalazione del consenso e, facoltativamente, il filtro del consenso per una o più connessioni. Per informazioni generali, consulta [Panoramica sui rapporti di consenso e filtri](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>Il filtro del consenso esclude i dati dei visitatori non consentiti al momento del caricamento. I dati esclusi dal filtro non vengono memorizzati in Customer Journey Analytics e non possono essere recuperati per le date passate. Rivedi attentamente le selezioni delle azioni di marketing prima di abilitare il filtro.

## Creare una configurazione

Quando crei una configurazione per la generazione di rapporti e il filtro del consenso, seleziona la sandbox e il set di dati profilo che contengono i dati di iscrizione ai criteri di consenso, scegli la connessione o le connessioni da configurare e scegli se filtrare i dati per ogni azione di marketing. Customer Journey Analytics crea quindi automaticamente il set di dati di ricerca dei criteri di consenso e i componenti dei criteri di consenso.

Per creare una configurazione di reporting e filtro del consenso:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Generazione rapporti di consenso e filtro]**.

1. Selezionare **[!UICONTROL Crea configurazione]**.

1. Nella sezione **[!UICONTROL Dettagli]**, specifica le seguenti informazioni:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL Nome]** | Specifica un nome per la configurazione. |
   | **[!UICONTROL Sandbox]** | Seleziona la sandbox di Experience Platform che contiene il set di dati Profilo con i dati di iscrizione al criterio di consenso. <p>Esiste un massimo di un set di dati di ricerca dei criteri di consenso per sandbox. Più configurazioni nella stessa sandbox condividono lo stesso set di dati di ricerca.</p> |

1. Nella sezione **[!UICONTROL Set di dati profilo]**, seleziona il set di dati profilo che contiene i dati di appartenenza ai criteri di consenso (campo `consentPoliciesIDMap`) su cui desideri creare un rapporto. Quando abiliti la segnalazione del consenso, questo set di dati profilo viene aggiunto alla connessione selezionata, se non ne fa già parte.

1. Nella sezione **[!UICONTROL Connessione]**, seleziona **[!UICONTROL Seleziona una connessione]**, seleziona la casella di controllo accanto a una o più connessioni da configurare, quindi seleziona **[!UICONTROL Usa connessione]**.

   La generazione di rapporti e i filtri di consenso vengono applicati a livello di connessione. Tutte le visualizzazioni dati in una connessione configurata ereditano lo stesso comportamento.

1. Nella sezione **[!UICONTROL Visualizzazioni dati]**, fai clic su **[!UICONTROL Seleziona visualizzazioni dati]**.

1. Nella finestra di dialogo Visualizzazioni dati, seleziona la casella di controllo accanto a una o più visualizzazioni dati che desideri utilizzare per la segnalazione del consenso. Queste visualizzazioni dati vengono configurate automaticamente con i dati di consenso di Experience Platform per il reporting.

1. Selezionare **[!UICONTROL Usa visualizzazioni dati]**.

1. (Facoltativo) Nella sezione **[!UICONTROL Filtro]**, puoi abilitare il filtro per le seguenti azioni di marketing:

   >[!NOTE]
   >
   >Quando il filtro per un&#39;azione di marketing è abilitato, Customer Journey Analytics acquisisce i dati di un visitatore solo se il visitatore corrisponde a **tutti** i criteri di consenso che si applicano a tale azione di marketing. Per ulteriori informazioni, vedere [Filtro del consenso](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) in [Panoramica sui report e i filtri del consenso](/help/connections/consent-reporting-filtering/consent-overview.md).

   | Azione di marketing | Descrizione |
   |---------|----------|
   | **[!UICONTROL Analytics]** | Filtra i dati utilizzati per il reporting standard di Customer Journey Analytics in Analysis Workspace. |
   | **[!UICONTROL Data science]** | Filtra i dati utilizzati per casi di utilizzo di analisi avanzate, apprendimento automatico e data science. |

1. Seleziona **[!UICONTROL Crea]** per creare la configurazione.

   Se hai abilitato la generazione rapporti, Customer Journey Analytics automaticamente:

   * Aggiunge il set di dati profilo selezionato alla connessione.
   * Crea un set di dati di ricerca dei criteri di consenso per la sandbox (se non ne esiste già uno) e sincronizza i nomi e le descrizioni dei criteri da Experience Platform.
   * Aggiunge i componenti dei criteri di consenso (dimensioni, metriche e un campo derivato) alle visualizzazioni dati all’interno della connessione configurata.

1. Al termine della configurazione, [visualizza i componenti dei criteri di consenso nella visualizzazione dati](#view-consent-policy-components-in-the-data-view) per verificare che siano disponibili.

## Visualizzare i componenti dei criteri di consenso nella visualizzazione dati

Dopo aver [creato una configurazione](#create-a-configuration), puoi verificare che i componenti dei criteri di consenso siano stati aggiunti alle visualizzazioni dati nella connessione configurata.

Per visualizzare i componenti del criterio di consenso nella visualizzazione dati, devi essere un amministratore del profilo di prodotto per il profilo di prodotto a cui è assegnata la visualizzazione dati. Per ulteriori informazioni, vedere [Controllo degli accessi](/help/technotes/access-control.md).

Per visualizzare i componenti del criterio di consenso nella visualizzazione dati:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Visualizzazioni dati]**.

1. Apri una visualizzazione dati associata alla connessione configurata.

1. Nella sezione **[!UICONTROL Dimensions]** (Dimensioni), ora dovrebbero essere disponibili le seguenti dimensioni:

   * **[!UICONTROL ID criterio di consenso]**

   * **[!UICONTROL Nome criterio]**

   * **[!UICONTROL Descrizione criterio]**

1. Nella sezione **[!UICONTROL Metriche]** dovrebbero essere disponibili le metriche seguenti:

   * **[!UICONTROL Visitatori con consenso]**

   * **[!UICONTROL Eventi con consenso]**

   * **[!UICONTROL Criteri di consenso univoci]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. Utilizza i componenti del criterio di consenso in Analysis Workspace.

   Gli utenti che hanno accesso alla visualizzazione dati in Analysis Workspace ora possono vedere i nuovi componenti e utilizzarli nelle loro analisi. Per informazioni su come utilizzare i componenti dei criteri di consenso in Analysis Workspace, consulta [Analizzare i dati dei criteri di consenso](/help/connections/consent-reporting-filtering/consent-analyze.md).
