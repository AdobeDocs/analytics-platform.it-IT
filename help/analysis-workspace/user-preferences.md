---
title: Come impostare le preferenze utente in Analysis Workspace
description: Puoi impostare le preferenze generali e di progetto per gli utenti.
feature: CJA Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
source-git-commit: b2931e40bd07b8bd3421216c1f1565bea7e3cd5d
workflow-type: tm+mt
source-wordcount: '3114'
ht-degree: 73%

---

# Preferenze utente

Puoi gestire le impostazioni di Analysis Workspace e dei relativi componenti per tutti i nuovi progetti o pannelli creati. I progetti e i pannelli esistenti non sono interessati.

## Aggiornare le preferenze

1. In Customer Journey Analytics, vai a [!UICONTROL **Progetti**] pagina di destinazione, quindi seleziona [!UICONTROL **Modifica preferenze**].

   ![Preferenze utente](assets/user-preferences.png)

   Oppure

   Gli amministratori di prodotto possono aggiornare le preferenze dell’organizzazione IMS da [!UICONTROL **Componenti**] , quindi selezionando [!UICONTROL **Preferenze**].

1. Per informazioni sulle preferenze disponibili in ogni scheda, continua con una delle sezioni seguenti di questo articolo:

   * [Preferenze generali](#general-preferences)

   * [Preferenze organizzazione IMS](#ims-organization-preferences)

   * [Preferenze per i progetti](#project-preferences)

   * [Preferenze delle tabelle a forma libera](#freeform-table-preferences)

   * [Preferenze delle visualizzazioni](#visualizations-preferences)

## Preferenze generali

Le preferenze generali sono applicabili all’esperienza CJA nel browser. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

| Preferenza | Opzioni |
| --- | --- |
| Pagina di destinazione | Scegli quale pagina visualizzare come pagina predefinita quando accedi ad Adobe Analytics: <ul><li>Elenco progetti (impostazione predefinita)</li><li>Progetto vuoto</li><li>Progetto specifico  selezionato da un elenco</li></ul> |
| Mostra suggerimenti | Visualizza i suggerimenti in una casella blu nell’area in basso a destra di Analysis Workspace. <p>L’opzione è abilitata per impostazione predefinita.</p> |
| Componenti visualizzati nei gruppi della barra a sinistra | Scegli il numero di componenti da visualizzare nel menu Components (Componenti) nella barra a sinistra. <p>Scegliendo 0, il componente non sarà più accessibile dalla barra a sinistra di Workspaces.</p><p>Per impostazione predefinita, vengono visualizzati 5 componenti per ciascuno dei seguenti elementi:</p> <ul><li>Dimensioni</li><li>Metriche</li><li>Filtri</li><li>Intervalli di date</li></ul> <p>Per ulteriori informazioni sui componenti in Analysis Workspace, consulta la sezione [Panoramica dei componenti](/help/components/overview.md).</p> |

## Preferenze organizzazione IMS

Puoi aggiornare le preferenze aziendali che si applicano a tutti gli utenti e i progetti all’interno dell’organizzazione. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Condivisione dei progetti** | | |
| | Consenti condivisione solo con gli utenti di Workspace | <p>Quando questa opzione è abilitata, gli utenti dell’organizzazione non possono visualizzare l’opzione &quot;Condividi con nessuno&quot; nel menu Condividi. Ciò significa che gli utenti non possono condividere i progetti con persone che non hanno un account Analysis Workspace nella tua organizzazione come descritto in [Condividere un progetto con altri utenti (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).</p><p>Questa opzione è disabilitata per impostazione predefinita per tutte le organizzazioni (ovvero gli utenti possono condividere i progetti con persone esterne all’organizzazione), ad eccezione dei clienti che dispongono di una licenza Healthcare Shield. </p><p>Quando abiliti o disabiliti questa opzione, tieni presente quanto segue:</p> <ul><li><p>Quando abiliti questa opzione, gli utenti che in precedenza avevano ricevuto l’accesso a un progetto tramite l’opzione di condivisione &quot;Condividi con chiunque&quot; non possono più accedere al progetto.</p></li><li><p>Se questa opzione è abilitata (per consentire la condivisione solo con gli utenti di Workspace) e successivamente disabilitata (per consentire la condivisione con chiunque), le persone che in precedenza hanno ricevuto l’accesso a un progetto tramite l’opzione di condivisione &quot;Condividi con chiunque&quot; non riacquistano automaticamente l’accesso al progetto. In questo caso, l’utente che ha condiviso il progetto deve abilitare [!UICONTROL **Il collegamento è attivo**] opzione disponibile quando condividi un progetto con chiunque ([!UICONTROL **Condividi**] > [!UICONTROL **Condividi con chiunque**]), come descritto in [Condividere un progetto con altri utenti (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).</p></li><li><p>**Per i clienti che dispongono di una licenza Healthcare Shield:** Questa opzione è attivata per impostazione predefinita e non può essere disattivata. Prima di poter disabilitare questa opzione in modo che gli utenti possano utilizzare l’opzione di condivisione &quot;Condividi con chiunque&quot;, devi aggiungere [!UICONTROL **Condividere collegamenti ai progetti con altri utenti**] autorizzazione (che si trova in [!UICONTROL **Strumenti di reporting**]) in Adobe Admin Console. Dopo aver aggiunto l’autorizzazione, puoi disabilitare questa opzione, quindi accettare l’avviso legale risultante. Per informazioni su come aggiungere un’autorizzazione nell’Admin Console, consulta [Gestione delle autorizzazioni del prodotto nell’Admin Console](https://helpx.adobe.com/it/enterprise/using/manage-permissions-and-roles.html).</p></li> |
| | Richiedi autenticazione Experience Cloud | <p>Quando questa opzione è abilitata, gli utenti a cui viene dato accesso a un progetto dall’opzione &quot;Condividi con chiunque&quot; in Analysis Workspace devono eseguire l’autenticazione utilizzando le credenziali di Experience Cloud.</p> <p>Quando questa opzione è abilitata, ogni volta che un utente condivide un progetto utilizzando l’opzione di condivisione &quot;Condividi con chiunque&quot;, l’opzione &quot;Richiedi autenticazione Experience Cloud&quot; è abilitata nella finestra di dialogo di condivisione e non può essere disabilitata dall’utente che condivide il progetto. (Per informazioni su come gli utenti possono condividere i progetti con chiunque, vedi [Condividere un progetto con altri utenti (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).)</p> <p>Quando abiliti questa opzione, tieni presente quanto segue:</p><ul><li><p>Quando abiliti questa opzione, tutti i progetti precedentemente condivisi con l’opzione di condivisione &quot;Condividi con chiunque&quot; e per i quali non è abilitata l’opzione &quot;Richiedi autenticazione Experience Cloud&quot;, vengono disattivati.</p></li> <li><p>Se questa opzione è abilitata (per richiedere l’autenticazione Experience Cloud) e successivamente disabilitata (per consentire a chiunque disponga del collegamento di accedere al progetto), le persone che in precedenza hanno ricevuto l’accesso a un progetto tramite l’opzione di condivisione &quot;Condividi con chiunque&quot; non riacquistano automaticamente l’accesso al progetto. In questo caso, l’utente che ha condiviso il progetto deve abilitare l’opzione &quot;Il collegamento è attivo&quot; disponibile quando condividi un progetto con chiunque ([!UICONTROL **Condividi**] > [!UICONTROL **Condividi con chiunque**] > [!UICONTROL **Il collegamento è attivo**]), come descritto in [Condividere un progetto con altri utenti (accesso non richiesto)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).</p></li> <li><p>Questa opzione è disponibile solo se SSO è implementato nell’organizzazione. Per informazioni su come gli amministratori di sistema possono abilitare l&#39;SSO per l&#39;organizzazione, vedere [Configurare identità e Single Sign-On](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html){target=_blank}.</p><p>Se l&#39;SSO è configurato per la tua organizzazione, controlla se nella console è implementato qualsiasi tipo di creazione di account automatico. In genere, questa configurazione viene configurata da un amministratore di sistema, come descritto in [Abilita creazione account automatica](https://helpx.adobe.com/enterprise/using/automatic-account-creation.html){target=_blank}.</p></li><li><p>Se l’organizzazione concede la licenza Healthcare Shield, questa opzione è abilitata per impostazione predefinita e non può essere disabilitata.</p></li></ul> |

{style="table-layout:auto"}

## Preferenze per i progetti

Puoi personalizzare le preferenze per i progetti per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per singoli progetti, come descritto in [Panoramica dei progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

Fai clic sui titoli delle preferenze collegati per ulteriori informazioni e contesto su ciascuna preferenza.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Visualizzazione** | | |
|  | [Densità di visualizzazione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=it) | Scegli il contenuto da visualizzare sullo schermo riducendo la spaziatura verticale della barra a sinistra, tabelle a forma libera e tabelle coorte. <ul><li>Compatta</li><li>Comoda</li><li>Espansa (impostazione predefinita)</li></ul> |
| | [Tavolozza dei colori](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=it) | Scegli la tavolozza dei colori di visualizzazione utilizzata in Analysis Workspace. <ul><li>Tavolozze fornite da Adobe (impostazione predefinita)</li><li>Tavolozza con formattazione condizionale </li><li>Tavolozza su/giù (divergente)<li>Tavolozze personalizzate</li></ul> |
| **Dati** | | |
|  | [Visualizzazione dati](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it#report-suite) | Scegli da dove le tabelle e le visualizzazioni derivano i propri dati. <ul><li>Più recente (impostazione predefinita)</li><li>Visualizzazione dati specifica selezionata da un elenco</li></ul> |
|  | [Calendario](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it#calendar) | Seleziona da un elenco di: <ul><li>Intervalli forniti da Adobe (l’impostazione predefinita è Questo mese)</li><li>Intervalli definiti personalizzati</li></ul> |
|  | [Tipo di pannello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it) | <ul><li>A forma libera (impostazione predefinita)</li><li>Vuoto</li><li>Quick Insights</li></ul> |
|  | Conta istanze ripetute | Consente di specificare se conteggiare o meno, per i rapporti, le istanze ripetute. Ad esempio, questa impostazione (se attivata) tratta più visualizzazioni consecutive della stessa pagina come molteplici visualizzazioni di pagina. Con questa opzione, vengono conteggiate come singole visualizzazioni di pagina. <p>**Nota:** questa impostazione ha effetto solo su determinate metriche (ad esempio Visite per pagina singola) e non sulle visualizzazioni Flusso o Fallout.</p> |
|  | Formato dei numeri | <ul><li>1.000,00 (impsotazione predefinita)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Separatore CSV   | <ul><li>Virgola (impostazione predefinita)</li><li>Punto e virgola</li><li>Due punti</li><li>Barra verticale</li><li>Punto</li><li>Spazio</li><li>Scheda</li></ul> |
|  | Mostra annotazioni | Scegli se rendere visibili le annotazioni nei progetti. Per ulteriori informazioni sulle annotazioni, consulta la sezione [Panoramica delle annotazioni](/help/components/annotations/overview.md). |


## Preferenze delle tabelle a forma libera

Puoi personalizzare le preferenze delle tabelle a forma libera per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per singole tabelle.

Fai clic sui titoli della sezione collegata per ulteriori informazioni e contesto sulle preferenze disponibili.

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
| | Mostra totali complessivi | Questo totale rappresenta tutti gli eventi che sono stati raccolti, talvolta denominati &quot;totale della visualizzazione dati&quot;. Quando un filtro viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli eventi che corrispondono ai criteri del filtro. Il totale complessivo non è supportato per tabelle o raggruppamenti con [righe statiche](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Mostra sparkline | Mostra o nascondi i grafici a linee nella parte inferiore del grafico. Quando è nascosta, la legenda non fa più riferimento visivamente alle linee. |
| | Numero | Determina se mostrare/nascondere il valore numerico di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore numerico corrisponde al numero di visualizzazioni di pagina per l’elemento riga. |
| | Percentuale | Determina se mostrare o nascondere il valore percentuale di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore percentuale corrisponde al numero di visualizzazioni di pagina per l’elemento riga, diviso per il totale di visualizzazioni di pagina per la colonna.  Nota: per garantire una maggiore precisione, è possibile visualizzare percentuali superiori al 100%. Inoltre, abbiamo spostato il limite superiore al 1000% per assicurare che le colonne possano crescere anche in larghezza. |
| | Mostra anomalie <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Determina se eseguire il rilevamento delle anomalie sui valori di questa colonna. |
| | Interpret zero as no value (Interpreta zero come nessun valore) | Per le celle con valore 0, determina se visualizzare 0 oppure la cella vuota. Questa funzione è particolarmente utile se si esaminano i dati quotidianamente e il mese in corso non è ancora terminato.  Invece di visualizzare valori 0 per le date future, è possibile sostituirli con delle celle vuote. Anche i grafici si adeguano a questa impostazione (ossia, se è stata selezionata, non visualizzano linee o barre con valori 0). |
| | Informazioni di base | Determina se mostrare o nascondere tutta la formattazione della cella, inclusi il grafico a barre e la formattazione condizionale <ul><li>Grafico a barre</li> Visualizza un grafico a barre orizzontale che rappresenta il valore della cella rispetto al totale della colonna. <li>Formattazione condizionale</li>Per ulteriori informazioni sulla formattazione condizionale, consulta la sezione “Formattazione condizionale” in [Impostazioni colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Anteprima cella | Mostra un’anteprima di ciascuna cella con le opzioni di formattazione attualmente selezionate attive. |
| **[Riga](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Raggruppamento per posizione | Seleziona questa opzione per far sì che il raggruppamento rimanga nella posizione dell’elemento anziché nell’elemento stesso. Per ulteriori informazioni sulle suddivisioni, consulta la sezione [Suddividere le dimensioni](/help/components/dimensions/t-breakdown-fa.md). |
| | Calcolo percentuale | <ul><li>Colonna</li><li>Riga</li></ul> |

## Preferenze delle visualizzazioni

Puoi aggiornare le preferenze di visualizzazione per tutti i nuovi progetti creati in Analysis Workspace. Per informazioni su come accedere a queste preferenze, consulta la sezione [Aggiornare le preferenze](#update-preferences).

Alcune di queste preferenze possono essere personalizzate anche per le singole visualizzazioni.

Fai clic sui titoli della sezione collegata per ulteriori informazioni e contesto sulle preferenze disponibili.

| Sezione | Preferenza | Opzioni |
| --- | --- | --- |
| **Impostazioni predefinite generali** | | |
| | Percentuali | Visualizza i valori in percentuale per tutte le visualizzazioni. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliato per tutte le visualizzazioni. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X per tutte le visualizzazioni. Questo può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Visualizza asse doppio (se applicabile) | Applicabile solo in presenza di due metriche. È possibile avere un asse y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Normalizzazione (se applicabile) | Forza le metriche ad adeguarsi alle proporzioni. Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Ancoraggio asse Y su zero | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |
| | Consenti alle anomalie di dimensionare l’asse Y | Se in un grafico sono presenti più metriche, passa il cursore su ogni valore anomalo per visualizzare la relativa banda di valori affidabili. Per rendere la visualizzazione più leggibile, l’intervallo di confidenza del rilevamento delle anomalie non dimensiona automaticamente l’asse y. Questa opzione consente all’intervallo di confidenza di dimensionare la visualizzazione. <p>Per ulteriori informazioni, consulta la sezione [Visualizzare le anomalie in Analysis Workspace](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md).</p> |
| **[Linee](/help/analysis-workspace/visualizations/line.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni delle linee. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione delle linee. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione delle linee. Questo può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Visualizza asse doppio (se applicabile) | Applicabile solo in presenza di due metriche. È possibile avere un asse y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Normalizzazione (se applicabile) | Forza le metriche ad adeguarsi alle proporzioni. Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| | Mostra asse x | Visualizza l’asse x sul grafico a linee. |
| | Mostra asse y | Visualizza l’asse y sul grafico a linee. |
| | Ancora asse Y | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |
| | Mostra min | Sovrapponi un’etichetta del valore minimo per evidenziare rapidamente gli avvallamenti in una metrica. Nota: i valori minimi sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione. |
| | Mostra max | Sovrapponi un’etichetta del valore massimo per evidenziare rapidamente i picchi di una metrica. Nota: i valori massimi sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione. |
| | Mostra linea di tendenza | Mostra una linea di tendenza di regressione o media mobile della serie di linee. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati. |
| **[Coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | Granularità | Per le visualizzazioni con tendenze, puoi modificare la granularità temporale (giorno, settimana, mese, trimestre o anno). Questa modifica si applica anche alla tabella dell’origine dati. |
| | Mostra solo percentuale | Rimuove il valore numerico e visualizza solo la percentuale. |
| | Arrotonda percentuale a intero più prossimo | Arrotonda il valore percentuale al numero intero più vicino invece di mostrare il valore decimale. |
| | Mostra riga percentuale media | Inserisce una nuova riga nella parte superiore della tabella, quindi aggiunge la media dei valori all’interno di ogni colonna. |
| | Anteprima coorte | Anteprima dell’aspetto della tavolozza dei colori nella visualizzazione della coorte. |
| | Tavolozza coorte | La tavolozza dei colori utilizzata nella visualizzazione coorte. |
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
| | Contenitore | Consente di passare da Visita a Visitatore per analizzare il percorso dei visitatori. Il valore predefinito è Visitatore. Queste impostazioni aiutano a comprendere il coinvolgimento della persona a livello di persona (tra più sessioni) o a vincolare l’analisi a una singola sessione. <p>Sono disponibili le seguenti opzioni:</p> <ul><li>Visita</li><li>Visitatore</li></ul> |
| **[Flusso](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Contenitore | Nella sezione [!UICONTROL **Flusso**] <ul><li>Visita</li><li>Visitatore</li></ul> |
| | Etichette wrap | Di norma, le etichette degli elementi di Flusso vengono troncate per risparmiare spazio sullo schermo, ma selezionando questa casella puoi rendere visibile l’intera etichetta. Impostazione predefinita = non selezionata. |
| | Includi istanze ripetute | Le visualizzazioni di Flusso si basano su istanze di una dimensione. Questa impostazione offre la possibilità di includere o escludere istanze ripetute, ad esempio i ricaricamenti delle pagine. Tuttavia, le ripetizioni non possono essere rimosse dalle visualizzazioni Flusso che includono dimensioni con più valori, come listVars, listProp, s.product, eVar di merchandising, ecc. Impostazione predefinita = non selezionata. |
| | Mostra descrizioni comandi | Determina se visualizzare le descrizioni comandi contenenti i dati dei nodi quando si passa il mouse sui singoli nodi all’interno di una visualizzazione del flusso. |
| | Numero di colonne | Determina il numero di colonne desiderato nel diagramma di flusso. |
| | Elementi espansi per colonna | Il numero di elementi che desideri inserire in ogni colonna. |
| **Grafici sovrapposti** | | |
| | Sovrapposizione 100% | Applicata alle visualizzazioni Superfici sovrapposte, Barre sovrapposte o Barre orizzontali sovrapposte, questa impostazione converte il grafico in una visualizzazione con sovrapposizione 100%. <p>Per ulteriori informazioni, consulta la sezione [Barre e barre sovrapposte](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Istogramma](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | Numero di bucket | Scegli il numero di intervalli di dati (bucket) nella visualizzazione. Il numero massimo consentito è 50. <p>Per ulteriori informazioni, consulta la sezione [Istogramma](/help/analysis-workspace/visualizations/histogram.md).</p> |
| | Metodo di conteggio | Scegli tra le seguenti opzioni: <ul><li>Hit</li><li>Visita</li><li>Visitatore</li></ul> <p>Ad esempio, se utilizzato insieme alle visualizzazioni di pagina, puoi scegliere le visualizzazioni di pagina per persona, quelle per visita o quelle per evento. Per Hit, “Occorrenze” viene usato come metrica dell’asse y in una tabella a forma libera.</p> |
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
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione Mappa ad albero. Questo può essere utile se disponi di un set di dati di grandi dimensioni. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** | | |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione Venn. |
| **[A dispersione](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Percentuali | Visualizza i valori in percentuale per le visualizzazioni A dispersione. |
| | Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliata per la visualizzazione A dispersione. |
| | Limite massimo elementi | Riduce il numero di elementi sull’asse X nella visualizzazione A dispersione. Questo può essere utile se disponi di un set di dati di grandi dimensioni. |
| | Ancoraggio asse y su zero | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |

## Ripristina preferenze predefinite

Puoi ripristinare tutte le preferenze utente alle impostazioni predefinite del sistema. Ciò non influisce sulle preferenze dell’amministratore nella scheda Società.

Questa azione non può essere annullata.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] **>** [!UICONTROL **Preferenze**].

   ![Preferenze utente](assets/user-preferences.png)

1. In alto a destra, seleziona **[!UICONTROL Restore defaults]** (Ripristina impostazioni predefinite).

1. Quando richiesto, seleziona **[!UICONTROL Restore defaults]** (Ripristina impostazioni predefinite).

## [!UICONTROL Dark theme]

Se preferisci uno sfondo scuro per l’interfaccia utente di Adobe Analytics, puoi passare a [!UICONTROL Dark theme].

1. Fai clic sull’icona utente Experience Cloud in alto a destra.

   ![tema scuro](assets/dark-theme.png)

1. Sposta **[!UICONTROL Dark theme]** verso destra.

