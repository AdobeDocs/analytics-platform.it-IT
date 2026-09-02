---
title: Configurare reporting e filtro del consenso
description: Scopri come creare una configurazione per abilitare i rapporti sul consenso e i filtri facoltativi in fase di acquisizione per una connessione in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 4661a066f90991e6fb149c6909ef4a9f75cf02ac
workflow-type: tm+mt
source-wordcount: 1326
ht-degree: 10%

---

# Configurare i rapporti e i filtri di consenso {#configure-consent-reporting}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-merge-policy"
>title="Criteri di unione"
>abstract="I criteri di unione combinano dati di profilo da più set di dati in profili cliente unificati utilizzati per la creazione del pubblico. Selezionare il criterio di unione corrispondente al set di dati profilo contenente i dati di appartenenza ai criteri di consenso (campo `consentPoliciesIDMap`) che si desidera includere nel rapporto. In alternativa, consulta il team di dati per scoprire quali tipi di pubblico sono associati a ciascun criterio di unione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-sandbox"
>title="Sandbox"
>abstract="Seleziona la sandbox che contiene i set di dati di profilo di Experience Platform corretti. Questi set di dati devono contenere i dati sul consenso che desideri segnalare in Analysis Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-person-id"
>title="ID persona"
>abstract="Seleziona un campo dallo schema basato su modello che rappresenta l’ID persona. La selezione è limitata all’elenco dei campi nello schema contrassegnati come &quot;Identity&quot; e che hanno uno spazio dei nomi dell’identità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-identity-namespace"
>title="Utilizza lo spazio dei nomi identità primaria"
>abstract="Abilita questa opzione se desideri che Customer Journey Analytics trovi l’identità in Identity Map contrassegnata con un attributo primary=true e che utilizzi tale identità come ID persona per quella riga. L’identità è la chiave primaria utilizzata in Experience Platform per il partizionamento. <br/>Se lasci questa opzione disabilitata, seleziona uno spazio dei nomi dal campo Spazio dei nomi identità sottostante. Customer Journey Analytics cerca la mappa delle identità di ogni riga per questa chiave di spazio dei nomi e utilizza l’identità in tale spazio dei nomi come ID persona per tale riga."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-enable-reporting"
>title="Abilita reporting"
>abstract="Abilita questa opzione per utilizzare Analysis Workspace per generare rapporti sui dati del consenso disponibili nella connessione. Le dimensioni e le metriche dei criteri di consenso vengono aggiunte alle visualizzazioni dati selezionate."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-consent-enable-filtering"
>title="Abilita filtro"
>abstract="Abilita questa opzione per escludere i dati dei visitatori non consenzienti dall’acquisizione in Customer Journey Analytics. Quando è abilitata, i dati di un visitatore vengono acquisiti solo se il visitatore corrisponde a tutti i criteri di consenso abilitati di seguito. <br>Questa opzione è destinata alle organizzazioni che devono escludere i dati dei visitatori non autorizzati al momento dell&#39;acquisizione."

<!-- markdownlint-enable MD034 -->

Gli amministratori di sistema possono abilitare la segnalazione del consenso e, facoltativamente, il filtro del consenso per una o più connessioni. Per informazioni generali, consulta [Panoramica sui rapporti di consenso e filtri](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>Il filtro del consenso esclude i dati dei visitatori non consentiti al momento del caricamento. I dati esclusi dal filtro non vengono memorizzati in Customer Journey Analytics e non possono essere recuperati per le date passate. Rivedi attentamente le selezioni delle azioni di marketing prima di abilitare il filtro.

## Creare una configurazione

Quando crei una configurazione per la generazione di rapporti e il filtro del consenso, seleziona la sandbox e il criterio di unione che contengono i dati di iscrizione al criterio di consenso, scegli la connessione o le connessioni da configurare e scegli se filtrare i dati per ogni azione di marketing. Customer Journey Analytics crea quindi automaticamente il set di dati di ricerca dei criteri di consenso e i componenti dei criteri di consenso.

Per creare una configurazione di reporting e filtro del consenso:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Generazione rapporti di consenso e filtro]**.

1. Selezionare **[!UICONTROL Crea configurazione]**.

   ![pagina di configurazione del consenso](assets/consent-configure.png)

1. Nella sezione **[!UICONTROL Dettagli]**, specifica le seguenti informazioni:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL Nome]** | Specifica un nome per la configurazione. |
   | **[!UICONTROL Sandbox]** | Seleziona la sandbox di Experience Platform che contiene il set di dati Profilo con i dati di iscrizione al criterio di consenso. <p>Esiste un massimo di un set di dati di ricerca dei criteri di consenso per sandbox. Più configurazioni nella stessa sandbox condividono lo stesso set di dati di ricerca.</p> |

1. Nella sezione **[!UICONTROL Set di dati profilo]**, nel campo **[!UICONTROL Criterio di unione]**, selezionare il criterio di unione corrispondente al set di dati profilo che contiene i dati di appartenenza ai criteri di consenso (campo `consentPoliciesIDMap`) su cui si desidera creare un rapporto. Quando abiliti la segnalazione del consenso, questo set di dati profilo viene aggiunto alla connessione selezionata, se non ne fa già parte.<p>I criteri di unione determinano il modo in cui Adobe Experience Platform combina i dati del profilo da più set di dati in profili cliente unificati utilizzati per i dati di iscrizione ai criteri di consenso. Ogni giorno in Experience Platform viene generata un’istantanea di questi dati. Questa istantanea fornisce una visualizzazione statica dei dati in un momento specifico e non include dati di eventi.</p><p>Selezionare il criterio di unione **[!UICONTROL Basato su tempo predefinito]** se sono presenti più criteri di unione e non si è sicuri di quale scegliere. Puoi anche consultare il team di dati per comprendere meglio quali dati sul consenso sono associati a ciascun criterio di unione.</p>

1. Nella sezione **[!UICONTROL Connessione]**, seleziona **[!UICONTROL Seleziona una connessione]**, seleziona la casella di controllo accanto alla connessione da configurare, quindi seleziona **[!UICONTROL Usa connessione]**.

   La generazione di rapporti e i filtri di consenso vengono applicati a livello di connessione. Tutte le visualizzazioni dati in una connessione configurata ereditano lo stesso comportamento.

1. Nel campo **[!UICONTROL ID persona]**, selezionare un campo dallo schema basato sul modello che rappresenta l&#39;ID persona. La selezione è limitata all’elenco dei campi nello schema contrassegnati come &quot;Identity&quot; e che hanno uno spazio dei nomi dell’identità.

1. Scegli se abilitare la generazione di rapporti per i dati del consenso.

   Per informazioni su quando abilitare il reporting, vedi [Generazione rapporti di consenso e filtro](/help/connections/consent-reporting-filtering/consent-overview.md#consent-reporting-vs-filtering).

   Per abilitare e configurare la generazione rapporti:

   1. Nella sezione **[!UICONTROL Reporting]**, seleziona **[!UICONTROL Abilita reporting]**.

   1. Seleziona le visualizzazioni dati associate alla tua connessione che desideri utilizzare durante l’analisi dei dati di consenso della piattaforma in Analysis Workspace. Nella sezione **[!UICONTROL Visualizzazioni dati]**, fai clic su **[!UICONTROL Seleziona visualizzazioni dati]**.

   1. Nella finestra di dialogo Visualizzazioni dati, seleziona la casella di controllo accanto a una o più visualizzazioni dati che desideri utilizzare per la segnalazione del consenso. Queste visualizzazioni dati vengono configurate automaticamente con i dati di consenso di Experience Platform per il reporting.

   1. Selezionare **[!UICONTROL Usa visualizzazioni dati]**.

1. Scegli se abilitare il filtro, che esclude i visitatori non consenzienti al momento dell’acquisizione.

   Quando il filtro è abilitato, Customer Journey Analytics acquisisce i dati di un visitatore solo se il visitatore corrisponde a tutti i criteri di consenso abilitati.

   Per informazioni su quando abilitare il filtro, vedi [Generazione rapporti di consenso e filtro](/help/connections/consent-reporting-filtering/consent-overview.md#consent-reporting-vs-filtering).

   Per abilitare e configurare il filtro:

   1. Nella sezione **[!UICONTROL Filtro]**, seleziona **[!UICONTROL Abilita filtro]** per filtrare i dati del consenso.

   1. Abilita il filtro per una o entrambe le seguenti azioni di marketing:

      >[!NOTE]
      >
      >Quando il filtro per un&#39;azione di marketing è abilitato, Customer Journey Analytics acquisisce i dati di un visitatore solo se il visitatore corrisponde a **tutti** i criteri di consenso che si applicano a tale azione di marketing. Per ulteriori informazioni, vedere [Filtro del consenso](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) in [Panoramica sui report e i filtri del consenso](/help/connections/consent-reporting-filtering/consent-overview.md).

      Le azioni di marketing sono legate alle etichette di utilizzo dei dati e ai criteri configurati in Experience Platform. Per ulteriori informazioni, consulta [Etichette, criteri e azioni di marketing](/help/data-views/data-governance.md).

      | Azione di marketing | Descrizione |
      | --------- | ---------- |
      | **[!UICONTROL Dati di Analytics]** | Filtra i dati utilizzati per il reporting standard di Customer Journey Analytics in Analysis Workspace. |
      | **[!UICONTROL Dati scientifici]** | Filtra i dati utilizzati per casi di utilizzo di analisi avanzate, apprendimento automatico e data science. |

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
