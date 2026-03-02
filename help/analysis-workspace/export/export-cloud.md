---
description: Scopri come esportare una tabella completa in una posizione cloud.
keywords: Analysis Workspace
title: Esportare Tabelle Complete Nel Cloud
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: c4a7884ae05d9290b2974483474ba8326492d014
workflow-type: tm+mt
source-wordcount: '3234'
ht-degree: 50%

---

# Esportare tabelle complete nel cloud {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Creare esportazioni di tabelle complete simili a data warehouse"
>abstract="Le esportazioni di tabelle complete risultano disponibili non appena sono visibili dati in Analysis Workspace. Puoi creare o pianificare esportazioni di tabelle complete in base alle esigenze.<br><br>È possibile creare esportazioni di tabelle complete in pochi minuti se si conoscono già i dati da includere nell&#39;esportazione."

<!-- markdownlint-enable MD034 -->

In Customer Journey Analytics, puoi esportare tabelle complete da Analysis Workspace a destinazioni cloud designate.

Sono disponibili anche altri metodi di esportazione dei rapporti di Customer Journey Analytics, come descritto in [Panoramica sull’esportazione](/help/analysis-workspace/export/export-project-overview.md).

## Informazioni sull’esportazione di una tabella completa

Puoi esportare tabelle complete da Analysis Workspace a provider cloud come Google, Azure, Amazon e Adobe.

[I vantaggi dell&#39;esportazione completa della tabella](#advantages-of-full-table-export) includono la possibilità di esportare milioni di righe, includere metriche calcolate, dati della struttura in output in valori concatenati e altro ancora.

Durante l’esportazione di tabelle complete, tieni presente quanto segue:

* Prima di esportare nel cloud, assicurati che le tabelle, l&#39;ambiente e le autorizzazioni soddisfino i [requisiti minimi di esportazione](#minimum-requirements).

* Alcune [funzionalità](#unsupported-features) e [componenti](#unsupported-components) non sono supportati durante l’esportazione di tabelle complete nel cloud.

Utilizza il seguente processo durante l’esportare tabelle complete nel cloud:

1. [Configurare un account cloud](/help/components/exports/cloud-export-accounts.md)

1. [Configurare una posizione sull’account](/help/components/exports/cloud-export-locations.md)

1. [Esportare una tabella completa da Workspace](#export-full-tables)

1. Accedi ai dati nell&#39;account cloud e [Gestisci le esportazioni in Adobe](/help/components/exports/manage-exports.md)

![Processo di esportazione della tabella completa descritto nei passaggi da 1 a 4.](assets/export-full-table-process.png)

## Esportare tabelle complete  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-details"
>title="Dettagli"
>abstract="Specifica un nome per l’esportazione. Puoi anche aggiungere una descrizione ed eventuali tag. Queste informazioni sono utili per identificare l’esportazione nella tabella delle esportazioni e nelle notifiche e-mail."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-data-structure"
>title="Struttura dei dati"
>abstract="Tabella a forma libera da esportare. Puoi modificare la struttura dati trascinando i componenti dal pannello di sinistra alla tabella. Puoi applicare un filtro trascinando un componente nell’area del filtro. La tabella viene aggiornata dinamicamente quando si aggiungono componenti all’area di lavoro."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="Includi file manifesto"
>abstract="Se questa opzione è selezionata, un file manifesto viene incluso in tutte le consegne di esportazione riuscite. Il file manifesto ti consente di confermare che tutti i file sono stati consegnati correttamente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-schedule"
>title="Pianificazione"
>abstract="Seleziona la frequenza con cui deve avvenire l’esportazione. Scegliere Invia ora (una tantum) per avviare immediatamente l&#39;esportazione. Le esportazioni programmate vengono avviate alla data e all&#39;ora specificate."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-destination"
>title="Destinazione"
>abstract="Seleziona l’account cloud e il percorso in cui desideri inviare i dati. Puoi scegliere un account e una posizione esistenti o selezionare &quot;Aggiungi nuovo&quot; per crearli. Specifica gli utenti e i gruppi a cui inviare le notifiche relative alle esportazioni non riuscite o in scadenza."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-format"
>title="Formato file"
>abstract="Quando si sceglie il formato di file Parquet, alcuni caratteri speciali inclusi nei nomi dei componenti vengono sostituiti da un carattere di sottolineatura (_). Consulta il collegamento seguente per un elenco completo dei caratteri sostituiti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-notifications"
>title="Notifiche"
>abstract="Aggiungi utenti e gruppi ai quali desideri ricevere notifiche quando l&#39;esportazione non riesce o sta per scadere."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Prima di esportare i dati come descritto in questa sezione, scopri di più sull’esportazione di tabelle complete nella sezione precedente [Informazioni sull’esportazione di tabelle complete](#understand-full-table-export).

Per esportare tabelle complete da Analysis Workspace:

1. Se non lo hai già fatto, configura un account e un percorso di esportazione, come descritto in [Configurare gli account di esportazione cloud](/help/components/exports/cloud-export-accounts.md) e [Configurare i percorsi di esportazione](/help/components/exports/cloud-export-locations.md).

1. In Analysis Workspace, fai clic con il pulsante destro del mouse sull&#39;intestazione di una tabella a forma libera per visualizzare il menu di scelta rapida, quindi seleziona [!UICONTROL **Esporta tabella completa**].

   ![Il menu di scelta rapida della tabella a forma libera con Esporta tabella completa evidenziato.](assets/export-full-table.png)

1. Nella finestra di dialogo [!UICONTROL **Nuova esportazione di tabella completa**], specifica le informazioni seguenti:

   | Nome campo: | Funzione |
   |---------|----------|
   | Nome | Specifica un nome per l’esportazione. Questo nome viene visualizzato nell’elenco delle esportazioni. |
   | Tag | Puoi applicare un tag esistente all’esportazione oppure creare un nuovo tag e applicarlo. <p>Per applicare un tag esistente all’esportazione, seleziona un tag qualsiasi dal menu a discesa. Tutti i tag della tua azienda sono disponibili per l’applicazione.</p> <p>Per creare un nuovo tag, digitane il nome, quindi premi Invio.</p><p>Durante l’applicazione di tag a un’esportazione, tieni presente quanto segue: <ul><li>I tag applicati possono essere filtrati o cercati nella tabella delle esportazioni.</li> <li>I tag applicati a un progetto non vengono applicati automaticamente durante l’esportazione di una tabella completa, come descritto in “Configurare le colonne nella pagina di esportazione” in [Gestire le esportazioni](/help/components/exports/manage-exports.md). In alternativa, quando [si pianifica un progetto completo per l&#39;esportazione](/help/analysis-workspace/export/t-schedule-report.md), tutti i tag applicati al progetto vengono automaticamente applicati all&#39;esportazione. </li></ul> |
   | Descrizione | Aggiungi una descrizione all’esportazione. Puoi scegliere di visualizzare le descrizioni come colonna nella [pagina Esportazioni](/help/components/exports/manage-exports.md) durante la visualizzazione delle esportazioni. |
   | Visualizzazione dati | Seleziona la visualizzazione dati che contiene i componenti da includere nell’esportazione. Il menu a discesa della visualizzazione dati ![Dati](/help/assets/icons/Data.svg) si trova nell&#39;angolo superiore sinistro della finestra di dialogo.  <p>**Nota:** se si seleziona una visualizzazione dati in cui mancano componenti già inclusi nella tabella dati, viene richiesto di cancellare e ricreare il pannello utilizzando i componenti inclusi nella visualizzazione dati selezionata. </p> |
   | Struttura dei dati | Visualizza la tabella a forma libera che stai esportando. Puoi modificare la struttura dati trascinando i componenti dal pannello di sinistra alla tabella. Puoi applicare un filtro trascinando un componente nell’area del filtro. La tabella viene aggiornata dinamicamente quando si aggiungono componenti all’area di lavoro. Puoi includere fino a 10 colonne.<p>Tutti i segmenti applicati all’intera tabella del progetto vengono visualizzati sopra la tabella. Puoi applicare un segmento o un gruppo di segmenti a un’esportazione.</p> |
   | Finestra rapporto | Seleziona l’intervallo di tempo di reporting da includere in ciascun file di esportazione. Le opzioni includono [!UICONTROL **Oggi**], **[!UICONTROL Ieri]**, **[!UICONTROL Ultimi 7 giorni]**, **[!UICONTROL Ultimi 30 giorni]**, **[!UICONTROL Questa settimana]** e **[!UICONTROL Questo mese]**. <p>Questa opzione non viene visualizzata se la **[!UICONTROL frequenza di esportazione]** è impostata su **[!UICONTROL Invia ora (una tantum)]**.</p> |
   | Cancella tutto | Cancella il contenuto della tabella dati. Questo consente di iniziare a creare una nuova tabella direttamente nella finestra di dialogo Nuova esportazione di tabella completa. |
   | Formato file | Scegli se i dati esportati devono essere in formato .csv, .json o .parquet. <p>Quando si sceglie il formato di file Parquet, i seguenti caratteri inclusi nei nomi dei componenti vengono sostituiti da un carattere di sottolineatura (_): <ul><li>&#39; &#39; - Spazio ASCII</li><li>&#39;,&#39; - virgola ASCII</li><li>&#39;;&#39; - Due punti ASCII</li><li>&#39;{&#39; o &#39;}&#39; - Parentesi graffa aperta/chiusa ASCII</li><li>&#39;(&#39; o &#39;)&#39; - Parentesi aperta/chiusa ASCII</li><li>&#39;\n&#39; - Nuova riga ASCII</li><li>&#39;\t&#39; - Scheda ASCII</li><li>&#39;=&#39; - ASCII è uguale a</li></ul></p> |
   | Includi file manifesto | Se questa opzione è abilitata, un file manifesto viene incluso in tutte le consegne di esportazione riuscite. <p>Il file manifesto consente di confermare che tutti i file sono stati consegnati correttamente. Include le seguenti informazioni:</p> <ul><li>Un elenco di tutti i file consegnati</li><li>Il checksum MD5 di ciascun file</li></ul><p>I dati esportati sono disponibili come file compresso nella destinazione cloud configurata, come descritto in [Configurare gli account di esportazione cloud](/help/components/exports/cloud-export-accounts.md) e [Configurare le posizioni di esportazione cloud](/help/components/exports/cloud-export-locations.md).</p><p>Il nome file del file compresso è il seguente, a seconda che si sia scelto **[!UICONTROL csv]**, **[!UICONTROL json]** o **[!UICONTROL parquet]** come formato file:</p><ul> <li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li><li>`cja-export-<instanceId>-<idx>.snappy.parquet`<p>Ogni colonna nel parquet è compressa.</p></li></ul><p>Scegliere il formato di file nel campo **[!UICONTROL Formato file]**.</p> |
   | Frequenza | Imposta la pianificazione per la frequenza con cui deve avvenire l’esportazione. <p>Puoi scegliere [!UICONTROL **Invia ora (una tantum)**] per inviare l’esportazione una sola volta. Quando selezioni questa opzione, l’esportazione viene avviata immediatamente.</p><p>In alternativa, puoi scegliere di inviare l’esportazione in base a una pianificazione definita. Quando si invia secondo una pianificazione, le opzioni includono **[!UICONTROL Giornaliero]**, **[!UICONTROL Settimanale]**, **[!UICONTROL Mensile per giorno della settimana]**, **[!UICONTROL Mensile per giorno del mese]**, **[!UICONTROL Annuale per giorno del mese]** e **[!UICONTROL Annuale per data specifica]**. </p> <p>Durante la selezione di una frequenza di esportazione, tieni in considerazione quanto segue:</p><ul><li>Le opzioni nel campo **[!UICONTROL Intervallo di lookback]** variano a seconda di ciò che selezioni qui.</li><li>Vengono visualizzati campi di configurazione aggiuntivi a seconda dell’opzione scelta.</li></ul> |
   | Data di inizio | Giorno e ora in cui dovrebbe iniziare l’esportazione pianificata. <p>Questa opzione è disponibile solo quando si sceglie una frequenza di esportazione pianificata.</p> |
   | Data di fine | Giorno e ora di scadenza dell’esportazione pianificata. L’esportazione pianificata non viene più eseguita dopo la data e l’ora impostate. <p>Questa opzione è disponibile solo quando si sceglie una frequenza di esportazione pianificata.</p> |
   | Visualizza le destinazioni per tutti gli utenti | Gli amministratori di sistema possono selezionare questa opzione per visualizzare tutti gli account e le posizioni, indipendentemente da chi li ha creati. |
   | Account | Seleziona l’account di esportazione cloud in cui desideri inviare i dati. <p>In alternativa, se non hai già configurato un account cloud da utilizzare, puoi configurare un nuovo account:<ol><li>Nel menu a discesa **[!UICONTROL Account]**, seleziona **[!UICONTROL Aggiungi account]**, quindi specifica le seguenti informazioni:<ul><li>**[!UICONTROL Nome account di posizione]**: specifica un nome per l’account di posizione. Questo nome viene visualizzato durante la creazione di una posizione </li><li>**[!UICONTROL Descrizione account di posizione]**: fornisci una breve descrizione dell’account per distinguerlo da altri account dello stesso tipo.</li><li>**Rendi l&#39;account disponibile a tutti gli utenti dell&#39;organizzazione**: seleziona questa opzione se desideri consentire ad altri utenti dell&#39;organizzazione di utilizzare l&#39;account.</li><li>**[!UICONTROL Tipo di account]**: seleziona il tipo di account cloud in cui desideri esportare i dati. I tipi di account disponibili sono Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e AEP Data Landing Zone.</li></ul><li>Per completare la configurazione dell’account, continua con il collegamento seguente corrispondente al **[!UICONTROL tipo di account]** selezionato:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Posizione | Seleziona la posizione dell’account in cui desideri inviare i dati di esportazione.<p>In alternativa, se non hai già configurato un account cloud da utilizzare, puoi configurare un nuovo account:<ol><li>Nel menu a discesa **[!UICONTROL Posizione]**, seleziona **[!UICONTROL Aggiungi posizione]**, quindi specifica le seguenti informazioni:<ul><li>**[!UICONTROL Nome]**: il nome della posizione.</li><li>**[!UICONTROL Descrizione]**: fornisci una breve descrizione della posizione per distinguerla da altre posizioni nell’account.</li><li>**Rendi la posizione disponibile a tutti gli utenti dell&#39;organizzazione**: seleziona questa opzione se desideri consentire ad altri utenti dell&#39;organizzazione di utilizzare la posizione.</li><li>**[!UICONTROL Account di posizione]**: seleziona l’account in cui desideri creare la posizione.</li></ul><li>Per completare la configurazione della posizione, continua con il collegamento seguente corrispondente al tipo di account selezionato nel campo **[!UICONTROL Account di posizione]**:<ul><li>[Data Landing Zone di AEP](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3 con ruolo ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |
   | Notifiche | Aggiungi utenti e gruppi ai quali desideri ricevere notifiche quando l&#39;esportazione non riesce o sta per scadere. Inizia a digitare il nome o l’indirizzo e-mail di un utente oppure inizia a digitare il nome di un gruppo, quindi selezionalo quando viene visualizzato nell’elenco a discesa. |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**] per salvare l’esportazione.

   I dati vengono inviati all’account cloud specificato alla frequenza specificata.

1. (Facoltativo) Dopo aver creato l’esportazione, che tu scelga di inviarla ora oppure in base a una pianificazione definita, puoi visualizzarla e gestirla nella [pagina Esportazioni](/help/components/exports/manage-exports.md) e visualizzarla nei [registri di esportazione](/help/components/exports/manage-export-logs.md).

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

* Esporta file in formato CSV, JSON o Parquet. (Disponibile anche con [altre opzioni di esportazione](/help/analysis-workspace/export/export-project-overview.md).)

* Esportare le tabelle che includono più dimensioni.

## Requisiti minimi

Assicurati che le tabelle, l’ambiente e le autorizzazioni soddisfino i seguenti requisiti:

* **Tabelle:** tutte le tabelle devono includere almeno una dimensione nella riga e una metrica in ogni colonna per essere supportate con un&#39;esportazione di tabella completa.

* **Ambiente:** verificare che gli [indirizzi IP](/help/technotes/ip-addresses.md) e i [domini](/help/technotes/domains.md) utilizzati da Customer Journey Analytics siano consentiti tramite il firewall dell’organizzazione.

* **Autorizzazioni:** In Adobe Admin Console, agli utenti deve essere assegnato un profilo di prodotto con l&#39;autorizzazione **[!UICONTROL Esportazione tabella completa]** assegnata per esportare tabelle complete. Per informazioni sull’assegnazione di un’autorizzazione a un profilo di prodotto in Admin Console, consulta [Autorizzazione Customer Journey Analytics in Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Gli utenti a cui è stato assegnato il [ruolo di amministratore di prodotto](/help/technotes/access-control.md#product-admin-role) hanno sempre accesso all’esportazione di tabelle complete; a questi utenti non è necessario assegnare l’autorizzazione **[!UICONTROL Esportazione tabella completa]**.


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
* L’ordinamento non è supportato per la maggior parte dei set di dati; i dati potrebbero essere ordinati per set di dati di piccole dimensioni.

## Componenti non supportati

I seguenti componenti non sono supportati e Analysis Workspace richiede di rimuoverli dalla tabella durante un’esportazione di tabella completa:

* Metriche calcolate che utilizzano funzioni non supportate nella definizione della metrica (vedere [Funzioni metriche calcolate non supportate](#unsupported-calculated-metric-functions) per ulteriori informazioni)
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

## Supporto delle funzioni metriche calcolate

Le sezioni di base e avanzate seguenti elencano le funzioni delle metriche calcolate supportate durante l’esportazione di tabelle complete:

### Supporto delle funzioni di base


| Funzione di base | Stato del supporto |
|---------|----------|
| Valore assoluto | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Massimo colonna | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Minimo colonna | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Somma colonna | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Conteggio | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Esponente | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Media | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Mediana | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Modulo | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Percentile | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Operatore di potenza | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Quartile | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Conteggio righe | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Massimo riga | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Minimo riga | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Somma righe | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Arrotondamento | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Radice quadrata | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Deviazione standard | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Varianza | ![StatusBlue](/help/assets/icons/StatusBlue.svg) pianificato |

### Supporto di funzioni avanzate

#### Funzioni algoritmiche

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Base logaritmo 10 (algebra esponenziale) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Radice cubica (algebra esponenziale) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Registro naturale (Algebra esponenziale) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Floor (algoritmo di regolazione numerica) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |

#### Funzioni logiche

| Funzione avanzata | Stato del supporto |
|---------|----------|
| If (Logica) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |

#### Funzioni booleane

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Not (logica dell&#39;operatore booleano) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Oppure (logica dell’operatore booleano) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| And (Logica Operatore Booleano) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |

#### Funzioni di confronto

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Minore di (logica di confronto) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Minore di o uguale a (logica di confronto) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Equal (Logica di confronto) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Maggiore di o uguale a (logica di confronto) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Maggiore di (logica di confronto) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Not Equal (Logica di confronto) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |


#### Funzioni trigonometriche

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Pi | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Seno (standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Coseno (standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Tangente (standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Arcoseno (Standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Arcocoseno (standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Arco tangente (standard) | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |

#### Funzioni iperboliche

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Coseno iperbolico | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Seno iperbolico | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |
| Tangente iperbolica | ![StatusGreen](/help/assets/icons/StatusGreen.svg) supportato |

#### Funzioni WASKR

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Affidabilità (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Affidabilità (inferiore) (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Affidabilità (superiore) (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |

#### Funzioni di distribuzione

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Punteggio T (Distribuzione T per studenti) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Test T (Distribuzione T di Student) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| CDF-T (Distribuzione T Student) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Punteggio Z (Distribuzione normale) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Test Z (distribuzione normale) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| CDF-Z (Distribuzione normale) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |

#### Funzioni di regressione

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Coefficiente di correlazione (regressione esponenziale) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Intercetta (regressione esponenziale) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Valore Y previsto (regressione esponenziale) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Pendenza (regressione esponenziale) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Coefficiente di correlazione (regressione lineare) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Intercetta (regressione lineare) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Valore Y previsto (regressione lineare) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Pendenza (regressione lineare) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Coefficiente di correlazione (regressione logaritmo) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Intercetta (regressione logaritmo) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Valore Y previsto (regressione logaritmo) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Pendenza (Regressione logaritmo) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Coefficiente di correlazione (regressione di potenza) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Intercetta (regressione di potenza) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Valore Y previsto (regressione di potenza) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Pendenza (regressione di potenza) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Coefficiente di correlazione (regressione quadratica) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Intercetta (regressione quadratica) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Previsione Y (Regressione Quadratica) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Pendenza (Regressione Quadratica) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Coefficiente di correlazione (regressione reciproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Intercetta (Regressione Reciproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Valore Y previsto (regressione reciproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |
| Pendenza (Regressione Reciproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) non supportato |

#### Altre funzioni avanzate

| Funzione avanzata | Stato del supporto |
|---------|----------|
| Conteggio distinto approssimativo | ![StatusBlue](/help/assets/icons/StatusBlue.svg) pianificato |
| Cumulativa | ![StatusBlue](/help/assets/icons/StatusBlue.svg) pianificato |
| Media cumulativa | ![StatusBlue](/help/assets/icons/StatusBlue.svg) pianificato |
| Incremento | ![StatusBlue](/help/assets/icons/StatusBlue.svg) pianificato |
| Varianza di esempio | ![StatusBlue](/help/assets/icons/StatusBlue.svg) pianificato |

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
