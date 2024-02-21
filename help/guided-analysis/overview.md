---
title: Panoramica dell’analisi guidata
description: Un metodo di analisi dei dati in Customer Journey Analytics che consente ai team di prodotto di ottenere rapidamente informazioni di alta qualità. Denominato anche Product Analytics.
keywords: analisi dei prodotti
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 1%

---

# Panoramica dell’analisi guidata

L’analisi guidata consente agli utenti di gestire autonomamente dati e informazioni di alta qualità sul percorso del cliente tramite flussi di lavoro guidati, basati sui dati multicanale del Customer Journey Analytics. I team cross-functional, dal marketing al prodotto, possono connettersi in tempo reale per utilizzare e comprendere questi rapporti.

>[!NOTE]
>
> L’analisi guidata è attualmente disponibile solo come parte di Adobe Product Analytics, che è un componente aggiuntivo a pagamento per il Customer Journey Analytics. Se la tua organizzazione desidera iniziare a utilizzare questo set di funzionalità, contatta il team dell’account Adobe.

Analogamente alle scorecard per Analysis Workspace e dispositivi mobili, l’analisi guidata utilizza dati provenienti da una [Visualizzazione dati](../data-views/data-views.md), che fa riferimento ai dati in Adobe Experience Platform tramite un [Connessione](../connections/overview.md). Molti rapporti creati nell’analisi guidata possono essere trasferiti facilmente ad Analysis Workspace per ulteriori ricerche.

Sono disponibili le seguenti viste di analisi guidate:

| Tipo di analisi | Tipo di visualizzazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Funnel] | [Attrito](types/friction.md) | Confronta i tassi di conversione tra passaggi. |
| [!UICONTROL Funnel] | [Tendenze di conversione](types/conversion-trends.md) | Tieni traccia delle modifiche nei tassi di conversione nel tempo. |
| [!UICONTROL Impact] | [Versione](types/release.md) | Confrontare le prestazioni in periodi uguali prima e dopo il rilascio. |
| [!UICONTROL Impact] | [Primo utilizzo](types/first-use.md) | Misura l’impatto del primo utilizzo delle funzioni sugli indicatori chiave. |
| [!UICONTROL Retention] | [Tassi di mantenimento](types/retention-rates.md) | Misura le abitudini di ritorno continuative degli utenti. |
| [!UICONTROL Trends] | [Utilizzo](types/usage.md) | Misura il coinvolgimento degli utenti nel tempo. |
| [!UICONTROL Trends] | [Frequenza](types/frequency.md) | Misura l’interazione in base alla frequenza d’uso. |
| [!UICONTROL User growth] | [Attivo](types/active.md) | Identifica gli utenti nuovi, mantenuti, che ritornano o inattivi. |
| [!UICONTROL User growth] | [Crescita netta](types/net-growth.md) | Stai guadagnando o perdendo utenti? |
| [!UICONTROL User stream] | [Linea temporale](types/timeline.md) | Esplora i pattern nell’attività della sessione. |

{style="table-layout:auto"}

## Accesso

Se la tua organizzazione dispone del provisioning per l’analisi guidata, puoi accedervi dalla pagina home del Customer Journey Analytics.

1. Clic **[!UICONTROL Guided analysis]** dalla home page, che ti porta direttamente al [Visualizzazione tendenze di utilizzo](types/usage.md).

   ![Riquadro della pagina di destinazione](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Clic **[!UICONTROL Create new]** per visualizzare le diverse opzioni di visualizzazione e scegliere un punto di partenza diverso per l&#39;analisi.

   ![Crea un nuovo modale](assets/create-new-modal.png){style="border:1px solid gray"}

Se per la tua organizzazione non è ancora disponibile il provisioning per l’analisi guidata, contatta il team del tuo account Adobe.

## Interfaccia

L&#39;interfaccia per l&#39;analisi guidata segue il formato di domanda e risposta. Crea una domanda nella barra delle query, quindi ottieni una risposta con un approfondimento scritto, un grafico e una tabella. A questo punto potrai rispondere alla domanda successiva con i tipi di visualizzazione e le relative impostazioni.

L’analisi guidata utilizza i seguenti elementi dell’interfaccia utente:

| Anteprima interfaccia | Elemento nell’interfaccia utente | Descrizione |
| --- | --- | --- |
| ![Barra delle query](assets/query-rail.png){style="border:1px solid gray"} | Barra delle query | Configura la &quot;domanda&quot; selezionando i componenti desiderati (eventi, proprietà e segmenti) che compongono un’analisi. Le seguenti opzioni sono disponibili per tutti i tipi di visualizzazione, con impostazioni aggiuntive disponibili per singole visualizzazioni. <ul><li>**Selettore di analisi**: elenco a discesa che consente di passare a un nuovo tipo di analisi. Le selezioni delle query vengono mantenute entro i limiti consentiti per il nuovo tipo di analisi.</li><li>**Selettore vista**: elenco a discesa che consente di passare a una nuova visualizzazione (&quot;risposta&quot;) per la query creata. Le selezioni delle query vengono mantenute entro i limiti consentiti per il nuovo tipo di visualizzazione.</li><li>**Eventi**: gli eventi che desideri misurare. Ogni tipo di visualizzazione applica limiti diversi al numero di eventi che è possibile configurare.</li><li>**Filtri**: utilizza ![Filtro](assets/filter.png) nella sezione Eventi o Segmenti per limitare l’ambito di proprietà specifiche. Quando viene selezionata una proprietà, vengono utilizzati entrambi i criteri di filtro standard, ad esempio [!UICONTROL Equals], [!UICONTROL Contains], o [!UICONTROL Ends with]) e sono disponibili i primi 1000 valori della proprietà.</li><li>**Conteggiato come**: metodo di conteggio da applicare agli eventi selezionati.</li><li>**Segmenti**: i segmenti che desideri misurare. Ogni tipo di visualizzazione applica limiti diversi al numero di segmenti che è possibile configurare.</li></ul> |
| ![Grafico](assets/chart.png){style="border:1px solid gray"} | Grafico | Visualizzazione dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. La visualizzazione visualizzata dipende dalla vista e dalle impostazioni sopra il grafico. Il grafico include anche: <ul><li>**Descrizione**: passa il puntatore del mouse su un punto dati del grafico per visualizzare una descrizione comando con ulteriori informazioni.</li><li>**Legenda**: passa il puntatore del mouse sulla serie di legende del grafico per visualizzare le definizioni, se disponibili, per concentrarti su tale serie e nascondere temporaneamente altre serie. Per nascondere una serie nella legenda, fare clic su di essa.</li><li>**Annotazioni**: Applicabile [annotazioni](../components/annotations/overview.md) sono visibili tra la visualizzazione e la legenda. Viene visualizzato come ![Icona Annotazione](assets/annotation.png) nel colore configurato dell’annotazione. I tipi di visualizzazione che mostrano i dati nel tempo inseriscono ![Icona Annotazione](assets/annotation.png) sotto la data o l’intervallo di date configurato. I tipi di visualizzazione che non mostrano dati nel tempo mostrano ![Icona Annotazione](assets/annotation.png) nell’angolo inferiore destro del grafico.</li><li>**Azioni di clic**: per esporre le azioni successive disponibili, fai clic con il pulsante sinistro del mouse su un punto dati. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Tabella](assets/table.png){style="border:1px solid gray"} | Tabella | Una rappresentazione in tabella dei dati restituiti in base all’input proveniente dalla barra delle query e dalle impostazioni. Le colonne della tabella dipendono dal tipo di visualizzazione sopra il grafico. La tabella include inoltre: <ul><li>**Azioni di clic**: per nascondere o esporre una serie di grafici, imposta il pulsante ![Mostra icona Nascondi](assets/hide-in-chart.png) in ogni riga. Sono disponibili azioni aggiuntive facendo clic sul pulsante **[!UICONTROL More]** menu. Le opzioni includono **Salva segmento**.</li></ul> |
| ![Impostazioni di visualizzazione](assets/visualization-settings.png){style="border:1px solid gray"} | Impostazioni di visualizzazione | Opzioni sopra il grafico che consentono di porre la domanda successiva e personalizzare la modalità di restituzione dei dati del grafico e della tabella. Le seguenti opzioni sono disponibili per tutti i tipi di visualizzazione, con impostazioni aggiuntive disponibili per singole visualizzazioni. <ul><li>**Impostazioni grafico**: regola con precisione la visualizzazione del grafico e della tabella. Le opzioni disponibili dipendono dalla vista selezionata.</li><li>**Intervallo di date**: selettore calendario che consente di determinare l’intervallo di date dell’analisi. È inoltre possibile selezionare un intervallo per le visualizzazioni con tendenze, ad esempio giornaliere, settimanali o mensili.</li><li>**Approfondimenti**: informazioni contestuali a seconda dell’analisi visualizzata. Puoi passare a ulteriori informazioni utilizzando le frecce oppure mostrare o nascondere tali informazioni utilizzando l’icona a forma di lampadina in alto a destra.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | Menu | Comandi in alto a destra dell’analisi guidata che forniscono azioni generali per l’analisi.<ul><li>**Selettore visualizzazione dati**: modifica la visualizzazione dati utilizzata dall’analisi. Quando modifichi la visualizzazione dati, cambiano anche i componenti disponibili nella barra delle query.</li><li>**Copia collegamento**: copia negli Appunti un collegamento all’analisi. Verrà richiesto di salvare prima della condivisione.</li><li>**Condividi**: apre la finestra modale di condivisione, con ulteriori opzioni per la condivisione a singoli utenti o gruppi. Verrà richiesto di salvare prima della condivisione.</li><li>**Salva**: salva l&#39;analisi. Se stai salvando una nuova analisi, viene visualizzata una finestra modale che richiede un nome e una descrizione.</li><li>**Salva con nome**: salva l&#39;analisi separatamente dall&#39;analisi corrente, creando una copia. Viene visualizzata una finestra modale che richiede un nuovo nome e una nuova descrizione.</li><li>**Apri in Workspace**: ricrea l’analisi guidata corrente in Analysis Workspace. Il progetto Workspace viene creato in una nuova scheda, evitando interruzioni durante l’analisi guidata. È una copia dell&#39;analisi e non rimane sincronizzata con l&#39;analisi guidata originale una volta aperta. Utilizza questo comando per passare al team di analisti o per approfondire i dati rispetto a quanto consente l’analisi guidata.</li><li>**Copia negli Appunti**: copia l&#39;elemento grafico negli Appunti per incollarlo in altre applicazioni. La barra delle query e la tabella non sono incluse nell&#39;immagine.</li><li>**Scarica PNG**: scarica l&#39;elemento grafico come `.png`. La barra delle query e la tabella non sono incluse nell&#39;immagine.</li><li>**Scarica CSV**: scarica i dati della tabella come `.csv`. La barra delle query e il grafico non sono inclusi nel file.</li></ul> |

{style="table-layout:auto"}

## Provisioning

L’analisi guidata fa parte di Adobe Product Analytics, un componente aggiuntivo a pagamento per il Customer Journey Analytics. Se la tua organizzazione desidera iniziare a utilizzare questo set di funzionalità, contatta il team dell’account Adobe.

Una volta che la tua organizzazione dispone del provisioning per utilizzare l’analisi guidata, gli amministratori dei profili di prodotto possono aggiungere o rimuovere l’accesso all’analisi guidata in Adobe Admin Console.

1. Accedi a [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleziona **[!UICONTROL Customer Journey Analytics]** nell’elenco dei prodotti.
1. Seleziona il profilo di prodotto desiderato per le autorizzazioni da modificare.
1. Fai clic su **[!UICONTROL Permissions]** , quindi fai clic su **[!UICONTROL Edit]** in [!UICONTROL Reporting Tools].
1. Fai clic sull’icona più accanto a **[!UICONTROL Guided Analysis Access]** nell’elenco di [!UICONTROL Available Permission Items], che lo aggiunge all&#39;elenco di [!UICONTROL Included Permission Items].
1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

>[!TIP]
>
>Alcuni amministratori preferiscono abilitare l’analisi guidata e disabilitare Analysis Workspace per il Customer Journey Analytics dei nuovi utenti. Una volta che questi utenti saranno al corrente del prodotto e dei tuoi dati organizzativi, potrai abilitare l’accesso ad Analysis Workspace.
