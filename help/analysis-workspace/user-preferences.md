---
title: Preferenze utente
description: Scopri come impostare le preferenze generali e di progetto per gli utenti.
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '3935'
ht-degree: 97%

---

# Preferenze utente

Puoi gestire le impostazioni o le preferenze dell’utente di Analysis Workspace e dei relativi componenti per tutti i nuovi progetti o pannelli creati. I progetti e i pannelli esistenti non sono interessati.

## Modifica preferenze

Puoi aggiornare le preferenze nei seguenti modi:

- Seleziona ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Edit preferences]** dall’interfaccia principale di Workspace.
- Seleziona **[!UICONTROL Project]** > **[!UICONTROL User preferences]** dal menu quando si lavora in un progetto Workspace.
- Seleziona **[!UICONTROL Components]** > **[!UICONTROL Preferences]** dalla barra dei menu superiore in Customer Journey Analytics (disponibile solo per gli amministratori di prodotto).

## Configurare le preferenze

Puoi configurare le seguenti preferenze:

### Preferenze generali

Le preferenze generali si applicano all’esperienza Customer Journey Analytics nel browser. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

| Preferenza | Opzioni |
| --- | --- |
| **[!UICONTROL Landing page]** | Scegli quale pagina visualizzare come pagina predefinita quando accedi a Customer Journey Analytics: <ul><li>Elenco progetti (impostazione predefinita)</li><li>Progetto vuoto</li><li>Analisi guidata delle tendenze vuota</li><li>Progetto specifico, selezionato da un elenco</li></ul> |
| **[!UICONTROL Tips]** | Visualizza i suggerimenti in una casella blu nell’area in basso a destra di Analysis Workspace. <p>L’opzione è abilitata per impostazione predefinita.</p> |
| **[!UICONTROL Components displayed in left panel groups]** | Scegli quanti elementi di ciascun gruppo di componenti visualizzare nel menu Componenti nel pannello di sinistra. <p>Se per un gruppo di componenti scegli 0, questo non sarà più accessibile dal pannello di sinistra.</p><p>Per impostazione predefinita, vengono visualizzati 5 componenti per ciascuno dei seguenti gruppi di componenti:</p> <ul><li>Dimensioni</li><li>Metriche</li><li>Segmenti</li><li>Intervalli di date</li></ul> <p>Per ulteriori informazioni sui componenti in Analysis Workspace, consulta la sezione [Panoramica dei componenti](/help/components/overview.md).</p> |

### Preferenze organizzazione IMS {#ims-organization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Consenti la condivisione solo con gli utenti di Workspace"
>abstract="Quando è abilitata, l’opzione **[!UICONTROL Share with anyone]** non è più disponibile per gli utenti che condividono un progetto Analysis Workspace. Le persone che in precedenza avevano ricevuto l’accesso a un progetto tramite questa opzione di condivisione non possono più accedere al progetto."

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Richiedere l’autenticazione Experience Cloud"
>abstract="Quando questa opzione è abilitata, le persone a cui viene dato accesso a un progetto dall’opzione **[!UICONTROL Share with anyone]** in Analysis Workspace devono autenticarsi utilizzando le credenziali di Experience Cloud."

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="Consenti commenti sui progetti"
>abstract="Quando questa opzione è abilitata, nella barra a destra di ciascun progetto in Analysis Workspace è disponibile un’area commenti."

<!-- markdownlint-enable MD034 -->

Puoi aggiornare le preferenze aziendali che si applicano a tutti gli utenti e ai progetti all’interno dell’organizzazione. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Scheda Modelli** | | |
|  | Nascondi scheda modelli | Nasconde la scheda Modelli per tutti gli utenti dell’organizzazione. |
| **Condivisione dei progetti** | | |
| | Consenti la condivisione solo con gli utenti di Workspace | Quando questa opzione è abilitata, gli utenti dell’organizzazione non possono visualizzare l’opzione **[!UICONTROL Share with anyone]** nel menu **[!UICONTROL Share]**. Ciò significa che gli utenti non possono condividere i progetti con persone che non dispongono di un account Analysis Workspace nell’organizzazione come descritto in [Condividere un progetto con chiunque (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).<br/>Questa opzione è disabilitata per impostazione predefinita per tutte le organizzazioni (gli utenti possono condividere i progetti con persone esterne all’organizzazione), ad eccezione della clientela che dispone di una licenza Healthcare Shield. <p>Quando abiliti o disabiliti questa opzione, prendi in considerazione quanto segue:<ul><li>Quando abiliti questa opzione, gli utenti che in precedenza avevano ricevuto l’accesso a un progetto tramite l’opzione di condivisione [!UICONTROL Share with anyone] non possono più accedere al progetto.</li><li>Se questa opzione è abilitata (per consentire la condivisione solo con gli utenti di Workspace) e viene successivamente disabilitata (per consentire la condivisione con chiunque), le persone che in precedenza hanno ricevuto l’accesso a un progetto tramite l’opzione di condivisione [!UICONTROL Share with anyone] non riottengono automaticamente l’accesso al progetto. In questo caso, l’utente che ha condiviso il progetto deve abilitare l’opzione [!UICONTROL **Il collegamento è attivo**] che è disponibile quando condividi un progetto con chiunque **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]**), come descritto in [Condividere un progetto con chiunque (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).</li><li>**Per chi dispone di una licenza Healthcare Shield:** questa opzione è attivata per impostazione predefinita e non può essere disattivata. Prima di poter disabilitare questa opzione in modo che gli utenti possano utilizzare l’opzione di condivisione [!UICONTROL Share with anyone], devi aggiungere l’autorizzazione [!UICONTROL Share project links with anyone] (che si trova in [!UICONTROL Reporting Tools]) in Adobe Admin Console. Dopo aver aggiunto l’autorizzazione, puoi disabilitare questa opzione, quindi accettarne l’avviso legale. Per informazioni su come aggiungere un’autorizzazione in Admin Console, consulta [Gestione delle autorizzazioni del prodotto in Admin Console](https://helpx.adobe.com/it/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Richiedere l’autenticazione Experience Cloud | Quando questa opzione è abilitata, gli utenti a cui viene concesso l&#39;accesso a un progetto dall&#39;opzione **[!UICONTROL Share with anyone]** in Analysis Workspace devono eseguire l&#39;autenticazione utilizzando le credenziali Experience Cloud.<p>Quando questa opzione è abilitata, ogni volta che un utente condivide un progetto utilizzando l’opzione di condivisione [!UICONTROL Share with anyone], l’opzione [!UICONTROL Require Experience Cloud authentication] è abilitata nella finestra di dialogo di condivisione e non può essere disabilitata dall’utente che condivide il progetto. Per informazioni su come gli utenti possono condividere i progetti con chiunque, consulta [Condividere un progetto con chiunque (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).) <p> <p>Quando abiliti questa opzione, prendi in considerazione quanto segue: <ul><li>Quando abiliti questa opzione, tutti i progetti precedentemente condivisi con l’opzione di condivisione [!UICONTROL Share with anyone] e per i quali non è abilitata l’opzione [!UICONTROL Require Experience Cloud authentication] vengono disattivati.<p>Se questa opzione è abilitata (per richiedere l’autenticazione Experience Cloud) e viene successivamente disabilitata (per consentire a chiunque disponga del collegamento di accedere al progetto), le persone che in precedenza hanno ricevuto l’accesso a un progetto tramite l’opzione di condivisione [!UICONTROL Share with anyone] non riottengono automaticamente l’accesso al progetto. In questo caso, l&#39;utente che ha condiviso il progetto deve abilitare l&#39;opzione [!UICONTROL Link is active] disponibile quando condivide un progetto con qualcuno **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]** > **[!UICONTROL Link is active]**), come descritto in [Condividere un progetto con qualcuno (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).</li><li>Questa opzione è disponibile solo se SSO è implementato nell’organizzazione. Per informazioni su come gli amministratori di sistema possono abilitare SSO per l’organizzazione, consulta [Configurare identità e Single Sign-On](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html).</p><p>Se SSO è configurato per l’organizzazione, verifica se nella console è implementato qualsiasi tipo di creazione automatica dell’account. In genere, questa configurazione viene configurata da un amministratore di sistema, come descritto in [Abilitare la creazione automatica dell’account](https://helpx.adobe.com/it/enterprise/using/automatic-account-creation.html).</li><li>Se l’organizzazione dispone della licenza Healthcare Shield, questa opzione è abilitata per impostazione predefinita e non può essere disabilitata.</li></ul> |
| Commenti sul progetto | Consenti commenti sui progetti | **Nota:** questa funzionalità è attualmente in fase di test e potrebbe non essere ancora disponibile nel tuo ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Customer Journey Analytics, consulta [Rilascio delle funzioni di Customer Journey Analytics](/help/release-notes/releases.md). <p>Quando questa opzione è abilitata, nella barra a destra di ciascun progetto in Analysis Workspace è disponibile un’area commenti.</p> <p>I proprietari dei progetti possono disabilitare l’area commenti per un determinato progetto, come descritto in [Creare progetti](/help/analysis-workspace/build-workspace-project/create-projects.md).</p> <p>Per ulteriori informazioni sui commenti nei progetti Analysis Workspace, consulta [Aggiungere e gestire i commenti nei progetti](/help/analysis-workspace/build-workspace-project/comment-projects.md).</p> |

{style="table-layout:auto"}

### Preferenze Progetti e Analisi {#project-and-analysis-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="Palette categorica"
>abstract="Applicata a molte visualizzazioni in Analysis Workspace e nell’analisi guidata. Ogni colore rappresenta un valore di categoria distinto."

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="Palette divergente"
>abstract="Applicata alla tabella coorte in Analysis Workspace e nell’analisi guidata della crescita degli utenti. Questa palette contiene un significato numerico con due estremi e una linea di base al centro."

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="Palette sequenziale"
>abstract="Applicata all’analisi guidata delle tendenze di frequenza (barre sovrapposte). Questa palette contiene un significato numerico che va dal chiaro allo scuro."

Puoi personalizzare queste preferenze per tutti i nuovi progetti e pannelli Analysis Workspace e le nuove analisi guidate. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per singoli progetti in Analysis Workspace, come descritto nella [Panoramica sui progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Visualizzazione** | | |
|  | [Densità di visualizzazione](/help/analysis-workspace/build-workspace-project/view-density.md) | Scegli il contenuto da visualizzare sullo schermo riducendo la spaziatura verticale del pannello di sinistra, tabelle a forma libera e tabelle coorte. <ul><li>Compatta</li><li>Comoda</li><li>Espansa (impostazione predefinita)</li></ul> |
| | [Tavolozza dei colori](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Scegli le palette di colori di visualizzazione utilizzate in Analysis Workspace e nell’analisi guidata. <ul><li> Palette per categorie: applicata a molte visualizzazioni in Analysis Workspace e nell’analisi guidata. Ogni colore rappresenta un valore di categoria distinto. Scegli tra le opzioni fornite da Adobe o immetti una palette personalizzata definita da valori esadecimali delimitati da virgole.</li><li> Palette divergente: applicata alla tabella coorte in Analysis Workspace e nell’analisi guidata della crescita degli utenti. Questa palette contiene un significato numerico con due estremi e una linea di base al centro.<li> Palette sequenziale: applicata all’analisi guidata delle tendenze di frequenza (barre sovrapposte). Questa palette contiene un significato numerico che va dal chiaro allo scuro.</li></ul> |
| **Dati** | | |
|  | [Visualizzazione dati](/help/analysis-workspace/c-panels/panels.md#data-view) | Scegli i dati da cui le tabelle e le visualizzazioni ricavano i propri dati. <ul><li>Più recente (impostazione predefinita)</li><li>Visualizzazione dati specifica selezionata da un elenco</li></ul> |
|  | [Calendario](/help/analysis-workspace/c-panels/panels.md#calendar) | Seleziona da un elenco di: <ul><li>Intervalli forniti da Adobe (l’impostazione predefinita è Questo mese)</li><li>Puoi abilitare [!UICONTROL Make date range components relative to panel calendar by default].</li></ul> |
|  | [Tipo di pannello](/help/analysis-workspace/c-panels/panels.md#panel-types) | <ul><li>A forma libera (impostazione predefinita)</li><li>Vuoto</li><li>Quick Insights</li></ul> |
|  | Conteggio istanze | Abilita [!UICONTROL Count repeat instances] per specificare se le istanze ripetute sono conteggiate nei rapporti. Ad esempio, se questa opzione è abilitata, più visualizzazioni consecutive della stessa pagina vengono trattate come visualizzazioni di più pagine. Se questa opzione è disabilitata, più visualizzazioni consecutive della stessa pagina vengono conteggiate come una singola pagina. <p>**Nota:** questa impostazione influisce solo su determinate metriche (ad esempio Sessioni) e non si applica alle visualizzazioni Flusso o Fallout.</p> |
|  | Formato dei numeri | <ul><li>1.000,00 (impsotazione predefinita)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Carattere separatore CSV | <ul><li>Virgola (impostazione predefinita)</li><li>Punto e virgola</li><li>Due punti</li><li>Barra verticale</li><li>Punto</li><li>Spazio</li><li>Scheda</li></ul> |
|  | Mostra annotazioni | Scegli se rendere visibili le annotazioni nei progetti. Per ulteriori informazioni sulle annotazioni, consulta la sezione [Panoramica delle annotazioni](/help/components/annotations/overview.md). |


### Preferenze delle tabelle a forma libera {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="Mostra anomalie"
>abstract="Selezionando **[!UICONTROL Show anomalies]** verrà automaticamente eseguito il rilevamento delle anomalie sulla prima colonna di metriche aggiunta a una visualizzazione Tabella a forma libera di una serie temporale."

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="Mostra previsione"
>abstract="Selezionando **[!UICONTROL Show forecast]** verrà automaticamente eseguita la previsione sulla prima colonna di metriche aggiunta a una visualizzazione Tabella a forma libera di una serie temporale."


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="Metrica tabella predefinita"
>abstract="Seleziona la metrica predefinita da utilizzare per le tabelle a forma libera. Se la visualizzazione dati selezionata non contiene la metrica predefinita selezionata, la tabella passa automaticamente a un’altra metrica primaria."


Puoi personalizzare le preferenze delle tabelle a forma libera per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per singole tabelle.

Seleziona i titoli della sezione collegata per ulteriori informazioni e contesto sulle preferenze disponibili.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Tabella** | | |
| | Tipo di tabella | <ul><li>A forma libera</li><li>Generatore di tabelle</li></ul> |
| | Metrica tabella predefinita | <ul><li>Eventi</li><li>Sessioni</li><li>Persone</li></ul> |
| | Dimensioni della tabella predefinita | Scegli tra Minuto, Ora, Giorno, Settimana, Mese, Trimestre o Anno. |
| | Allinea date | Seleziona questa opzione per allineare le date di ogni colonna affinché inizino tutte sulla stessa riga. |
| **[Colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Testo a capo nelle intestazioni | Consente di mandare automaticamente a capo il testo delle intestazioni nelle tabelle a forma libera, per agevolare la lettura delle intestazioni e la condivisione delle tabelle. Questa opzione è utile per la creazione di file PDF e per le metriche con nomi lunghi. È attivata per impostazione predefinita. |
| | Mostra totali | Questo numero relativo ai totali è in genere uguale o un sottoinsieme del [!UICONTROL Grand Total]. Riflette eventuali segmenti di tabella applicati all’interno della tabella a forma libera, inclusa l’opzione [!UICONTROL Include None]. |
| | Mostra totali complessivi | Questi totali rappresentano tutti gli eventi che sono stati raccolti, talvolta denominati *totale della visualizzazione dati*. Quando un segmento viene applicato a livello di pannello o nella tabella a forma libera, il totale viene regolato in modo da riflettere tutti gli eventi che corrispondono ai criteri del segmento. Il totale complessivo non è supportato per tabelle o raggruppamenti con [righe statiche](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Mostra sparkline | Mostra o nascondi i grafici a linee nella parte inferiore del grafico. Quando è nascosta, la legenda non fa più riferimento visivamente alle linee. |
| | Numero | Determina se mostrare/nascondere il valore numerico di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore numerico corrisponde al numero di visualizzazioni di pagina per l’elemento riga. |
| | Percentuale | Determina se mostrare o nascondere il valore percentuale di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni pagina, il valore percentuale corrisponde al numero di visualizzazioni pagina per l’elemento della riga, diviso per il totale di visualizzazioni pagina per la colonna.  Nota: per garantire una maggiore precisione, è possibile visualizzare percentuali superiori al 100%. Inoltre, abbiamo spostato il limite superiore al 1000% per assicurare che le colonne possano crescere anche in larghezza. |
| | Mostra anomalie <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Determina se eseguire il rilevamento delle anomalie sui valori di questa colonna. |
| | Mostra previsione | Determina se i valori di previsione vengono visualizzati automaticamente per la prima colonna di metriche in qualsiasi tabella a forma libera con serie temporale creata. |
| | Interpret zero as no value (Interpreta zero come nessun valore) | Per le celle con valore 0, determina se visualizzare 0 oppure la cella vuota. Questa funzione è particolarmente utile se si esaminano i dati quotidianamente e il mese in corso non è ancora terminato.  Invece di visualizzare valori 0 per le date future, è possibile sostituirli con delle celle vuote. Anche i grafici si adeguano a questa impostazione (ad esempio, non mostrano una linea o una barra con valore 0 quando questa opzione è selezionata). |
| | Informazioni di base | Determina se mostrare o nascondere tutta la formattazione della cella, inclusi il grafico a barre e la formattazione condizionale <ul><li>Grafico a barre</li> Visualizza un grafico a barre orizzontale che rappresenta il valore della cella rispetto al totale della colonna. <li>Formattazione condizionale</li>Per ulteriori informazioni sulla formattazione condizionale, consulta la sezione “Formattazione condizionale” in [Impostazioni colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Anteprima cella | Mostra un’anteprima di ciascuna cella con le opzioni di formattazione attualmente selezionate attive. |
| **[Riga](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Raggruppamento per posizione | Seleziona questa opzione per far sì che il raggruppamento rimanga nella posizione dell’elemento anziché nell’elemento stesso. Per ulteriori informazioni sulle suddivisioni, consulta la sezione [Suddividere le dimensioni](/help/components/dimensions/t-breakdown-fa.md). |
| | Calcolo percentuale | <ul><li>Colonna</li><li>Riga</li></ul> |
| | Totali colonne (solo righe statiche) | <ul><li>Visualizza somma di righe: mostra la somma dei singoli elementi di riga </li><li>Visualizza totale complessivo: mostra la somma deduplicata di righe.</li></ul> |

### Preferenze delle visualizzazioni {#visalization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultflowcontainer"
>title="Contenitore predefinito"
>abstract="Seleziona il contenitore predefinito da utilizzare per le visualizzazioni [!UICONTROL Flow]. Se la visualizzazione dati selezionata non contiene il contenitore predefinito selezionato, la visualizzazione [!UICONTROL Flow] passa automaticamente a un altro contenitore principale."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultfalloutcontainer"
>title="Contenitore predefinito"
>abstract="Seleziona il contenitore predefinito da utilizzare per le visualizzazioni [!UICONTROL Fallout]. Se la visualizzazione dati selezionata non contiene il contenitore predefinito selezionato, la visualizzazione [!UICONTROL Fallout] passa automaticamente a un altro contenitore primario."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulthistogramcountingmethod"
>title="Metodo di conteggio predefinito"
>abstract="Seleziona il metodo di conteggio predefinito da utilizzare per le visualizzazioni [!UICONTROL Histogram]. Se la visualizzazione dati selezionata non contiene il metodo di conteggio predefinito selezionato, la visualizzazione [!UICONTROL Histogram] passa automaticamente a un altro metodo di conteggio primario."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultjourneycanvascontainer"
>title="Contenitore predefinito"
>abstract="Seleziona il contenitore predefinito da utilizzare per le visualizzazioni [!UICONTROL Journey canvas]. Se la visualizzazione dati selezionata non contiene il contenitore predefinito selezionato, la visualizzazione [!UICONTROL Journey canvas] passa automaticamente a un altro contenitore primario."


Puoi aggiornare le preferenze di visualizzazione per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per le singole visualizzazioni.

Seleziona i titoli della sezione collegata per ulteriori informazioni e contesto sulle preferenze disponibili.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Impostazioni predefinite generali** | | |
| | Percentuali | Visualizza i valori in percentuale per tutte le visualizzazioni. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliato per tutte le visualizzazioni. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X per tutte le visualizzazioni. Questa preferenza può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Visualizza asse doppio (se applicabile) | Applicabile solo in presenza di due metriche: puoi avere un asse Y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa preferenza è utile quando le metriche tracciate sono di entità molto diversa. |
| | Normalizzazione (se applicabile) | Applica alle metriche le stesse proporzioni. Questa preferenza è utile quando le metriche tracciate sono di entità molto diversa. |
| | Ancoraggio asse Y su zero | Se tutti i valori tracciati sul grafico sono notevolmente al di sopra dello zero, per impostazione predefinita il grafico viene aggiornato facendo iniziare l’asse y da un valore DIVERSO DA ZERO. Se questa casella è selezionata, l’asse y inizierà comunque dallo zero (e il grafico viene ritracciato). |
| | Consenti alle anomalie di ridimensionare l’asse Y | L’asse y viene ridimensionato tenendo conto dei valori di anomalie. |
| **[Linee](/help/analysis-workspace/visualizations/line.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni delle linee. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione delle linee. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione delle linee. Questa preferenza può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Visualizza asse doppio (se applicabile) | Applicabile solo in presenza di due metriche: puoi avere un asse Y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa preferenza è utile quando le metriche tracciate sono di entità molto diversa. |
| | Normalizzazione (se applicabile) | Applica alle metriche le stesse proporzioni. Questa preferenza è utile quando le metriche tracciate sono di entità molto diversa. |
| | Mostra asse x | Visualizza l’asse x sul grafico a linee. |
| | Mostra asse y | Visualizza l’asse y sul grafico a linee. |
| | Ancora asse Y | Se tutti i valori tracciati sul grafico sono notevolmente al di sopra dello zero, per impostazione predefinita il grafico viene creato facendo iniziare l’asse y da un valore DIVERSO DA ZERO. Se questa casella è selezionata, l’asse y inizia comunque dallo zero (e il grafico viene ritracciato). |
| | Consenti alle anomalie di dimensionare l’asse Y | Se in un grafico sono presenti più metriche, passa il puntatore su ogni valore anomalo per visualizzare la relativa banda di valori affidabili. Per rendere la visualizzazione più leggibile, l’intervallo di confidenza del rilevamento delle anomalie non dimensiona automaticamente l’asse y. Questa impostazione consente all’intervallo di affidabilità di dimensionare la visualizzazione. <p>Per ulteriori informazioni, consulta la sezione [Visualizzare le anomalie in Analysis Workspace](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| | Consenti previsione per ampliare l’asse Y | Se i valori di previsione non rientrano nei limiti superiore e inferiore dei valori storici, l’asse y non viene ridimensionato automaticamente per tali valori previsti. Quando questa opzione è attivata, l’asse y viene ridimensionata correttamente per i valori previsti. |
| | Mostra min | Un’etichetta del valore minimo viene aggiunta in sovrapposizione per evidenziare rapidamente i punti minimi (o valli) di una metrica. Nota: i valori minimi sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione. |
| | Mostra max | Un’etichetta del valore massimo viene aggiunta in sovrapposizione per evidenziare rapidamente i punti massimi (o picchi) di una metrica. Nota: i valori massimi sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione. |
| | Mostra linea di tendenza | Mostra una linea di tendenza di regressione o media mobile della serie di linee. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati. |
| **[Coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>Contenitore | Seleziona il contenitore preferito per l’analisi per coorte in caso di connessione [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} basata su account. <p>Sono disponibili le seguenti opzioni:</p> <ul><li>Account globali [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Gruppi acquisti [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Opportunità [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Persona</li></ul> |
| | Granularità | Per le visualizzazioni con tendenze, puoi modificare la granularità temporale (giorno, settimana, mese, trimestre o anno). Questa modifica si applica anche alla tabella dell’origine dati. |
| | Mostra solo percentuale | Rimuove il valore numerico e visualizza solo la percentuale. |
| | Arrotonda percentuale a intero più prossimo | Arrotonda il valore percentuale al numero intero più vicino invece di mostrare il valore decimale. |
| | Mostra riga percentuale media | Inserisce una nuova riga nella parte superiore della tabella, quindi aggiunge la media dei valori all’interno di ogni colonna. |
| **[Grafici combinati](/help/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Mostra asse X | Visualizza l’asse x sul grafico combinato. |
| | Mostra asse Y | Visualizza l’asse y sul grafico combinato. |
| | Visualizza i manubri sulle linee | Mostra i manubri sulle linee nei grafici combinati. |
| **[Riepilogo delle metriche chiave](/help/analysis-workspace/visualizations/key-metric.md)** | | |
| | Tipo di visualizzazione sintetico | <ul><li>Enfatizza la variazione percentuale</li><li>Enfatizza il valore numerico</li></ul> |
| | Mostra sparkline | Mostra o nascondi i grafici a linee nella parte inferiore del grafico. Quando è nascosta, la legenda non fa più riferimento visivamente alle linee. |
| | Mostra max e min su sparkline | Mostra i valori minimi e massimi nei grafici a linee principali e a linee di confronto. |
| | Mostra confronto | Mostra i dati di confronto. Quando sono nascosti, non vengono visualizzati gli oggetti Grafico a linee di confronto e Variazione di riepilogo. |
| | Opzioni per valore numerico | Nella sezione [!UICONTROL **Riepilogo delle metriche chiave**] <ul><li>Mostra variazione percentuale</li><li>Mostra differenza grezza</li>Differenza non elaborata tra il valore totale della metrica nell’intervallo di date principale e l’intervallo di date secondario</ul> |
| **[Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Contenitore | Seleziona il contenitore preferito per analizzare i percorsi. Il contenitore preferito ti aiuta a comprendere il coinvolgimento dell’account a vari livelli di contenitore B2B [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, il coinvolgimento della persona a livello di persona (tra sessioni) o a vincolare l’analisi a una singola sessione. <p>Sono disponibili le seguenti opzioni:</p> <ul><li>Account globali [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Gruppi acquisti [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Opportunità [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Sessione</li><li>Persona</li></ul> |
| **[Flusso](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Contenitore | Seleziona il contenitore preferito da analizzare. Il contenitore preferito ti aiuta a comprendere il coinvolgimento dell’account a vari livelli di contenitore B2B [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, il coinvolgimento della persona a livello di persona (tra sessioni) o a vincolare l’analisi a una singola sessione. <p>Sono disponibili le seguenti opzioni:</p> <ul><li>Account globali [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Gruppi acquisti [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Opportunità [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Sessione</li><li>Persona</li></ul> |
| | Etichette wrap | Di norma, le etichette degli elementi di Flusso vengono troncate per risparmiare spazio sullo schermo, ma selezionando questa casella puoi rendere visibile l’intera etichetta. Impostazione predefinita = non selezionata. |
| | Includi istanze ripetute | Le visualizzazioni di Flusso si basano su istanze di una dimensione. Questa impostazione offre la possibilità di includere o escludere istanze ripetute, ad esempio i ricaricamenti delle pagine. Tuttavia, le ripetizioni non possono essere rimosse dalle visualizzazioni Flusso che includono dimensioni con più valori, come listVars, listProp, s.product, eVar di merchandising, ecc. Impostazione predefinita = non selezionata. |
| | Mostra descrizioni comandi | Determina se visualizzare le descrizioni comandi contenenti i dati dei nodi quando si passa il puntatore del mouse sui singoli nodi all’interno di una visualizzazione del flusso. |
| | Numero di colonne | Determina il numero di colonne desiderato nel diagramma di flusso. |
| | Elementi espansi per colonna | Il numero di elementi che desideri inserire in ogni colonna. |
| **[Area di lavoro del percorso](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)** | | |
| | Contenitore | Seleziona il contenitore preferito per analizzare i percorsi. Il contenitore preferito ti aiuta a comprendere il coinvolgimento dell’account a vari livelli di contenitore B2B [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, il coinvolgimento della persona a livello di persona (tra sessioni) o a vincolare l’analisi a una singola sessione. <p>Sono disponibili le seguenti opzioni:</p> <ul><li>Account globali [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Gruppi acquisti [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Opportunità [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}</li><li>Sessione</li><li>Persona</li></ul> |
| **Grafici sovrapposti** | | |
| | Sovrapposizione 100% | Applicata alle visualizzazioni Superfici sovrapposte, Barre sovrapposte o Barre orizzontali sovrapposte, questa impostazione converte il grafico in una visualizzazione con sovrapposizione 100%. <p>Per ulteriori informazioni, consulta [Barre e barre sovrapposte](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Istogramma](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | Numero di bucket | Scegli il numero di intervalli di date (bucket) nella visualizzazione. Il numero massimo consentito è 50. <p>Per ulteriori informazioni, consulta la sezione [Istogramma](/help/analysis-workspace/visualizations/histogram.md).</p> |
| | Metodo di conteggio | Scegli tra le seguenti opzioni: <ul><li>Hit</li><li>Sessione</li><li>Persona</li></ul> <p>Ad esempio, se utilizzato insieme alle visualizzazioni di pagina, puoi scegliere le visualizzazioni di pagina per persona, per visita o per evento. Per Hit, “Occorrenze” viene usato come metrica dell’asse y in una tabella a forma libera.</p> |
| **[Variazione di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Valore | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Variazione percentuale</li><li>Differenza grezza</li></ul> |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Variazione di riepilogo. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Variazione di riepilogo. |
| **[Numero di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Numero di riepilogo. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Numero di riepilogo. |
| | Valore di riepilogo per | Scegli tra Max, Min, Medio, Mediana e Somma. |
| | Abbrevia il valore | Nella sezione **[!UICONTROL Summary Number]** |
| **[Mappa ad albero](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Mappa ad albero. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione Mappa ad albero. Questa preferenza può essere utile se disponi di un set di dati di grandi dimensioni. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** | | |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Venn. |
| **[A dispersione](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni A dispersione. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione A dispersione. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione A dispersione.  Questa preferenza può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Ancoraggio asse Y su zero | Se tutti i valori tracciati sul grafico sono notevolmente al di sopra dello zero, per impostazione predefinita il grafico viene creato facendo iniziare l’asse y da un valore DIVERSO DA ZERO. Se questa casella è selezionata, l’asse y inizierà comunque dallo zero (e il grafico viene ritracciato). |

## Ripristina preferenze predefinite

Puoi ripristinare tutte le preferenze utente alle impostazioni predefinite del sistema. Questa preferenza non influisce sulle preferenze impostate dall’amministratore nella scheda Azienda.

Questa azione non può essere annullata.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] **>** [!UICONTROL **Preferenze**] dal menu principale. In alternativa, seleziona **[!UICONTROL Project]** > **[!UICONTROL User settings]** dal menu Workspace.

1. In alto a destra, seleziona **[!UICONTROL Restore defaults]**.

1. Seleziona **[!UICONTROL Restore defaults]** in **[!UICONTROL Restore system default settings]**.

## [!UICONTROL Dark theme]

Se preferisci uno sfondo scuro per l’interfaccia utente di Customer Journey Analytics, puoi passare a [!UICONTROL Dark theme].

1. Seleziona l’icona utente Experience Cloud in alto a destra.

   ![tema scuro](assets/dark-theme.png)

1. Abilita **[!UICONTROL Dark theme]**.

