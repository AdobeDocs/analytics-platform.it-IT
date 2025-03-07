---
description: Come porre domande sull’analisi dei dati nella documentazione di Customer Journey Analytics
title: Assistente AI per l’analisi dei dati in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: ac3ec479938acf509bbd26be282b75e75dd49c33
workflow-type: tm+mt
source-wordcount: '1633'
ht-degree: 3%

---

# Visualizzare i dati con l’Assistente AI in Customer Journey Analytics

L’Assistente per l’intelligenza artificiale in Customer Journey Analytics è un agente di conversazione generativo che risponde in modo rapido ed efficiente alle domande sui tuoi dati. Crea visualizzazioni rilevanti in Analysis Workspace utilizzando i componenti della visualizzazione dati e utilizzando i dati effettivi.

L’utilizzo dell’Assistente AI per rispondere a domande incentrate sui dati in Analysis Workspace consente di risparmiare innumerevoli ore che altrimenti rischieresti di trascorrere manualmente per creare visualizzazioni in Analysis Workspace e acquisire familiarità con i componenti della visualizzazione dati.

![Assistente di IA per l&#39;analisi dei dati](assets/cja-ai-asst-da.gif)

## Funzioni interne ed esterne all’ambito per la versione di Alpha

### Funzioni di Alpha nell’ambito

| Funzione supportata | Descrizione |
| --- | --- |
| **Creare e aggiornare visualizzazioni** | Genera una tabella a forma libera e la relativa visualizzazione (ad esempio una linea, una barra, un anello e così via).<p>Esempio: *Qual è il profitto tra SKU da febbraio a maggio?* |
| **Tipi di visualizzazione supportati** | <ul><li>A linee</li><li>Multiriga</li><li>Tabella a forma libera</li><li>Barre</li><li>Ad anello</li><li>Numero di riepilogo</li></ul> |
| **Rilevamento prompt fuori ambito** | Se si invia un messaggio che non rientra nell&#39;ambito, ad esempio &quot;Esporta il progetto&quot;, l&#39;Assistente risponde informando che la domanda non rientra nell&#39;ambito. |
| **Domande chiarificatrici** | Se poni una domanda che non ha abbastanza contesto per cui l’Assistente IA deve rispondere, o è troppo generica, l’Assistente IA risponde con una domanda chiarificatrice o con opzioni suggerite. Esempi: <p>**Componenti**<ul><li>Metrica: *Quale metrica &quot;ricavi&quot; intendevi usare?*</li><li>Dimension: *Specificare su quale delle seguenti &quot;aree geografiche&quot; concentrare l&#39;attenzione.*</li><li>Filtro: *Quale filtro &quot;Account&quot; desideri applicare?*</li><li>Intervallo date: *Per &quot;ultimo mese&quot;, intendevi l&#39;ultimo mese completo o gli ultimi 30 giorni?*</li></ul>**Elementi Dimension**: quale &quot;nome archivio&quot; intendevi? Ad esempio, #5274 store, #2949 store e così via. |
| **Turno multiplo** | L’Assistente AI risponde a un prompt con il contesto da qualsiasi prompt precedente, consentendo agli utenti di aggiornare le visualizzazioni e porre domande di follow-up. Esempio: <ul><li>Prompt 1: *Eventi di tendenza da marzo.*</li><li>Prompt 2: *Visualizza i dati da marzo ad aprile*</li></ul> |
| **Verificabilità** | La verificabilità e la correttezza dei dati possono essere confermate tramite la tabella a forma libera generata e la visualizzazione dei dati. Ad esempio, se un utente chiede *Trend ordini del mese scorso*, puoi confermare che la metrica corretta (&quot;ordini&quot;) e l&#39;intervallo di date (&quot;mese scorso&quot;) sono stati selezionati nel pannello, nella visualizzazione dati e nella tabella a forma libera appena generati. |
| **Feedback** | <ul><li>Miniature in alto</li><li>Miniature in basso</li><li>Contrassegno</li></ul> |

### Funzioni di Beta fuori ambito

| Funzione non supportata | Descrizione |
| --- | --- |
| **Riepilogo o risposta in linea** | L’Assistente AI non può rispondere in linea nella barra della chat con una risposta di riepilogo di un prompt utente. Esempio di prompt fuori ambito:<ul><li>*Visualizza un riepilogo delle informazioni contenute nell&#39;ultimo prompt.*</li><li>*Riepiloga gli elementi di rilievo dalla visualizzazione delle linee.*</li></ul> |
| **Domande chiarificatrici** | Le domande più chiare sono limitate ai componenti e agli elementi dimensionali. L’Assistente AI non è in grado di chiarire elementi quali visualizzazioni dati, visualizzazioni, granularità dei dati, confronto e ambito. Quando non è possibile utilizzare le domande di chiarimento, l&#39;Assistente utilizza per impostazione predefinita ciò che viene richiesto. Se restituisce una visualizzazione o una granularità dei dati impreviste, puoi utilizzare la funzionalità multi-turn/update per regolare la visualizzazione e i dati. |
| **Azioni/funzionalità Workspace** | L’Assistente AI non può intraprendere azioni per un utente in Workspace a parte la creazione e l’aggiornamento delle visualizzazioni. Ad esempio, non può effettuare nessuna delle seguenti operazioni:<ul><li>Pulsanti dell’interfaccia utente per le azioni contestuali (aggiungi al grafico, nuovo pannello, nuova tabella)</li><li>Condividi</li><li>Esportazione</li><li>Scaricare</li><li>Gestire le preferenze utente</li><li>Cura</li><li>Gestire la visualizzazione dati</li><li>App delle dashboard di Analytics</li><li>Attribuzione</li></ul> |
| **Tipi di visualizzazione non supportati** | <ul><li>Flusso</li><li>Fallout (abbandono)</li><li>Tabella coorte</li><li>Superfici, Superfici sovrapposte</li><li>Barre sovrapposte</li><li>Bullet</li><li>Combinato</li><li>Istogramma</li><li>Barre orizzontali, barre orizzontali sovrapposte</li><li>Riepilogo delle metriche chiave</li><li>A dispersione</li><li>Variazione di riepilogo</li><li>Testo</li><li>Mappa ad albero</li><li>Venn</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to Data visualization in AI Assistant:

* **Solution access**: Data visualization in AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data visualization in AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data visualization]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data visualization** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Accedere e utilizzare la visualizzazione dei dati in AI Assistant

1. Vai a [experience.adobe.com](https://experience.adobe.com/) e accedi con il tuo Adobe ID.

2. Seleziona **Customer Journey Analytics** dalla Home di Experience Cloud.

3. Seleziona **[!UICONTROL Blank project]** nel banner nella parte superiore della pagina dei progetti per aprire un nuovo progetto vuoto.

4. Assicurati che la visualizzazione dati selezionata per il pannello sia la stessa abilitata per l’utilizzo con l’Assistente IA per i test di Beta.

   In caso di dubbi, contatta il canale Slack di Beta.

5. Seleziona l’icona della chat dell’Assistente AI nell’area in alto a destra della pagina.

   Se l’icona della chat non è visibile, contatta l’amministratore in modo che possa abilitare le seguenti funzioni in Admin Console:

   * **[!UICONTROL AI Assistant: Product Knowledge]**

   * **[!UICONTROL AI Assistant: Data Analysis]**

   Per ulteriori dettagli, gli amministratori possono visualizzare [queste istruzioni](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

   ![Icona Assistente IA](/help/assets/ai-asst-icon.png)

6. Nella finestra di dialogo **[!UICONTROL Ask about Customer Journey Analytics]** nella parte inferiore della pagina, fai una domanda sulla visualizzazione dei dati nell&#39;Assistente AI.

   Per ulteriori informazioni, vedi gli esempi seguenti.

### Esempio 1

Ad esempio, supponiamo che tu sia interessato agli ordini ricevuti dalla tua azienda in luglio.

**Prompt:** Inserisci *&quot;Trend ordini in luglio.&quot;*

![prompt IA](/help/assets/ai-asst-prompt1.png)

**Risposta:** L&#39;Assistente AI raccoglie informazioni approfondite esaminando i dati nella visualizzazione dati, incluse le metriche e i componenti. Traduce il prompt nelle dimensioni e nelle metriche corrette all’interno dell’intervallo di dati.

Come puoi vedere, ha generato automaticamente un grafico a linee e una tabella a forma libera per mostrare gli ordini di luglio.

![Risposta alla richiesta - grafico a linee e tabella a forma libera](/help/assets/ai-asst-result.png)

### Esempio 2

Ora vuoi vedere come si confrontano i ricavi per regione.

**Prompt:** Nella finestra del prompt, immettere *&quot;Mostra ricavi per area&quot;*

**Risposta:** L&#39;Assistente AI comprende in modo intelligente che per &quot;area&quot; si intende &quot;area del cliente&quot;. Produce un grafico a barre che mostra al meglio i ricavi per area:

![Grafico a barre](/help/assets/ai-asst-result2.png)

### Esempio 3

Quindi, oltre a comprendere i ricavi per regione, è necessario visualizzare anche i dati relativi ai profitti per regione. Invece di ripetere il prompt precedente, puoi chiedere all’Assistente IA di aggiornare la visualizzazione e la tabella a forma libera più recenti.

**Prompt:** Nella finestra del prompt, digitare *&quot;Aggiungi profitto.&quot;*

**Risposta:** Il grafico **[!UICONTROL Bar]** fornisce ancora la risposta più concisa, ma la metrica di profitto è stata aggiunta come colonna nella tabella a forma libera:

![Grafico a barre](/help/assets/ai-asst-result4.png)

### Esempio 4

Infine, esaminiamo i ricavi per categoria di prodotto.

**Prompt:** Nella finestra del prompt, immettere *&quot;Proporzione di ricavi per categoria di prodotto.&quot;*

**Risposta:** di nuovo, la visualizzazione dati nell&#39;Assistente di intelligenza artificiale sceglie la visualizzazione più appropriata, in questo caso la visualizzazione **[!UICONTROL Donut]**, per rispondere alla domanda.

![Anello](/help/assets/ai-asst-result3.png)

## Esempio di prompt di visualizzazione dati

Di seguito sono riportati alcuni esempi di prompt comuni e delle visualizzazioni utilizzate dall’Assistente IA per rispondere a tali prompt.

| Esempio di prompt | Visualizzazione prevista |
| --- | --- |
| Mostra profitti in [Mese] | A linee<p>La richiesta di una tendenza o di una metrica entro un determinato intervallo di tempo per impostazione predefinita restituisce una visualizzazione a linee. |
| Andamento ordini in [Mese] | A linee |
| Mostra ricavi per area geografica in [Mese] | Barre |
| Quota di ricavi per categoria di prodotto | Ad anello |
| Ordini per giorno della settimana, da gennaio a maggio | Barre |
| Mostra ordini per genere, da marzo a giugno | Barre |
| Qual è il profitto tra SKU da febbraio a maggio | Barre |
| Ricavi per nome archivio in [Mese] | Barre |
| Quali sono stati i miei 10 SKU principali in base al profitto in [Mese]? | Barre |
| Percentuale di acquisti per mese dell&#39;anno | Ad anello |
| Profitto totale in [Mese] | Numero di riepilogo<p>Se si richiede il &quot;totale&quot; di una metrica in un determinato intervallo di tempo, viene restituita una visualizzazione del numero di riepilogo. |


## Best practice per la richiesta di informazioni

L’Assistente AI elabora il contesto fornito da ogni prompt utente e tenta di rispondere in modo intelligente con la visualizzazione e i componenti più appropriati in una tabella a forma libera.

Le risposte possono variare in base alle parole e alle frasi specifiche utilizzate nel prompt, e lievi modifiche nella lingua possono portare a risultati diversi.

Per ottenere i migliori risultati, considera le seguenti linee guida:

* Sii specifico: includi termini esatti per limitare la risposta. Di seguito è riportato un esempio di un prompt specifico: &quot;Last month&#39;s sales in California&quot; (Vendite del mese scorso in California)

* Utilizzare metriche e filtri chiari: l’aggiunta di metriche specifiche (ad esempio &quot;Ricavi&quot;), dimensioni (ad esempio &quot;nome del sito web&quot;), filtri (ad esempio &quot;utenti iPhone&quot;) e intervalli di date (ad esempio &quot;ultimi tre mesi&quot;) consente all’Assistente AI di concentrarsi sui dati giusti.

* Domande dirette: la formulazione delle domande facilita l’assistente AI nel fornire informazioni chiare e pertinenti. Di seguito è riportato un esempio di una domanda diretta in un prompt: &quot;Qual è il reddito medio per categoria di prodotto quest&#39;anno?&quot;

Rivedi la seguente tabella di termini e frasi di esempio che puoi utilizzare nei prompt con la visualizzazione dei dati nell’Assistente AI, insieme ai tipi di risposte che puoi aspettarti.

Questi esempi sono progettati per aiutarti a comprendere in che modo parole o strutture specifiche possono influenzare l’output dell’Assistente AI, garantendo informazioni più precise e preziose. L’Assistente AI utilizza l’intelligenza artificiale generativa, pertanto le visualizzazioni o i dati selezionati possono variare leggermente in base a prompt simili.

| Risultato desiderato | Termini e frasi di esempio |
| --- | --- |
| Visualizzazione Numero di riepilogo | <ul><li>Totale</li></ul> |
| Confronta componenti | <ul><li>Confronta</li><li>VS</li><li>Contrasto</li><li>Settimana per settimana</li><li>Su base mensile</li><li>Trimestre su trimestre</li><li>Anno su Anno</li></ul> |
| Visualizzazione Anello | <ul><li>Proporzione</li><li>Quota di</li><li>Distribuzione</li><li>Percento</li><li>Contributo</li><li>Porzione</li><li>Parti</li></ul> |
| Visualizzazione Linee | <ul><li>Tendenza</li><li>[Metrica] in [Intervallo di tempo]</li></ul> |
| Visualizzazione a barre | <ul><li>[Metrica] da [Dimension]</li></ul> |

## Aspettative di test di Beta e feedback richiesto

Dopo aver posto ciascuna domanda, rivedi attentamente la risposta fornita dall’assistente. È fondamentale valutare in modo completo le visualizzazioni generate prima di fornire un feedback.

Durante la valutazione di una risposta dall’Assistente IA, considera quanto segue:

* Risposta o modello della barra di chat: valuta la risposta testuale fornita dall’Assistente. La risposta è appropriata dato il contesto della richiesta?

* Visualizzazione/grafico: valuta la visualizzazione. È la visualizzazione appropriata o prevista per la domanda, o ti saresti aspettato una visualizzazione diversa?

* Tabella a forma libera: valuta la tabella a forma libera. I dati della tabella a forma libera sono corretti? I dati vengono suddivisi dove richiesto? I filtri applicati sono quelli richiesti o previsti?

* Messaggio di errore/fuori ambito: se viene visualizzato un messaggio di errore generico che indica che la domanda non rientra nell’ambito, indica se il messaggio fuori ambito è appropriato, in base al prompt. Il prompt era nell&#39;ambito?

**Per ogni risposta, assegna un pollice in alto o un pollice in basso, in base alla risposta.**

Dopo la selezione del pollice verso l&#39;alto o del pollice verso il basso, effettuare una selezione per le caselle di feedback selezionate più volte. Se si desidera fornire un feedback aggiuntivo, aggiungere note nella casella di testo aperta.

## Domande e contatti

* Invia domande e feedback nel canale Slack di Alpha: #cja-assistant-data-alpha
