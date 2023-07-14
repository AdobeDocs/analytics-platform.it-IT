---
title: Panoramica dell’analisi guidata
description: Un metodo di analisi dei dati in Customer Journey Analytics che consente ai team di prodotto di ottenere rapidamente informazioni di alta qualità.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: cc76b4c3b03647f6e90f0b57f4d8c819caa8823f
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 3%

---

# Panoramica dell’analisi guidata

{{release-limited-testing}}

L’analisi guidata è un formato di reporting che consente ai team di prodotto di gestire autonomamente e rapidamente le esigenze di dati, in modo da ottenere rapidamente informazioni di alta qualità e prendere decisioni sui prodotti più basate sui dati. I team cross-functional possono connettersi in tempo reale per utilizzare e comprendere questi rapporti.

Analogamente alle scorecard per dispositivi mobili e Analysis Workspace, un rapporto di analisi guidato utilizza dati provenienti da un [Visualizzazione dati](../data-views/data-views.md), che fa riferimento ai dati in Adobe Experience Platform tramite un [Connessione](../connections/overview.md). Tutti i rapporti creati nell’analisi guidata possono essere trasferiti facilmente ad Analysis Workspace per ulteriori ricerche.

L’analisi guidata offre diversi modi per analizzare e visualizzare i dati. I tipi di visualizzazione possono mostrare gli stessi dati in modi diversi, consentendo di ottenere informazioni diverse utilizzando gli stessi eventi e segmenti. Le barre di query e le impostazioni di visualizzazione variano a seconda della vista scelta. Puoi passare liberamente da una visualizzazione all’altra e tutti i componenti della barra delle query applicabili verranno riportati, se la vista li supporta.

L&#39;analisi guidata categorizza i tipi di vista in **Tipi di analisi**. Sono disponibili i seguenti tipi di analisi e viste:

| Tipo di analisi | Tipo di visualizzazione | Descrizione |
| --- | --- | --- |
| Impatto | [del prossimo maggio (?)](types/release.md) | Confrontare le prestazioni in periodi uguali prima e dopo il rilascio. |
| Impatto | [Primo utilizzo](types/first-use.md) | Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave. |
| Funnel | [Attrito](types/friction.md) | Confronta i tassi di conversione tra passaggi. |
| Funnel | [Tendenze di conversione](types/conversion-trends.md) | Tieni traccia delle modifiche nei tassi di conversione nel tempo. |
| Crescita degli utenti | [Attivo](types/active.md) | Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi. |
| Crescita degli utenti | [Crescita netta](types/net-growth.md) | Stai guadagnando o perdendo utenti? |
| Tendenze | [Utilizzo](types/usage.md) | Misura il coinvolgimento degli utenti nel tempo. |

{style="table-layout:auto"}

## Accedere ad

Se la tua organizzazione dispone del provisioning per l’analisi guidata, è possibile accedervi dalla pagina home del Customer Journey Analytics.

Clic **Analisi guidata** dalla home page per passare direttamente al [Visualizzazione tendenze di utilizzo](types/usage.md).

Clic **Crea nuovo** per visualizzare le diverse opzioni di visualizzazione e scegliere un punto di partenza diverso per l&#39;analisi.

## Interfaccia

L’interfaccia per l’analisi guidata, indipendentemente dal tipo di analisi, comprende i seguenti elementi principali dell’interfaccia utente:

| Anteprima interfaccia | Elemento nell’interfaccia utente | Descrizione |
| --- | --- | --- |
| ![Barra delle query](assets/query-rail.png) | Barra delle query | Configura i componenti desiderati (eventi, proprietà e segmenti) che compongono un’analisi. Ogni tipo di analisi applica limiti diversi al numero di eventi e segmenti che è possibile configurare. Se si passa a un nuovo tipo di analisi, le selezioni delle query vengono mantenute entro i limiti consentiti per tale tipo di analisi. |
| ![Grafico](assets/chart.png) | Grafico | Visualizzazione dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. La visualizzazione visualizzata dipende dalla vista e dalle impostazioni sopra il grafico. Le viste disponibili dipendono dal tipo di analisi presente sopra la barra delle query. Il grafico include anche: <ul><li>**Descrizione**: passa il puntatore del mouse su un punto dati del grafico per visualizzare una descrizione comando con ulteriori informazioni.</li><li>**Legenda**: passa il cursore del mouse sulla legenda del grafico per esporre le definizioni delle serie, se disponibili.</li><li>**Azioni di clic**: per esporre le azioni successive disponibili, fai clic con il pulsante sinistro del mouse su un punto dati. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Tabella](assets/table.png) | Tabella | Una rappresentazione in tabella dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. Le colonne della tabella dipendono dal tipo di visualizzazione sopra il grafico. Le viste disponibili dipendono dal tipo di analisi presente sopra la barra delle query. La tabella include inoltre: <ul><li>**Azioni di clic**: per esporre le azioni successive disponibili, fai clic su **[!UICONTROL More]** menu. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Impostazioni di visualizzazione](assets/visualization-settings.png) | Impostazioni di visualizzazione | Diverse opzioni sopra il grafico che consentono di personalizzare la modalità di restituzione dei dati da parte del grafico e della tabella.<ul><li>**Tipo di visualizzazione**: selettore a discesa che consente di presentare i dati per un determinato tipo di analisi in modo diverso.</li><li>**Impostazioni grafico**: regola con precisione la visualizzazione del grafico e della tabella. Le opzioni disponibili dipendono dalla vista selezionata.</li><li>**Intervallo di date**: selettore calendario che consente di determinare l’intervallo di date dell’analisi. È inoltre possibile selezionare un intervallo per le visualizzazioni con tendenze, ad esempio giornaliere, settimanali o mensili.</li><li>**Approfondimenti**: informazioni contestuali a seconda dell’analisi visualizzata. Puoi passare a ulteriori informazioni utilizzando le frecce oppure mostrare o nascondere tali informazioni utilizzando l’icona a forma di lampadina in alto a destra.</li></ul> |
| ![Menu](assets/menu.png) | Menu | Comandi in alto a destra di Analisi guidata che forniscono azioni generali per l’analisi.<ul><li>**Selettore visualizzazione dati**: modifica la visualizzazione dati utilizzata dall’analisi. Quando modifichi la visualizzazione dati, cambiano anche i componenti disponibili nella barra delle query.</li><li>**Salva**: salva l&#39;analisi. Se stai salvando una nuova analisi, viene visualizzata una finestra modale che richiede un nome e una descrizione.</li><li>**Salva con nome**: salva l&#39;analisi separatamente dall&#39;analisi corrente, creando una copia. Viene visualizzata una finestra modale che richiede un nuovo nome e una nuova descrizione.</li><li>**Apri in Workspace**: ricrea l’analisi guidata corrente in Analysis Workspace. Il progetto Workspace viene creato in una nuova scheda, evitando interruzioni durante l’analisi guidata. È una copia dell&#39;analisi e non rimane sincronizzata con l&#39;analisi guidata originale una volta aperta. Utilizza questo comando per passare al team di analisti o per approfondire i dati rispetto a quanto consente l’analisi guidata.</li><li>**Copia negli Appunti**: copia l&#39;elemento grafico negli Appunti per incollarlo in altre applicazioni. La barra delle query e la tabella non sono incluse nell&#39;immagine.</li><li>**Scarica PNG**: scarica l&#39;elemento grafico come `.png`. La barra delle query e la tabella non sono incluse nell&#39;immagine.</li><li>**Scarica CSV**: scarica i dati della tabella come `.csv`. La barra delle query e il grafico non sono inclusi nel file.</li></ul> |

{style="table-layout:auto"}

## Provisioning

L’analisi guidata fa parte di Adobe Product Analytics, un componente aggiuntivo a pagamento per il Customer Journey Analytics. Se la tua organizzazione desidera iniziare a utilizzare questo set di funzionalità, contatta il team dell’account Adobe.

Una volta che la tua organizzazione dispone del provisioning per utilizzare l’analisi guidata, gli amministratori dei profili di prodotto possono aggiungere o rimuovere l’accesso all’analisi in Adobe Admin Console.

1. Accedi a [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleziona **[!UICONTROL Customer Journey Analytics]** nell’elenco dei prodotti.
1. Seleziona il profilo di prodotto desiderato per le autorizzazioni da modificare.
1. Fai clic su **[!UICONTROL Permissions]** , quindi fai clic su **[!UICONTROL Edit]** in [!UICONTROL Reporting Tools].
1. Fai clic sull’icona più accanto a **[!UICONTROL Guided Analysis Access]** nell’elenco di [!UICONTROL Available Permission Items], che lo aggiunge all&#39;elenco di [!UICONTROL Included Permission Items].
1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

>[!TIP]
>
>Alcuni amministratori preferiscono abilitare l’analisi guidata e disabilitare Analysis Workspace per il Customer Journey Analytics dei nuovi utenti. Una volta che questi utenti saranno al corrente del prodotto e dei tuoi dati organizzativi, potrai abilitare l’accesso ad Analysis Workspace.
