---
description: Come porre domande sull’analisi dei dati nella documentazione di Customer Journey Analytics
title: Visualizzare i dati con l’agente Data Insights in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: f3f3b34c904c1aeba3fbd07218f323ccd81974d4
workflow-type: tm+mt
source-wordcount: '1792'
ht-degree: 3%

---

# Visualizzare i dati con Data Insights Agent in Customer Journey Analytics

{{release-limited-testing}}

>[!AVAILABILITY]
>
>Data Insights Agent è disponibile per i clienti idonei di Customer Journey Analytics fino al 30 novembre 2025. Dopo tale data, è necessaria una licenza se si desidera continuare a utilizzare Data Insights Agent. Contatta il team del tuo account Adobe per assistenza sulla procedura di gestione delle licenze.

Data Insights Agent, accessibile dall’assistente di intelligenza artificiale in Customer Journey Analytics, è un agente di conversazione di intelligenza artificiale generativo che risponde in modo rapido ed efficiente alle domande sui tuoi dati. Crea visualizzazioni rilevanti in Analysis Workspace utilizzando i componenti della visualizzazione dati e utilizzando i dati effettivi.

L’utilizzo di Data Insights Agent per rispondere a domande incentrate sui dati in Analysis Workspace consente di risparmiare innumerevoli ore che altrimenti trascorreresti manualmente creando visualizzazioni in Analysis Workspace e acquisendo familiarità con i componenti di visualizzazione dati.

![Agente di Data Insights nell&#39;Assistente AI](assets/cja-ai-asst-da.gif)

## Caratteristiche interne ed esterne all&#39;ambito



### Funzioni nell&#39;ambito

| Funzione supportata | Descrizione |
| --- | --- |
| **Creare e aggiornare visualizzazioni** | Genera una tabella a forma libera e la relativa visualizzazione (ad esempio una linea, una barra, un anello e così via).<p>Esempio: *Qual è il profitto tra SKU da febbraio a maggio?* |
| **Tipi di visualizzazione supportati** | <ul><li>A linee</li><li>Multiriga</li><li>Tabella a forma libera</li><li>A barre</li><li>Ad anello</li><li>Numero di riepilogo</li></ul> |
| **Rilevamento prompt fuori ambito** | Se si invia un messaggio che non rientra nell&#39;ambito, ad esempio &quot;Esporta questo progetto&quot;, Data Insights Agent risponde informando che la domanda non rientra nell&#39;ambito. |
| **Domande chiarificatrici** | Se si pone una domanda a cui non è disponibile un contesto sufficiente per la risposta di Data Insights Agent o che è troppo generica, Data Insights Agent risponde con una domanda chiarificatrice o con opzioni suggerite. Esempi: <p>**Componenti**<ul><li>Metrica: *Quale metrica &quot;ricavi&quot; intendevi usare?*</li><li>Dimension: *Specificare su quale delle seguenti &quot;aree geografiche&quot; concentrare l&#39;attenzione.*</li><li>Segmento: *Quale segmento &quot;Account&quot; desideri applicare?*</li><li>Intervallo date: *Per &quot;ultimo mese&quot;, intendevi l&#39;ultimo mese completo o gli ultimi 30 giorni?*</li></ul>**Elementi Dimension**: quale &quot;nome archivio&quot; intendevi? Ad esempio, #5274 store, #2949 store e così via. |
| **Turno multiplo** | Data Insights Agent risponde a un prompt con il contesto da qualsiasi prompt precedente, consentendo agli utenti di aggiornare le visualizzazioni e porre domande di follow-up. Esempio: <ul><li>Prompt 1: *Eventi di tendenza da marzo.*</li><li>Prompt 2: *Visualizza i dati da marzo ad aprile*</li></ul> |
| **Verificabilità** | La verificabilità e la correttezza dei dati possono essere confermate tramite la tabella a forma libera generata e la visualizzazione dei dati. Ad esempio, se un utente chiede *Trend ordini del mese scorso*, puoi confermare che la metrica corretta (&quot;ordini&quot;) e l&#39;intervallo di date (&quot;mese scorso&quot;) sono stati selezionati nel pannello, nella visualizzazione dati e nella tabella a forma libera appena generati. |
| **Feedback** | <ul><li>Miniature in alto</li><li>Miniature in basso</li><li>Contrassegno</li></ul> |

### Funzioni fuori ambito

| Funzione non supportata | Descrizione |
| --- | --- |
| **Riepilogo o risposta in linea** | Data Insights Agent non può rispondere in linea nella barra chat con una risposta di riepilogo di un prompt utente. Esempio di prompt fuori ambito:<ul><li>*Visualizza un riepilogo delle informazioni contenute nell&#39;ultimo prompt.*</li><li>*Riepiloga gli elementi di rilievo dalla visualizzazione delle linee.*</li></ul> |
| **Domande chiarificatrici** | Le domande più chiare sono limitate ai componenti e agli elementi dimensionali. Data Insights Agent non è in grado di chiarire elementi quali visualizzazioni dati, visualizzazioni, granularità dei dati, confronto e ambito. Quando non è possibile utilizzare le domande di chiarimento, l’agente utilizza per impostazione predefinita ciò che viene richiesto con maggiore probabilità. Se restituisce una visualizzazione o una granularità dei dati impreviste, puoi utilizzare la funzionalità multi-turn/update per regolare la visualizzazione e i dati. |
| **Azioni/funzionalità Workspace** | Data Insights Agent non può intraprendere azioni per un utente in Workspace a parte la creazione e l’aggiornamento delle visualizzazioni. Ad esempio, non può effettuare nessuna delle seguenti operazioni:<ul><li>Pulsanti dell’interfaccia utente per le azioni contestuali (aggiungi al grafico, nuovo pannello, nuova tabella)</li><li>Condividi</li><li>Esportare</li><li>Scaricare</li><li>Gestire le preferenze utente</li><li>Cura</li><li>Gestire la visualizzazione dati</li><li>App delle dashboard di Analytics</li><li>Attribution</li></ul> |
| **Tipi di visualizzazione non supportati** | <ul><li>Flusso</li><li>Abbandono</li><li>Tabella coorte</li><li>Superfici, Superfici sovrapposte</li><li>Barre sovrapposte</li><li>Bullet</li><li>Combinato</li><li>Istogramma</li><li>Barre orizzontali, barre orizzontali sovrapposte</li><li>Riepilogo delle metriche chiave</li><li>A dispersione</li><li>Variazione di riepilogo</li><li>Testo</li><li>Mappa ad albero</li><li>Venn</li></ul> |

## Gestire l’accesso a Data Insights Agent in Customer Journey Analytics

I seguenti parametri regolano l’accesso a Data Insights Agent in Customer Journey Analytics:

* **Accesso alla soluzione**: Data Insights Agent è disponibile per i clienti Customer Journey Analytics Prime e Ultimate. Non è disponibile in Adobe Analytics.

* **Accesso contrattuale**: se non sei in grado di utilizzare Data Insights Agent nell&#39;Assistente AI, contatta l&#39;amministratore della tua organizzazione o il team dell&#39;account Adobe. Prima che la tua organizzazione possa utilizzare Data Insights Agent, devi accettare alcuni termini legali relativi all’intelligenza artificiale generativa.

* **Autorizzazioni**: per consentire agli utenti di accedere a Data Insights Agent, è necessario concedere le autorizzazioni necessarie in [!UICONTROL Adobe Admin Console].

  Per concedere le autorizzazioni, un [amministratore del profilo di prodotto](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html) deve completare i seguenti passaggi in [!UICONTROL Admin Console]:
   1. In **[!UICONTROL Admin Console]**, selezionare la scheda **[!UICONTROL Products]** per visualizzare la pagina **[!UICONTROL All products and services]**.
   1. Seleziona **[!UICONTROL Customer Journey Analytics]**.
   1. Nella scheda **[!UICONTROL Product Profiles]** selezionare il titolo del profilo di prodotto per il quale si desidera fornire l&#39;accesso a [!UICONTROL AI Assistant: Product Knowledge].
   1. Nel profilo di prodotto specifico, selezionare la scheda **[!UICONTROL Permissions]**.

      ![Scheda Autorizzazioni in Admin Console](assets/ai-assistant-permissions-tab.png)

   1. Nella riga **[!UICONTROL Reporting Tools]** della tabella fornita, seleziona l&#39;icona di modifica ![Modifica](/help/assets/icons/Edit.svg).
   1. Scorri fino a o cerca **[!UICONTROL AI Assistant: Product Knowledge]**, quindi seleziona l&#39;icona più ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) accanto a questa autorizzazione.

      L&#39;autorizzazione **[!UICONTROL AI Assistant: Product Knowledge]** è stata aggiunta alla colonna **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](assets/ai-assistant-permissions.png).

   1. Seleziona la scheda **[!UICONTROL Data View Tools]**, quindi fai clic sull&#39;icona più ![AggiungiCerchio](/help/assets/icons/AddCircle.svg) accanto all&#39;autorizzazione **[!UICONTROL Data Insights Agent]**.

      L&#39;autorizzazione **[!UICONTROL Data Insights Agent]** è stata aggiunta alla colonna **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](assets/ai-assistant-permissions-dataviewtools.png).

   1. Selezionare la scheda **[!UICONTROL Data Views]** per scegliere le visualizzazioni dati che si desidera abilitare per Data Insights Agent.

      >[!IMPORTANT]
      >
      >Data Insights Agent può fare riferimento alle visualizzazioni dati incluse nello stesso giorno in cui vengono abilitate in Admin Console.

   1. Cerca o scorri fino alle visualizzazioni dati che desideri abilitare, quindi seleziona l&#39;icona più (![AggiungiCerchio](/help/assets/icons/AddCircle.svg)) accanto al nome di ciascuna visualizzazione dati.

      Ogni visualizzazione dati aggiunta è visibile nella colonna **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](assets/ai-assistant-permissions-dataviews.png).

   1. Seleziona **[!UICONTROL Save]** per salvare le modifiche.

  Per ulteriori informazioni sul controllo di accesso, vedere [Controllo di accesso](/help/technotes/access-control.md#access-control).

## Accedere a Data Insights Agent nell’Assistente AI

1. Vai a [experience.adobe.com](https://experience.adobe.com/) e accedi con il tuo Adobe ID.

2. Seleziona **Customer Journey Analytics** dalla Home di Experience Cloud.

3. Seleziona **[!UICONTROL Blank project]** nel banner nella parte superiore della pagina dei progetti per aprire un nuovo progetto vuoto.

4. Verificare che la visualizzazione dati selezionata per il pannello sia abilitata per l&#39;utilizzo con Data Insights Agent, come descritto in [Gestione dell&#39;accesso a Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

5. Seleziona l’icona della chat dell’Assistente AI nell’area in alto a destra della pagina.

   Se l’icona della chat non è visibile, contatta l’amministratore in modo che possa abilitare le seguenti funzioni in Admin Console:

   * Strumenti di reporting: **[!UICONTROL AI Assistant: Product Knowledge]**

   * Strumenti visualizzazione dati: **[!UICONTROL Data Insights Agent]**

   Per ulteriori dettagli, vedere [Gestire l&#39;accesso a Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![Icona Assistente IA](/help/assets/ai-asst-icon.png)

6. Nella finestra di dialogo **[!UICONTROL Ask about Customer Journey Analytics]** nella parte inferiore della pagina, fai una domanda sulla visualizzazione dei dati utilizzando Data Insights Agent.

   Per ulteriori informazioni, vedi gli esempi seguenti.

### Esempio 1

Ad esempio, supponiamo che tu sia interessato agli ordini ricevuti dalla tua azienda in luglio.

**Prompt:** Inserisci *&quot;Trend ordini in luglio.&quot;*

![prompt IA](/help/assets/ai-asst-prompt1.png)

**Risposta:** Data Insights Agent raccoglie informazioni approfondite esaminando i dati nella visualizzazione dati, incluse le metriche e i componenti. Traduce il prompt nelle dimensioni e nelle metriche corrette all’interno dell’intervallo di dati.

Come puoi vedere, ha generato automaticamente un grafico a linee e una tabella a forma libera per mostrare gli ordini di luglio.

![Risposta alla richiesta - grafico a linee e tabella a forma libera](/help/assets/ai-asst-result.png)

### Esempio 2

Ora vuoi vedere come si confrontano i ricavi per regione.

**Prompt:** Nella finestra del prompt, immettere *&quot;Mostra ricavi per area&quot;*

**Risposta:** Data Insights Agent comprende in modo intelligente che per &quot;area geografica&quot; si intende &quot;area del cliente&quot;. Produce un grafico a barre che mostra al meglio i ricavi per area:

![Grafico a barre](/help/assets/ai-asst-result2.png)

### Esempio 3

Quindi, oltre a comprendere i ricavi per area, vuoi anche visualizzare i dati per i profitti per area. Invece di ripetere la richiesta precedente, puoi chiedere a Data Insights Agent di aggiornare la visualizzazione e la tabella a forma libera più recenti.

**Prompt:** Nella finestra del prompt, digitare *&quot;Aggiungi profitto.&quot;*

**Risposta:** Il grafico **[!UICONTROL Bar]** fornisce ancora la risposta più concisa, ma la metrica di profitto è stata aggiunta come colonna nella tabella a forma libera:

![Grafico a barre](/help/assets/ai-asst-result4.png)

### Esempio 4

Infine, esaminiamo i ricavi per categoria di prodotto.

**Prompt:** Nella finestra del prompt, immettere *&quot;Proporzione di ricavi per categoria di prodotto.&quot;*

**Risposta:** Anche in questo caso, Data Insights Agent sceglie la visualizzazione più appropriata, in questo caso **[!UICONTROL Donut]**, per rispondere alla domanda.

![Anello](/help/assets/ai-asst-result3.png)

## Esempio di prompt di visualizzazione dati

Di seguito sono riportati alcuni esempi di prompt comuni e delle visualizzazioni utilizzate da Data Insights Agent per rispondere a tali prompt.

| Esempio di prompt | Visualizzazione prevista |
| --- | --- |
| Mostra profitti in [Mese] | A linee<p>La richiesta di una tendenza o di una metrica entro un determinato intervallo di tempo per impostazione predefinita restituisce una visualizzazione a linee. |
| Andamento ordini in [Mese] | A linee |
| Mostra ricavi per area geografica in [Mese] | A barre |
| Quota di ricavi per categoria di prodotto | Ad anello |
| Ordini per giorno della settimana, da gennaio a maggio | A barre |
| Mostra ordini per genere, da marzo a giugno | A barre |
| Qual è il profitto tra SKU da febbraio a maggio | A barre |
| Ricavi per nome archivio in [Mese] | A barre |
| Quali sono stati i miei 10 SKU principali in base al profitto in [Mese]? | A barre |
| Percentuale di acquisti per mese dell&#39;anno | Ad anello |
| Profitto totale in [Mese] | Numero di riepilogo<p>Se si richiede il &quot;totale&quot; di una metrica in un determinato intervallo di tempo, viene restituita una visualizzazione del numero di riepilogo. |


## Best practice per la richiesta di informazioni

Data Insights Agent elabora il contesto fornito da ogni richiesta dell’utente e tenta di rispondere in modo intelligente con la visualizzazione e i componenti più appropriati in una tabella a forma libera.

Le risposte possono variare in base alle parole e alle frasi specifiche utilizzate nel prompt, e lievi modifiche nella lingua possono portare a risultati diversi.

Per ottenere i migliori risultati, considera le seguenti linee guida:

* **Specificare:** Includere termini esatti per limitare la risposta. Di seguito è riportato un esempio di un prompt specifico: &quot;Vendite del mese scorso in California&quot;

* **Usa metriche, dimensioni e segmenti chiari:** L&#39;aggiunta di metriche specifiche (ad esempio &quot;Ricavi&quot;), dimensioni (ad esempio &quot;nome sito Web&quot;), segmenti (ad esempio &quot;utenti iPhone&quot;) e intervalli di date (ad esempio &quot;ultimi tre mesi&quot;) consente a Data Insights Agent di concentrarsi sui dati giusti.

* **Fai domande dirette:** La formulazione delle domande semplifica la fornitura da parte di Data Insights Agent di informazioni chiare e pertinenti. Di seguito è riportato un esempio di una domanda diretta in un prompt: &quot;Qual è il reddito medio per categoria di prodotto quest&#39;anno?&quot;

Rivedi la seguente tabella di termini e frasi di esempio che puoi utilizzare nei prompt con Data Insights Agent, insieme ai tipi di risposte che puoi aspettarti.

Questi esempi sono progettati per aiutarti a capire in che modo parole o strutture specifiche possono influenzare l’output dell’agente di Data Insight, garantendo informazioni più precise e preziose. Data Insights Agent utilizza un’intelligenza artificiale generativa, pertanto le visualizzazioni o i dati selezionati possono variare leggermente in base a prompt simili.

| Risultato desiderato | Termini e frasi di esempio |
| --- | --- |
| Visualizzazione Numero di riepilogo | <ul><li>Totale</li></ul> |
| Confronta componenti | <ul><li>Confronto</li><li>VS</li><li>Contrasto</li><li>Settimana per settimana</li><li>Su base mensile</li><li>Trimestre su trimestre</li><li>Anno su Anno</li></ul> |
| Visualizzazione Anello | <ul><li>Proporzione</li><li>Quota di</li><li>Distribuzione</li><li>Percento</li><li>Contributo</li><li>Porzione</li><li>Parti</li></ul> |
| Visualizzazione Linee | <ul><li>Tendenza</li><li>[Metrica] in [Intervallo di tempo]</li></ul> |
| Visualizzazione a barre | <ul><li>[Metrica] da [Dimension]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->

