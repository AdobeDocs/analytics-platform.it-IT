---
title: Come impostare le preferenze utente in Analysis Workspace
description: Puoi impostare le preferenze generali e di progetto per gli utenti.
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '3355'
ht-degree: 74%

---

# Preferenze utente

Puoi gestire le impostazioni o le preferenze utente per Analysis Workspace e i componenti correlati per tutti i nuovi progetti o pannelli creati. I progetti e i pannelli esistenti non sono interessati.

## Aggiornare le preferenze

Puoi aggiornare le tue preferenze nei seguenti modi:

- Selezionare ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Edit preferences]** dall&#39;interfaccia principale di Workspace.
- Selezionare **[!UICONTROL Project]** > **[!UICONTROL User preferences]** dal menu quando si lavora in un progetto Workspace.
- Selezionare **[!UICONTROL Components]** > **[!UICONTROL Preferences]** dalla barra superiore principale del Customer Journey Analytics (disponibile solo per gli amministratori di prodotto).

## Configurare le preferenze

Puoi configurare le seguenti preferenze:

### Preferenze generali

Le preferenze generali si applicano all’esperienza Customer Journey Analytics nel browser. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

| Preferenza | Opzioni |
| --- | --- |
| **[!UICONTROL Landing page]** | Scegliere la pagina da visualizzare come pagina predefinita quando si accede al Customer Journey Analytics: <ul><li>Elenco progetti (impostazione predefinita)</li><li>Progetto vuoto</li><li>Analisi guidata tendenze vuota</li><li>Progetto specifico, selezionato da un elenco</li></ul> |
| **[!UICONTROL Tips]** | Visualizza i suggerimenti in una casella blu nell’area in basso a destra di Analysis Workspace. <p>L’opzione è abilitata per impostazione predefinita.</p> |
| **[!UICONTROL Components displayed in left panel groups]** | Scegliete il numero di ciascun gruppo di componenti da visualizzare nel menu Componenti nel pannello a sinistra. <p>Se scegli 0 per un gruppo di componenti, questo non sarà più accessibile dal pannello a sinistra.</p><p>Per impostazione predefinita, vengono visualizzati 5 componenti per ciascuno dei seguenti gruppi di componenti:</p> <ul><li>Dimensioni</li><li>Metriche</li><li>Filtri</li><li>Intervalli di date</li></ul> <p>Per ulteriori informazioni sui componenti in Analysis Workspace, consulta la sezione [Panoramica dei componenti](/help/components/overview.md).</p> |

### Preferenze organizzazione IMS {#ims-organization-preferences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_shareonlyworkspace"
>title="Consenti condivisione solo con gli utenti di Workspace"
>abstract="Quando è abilitata, l&#39;opzione **[!UICONTROL Share with anyone]** non è più disponibile per gli utenti che condividono un progetto Analysis Workspace. Le persone che in precedenza avevano ricevuto l’accesso a un progetto tramite questa opzione di condivisione non possono più accedere al progetto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_requireexperiencecloudauth"
>title="Richiedere autenticazione Experience Cloud"
>abstract="Quando questa opzione è abilitata, gli utenti a cui viene dato accesso a un progetto dall’opzione Condividi con chiunque in Analysis Workspace devono eseguire l’autenticazione utilizzando le credenziali di Experience Cloud."

<!-- markdownlint-enable MD034 -->


Puoi aggiornare le preferenze aziendali che si applicano a tutti gli utenti e ai progetti all’interno dell’organizzazione. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Condivisione dei progetti** | | |
| | Consenti condivisione solo con gli utenti di Workspace | Quando questa opzione è abilitata, gli utenti dell&#39;organizzazione non possono visualizzare l&#39;opzione **[!UICONTROL Share with anyone]** nel menu **[!UICONTROL Share]**. Ciò significa che gli utenti non possono condividere i progetti con persone che non hanno un account Analysis Workspace nell’organizzazione come descritto in [Condividere un progetto con chiunque (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).<br/>Questa opzione è disabilitata per impostazione predefinita per tutte le organizzazioni (ovvero gli utenti possono condividere i progetti con persone esterne all&#39;organizzazione) ad eccezione dei clienti con licenza Healthcare Shield. <p>Quando abiliti o disabiliti questa opzione, prendi in considerazione quanto segue:<ul><li>Se si abilita questa opzione, gli utenti che in precedenza hanno ricevuto l&#39;accesso a un progetto tramite l&#39;opzione di condivisione [!UICONTROL Share with anyone] non potranno più accedere al progetto.</li><li>Se questa opzione è abilitata (per consentire solo la condivisione con gli utenti di Workspace) e successivamente disabilitata (per consentire la condivisione con chiunque), gli utenti che in precedenza hanno ricevuto l&#39;accesso a un progetto tramite l&#39;opzione di condivisione [!UICONTROL Share with anyone] non recuperano automaticamente l&#39;accesso al progetto. In questo caso, l&#39;utente che ha condiviso il progetto deve abilitare l&#39;opzione [!UICONTROL **Il collegamento è attivo**] disponibile quando condivide un progetto con qualcuno **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]**), come descritto in [Condividere un progetto con qualcuno (non è richiesto l&#39;accesso)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).</li><li>**Per i clienti che dispongono di una licenza Healthcare Shield:** questa opzione è attivata per impostazione predefinita e non può essere disattivata. Prima di poter disabilitare questa opzione per consentire agli utenti di utilizzare l&#39;opzione di condivisione [!UICONTROL Share with anyone], è necessario aggiungere l&#39;autorizzazione [!UICONTROL Share project links with anyone] (che si trova in [!UICONTROL Reporting Tools]) in Adobe Admin Console. Dopo aver aggiunto l’autorizzazione, puoi disabilitare questa opzione, quindi accettarne l’avviso legale. Per informazioni su come aggiungere un’autorizzazione in Admin Console, consulta [Gestione delle autorizzazioni del prodotto in Admin Console](https://helpx.adobe.com/it/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Richiedere autenticazione Experience Cloud | Quando questa opzione è abilitata, gli utenti a cui viene dato accesso a un progetto dall’opzione Condividi con chiunque in Analysis Workspace devono eseguire l’autenticazione utilizzando le credenziali di Experience Cloud.<p>Quando questa opzione è abilitata, ogni volta che un utente condivide un progetto utilizzando l&#39;opzione di condivisione [!UICONTROL Share with anyone], l&#39;opzione [!UICONTROL Require Experience Cloud authentication] viene abilitata nella finestra di dialogo di condivisione e non può essere disabilitata dall&#39;utente che condivide il progetto. Per informazioni su come gli utenti possono condividere i progetti con altri utenti, vedi [Condividere un progetto con altri utenti (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md). <p> <p>Quando abiliti questa opzione, prendi in considerazione quanto segue: <ul><li>Quando si abilita questa opzione, tutti i progetti precedentemente condivisi con l&#39;opzione di condivisione [!UICONTROL Share with anyone] e per i quali l&#39;opzione [!UICONTROL Require Experience Cloud authentication] non è abilitata vengono disattivati.<p>Se questa opzione è abilitata (per richiedere l&#39;autenticazione Experience Cloud) e successivamente disabilitata (per consentire a chiunque disponga del collegamento di accedere al progetto), gli utenti che in precedenza hanno ricevuto l&#39;accesso a un progetto tramite l&#39;opzione di condivisione [!UICONTROL Share with anyone] non recuperano automaticamente l&#39;accesso al progetto. In questo caso, l&#39;utente che ha condiviso il progetto deve abilitare l&#39;opzione [!UICONTROL Link is active]*disponibile quando condivide un progetto con qualcuno **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]** > **[!UICONTROL Link is active]**), come descritto in [Condividere un progetto con qualcuno (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).</li><li>Questa opzione è disponibile solo se SSO è implementato nell’organizzazione. Per informazioni su come gli amministratori di sistema possono abilitare SSO per l&#39;organizzazione, vedere [Configurare identità e Single Sign-On](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html).</p><p>Se SSO è configurato per l’organizzazione, verifica se nella console è implementato qualsiasi tipo di creazione automatica dell’account. In genere questa configurazione viene configurata da un amministratore di sistema, come descritto in [Abilita creazione automatica account](https://helpx.adobe.com/it/enterprise/using/automatic-account-creation.html).</li><li>Se l’organizzazione concede la licenza Healthcare Shield, questa opzione è abilitata per impostazione predefinita e non può essere disabilitata.</li></ul> |

{style="table-layout:auto"}

### Preferenze Progetti e Analisi {#project-and-analysis-preferences}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_categoricalpalette"
>title="Tavolozza categorica"
>abstract="Applicato a molte visualizzazioni in Analysis Workspace e analisi guidata. Ogni colore rappresenta un valore categorico distinto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_divergingpalette"
>title="Tavolozza divergente"
>abstract="Applicato alla tabella coorte nell’analisi guidata della crescita di Analysis Workspace e utente. Questa palette contiene un significato numerico con due estremi e una linea di base al centro."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_sequentialpalette"
>title="Tavolozza sequenziale"
>abstract="Applicato all&#39;analisi guidata delle tendenze di frequenza (barre sovrapposte). Questa palette contiene un significato numerico che va dal chiaro allo scuro."

<!-- markdownlint-enable MD034 -->


Puoi personalizzare queste preferenze per tutti i nuovi progetti e pannelli Analysis Workspace e le nuove analisi guidate. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per singoli progetti in Analysis Workspace, come descritto nella [Panoramica sui progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Visualizzazione** | | |
|  | [Densità di visualizzazione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=it) | Scegli la quantità di contenuto da visualizzare sullo schermo riducendo la spaziatura verticale del pannello sinistro, delle tabelle a forma libera e delle tabelle a coorte. <ul><li>Compatta</li><li>Comoda</li><li>Espansa (impostazione predefinita)</li></ul> |
| | [Tavolozza dei colori](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=it) | Scegli le palette di colori di visualizzazione utilizzate in Analysis Workspace e nell’analisi guidata. <ul><li> Palette per categorie: applicata a molte visualizzazioni in Analysis Workspace e nell’analisi guidata. Ogni colore rappresenta un valore di categoria distinto. Scegli tra le opzioni fornite da Adobe o immetti una palette personalizzata definita da valori esadecimali delimitati da virgole.</li><li> Palette divergente: applicata alla tabella coorte in Analysis Workspace e nell’analisi guidata della crescita degli utenti. Questa palette contiene un significato numerico con due estremi e una linea di base al centro.<li> Palette sequenziale: applicata all’analisi guidata delle tendenze di frequenza (barre sovrapposte). Questa palette contiene un significato numerico che va dal chiaro allo scuro.</li></ul> |
| **Dati** | | |
|  | [Visualizzazione dati](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it#report-suite) | Scegli i dati da cui derivano i dati di tabelle e visualizzazioni. <ul><li>Più recente (impostazione predefinita)</li><li>Visualizzazione dati specifica selezionata da un elenco</li></ul> |
|  | [Calendario](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it#calendar) | Seleziona da un elenco di: <ul><li>Intervalli forniti da Adobe (l’impostazione predefinita è Questo mese)</li><li>È possibile abilitare [!UICONTROL Make date range components relative to panel calendar by default].</li></ul> |
|  | [Tipo di pannello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it) | <ul><li>A forma libera (impostazione predefinita)</li><li>Vuoto</li><li>Quick Insights</li></ul> |
|  | Conteggio istanze | Abilita [!UICONTROL Count repeat instances] per specificare se le istanze ripetute vengono conteggiate nei rapporti. Ad esempio, se questa opzione è abilitata, più visualizzazioni consecutive della stessa pagina vengono considerate come visualizzazioni di più pagine. Se l’opzione è disattivata, più visualizzazioni consecutive della stessa pagina vengono conteggiate come una singola pagina. <p>**Nota:** questa impostazione influisce solo su determinate metriche (ad esempio Sessioni) e non si applica alle visualizzazioni Flusso o Abbandono.</p> |
|  | Formato dei numeri | <ul><li>1.000,00 (impsotazione predefinita)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Carattere separatore CSV | <ul><li>Virgola (impostazione predefinita)</li><li>Punto e virgola</li><li>Due punti</li><li>Barra verticale</li><li>Punto</li><li>Spazio</li><li>Scheda</li></ul> |
|  | Mostra annotazioni | Scegli se rendere visibili le annotazioni nei progetti. Per ulteriori informazioni sulle annotazioni, consulta la sezione [Panoramica delle annotazioni](/help/components/annotations/overview.md). |


### Preferenze delle tabelle a forma libera {#freeform-table-preferences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_showanomalies"
>title="Mostra anomalie"
>abstract="Selezionando **[!UICONTROL Show anomalies]** verrà automaticamente eseguito il rilevamento delle anomalie sulla prima colonna di metriche aggiunta a una visualizzazione a forma libera della serie temporale."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_prefs_showforecast"
>title="Mostra previsione"
>abstract="Se selezioni **[!UICONTROL Show forecast]**, verrà automaticamente prevista la prima colonna di metriche aggiunta a una visualizzazione a forma libera della serie temporale."

<!-- markdownlint-enable MD034 -->


Puoi personalizzare le preferenze delle tabelle a forma libera per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per singole tabelle.

Seleziona i titoli delle sezioni collegate per ulteriori informazioni e contesto sulle preferenze disponibili.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Tabella** | | |
| | Tipo di tabella | <ul><li>A forma libera</li><li>Generatore di tabelle</li></ul> |
| | Metrica tabella predefinita | <ul><li>Occorrenze</li><li>Visitatori univoci</li><li>Visite</li></ul> |
| | Dimensioni della tabella predefinita | Scegli tra Minuto, Ora, Giorno, Settimana, Mese, Trimestre o Anno. |
| | Allinea date | Seleziona questa opzione per allineare le date di ogni colonna affinché inizino tutte sulla stessa riga. |
| **[Colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Testo a capo nelle intestazioni | Consente di mandare automaticamente a capo il testo delle intestazioni nelle tabelle a forma libera, per agevolare la lettura delle intestazioni e la condivisione delle tabelle. Questa opzione è utile per la creazione di file PDF e per le metriche con nomi lunghi. È attivata per impostazione predefinita. |
| | Mostra totali | Questo totale è in genere uguale o un sottoinsieme del [!UICONTROL Grand Total] (Totale complessivo). Riflette eventuali filtri applicati alla tabella a forma libera, inclusa l’opzione [!UICONTROL Include None] (Includi nessuna). |
| | Mostra totali complessivi | Questo totale rappresenta tutti gli eventi che sono stati raccolti, talvolta denominati “totale visualizzazione dati”. Quando un filtro viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli eventi che corrispondono ai criteri di filtro. Il totale complessivo non è supportato per tabelle o raggruppamenti con [righe statiche](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Mostra sparkline | Mostra o nascondi i grafici a linee nella parte inferiore del grafico. Quando è nascosta, la legenda non fa più riferimento visivamente alle linee. |
| | Numero | Determina se mostrare/nascondere il valore numerico di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore numerico corrisponde al numero di visualizzazioni di pagina per l’elemento riga. |
| | Percentuale | Determina se mostrare o nascondere il valore percentuale di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore percentuale corrisponde al numero di visualizzazioni di pagina per l’elemento riga, diviso per il totale di visualizzazioni di pagina per la colonna.  Nota: per garantire una maggiore precisione, è possibile visualizzare percentuali superiori al 100%. Inoltre, abbiamo spostato il limite superiore al 1000% per assicurare che le colonne possano crescere anche in larghezza. |
| | Mostra anomalie <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Determina se eseguire il rilevamento delle anomalie sui valori di questa colonna. |
| | Mostra previsione | Determina se i valori di previsione vengono visualizzati automaticamente per la prima colonna di metriche in qualsiasi tabella a forma libera con serie temporale creata. |
| | Interpret zero as no value (Interpreta zero come nessun valore) | Per le celle con valore 0, determina se visualizzare 0 oppure la cella vuota. Questa funzione è particolarmente utile se si esaminano i dati quotidianamente e il mese in corso non è ancora terminato.  Invece di visualizzare valori 0 per le date future, è possibile sostituirli con delle celle vuote. Anche i grafici si adeguano a questa impostazione (ossia, se è stata selezionata, non visualizzano linee o barre con valori 0). |
| | Informazioni di base | Determina se mostrare o nascondere tutta la formattazione della cella, inclusi il grafico a barre e la formattazione condizionale <ul><li>Grafico a barre</li> Visualizza un grafico a barre orizzontale che rappresenta il valore della cella rispetto al totale della colonna. <li>Formattazione condizionale</li>Per ulteriori informazioni sulla formattazione condizionale, consulta la sezione “Formattazione condizionale” in [Impostazioni colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Anteprima cella | Mostra un’anteprima di ciascuna cella con le opzioni di formattazione attualmente selezionate attive. |
| **[Riga](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Raggruppamento per posizione | Seleziona questa opzione per far sì che il raggruppamento rimanga nella posizione dell’elemento anziché nell’elemento stesso. Per ulteriori informazioni sulle suddivisioni, consulta la sezione [Suddividere le dimensioni](/help/components/dimensions/t-breakdown-fa.md). |
| | Calcolo percentuale | <ul><li>Colonna</li><li>Riga</li></ul> |
| | Totali colonne (solo righe statiche) | <ul><li>Visualizza somma di righe: mostra la somma dei singoli elementi di riga </li><li>Visualizza totale complessivo: mostra la somma deduplicata di righe.</li></ul> |

### Preferenze delle visualizzazioni

Puoi aggiornare le preferenze di visualizzazione per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per le singole visualizzazioni.

Seleziona i titoli delle sezioni collegate per ulteriori informazioni e contesto sulle preferenze disponibili.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Impostazioni predefinite generali** | | |
| | Percentuali | Visualizza i valori in percentuale per tutte le visualizzazioni. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliato per tutte le visualizzazioni. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X per tutte le visualizzazioni. Può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Visualizza asse doppio (se applicabile) | Applicabile solo in presenza di due metriche. È possibile avere un asse y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Normalizzazione (se applicabile) | Forza le metriche ad adeguarsi alle proporzioni. Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Ancoraggio asse Y su zero | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |
| | Ancoraggio delle anomalie in scala sull&#39;asse Y | L’asse y verrà ridimensionato utilizzando valori di anomalia. |
| **[Linee](/help/analysis-workspace/visualizations/line.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni delle linee. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione delle linee. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione delle linee. Può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Visualizza asse doppio (se applicabile) | Applicabile solo in presenza di due metriche. È possibile avere un asse y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Normalizzazione (se applicabile) | Forza le metriche ad adeguarsi alle proporzioni. Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Mostra asse x | Visualizza l’asse x sul grafico a linee. |
| | Mostra asse y | Visualizza l’asse y sul grafico a linee. |
| | Ancora asse Y | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |
| | Consenti alle anomalie di dimensionare l’asse Y | Se in un grafico sono presenti più metriche, passa il cursore su ogni valore anomalo per visualizzare la relativa banda di valori affidabili. Per rendere la visualizzazione più leggibile, l’intervallo di confidenza del rilevamento delle anomalie non dimensiona automaticamente l’asse y. Questa opzione consente all’intervallo di confidenza di dimensionare la visualizzazione. <p>Per ulteriori informazioni, consulta la sezione [Visualizzare le anomalie in Analysis Workspace](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| | Consenti previsione per ampliare l’asse Y | Se i valori di previsione non rientrano nei limiti superiore e inferiore dei valori storici, l’asse y non viene ridimensionato automaticamente per questi valori previsti. Quando è attivata, questa opzione ridimensiona correttamente l’asse y per i valori previsti. |
| | Mostra min | Sovrapponi un’etichetta del valore minimo per evidenziare rapidamente gli avvallamenti in una metrica. Nota: i valori minimi sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione. |
| | Mostra max | Sovrapponi un’etichetta del valore massimo per evidenziare rapidamente i picchi di una metrica. Nota: i valori massimi sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione. |
| | Mostra linea di tendenza | Mostra una linea di tendenza di regressione o media mobile della serie di linee. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati. |
| **[Coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
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
| | Mostra confronto | Mostra i dati di confronto. Se nascosti, gli oggetti grafico a linee di confronto e di riepilogo delle modifiche saranno nascosti dalla visualizzazione. |
| | Opzioni per valore numerico | Nella sezione [!UICONTROL **Riepilogo delle metriche chiave**] <ul><li>Mostra variazione percentuale</li><li>Mostra differenza grezza</li>Differenza non elaborata tra il valore totale della metrica nell’intervallo di date principale e l’intervallo di date secondario</ul> |
| **[Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Contenitore | Consente di passare da **[!UICONTROL Session]** a **[!UICONTROL Person]** per analizzare il percorso della persona. Il valore predefinito è **[!UICONTROL Person]**. Queste impostazioni consentono di comprendere il coinvolgimento di persone a livello di persona singola (attraverso più sessioni) o di limitare l’analisi a una singola sessione. <p>Sono disponibili le seguenti opzioni:</p> <ul><li>Sessione</li><li>Persona</li></ul> |
| **[Flusso](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Contenitore | Nella sezione [!UICONTROL **Flusso**] <ul><li>Sessione</li><li>Persona</li></ul> |
| | Etichette wrap | Di norma, le etichette degli elementi di Flusso vengono troncate per risparmiare spazio sullo schermo, ma selezionando questa casella puoi rendere visibile l’intera etichetta. Impostazione predefinita = non selezionata. |
| | Includi istanze ripetute | Le visualizzazioni di Flusso si basano su istanze di una dimensione. Questa impostazione offre la possibilità di includere o escludere istanze ripetute, ad esempio i ricaricamenti delle pagine. Tuttavia, le ripetizioni non possono essere rimosse dalle visualizzazioni Flusso che includono dimensioni con più valori, come listVars, listProp, s.product, eVar di merchandising, ecc. Impostazione predefinita = non selezionata. |
| | Mostra descrizioni comandi | Determina se visualizzare le descrizioni comandi contenenti i dati dei nodi quando si passa il mouse sui singoli nodi all’interno di una visualizzazione del flusso. |
| | Numero di colonne | Determina il numero di colonne desiderato nel diagramma di flusso. |
| | Elementi espansi per colonna | Il numero di elementi che desideri inserire in ogni colonna. |
| **Grafici sovrapposti** | | |
| | Sovrapposizione 100% | Applicata alle visualizzazioni Superfici sovrapposte, Barre sovrapposte o Barre orizzontali sovrapposte, questa impostazione converte il grafico in una visualizzazione con sovrapposizione 100%. <p>Per ulteriori informazioni, consulta la sezione [Barre e barre sovrapposte](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Istogramma](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | Numero di bucket | Scegli il numero di intervalli di dati (bucket) nella visualizzazione. Il numero massimo consentito è 50. <p>Per ulteriori informazioni, consulta la sezione [Istogramma](/help/analysis-workspace/visualizations/histogram.md).</p> |
| | Metodo di conteggio | Scegli tra le seguenti opzioni: <ul><li>Hit</li><li>Sessione</li><li>Persona</li></ul> <p>Ad esempio, se utilizzato insieme alle visualizzazioni di pagina, puoi scegliere le visualizzazioni di pagina per persona, per visita o per evento. Per Hit, “Occorrenze” viene usato come metrica dell’asse y in una tabella a forma libera.</p> |
| **[Variazione di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Valore | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Variazione percentuale</li><li>Differenza grezza</li></ul> |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Variazione di riepilogo. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Variazione di riepilogo. |
| **[Numero di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Numero di riepilogo. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Numero di riepilogo. |
| | Valore di riepilogo per | Scegli tra Max, Min, Medio, Mediana e Somma. |
| | Abbrevia il valore | Nella sezione [!UICONTROL **Numero di riepilogo**] |
| **[Mappa ad albero](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni Mappa ad albero. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione Mappa ad albero. Può essere utile se disponi di un set di dati di grandi dimensioni. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** | | |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Venn. |
| **[A dispersione](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni A dispersione. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione A dispersione. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione A dispersione. Può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Ancoraggio asse y su zero | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |

## Ripristina preferenze predefinite

Puoi ripristinare tutte le preferenze utente alle impostazioni predefinite del sistema. Ciò non influisce sulle preferenze dell’amministratore nella scheda Società.

Questa azione non può essere annullata.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] **>** [!UICONTROL **Preferenze**] dal menu principale. In alternativa, selezionare **[!UICONTROL Project]** > **[!UICONTROL User settings]** dal menu Workspace.

1. In alto a destra, seleziona **[!UICONTROL Restore defaults]** (Ripristina impostazioni predefinite).

1. Seleziona **[!UICONTROL Restore defaults]** in **[!UICONTROL Restore system default settings]**, .

## [!UICONTROL Dark theme]

Se preferisci uno sfondo scuro per l’interfaccia utente di Customer Journey Analytics, puoi passare a [!UICONTROL Dark theme].

1. Seleziona l’icona utente Experience Cloud in alto a destra.

   ![tema scuro](assets/dark-theme.png)

1. Abilita **[!UICONTROL Dark theme]**..

