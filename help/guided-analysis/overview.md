---
title: Panoramica dell’analisi guidata
description: Un metodo di analisi dei dati in Customer Journey Analytics che consente ai team di prodotto di ottenere rapidamente informazioni approfondite di alta qualità. Denominato anche Analisi di prodotto.
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '1356'
ht-degree: 92%

---

# Panoramica dell’analisi guidata

L’analisi guidata consente agli utenti di gestire in autonomia dati e informazioni approfondite di alta qualità sul percorso del cliente tramite flussi di lavoro guidati, basati sui dati cross-channel di Customer Journey Analytics. I team interfunzionali, dal marketing al prodotto, possono connettersi in tempo reale per utilizzare e comprendere questi rapporti.

>[!NOTE]
>
> L’analisi guidata è attualmente disponibile solo come parte di Adobe Product Analytics, che è un componente aggiuntivo a pagamento di Customer Journey Analytics. Contatta il team Adobe Account per iniziare a utilizzare questo insieme di funzionalità nella tua organizzazione.

Analogamente alle scorecard per Analysis Workspace e dispositivi mobili, l’analisi guidata utilizza dati provenienti da una [Visualizzazione dati](../data-views/data-views.md), che fa riferimento ai dati in Adobe Experience Platform tramite una [Connessione](../connections/overview.md). Molti rapporti creati nell’analisi guidata possono essere trasferiti facilmente in Analysis Workspace per ulteriori ricerche.

Sono disponibili le seguenti visualizzazioni di analisi guidata:

| Tipo di analisi | Tipo di visualizzazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Feature matrix] | [Coinvolgimento](types/engagement.md) | Comprendi l’ampiezza e l’ampiezza del coinvolgimento delle funzioni. |
| [!UICONTROL Funnel] | [Attrito](types/friction.md) | Confronta i tassi di conversione tra passaggi. |
| [!UICONTROL Funnel] | [Tendenze di conversione](types/conversion-trends.md) | Tieni traccia delle modifiche nei tassi di conversione nel tempo. |
| [!UICONTROL Impact] | [Versione](types/release.md) | Confronta le prestazioni in periodi uguali prima e dopo il rilascio. |
| [!UICONTROL Impact] | [Primo utilizzo](types/first-use.md) | Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave. |
| [!UICONTROL Retention] | [Tassi di mantenimento](types/retention-rates.md) | Misura le abitudini attuali riguardo il ritorno degli utenti. |
| [!UICONTROL Trends] | [Utilizzo](types/usage.md) | Misura il coinvolgimento utenti nel tempo. |
| [!UICONTROL Trends] | [Frequenza](types/frequency.md) | Misura il coinvolgimento in base alla frequenza d’uso. |
| [!UICONTROL User growth] | [Attivo](types/active.md) | Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi. |
| [!UICONTROL User growth] | [Crescita netta](types/net-growth.md) | Stai guadagnando o perdendo utenti? |
| [!UICONTROL User stream] | [Timeline](types/timeline.md) | Esplora i pattern nell’attività della sessione. |

{style="table-layout:auto"}

## Accesso

Se la tua organizzazione dispone del provisioning per l’analisi guidata, puoi accedervi dalla pagina Home di Customer Journey Analytics.

1. Dalla pagina Home, fai clic su **[!UICONTROL Guided analysis]** , che ti indirizza direttamente alla [Visualizzazione tendenze di utilizzo](types/usage.md).

   ![Riquadro della pagina di destinazione](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Fai clic su **[!UICONTROL Create new]** per visualizzare le diverse opzioni di visualizzazione e scegliere un punto di partenza diverso per l’analisi.

   ![Creare un nuovo modale](assets/create-new-modal.png){style="border:1px solid gray"}

Se per la tua organizzazione non è ancora disponibile il provisioning per l’analisi guidata, contatta il team Adobe Account.

## Interfaccia

L’interfaccia per l’analisi guidata segue un formato di domanda e risposta. Crea una domanda nella barra delle query, quindi ottieni una risposta con un approfondimento scritto, un grafico e una tabella. A questo punto potrai rispondere alla domanda successiva con i tipi di visualizzazione e le relative impostazioni.

L’analisi guidata utilizza i seguenti elementi dell’interfaccia utente:

| Anteprima interfaccia | Elemento nell’interfaccia utente | Descrizione |
| --- | --- | --- |
| ![Barra delle query](assets/query-rail.png){style="border:1px solid gray"} | Barra delle query | Configura la “domanda” selezionando i componenti desiderati (eventi, proprietà e segmenti) che compongono un’analisi. Le seguenti opzioni sono disponibili per tutti i tipi di visualizzazione, con impostazioni aggiuntive disponibili per singole visualizzazioni. <ul><li>**Selettore di analisi**: elenco a discesa che consente di passare a un nuovo tipo di analisi. Le selezioni delle query vengono mantenute entro i limiti consentiti per il nuovo tipo di analisi.</li><li>**Selettore vista**: elenco a discesa che consente di passare a una nuova visualizzazione (“risposta”) per la query creata. Le selezioni delle query vengono mantenute entro i limiti consentiti per il nuovo tipo di visualizzazione.</li><li>**Eventi**: gli eventi che desideri misurare. Ogni tipo di visualizzazione applica limiti diversi al numero di eventi che è possibile configurare.</li><li>**Filtri**: utilizza l’icona ![Filtro](assets/filter.png) nella sezione Eventi o Segmenti per limitare il numero di proprietà specifiche. Quando viene selezionata una proprietà, vengono utilizzati entrambi i criteri di filtro standard (ad esempio [!UICONTROL Equals], [!UICONTROL Contains] o [!UICONTROL Ends with]) e sono disponibili i primi 1000 valori della proprietà.</li><li>**Conteggiato come**: metodo di conteggio che desideri applicare agli eventi selezionati.</li><li>**Segmenti**: i segmenti che desideri misurare. Ogni tipo di visualizzazione applica limiti diversi al numero di segmenti che è possibile configurare.</li></ul> |
| ![Grafico](assets/chart.png){style="border:1px solid gray"} | Grafico | Una visualizzazione dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. La visualizzazione che vedi dipende dalla vista e dalle impostazioni sopra il grafico. Il grafico include anche: <ul><li>**Descrizioni**: passa il puntatore del mouse su un punto dati del grafico per visualizzare una descrizione comando con ulteriori informazioni.</li><li>**Legenda**: passa il puntatore del mouse sulla serie di legende del grafico per visualizzare le definizioni, se disponibili, per concentrarti su tale serie e nasconderne temporaneamente altre. Per nascondere una serie nella legenda, fai clic su di essa.</li><li>**Annotazioni**: le [annotazioni](../components/annotations/overview.md) applicabili sono visibili tra la visualizzazione e la legenda. Vengono visualizzate come ![icona Annotazione](assets/annotation.png) nel colore configurato dell’annotazione. I tipi di visualizzazione che mostrano i dati nel tempo inseriscono l’![icona Annotazione](assets/annotation.png) sotto la data o l’intervallo di date configurato. I tipi di visualizzazione che non mostrano dati nel tempo mostrano l’![Icona Annotazione](assets/annotation.png) nell’angolo inferiore a destra del grafico.</li><li>**Azioni di clic**: per esporre le azioni successive disponibili, fai clic con il pulsante sinistro del mouse su un punto dati. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Tabella](assets/table.png){style="border:1px solid gray"} | Tabella | Una rappresentazione in tabella dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. Le colonne della tabella dipendono dal tipo di visualizzazione sopra il grafico. La tabella include anche: <ul><li>**Azioni di clic**: per nascondere o esporre una serie di grafici, clicca sull’![icona Mostra/Nascondi](assets/hide-in-chart.png) in ogni riga. Sono disponibili azioni aggiuntive facendo clic sul menu **[!UICONTROL More]**. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Impostazioni di visualizzazione](assets/visualization-settings.png){style="border:1px solid gray"} | Impostazioni di visualizzazione | Opzioni sopra il grafico che consentono di porre la domanda successiva e personalizzare la modalità di restituzione dei dati del grafico e della tabella. Le seguenti opzioni sono disponibili per tutti i tipi di visualizzazione, con impostazioni aggiuntive disponibili per singole visualizzazioni. <ul><li>**Impostazioni grafico**: regola con precisione la visualizzazione del grafico e della tabella. Le opzioni disponibili dipendono dalla visualizzazione selezionata.</li><li>**Intervallo di date**: selettore calendario che consente di determinare l’intervallo di date dell’analisi. È inoltre possibile selezionare un intervallo per le visualizzazioni con tendenze, ad esempio giornaliere, settimanali o mensili.</li><li>**Approfondimenti**: informazioni contestuali a seconda dell’analisi visualizzata. Queste informazioni forniscono osservazioni per l’analisi corrente. Se sono disponibili più informazioni, puoi visualizzarle utilizzando le frecce a destra. È possibile attivare o disattivare la visibilità di questa casella utilizzando l&#39;icona della lampadina in alto a destra.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | Menu | Comandi in alto a destra dell’analisi guidata che forniscono azioni generali per l’analisi.<ul><li>**Selettore visualizzazione dati**: modifica la visualizzazione dati utilizzata dall’analisi. Quando modifichi la visualizzazione dati, cambiano anche i componenti disponibili nella barra delle query.</li><li>**Copia collegamento**: copia negli Appunti un collegamento all’analisi. Viene richiesto di salvare prima della condivisione.</li><li>**Condividi**: apre la finestra modale di condivisione, con ulteriori opzioni per la condivisione a singoli utenti o gruppi. Puoi condividere un’analisi con altri utenti o generare un collegamento da condividere con chiunque.</li><li>**Salva**: salva l’analisi. Se stai salvando una nuova analisi, viene visualizzata una finestra modale che richiede un nome e una descrizione.</li><li>**Salva con nome**: salva l’analisi separatamente da quella corrente, creando una copia. Viene visualizzata una finestra modale che richiede un nuovo nome e una nuova descrizione.</li><li>**Apri in Workspace**: ricrea l’analisi guidata corrente in Analysis Workspace. Il progetto Workspace viene creato in una nuova scheda, evitando interruzioni durante l’analisi guidata. È una copia dell’analisi e non rimane sincronizzata con l’analisi guidata originale una volta aperta. Utilizza questo comando per trasmetterla al team di analisti o per approfondire i dati rispetto a quanto consente l’analisi guidata.</li><li>**Copia negli Appunti**: copia l’elemento grafico negli Appunti per incollarlo in altre applicazioni. La barra delle query e la tabella non sono incluse nel grafico.</li><li>**Scarica PNG**: scarica l’elemento grafico come `.png`. La barra delle query e la tabella non sono incluse nel grafico.</li><li>**Scarica CSV**: scarica i dati della tabella come `.csv`. La barra delle query e il grafico non sono inclusi nel file.</li></ul> |

{style="table-layout:auto"}

## Provisioning

L’analisi guidata fa parte di Adobe Product Analytics, un componente aggiuntivo a pagamento di Customer Journey Analytics. Contatta il team Adobe Account per iniziare a utilizzare questo insieme di funzionalità nella tua organizzazione.

Una volta che la tua organizzazione dispone del provisioning per utilizzare l’analisi guidata, gli amministratori dei profili di prodotto possono aggiungere o rimuovere l’accesso ad essi tramite Adobe Admin Console.

1. Accedi ad [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleziona **[!UICONTROL Customer Journey Analytics]** nell’elenco dei prodotti.
1. Seleziona il profilo di prodotto desiderato per le autorizzazioni da modificare.
1. Fai clic sulla scheda **[!UICONTROL Permissions]**, quindi fai clic su **[!UICONTROL Edit]** in [!UICONTROL Reporting Tools].
1. Fai clic sull’icona più accanto a **[!UICONTROL Guided Analysis Access]** nell&#39;elenco di [!UICONTROL Available Permission Items], che lo aggiunge all&#39;elenco di [!UICONTROL Included Permission Items].
1. Fai clic su **[!UICONTROL Save]**.

>[!TIP]
>
>Alcuni amministratori preferiscono abilitare l’analisi guidata e disabilitare Analysis Workspace per i nuovi utenti di Customer Journey Analytics. Una volta che questi utenti avranno una maggiore conoscenza del prodotto e dei tuoi dati organizzativi, potrai abilitare l’accesso ad Analysis Workspace.
