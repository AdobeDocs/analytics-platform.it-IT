---
description: Scopri come esportare una tabella completa in una posizione cloud.
keywords: Analysis Workspace
title: Esportare Tabelle Complete Nel Cloud
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: c16fc1a239c9ce1b701b3d03539bc9696f1c6489
workflow-type: tm+mt
source-wordcount: '2229'
ht-degree: 72%

---

# Esportare tabelle complete nel cloud {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Creare esportazioni di tabelle complete simili a data warehouse"
>abstract="Le esportazioni di tabelle complete risultano disponibili non appena sono visibili dati in Analysis Workspace. Puoi creare o pianificare esportazioni di tabelle complete in base alle esigenze.<br><br>La creazione di esportazioni di tabelle complete può essere completata in pochi minuti se sai già quali dati includere nell’esportazione."

<!-- markdownlint-enable MD034 -->

Puoi esportare tabelle complete di Analysis Workspace da Customer Journey Analytics e inviare le esportazioni alle destinazioni cloud designate.

Sono disponibili anche altri metodi di esportazione dei rapporti di Customer Journey Analytics, come descritto in [Panoramica sull’esportazione](/help/analysis-workspace/export/export-project-overview.md).

## Informazioni sull’esportazione di una tabella completa

Puoi esportare tabelle complete da Analysis Workspace a provider cloud come Google, Azure, Amazon e Adobe.

[I vantaggi dell&#39;esportazione di tabelle complete nel cloud](#advantages-of-exporting-to-the-cloud) includono la possibilità di esportare milioni di righe, le metriche calcolate, l’output dei dati della struttura in valori concatenati e altro ancora.

Durante l’esportazione di tabelle complete, tieni presente quanto segue:

* Prima di esportare nel cloud, assicurati che le tabelle, l’ambiente e le autorizzazioni soddisfino i [requisiti di esportazione](#export-requirements).

* Alcune [funzionalità](#unsupported-features) e [componenti](#unsupported-components) non sono supportati durante l’esportazione di tabelle complete nel cloud.

Utilizza il seguente processo durante l’esportare tabelle complete nel cloud:

1. [Configurare un account cloud](/help/components/exports/cloud-export-accounts.md)

1. [Configurare una posizione sull’account](/help/components/exports/cloud-export-locations.md)

1. [Esportare una tabella completa da Workspace](#export-full-tables-from-analysis-workspace)

1. [Accedere ai dati nel cloud](#view-exported-data-and-manifest-file) e [Gestire le esportazioni in Adobe](/help/components/exports/manage-exports.md)

![Processo di esportazione della tabella completa descritto nei passaggi da 1 a 4.](assets/export-full-table-process.png)

## Esporta tabelle complete  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="File manifesto"
>abstract="Se è abilitato, un file manifesto viene incluso in tutte le consegne esportate riuscite. Il file manifesto ti consente di confermare che tutti i file sono stati consegnati correttamente."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Prima di esportare i dati come descritto in questa sezione, scopri di più sull’esportazione di tabelle complete nella sezione precedente [Informazioni sull’esportazione di tabelle complete](#understand-full-table-export).

Per esportare tabelle complete da Analysis Workspace:

1. Se non lo hai già fatto, configura un account e una posizione di esportazione, come descritto in [Configurare gli account di esportazione cloud](/help/components/exports/cloud-export-accounts.md).

1. In Analysis Workspace, seleziona [!UICONTROL **Esporta tabella completa**] dal menu di scelta rapida di una tabella a forma libera.

   ![Menu a discesa della tabella a forma libera con l’opzione Esporta tabella completa evidenziata.](assets/export-full-table.png)

1. Nella finestra di dialogo [!UICONTROL **Nuova esportazione di tabella completa**], specifica le informazioni seguenti:

   | Nome campo: | Funzione |
   |---------|----------|
   | Nome | Specifica un nome per l’esportazione. Questo nome viene visualizzato nell’elenco delle esportazioni. |
   | Tag | Puoi applicare un tag esistente all’esportazione oppure creare un nuovo tag e applicarlo. <p>Per applicare un tag esistente all’esportazione, seleziona un tag qualsiasi dal menu a discesa. Tutti i tag dell’azienda sono disponibili per l’applicazione<!-- double-check this -->.</p> <p>Per creare un nuovo tag, digitane il nome, quindi premi Invio.</p><p>Durante l’applicazione di tag a un’esportazione, tieni presente quanto segue: <ul><li>I tag applicati possono essere filtrati o cercati nella tabella delle esportazioni.</li> <li>I tag applicati a un progetto non vengono applicati automaticamente durante l’esportazione di una tabella completa, come descritto in “Configurare le colonne nella pagina di esportazione” in [Gestire le esportazioni](/help/components/exports/manage-exports.md). (In alternativa, durante la [pianificazione di un progetto completo per l’esportazione](/help/analysis-workspace/export/t-schedule-report.md), tutti i tag applicati al progetto vengono automaticamente applicati all’esportazione.)  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Descrizione | Aggiungi una descrizione all’esportazione. Puoi scegliere di visualizzare le descrizioni come colonna nella [pagina Esportazioni](/help/components/exports/manage-exports.md) durante la visualizzazione delle esportazioni. |
   | Visualizzazione dati | Seleziona la visualizzazione dati che contiene i componenti da includere nell’esportazione. Il menu a discesa della visualizzazione dati ![Dati](/help/assets/icons/Data.svg) si trova nell&#39;angolo superiore sinistro della finestra di dialogo.  <p>**Nota:** se si seleziona una visualizzazione dati in cui mancano componenti già inclusi nella tabella dati, viene richiesto di cancellare e ricreare il pannello utilizzando i componenti inclusi nella visualizzazione dati selezionata. </p> |
   | Intervallo di lookback | Seleziona l’intervallo di tempo di reporting da includere in ciascun file di esportazione. Le opzioni includono [!UICONTROL **Oggi**], **[!UICONTROL Yesterday]**, **[!UICONTROL Last 7 days]**, **[!UICONTROL Last 30 days]**, **[!UICONTROL This week]** e **[!UICONTROL This month]**. <p>Questa opzione non viene visualizzata quando **[!UICONTROL Export frequency]** è impostato su **[!UICONTROL Send now (one-time)]**. |
   | Tabella dati | Visualizza la tabella a forma libera che stai esportando. Puoi modificare la tabella di dati trascinando i componenti dal pannello di sinistra alla tabella. Il progetto viene aggiornato dinamicamente quando si aggiungono componenti all’area di lavoro.  <p>Tutti i segmenti applicati alla tabella completa nel progetto vengono visualizzati nella parte superiore di ogni singola colonna della tabella.</p> |
   | Cancella | Cancella il contenuto della tabella dati. Questo consente di iniziare a creare una nuova tabella direttamente nella finestra di dialogo Nuova esportazione di tabella completa. |
   | Frequenza di esportazione | Imposta la pianificazione per la frequenza con cui deve avvenire l’esportazione. <p>Puoi scegliere [!UICONTROL **Invia ora (una tantum)**] per inviare l’esportazione una sola volta. Quando selezioni questa opzione, l’esportazione viene avviata immediatamente.<p>In alternativa, puoi scegliere di inviare l’esportazione in base a una pianificazione definita. Durante l&#39;invio secondo una pianificazione, le opzioni includono **[!UICONTROL Daily]**, **[!UICONTROL Weekly]**, **[!UICONTROL Monthly by day of the week]**, **[!UICONTROL Monthly by day of the month]**, **[!UICONTROL Yearly by day of the month]** e **[!UICONTROL Yearly by specific date]**. </p><p>Durante la selezione di una frequenza di esportazione, tieni in considerazione quanto segue:</p><ul><li>Le opzioni nel campo **[!UICONTROL Lookback window]** variano a seconda di ciò che si seleziona qui.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Vengono visualizzati campi di configurazione aggiuntivi a seconda dell’opzione scelta.</li></ul> |
   | Data di inizio | Giorno e ora in cui dovrebbe iniziare l’esportazione pianificata. <p>Questa opzione è disponibile solo quando si sceglie una frequenza di esportazione pianificata.</p> |
   | Data di fine | Giorno e ora di scadenza dell’esportazione pianificata. L’esportazione pianificata non viene più eseguita dopo la data e l’ora impostate. <p>Questa opzione è disponibile solo quando si sceglie una frequenza di esportazione pianificata.</p> |
   | Formato file | Scegli se i dati esportati devono essere in formato .csv o .json. |
   | Includi file manifesto | Se è abilitato, un file manifesto viene incluso in tutte le consegne esportate riuscite. Il file manifesto consente di confermare che tutti i file sono stati consegnati correttamente. Include le seguenti informazioni:<ul><li>Un elenco di tutti i file consegnati</li><li>Il checksum MD5 di ciascun file</li></ul><p>I dati esportati sono disponibili come file compresso nella destinazione cloud configurata, come descritto in [Configurare gli account di esportazione cloud](/help/components/exports/cloud-export-accounts.md) e [Configurare le posizioni di esportazione cloud](/help/components/exports/cloud-export-locations.md).</p><p>A seconda che sia stato scelto CSV o JSON come formato di file, il nome del file compresso può essere:</p><ul><li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li></ul><p>Scegliere il formato di file nel campo **[!UICONTROL *Formato file**] sopra.</p> |
   | Account | Seleziona l’account di esportazione cloud in cui desideri inviare i dati. <p>In alternativa, se non hai già configurato un account cloud da utilizzare, puoi configurare un nuovo account:<ol><li>Selezionare **[!UICONTROL Add account]**, quindi specificare le informazioni seguenti:<ul><li>**[!UICONTROL Location account name]**: specificare un nome per l&#39;account della posizione. Questo nome viene visualizzato durante la creazione di una posizione </li><li>**[!UICONTROL *ocation account description]**: fornire una breve descrizione dell&#39;account per distinguerlo dagli altri account dello stesso tipo.</li><li>**[!UICONTROL Account type]**: selezionare il tipo di account cloud in cui si desidera esportare i dati. I tipi di account disponibili sono Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e AEP Data Landing Zone.</li></ul><li>Per completare la configurazione dell&#39;account, continuare con il collegamento seguente corrispondente a **[!UICONTROL Account type]** selezionato:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Posizione | Seleziona la posizione dell’account in cui desideri inviare i dati di esportazione.<p>Oppure, se non hai già configurato la posizione da utilizzare sull’account selezionato, puoi configurarne una nuova:<ol><li>Selezionare **[!UICONTROL *dd location]**, quindi specificare le informazioni seguenti: <ul><li>**[!UICONTROL Name]**: nome del percorso.</li><li>**[!UICONTROL Description]**: fornire una breve descrizione della posizione per distinguerla dalle altre posizioni dell&#39;account.</li><li>**[!UICONTROL Location account]**: selezionare l&#39;account in cui si desidera creare il percorso.</li></ul><li>Per completare la configurazione della posizione, continua con il collegamento seguente corrispondente al tipo di account selezionato nel campo **[!UICONTROL Location account]**:<ul><li>[Data Landing Zone di AEP](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3 con ruolo ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**] per salvare l’esportazione.

   I dati vengono inviati all’account cloud specificato alla frequenza specificata.

1. (Facoltativo) Dopo aver creato l’esportazione, che tu scelga di inviarla ora oppure in base a una pianificazione definita, puoi visualizzarla e gestirla nella [pagina Esportazioni](/help/components/exports/manage-exports.md) e visualizzarla nei [registri di esportazione](/help/components/exports/manage-export-logs.md).</p>

## Gestire le esportazioni

Dopo l’esportazione dei dati da Analysis Workspace, puoi modificare, riesportare, duplicare, assegnare tag o eliminare le esportazioni esistenti, come descritto in [Gestire le esportazioni](/help/components/exports/manage-exports.md).

## Vantaggi dell’esportazione di tabelle complete {#advantages}

L’esportazione di dati di Customer Journey Analytics nel cloud consente di:

* Esportare in una posizione condivisa, ad esempio Data Landing Zone di Adobe Experience Platform, Google Cloud Platform, Microsoft Azure, Amazon S3 o Snowflake.

* Memorizzare grandi quantità di dati storici.

  Questo tipo di dati può essere utilizzato per rilevare tendenze a lungo termine per acquisire informazioni aziendali e, in ultima analisi, per migliorare il processo decisionale aziendale.

* Esportare tabelle complete contenenti migliaia o milioni di righe (3 milioni, 30 milioni, 150 milioni o 300 milioni di righe, a seconda del tipo di licenza). Altri metodi di esportazione consentono un massimo di 50.000 righe.

* Includere le metriche calcolate nei dati di Customer Journey Analytics esportati.

* Strutturare l’output dei dati come valori concatenati.

* Esporta una tantum o in base a una pianificazione. (Disponibile anche con [altre opzioni di esportazione](/help/analysis-workspace/export/export-project-overview.md).)

* Esportare file in formato CSV o JSON. (Disponibile anche con [altre opzioni di esportazione](/help/analysis-workspace/export/export-project-overview.md).)

* Esportare le tabelle che includono più dimensioni.

## Requisiti minimi

Assicurati che le tabelle, l’ambiente e le autorizzazioni soddisfino i seguenti requisiti:

* **Tabelle:** tutte le tabelle devono includere almeno una dimensione nella riga e una metrica in ogni colonna per essere supportate con un&#39;esportazione di tabella completa.

* **Ambiente:** verificare che gli [indirizzi IP](/help/technotes/ip-addresses.md) e i [domini](/help/technotes/domains.md) utilizzati da Customer Journey Analytics siano consentiti tramite il firewall dell’organizzazione.

* **Autorizzazioni:** In Adobe Admin Console, agli utenti deve essere assegnato un profilo di prodotto con l&#39;autorizzazione **[!UICONTROL Full Table Export]** assegnata per esportare tabelle complete. Per informazioni sull’assegnazione di un’autorizzazione a un profilo di prodotto in Admin Console, consulta [Autorizzazione Customer Journey Analytics in Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Gli utenti a cui è assegnato il ruolo di [amministratore prodotto](/help/technotes/access-control.md#product-admin-role) hanno sempre accesso all&#39;esportazione di tabelle complete; a questi utenti non deve essere assegnata l&#39;autorizzazione **[!UICONTROL Full Table Export]**.


## Funzioni non supportate

Le seguenti funzioni non sono supportate e vengono rimosse automaticamente dalle esportazioni di tabelle complete:

* Percentuali
* Totali
* Filtro di ricerca
* Righe statiche
* Allineamento data
* Metriche da set di dati di riepilogo
* Elementi dimensionali dinamici

  Gli elementi dimensionali dinamici vengono creati quando rilasci una dimensione su un’intestazione di colonna in una tabella a forma libera, in modo che la colonna venga filtrata dinamicamente in base ai primi 5 elementi dimensionali. In Analysis Workspace, questi primi 5 elementi dimensionali vengono aggiornati ogni volta che carichi il progetto. In un’esportazione di tabelle complete, questi elementi dimensionali diventano statici. Per ulteriori informazioni, consulta [Elementi dimensionali dinamici e statici nelle tabelle a forma libera](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Le dimensioni nel primo raggruppamento vengono convertite e aggiunte come dimensione secondaria nella riga della tabella esportata. Qualsiasi altra disaggregazione non è inclusa nella tabella.
* L&#39;ordinamento non è supportato per la maggior parte dei set di dati; i dati potrebbero essere ordinati per set di dati di piccole dimensioni.

## Componenti non supportati

I seguenti componenti non sono supportati e Analysis Workspace richiede di rimuoverli dalla tabella durante un’esportazione di tabella completa:

* Metriche calcolate che utilizzano funzioni di base o avanzate nella definizione della metrica (per ulteriori informazioni, consulta [Funzioni di base](/help/components/calc-metrics/cm-functions.md) e [Funzioni avanzate](/help/components/calc-metrics/cm-adv-functions.md))
* Non è possibile esportare i componenti per i quali un amministratore ha impostato un limite (per ulteriori informazioni, consulta la sezione *Segmento sui criteri di governance dei dati nelle visualizzazioni dati* in [Etichette e criteri](/help/data-views/data-governance.md))
* Qualsiasi dimensione che soddisfi tutti i seguenti criteri:
   * Viene creato da un campo che fa parte di un [array di oggetti](/help/use-cases/object-arrays.md) (simile alle variabili con più valori in Adobe Analytics).
   * Ha [persistenza abilitata](/help/data-views/component-settings/persistence.md).
   * Non utilizza una [dimensione di binding](/help/use-cases/data-views/binding-dimensions-metrics.md).
* Più dimensioni provenienti da campi che fanno riferimento a [array di oggetti](/help/use-cases/object-arrays.md) diversi. (Sono consentite più dimensioni che fanno riferimento allo stesso array di oggetti.)
* Più di 10 dimensioni e 10 metriche per rapporto (sono supportate fino a 10 dimensioni e 10 metriche)
* Nelle colonne della tabella:
   * Intervalli di date
   * Dimensioni
* Nelle righe della tabella:
   * Metriche calcolate
   * Metriche
   * Intervalli di date
   * Segmenti

## Comportamento attribuzione

L’esportazione di tabella completa supporta le metriche calcolate che utilizzano un modello di attribuzione non predefinito (come descritto nella sezione *Utilizzare un modello di attribuzione non predefinito* in [Impostazioni colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)).

Se in un rapporto viene utilizzato un modello di attribuzione non predefinito, il modello di allocazione utilizzato nel rapporto viene ignorato o mantenuto, a seconda che il rapporto abbia una o più dimensioni:

* **Per i rapporti che includono l’attribuzione della metrica in una singola dimensione:** [l’attribuzione della metrica](/help/data-views/component-settings/attribution.md) sostituisce il [modello di allocazione](/help/data-views/component-settings/persistence.md), come avviene di solito durante l’utilizzo dell’attribuzione della metrica.

  Ad esempio, l’attribuzione di una metrica di “primo contatto” sostituisce l’allocazione di una dimensione “più recente”.

* **Per i rapporti che includono l’attribuzione della metrica su più dimensioni contemporaneamente:** [l’attribuzione della metrica](/help/data-views/component-settings/attribution.md) viene applicata in aggiunta alla dimensione [modello di allocazione](/help/data-views/component-settings/persistence.md).

  Ad esempio, viene applicata un’attribuzione di metrica “primo contatto” oltre a un’allocazione di dimensione “più recente”. Inoltre, l’attribuzione metrica viene applicata alle coppie di elementi dimensionali post-allocati come se fossero elementi dimensionali singoli, anziché a ciascun elemento dimensionale in modo indipendente, come si fa normalmente in una tabella a forma libera.

  >[!NOTE]
  >
  >I rapporti multidimensionali sono supportati solo quando si esportano dati nel cloud, come descritto in questo articolo.

## Confronto con Data Warehouse

Se in precedenza si utilizzava Data Warehouse per esportare dati di Adobe Analytics, la tabella seguente consente di comprendere le differenze tra l’esportazione di tabelle complete in Customer Journey Analytics e l’esportazione di dati con Data Warehouse in Adobe Analytics.


| Funzione | Esportazione di tabelle complete in Customer Journey Analytics | Data Warehouse in Adobe Analytics |
|---------|----------|---------|
| Creare un rapporto personalizzato | Sì | Sì |
| Metriche calcolate | Sì | No |
| Segmenti | Sì | Limitato |
| Dimensioni | Limite di 10 | Senza limiti |
| Metriche | Limite di 10 | Senza limiti |
| Righe di reporting | Limite di 3 milioni, 30 milioni, 150 milioni o 300 milioni, a seconda del livello | Senza limiti |
| Numero di rapporti | Senza limiti | Senza limiti |
| Consegna ad hoc (una tantum) | Sì | Sì |
| Pianificare una consegna ricorrente | Sì | Sì |
| Consegna e-mail | No | Sì |
| FTP / SFTP | No | Supporto legacy |
| Azure | Sì | Sì |
| Amazon S3 | Sì | Sì |
| Google Cloud Platform | Sì | Sì |
| Snowflake | Sì | No |
| Frequenza di consegna | Giornaliero | Oraria |
