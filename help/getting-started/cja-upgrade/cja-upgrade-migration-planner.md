---
title: Migrazione da AppMeasurement o tag a XDM
description: Scopri come effettuare la migrazione da AppMeasurement o dai tag a XDM
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: db34e721f156b3eb0aab20b2dca57e194c83d6fb
workflow-type: tm+mt
source-wordcount: '2379'
ht-degree: 4%

---

# Migrazione dai tag a XDM {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="Panoramica sulle migrazioni"
>abstract="Eseguire la migrazione di un&#39;implementazione di tag a Adobe Experience Platform Web SDK durante l&#39;aggiornamento a Customer Journey Analytics.<br/>Continuare con una migrazione esistente o avviarne una nuova."

<!-- markdownlint-enable MD034 -->

Il Pianificatore di migrazione fornisce una procedura guidata di migrazione che automatizza la migrazione dai tag a XDM, inclusa la creazione di schemi. Queste sono alcune delle attività più complesse e dispendiose in termini di tempo associate a un aggiornamento da Adobe Analytics a Customer Journey Analytics.

## Implementazioni di Adobe Analytics supportate

Migration Planner supporta le implementazioni di Adobe Analytics che utilizzano l’estensione Analytics (tag).

Il Pianificatore della migrazione non è disponibile per le implementazioni di Adobe Analytics che utilizzano AppMeasurement o Experience Platform Web SDK.

## Attività di aggiornamento incluse nella pianificazione della migrazione

Migration Planner fornisce una procedura guidata di migrazione che automatizza le seguenti attività di aggiornamento complesse e dispendiose in termini di tempo:

* **Creazione schema XDM**: crea automaticamente un nuovo schema XDM basato sulle variabili della suite di rapporti di Adobe Analytics. Migration Planner esegue una scansione intelligente delle variabili della suite di rapporti di Adobe Analytics, quindi utilizza tali informazioni per creare i campi necessari in XDM. Lo schema XDM risultante include solo i campi necessari nello schema Customer Journey Analytics.

  In alternativa, puoi puntare a uno schema XDM esistente oppure creare uno schema XDM da zero.

  +++ Se scegli di creare uno schema XDM da zero, puoi espandere questa sezione per informazioni sulle risorse utili.

  * [Pianifica l’architettura dello schema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}.

  * [Crea lo schema personalizzato che desideri in Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}.

    Quando crei lo schema, considera le seguenti opzioni:

    * Se desideri integrare Customer Journey Analytics con RTCDP, devi abilitare l&#39;opzione **[!UICONTROL Profilo]** nello schema, come descritto in [Creare uno schema XDM da utilizzare con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}. Con questa opzione abilitata, i dati inseriti in set di dati basati su questo schema vengono uniti sul profilo cliente in tempo reale.

    * Se desideri includere dati multimediali in streaming, devi [configurare lo schema per acquisire e utilizzare dati in streaming](/help/data-ingestion/streaming.md){target="_blank"}.

    +++

  * **Migrazione dell&#39;implementazione Adobe Analytics al Web SDK**: sia che l&#39;implementazione Adobe Analytics utilizzi tag o JavaScript, Migration Planner consente di eseguire la migrazione al Web SDK Experience Platform.

    * **Migrazione delle proprietà dei tag da AppMeasurement al Web SDK**:

    * **Migrare un&#39;implementazione di JavaScript da AppMeasurement alla libreria JavaScript di Web SDK**

  * **Creazione della visualizzazione dati in Customer Journey Analytics**: crea automaticamente le visualizzazioni dati e le popola con i componenti, in base ai campi dello schema XDM creati.


## Prima di iniziare

Prima di creare una migrazione, assicurati di disporre dei seguenti elementi:

* Un’implementazione di Adobe Analytics supportata (l’estensione Analytics per i tag). Consulta [Implementazioni di Adobe Analytics supportate](#supported-adobe-analytics-implementations).

* Accedi alla proprietà Tag di Adobe di cui desideri eseguire la migrazione, nell’organizzazione Experience Cloud a cui hai effettuato l’accesso.

* Accedi alla suite di rapporti di Adobe Analytics di cui desideri mappare le variabili su XDM.

* Autorizzazione a creare schemi in Adobe Experience Platform.

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## Migrare un’implementazione di Analytics al Web SDK

Una migrazione si sposta attraverso tre fasi: [!UICONTROL **Audit**], [!UICONTROL **Mappatura**] e [!UICONTROL **Implementazione**]. Utilizza i seguenti passaggi per creare una migrazione, quindi continua con [Convalida e distribuisci una migrazione](#validate-and-deploy-a-migration) per completare ogni fase.

1. In Customer Journey Analytics, apri [!UICONTROL **Pianificazione migrazione**].

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. In Pianificazione migrazione, nella scheda [!UICONTROL **Migrazioni**], selezionare [!UICONTROL **Nuove**].

   ![Finestra di dialogo Nuova migrazione, in cui è possibile scegliere un tipo di migrazione e immettere un nome di migrazione.](assets/migration-planner-new-migration.png)

1. Specifica le seguenti informazioni:

   | Nome campo: | Funzione |
   | --------- | ---------- |
   | [!UICONTROL **Nome**] | Specifica un nome per la migrazione. |
   | [!UICONTROL **Descrizione**] | Specificare una descrizione facoltativa per la migrazione. |
   | [!UICONTROL **Proprietà tag**] | Seleziona la proprietà Adobe Tags di cui vuoi eseguire la migrazione. Per ulteriori informazioni, consulta [Proprietà](https://experienceleague.adobe.com/it/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"} nella documentazione di Experience Platform. |
   | [!UICONTROL **Libreria tag**] | Seleziona lo snapshot della libreria di tag su cui si basa la migrazione. Lo snapshot determina quale versione della libreria di tag viene utilizzata. Per ulteriori informazioni, consulta [Panoramica sulla pubblicazione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/publish/overview){target="_blank"} nella documentazione di Experience Platform. |

1. Nel campo [!UICONTROL **Nome migrazione**], specifica un nome per la migrazione, quindi seleziona [!UICONTROL **Successivo**].

1. Seleziona la proprietà tag di cui vuoi eseguire la migrazione, quindi seleziona [!UICONTROL **Successivo**].

   Vengono visualizzate solo le proprietà del tag disponibili per l’organizzazione Experience Cloud che ha effettuato l’accesso.

1. Selezionare lo snapshot della libreria di tag di cui si desidera eseguire la migrazione, quindi selezionare [!UICONTROL **Avanti**].

   Lo snapshot determina su quale versione della libreria di tag si basa la migrazione. Ogni istantanea mostra il relativo ambiente (ad esempio [!UICONTROL **Sviluppo**], [!UICONTROL **Gestione temporanea**] o [!UICONTROL **Produzione**]).

1. Seleziona il set di mappatura per determinare come le variabili di Analytics verranno mappate sui campi dello schema XDM.

   Esegui una delle operazioni seguenti:

   * Selezionare [!UICONTROL **Crea un nuovo set di mappatura**].

   * Seleziona un set di mappatura esistente.

     I set di mappatura creati durante una migrazione precedente o come set di mappatura autonomo sono disponibili per la selezione.

     Il riutilizzo di un set di mappatura in più migrazioni applica le stesse mappature a ciascuna migrazione.

1. Seleziona [!UICONTROL **Crea migrazione**].

1. Continuare con la seguente sezione [Convalidare e distribuire una migrazione](#validate-and-deploy-a-migration).

## Convalidare e distribuire una migrazione

Dopo aver creato una migrazione, aprirla per completare le tre fasi: [!UICONTROL **Audit**], [!UICONTROL **Mappatura**] e [!UICONTROL **Implementazione**].

1. In Pianificazione migrazione, seleziona la scheda [!UICONTROL **Migrazioni**].

1. Accanto alla migrazione da convalidare, selezionare [!UICONTROL **Apri**].

   La pagina di panoramica sulla migrazione mostra le tre fasi da completare, insieme a un riepilogo della migrazione e dei relativi artefatti.

   ![Pagina di panoramica sulla migrazione con le schede della fase Audit, Mapping e Implementazione.](assets/migration-planner-overview.png)

1. Completa la fase [!UICONTROL **Audit**]:

   1. Nella scheda di controllo ([!UICONTROL **Assegna tag all&#39;audit dell&#39;estensione**] o [!UICONTROL **JavaScript audit**], a seconda del tipo di migrazione), seleziona [!UICONTROL **Avvia audit**] per rivedere le regole e gli elementi dati inclusi nella migrazione.

      ![Pagina di controllo, in cui è possibile selezionare regole ed elementi dati e risolvere eventuali risultati.](assets/migration-planner-audit.png)

   1. Nelle schede [!UICONTROL **Regole**] e [!UICONTROL **Elementi dati**], seleziona gli elementi da includere nella migrazione.

      Le regole contrassegnate [!UICONTROL **Nella libreria**] sono pubblicate. Le regole contrassegnate [!UICONTROL **Solo proprietà**] esistono nella proprietà ma non fanno parte della libreria selezionata.

   1. Esamina eventuali risultati sulle regole selezionate. Per ogni risultato, seleziona [!UICONTROL **Rivedi**] per risolverlo, oppure [!UICONTROL **Ignora**] per non indirizzarlo.

      Ad esempio, se due regole hanno eventi e condizioni identici, il risultato [!UICONTROL **Eventi regola duplicati**] consente di mantenere una regola e di rimuovere l&#39;altra, oppure selezionare [!UICONTROL **Non eseguire alcuna operazione**] per confermare il risultato senza apportare alcuna modifica.

      La risoluzione dei risultati è facoltativa prima di continuare. Per l&#39;elenco completo dei tipi di risultati e per informazioni su come risolverli, vedere [Esaminare e risolvere i risultati dei controlli di audit](#review-and-resolve-audit-findings).

   1. Seleziona [!UICONTROL **Salva e continua**].

1. Completa la fase [!UICONTROL **Mappatura**]:

   1. Nella scheda [!UICONTROL **Mapping XDM di Analytics →**], seleziona [!UICONTROL **Crea nuovo mapping**].

   1. Scegli se creare un nuovo schema basato sulle variabili di Analytics o eseguire la mappatura rispetto a uno schema Experience Platform esistente, quindi segui le istruzioni per selezionare la suite di rapporti, mappare i campi e rivedere lo schema.

      Per i passaggi dettagliati, consulta [Mappare le variabili di Analytics ai campi XDM](#map-analytics-variables-to-xdm-fields). Per riutilizzare un set di mapping tra le migrazioni, vedere [Creare e gestire set di mapping](#create-and-manage-mapping-sets).

1. Completa la fase [!UICONTROL **Implementazione**]:

   1. Nella scheda [!UICONTROL **Generate Web SDK implementation**] (Genera implementazione Web), utilizzare i risultati del controllo e della mappatura per generare il pacchetto di implementazione Web SDK, quindi distribuirlo sul sito.

      Per i passaggi dettagliati, vedere [Generare e distribuire l&#39;implementazione di Web SDK](#generate-and-deploy-the-web-sdk-implementation).


## Rivedere e risolvere i risultati dell’audit

Durante la fase [!UICONTROL **Audit**], il Pianificatore della migrazione segnala i risultati relativi alle regole selezionate. La risoluzione dei risultati è facoltativa prima di continuare, ma aiuta a garantire una migrazione pulita.

Per ogni risultato, seleziona [!UICONTROL **Rivedi**] per aprirlo e scegliere come risolverlo, oppure seleziona [!UICONTROL **Ignora**] per non indirizzarlo.

Il Pianificatore della migrazione può contrassegnare i seguenti tipi di risultati:

* [!UICONTROL **Eventi regola duplicati**]: due o più regole hanno eventi e condizioni identici. Quando rivedi il risultato, confronta le regole principali e duplicate, quindi mantieni una regola e rimuovi l&#39;altra, oppure seleziona [!UICONTROL **Non fare nulla**] per confermare il risultato senza apportare alcuna modifica.

* [!UICONTROL **Logica regola duplicata**]: le regole condividono la stessa logica. <!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **Azioni regola non ordinate correttamente**]: le azioni di una regola vengono eseguite in un ordine che potrebbe causare problemi durante la migrazione. <!-- Confirm the exact remediation options for this finding type. -->

Se un risultato non dispone di correzione guidata, in Pianificazione migrazione verrà visualizzato [!UICONTROL **Nessun dettaglio di correzione disponibile**]. Esaminare il risultato manualmente e ignorarlo quando viene risolto.

Il pannello [!UICONTROL **Risultati**] mostra quanti risultati hai risolto e quanti sono ancora aperti. Al termine, selezionare [!UICONTROL **Salva e continua**].

## Mappare le variabili di Analytics ai campi XDM

Durante la fase [!UICONTROL **Mappatura**], mappi le variabili di Analytics ai campi XDM e generi o selezioni lo schema di destinazione. Nella scheda [!UICONTROL **Mappatura XDM di Analytics →**], seleziona [!UICONTROL **Crea nuova mappatura**], quindi completa i passaggi seguenti:

1. **Scelta dello schema**: scegli se creare un nuovo schema basato sulle variabili di Analytics o eseguire la mappatura rispetto a uno schema Experience Platform esistente.

1. **Suite di rapporti**: seleziona la suite di rapporti di Analytics di cui vuoi mappare le variabili.

1. **Schema Experience Platform**: crea lo schema XDM di destinazione o seleziona lo schema esistente su cui eseguire il mapping.

1. **Mappatura manuale**: rivedi le mappature automatiche e regola il modo in cui le singole variabili di Analytics vengono mappate ai campi XDM.

1. **Rivedi schema**: controlla i mapping e lo schema risultanti, quindi conferma.

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

Per riutilizzare un set di mapping tra le migrazioni, vedere [Creare e gestire set di mapping](#create-and-manage-mapping-sets).

## Confrontare i risultati della migrazione

Utilizza [!UICONTROL **Confronta output**] nella pagina panoramica della migrazione per convalidare la migrazione prima di distribuirla.

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## Generare e distribuire l’implementazione di Web SDK

Durante la fase [!UICONTROL **Implementazione**], il Pianificatore della migrazione utilizza i risultati dell&#39;audit e della mappatura per generare il pacchetto di implementazione di Web SDK.

1. Nella scheda [!UICONTROL **Generate Web SDK implementation**] (Genera implementazione Web) della pagina di panoramica sulla migrazione, generare il pacchetto di implementazione.

1. Creare la libreria tag per la migrazione selezionando [!UICONTROL **Genera libreria tag**].

1. Configura la distribuzione doppia, quindi distribuisci l’implementazione del Web SDK sul tuo sito.

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

Per gli artifact prodotti da questa fase, vedere [Esporta artifact di migrazione](#export-migration-artifacts).

## Esporta artefatti di migrazione

La pagina di panoramica sulla migrazione fornisce gli artefatti generati dal Pianificatore migrazione. Puoi scaricare singoli artifact dal pannello [!UICONTROL **Artifact progetto**] oppure selezionare [!UICONTROL **Esporta tutto**] per esportare tutto in una sola volta.

Sono disponibili i seguenti artefatti:

* [!UICONTROL **Mappatura JSON**]: la mappatura tra le variabili di Analytics e i campi XDM.

* [!UICONTROL **Schema XDM (JSON)**]: lo schema XDM di destinazione creato per la migrazione.

* [!UICONTROL **Libreria di sviluppo tag**]: libreria di tag generata per l&#39;implementazione di Web SDK.

Ogni artefatto mostra il relativo stato, ad esempio [!UICONTROL **Pronto**] o [!UICONTROL **Non generato**]. Un artefatto è disponibile per il download dopo che è stato generato nella fase corrispondente.

## Creare e gestire i set di mappatura {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="Set di mappatura"
>abstract="I set di mappatura determinano il modo in cui le variabili di Analytics vengono mappate ai campi XDM.<br/>Creare un nuovo set di mappatura o sceglierne uno esistente per applicare le stesse mappature in più migrazioni. È inoltre possibile fare riferimento ai set di mappatura in altre attività di migrazione."

<!-- markdownlint-enable MD034 -->

I set di mappatura determinano il modo in cui le variabili di Analytics vengono mappate ai campi dello schema XDM.

È possibile creare un nuovo set di mappatura [durante il processo di migrazione](#migrate-an-analytics-implementation-to-the-web-sdk). In alternativa, puoi creare un set di mappatura autonomo da utilizzare con una migrazione futura o con altre attività di migrazione.

### Creare un set di mappatura autonomo {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="Scegli uno schema"
>abstract="I set di mappatura determinano il modo in cui le variabili di Analytics vengono mappate ai campi XDM.<br/>Creare un nuovo set di mappatura o sceglierne uno esistente per applicare le stesse mappature in più migrazioni. È inoltre possibile fare riferimento ai set di mappatura in altre attività di migrazione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="Preferenza gruppo di campi"
>abstract="Scegli i gruppi di campi standard per utilizzare i gruppi di campi Adobe pubblicati, quando possibile. Ciò promuove la massima coerenza e torna ai campi tenant personalizzati quando non sono disponibili campi standard.<br/>Scegliere i gruppi di campi personalizzati per utilizzare i campi personalizzati dello spazio dei nomi del tenant, quando possibile. Ciò promuove la massima flessibilità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="Periodo di lookback"
>abstract="Controlla la distanza da osservare quando si determinano le variabili che ricevono attivamente i dati. Le variabili che includono dati all’interno del periodo di lookback sono incluse nello schema."

<!-- markdownlint-enable MD034 -->

1. In Pianificazione migrazione, selezionare la scheda [!UICONTROL **Set di mappatura**].

1. Seleziona [!UICONTROL **Nuovo set di mappatura**].

1. Nel campo [!UICONTROL **Name**], immetti un nome descrittivo che ti consenta di identificare il set di mappatura in seguito, quindi seleziona [!UICONTROL **Next**].

1. Dal menu [!UICONTROL **Suite di rapporti**], seleziona la suite di rapporti di cui vuoi mappare le variabili ai campi XDM, quindi seleziona [!UICONTROL **Successivo**].

1. In [!UICONTROL **Scegli uno schema per la sezione di mappatura XDM**], scegli se creare un nuovo schema basato sulle variabili di Analytics o eseguire la mappatura su uno schema Experience Platform esistente.

   La scelta di creare un nuovo schema ti guida attraverso il processo di mappatura delle variabili di Analytics ai campi XDM. La scelta di utilizzare uno schema esistente consente di mappare manualmente le variabili a uno schema preregistrato nel registro dello schema di Experience Platform.

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **Crea un nuovo schema**]: esegui le scansioni di base e avanzate per suggerire automaticamente i mapping dei campi XDM per le variabili di Analytics, quindi controlla lo schema risultante.

   * [!UICONTROL **Usa uno schema esistente**]: cerca e seleziona uno schema già registrato nel registro degli schemi di Experience Platform, quindi trascina manualmente le variabili di Analytics nei campi XDM.

1. Nel menu a discesa [!UICONTROL **Preferenza gruppo di campi**], scegliere come organizzare le variabili personalizzate in gruppi di campi:

   * [!UICONTROL **Standard first**]: utilizza i gruppi di campi Adobe pubblicati quando possibile. Ciò promuove la massima coerenza e torna ai campi tenant personalizzati quando non sono disponibili campi standard.

   * [!UICONTROL **Personalizzato per primo**]: se possibile, usa campi personalizzati dello spazio dei nomi del tenant. Ciò promuove la massima flessibilità.

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. Nel campo [!UICONTROL **Periodo di lookback**], seleziona il periodo di tempo precedente da considerare per determinare quali variabili stanno attivamente ricevendo i dati. Le variabili che includono dati all’interno del periodo di lookback sono incluse nello schema.

1. Selezionare [!UICONTROL **Crea set di mappatura**].

Il nuovo set di mappatura viene visualizzato nella scheda [!UICONTROL **Set di mappatura**], dove è possibile aprirlo per esaminarne i dettagli.

### Esportare un set di mappatura

Puoi esportare un set di mappatura per utilizzarlo con altre attività di migrazione o in altri strumenti.

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### Set di mappatura di pubblicazione e versione

Ogni set di mappatura ha uno stato e una versione. Nella scheda [!UICONTROL **Set di mappatura**], un set di mappatura può essere visualizzato come:

* [!UICONTROL **bozza**]: il set di mappatura è ancora in fase di modifica.

* [!UICONTROL **published**]: il set di mappatura è stato finalizzato.

* [!UICONTROL **nella migrazione**]: il set di mappatura è associato a una o più migrazioni.

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### Modificare un set di mappatura <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### Eliminare un set di mappatura <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## Gestire le migrazioni esistenti

### Trovare e tenere traccia delle migrazioni

Nella scheda [!UICONTROL **Migrazioni**] sono elencate le migrazioni e il relativo avanzamento. Utilizzala per trovare una migrazione da continuare o per controllare lo stato delle migrazioni in corso.

* **Ricerca**: utilizzare il campo di ricerca per trovare una migrazione in base al nome o alla proprietà.

* **Filtro**: filtra l&#39;elenco in base al tipo di migrazione o allo stato.

* **Tracciamento avanzamento**: ogni migrazione mostra lo stato di avanzamento nei tre stadi (ad esempio, 1/3) e uno stato complessivo:

  * [!UICONTROL **Non avviato**]: la migrazione è stata creata, ma nessuna fase è stata completata.

  * [!UICONTROL **In corso**]: almeno una fase è stata completata.

  * [!UICONTROL **Completato**]: tutte e tre le fasi sono completate.

Per continuare una migrazione, selezionare [!UICONTROL **Apri**] accanto.

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

