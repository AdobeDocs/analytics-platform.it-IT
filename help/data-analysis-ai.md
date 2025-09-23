---
description: Documentazione di Customer Journey Analytics su come porre domande sull’analisi dei dati
title: Visualizzare i dati con l’agente Data Insights in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: cd92bde10b9cb473c4df791e91296a2a43b2ad84
workflow-type: tm+mt
source-wordcount: '2390'
ht-degree: 94%

---

# Visualizzare i dati con l’agente Data Insights

>[!AVAILABILITY]
>
>L’agente Data Insights è disponibile per la clientela idonea per un periodo limitato. L’accesso all’agente Data Insights terminerà il 30 novembre 2025. Per continuare a utilizzare l’agente Data Insights senza interruzioni, contatta il rappresentante del tuo account Adobe per ulteriori informazioni sulle relative licenze.

L’agente Data Insights, accessibile dall’[Assistente IA](/help/ai-assistant.md) in Customer Journey Analytics, è un agente per conversazioni basate sull’IA generativa che risponde in modo rapido ed efficiente alle domande sui tuoi dati. Crea visualizzazioni pertinenti in Analysis Workspace utilizzando i componenti della visualizzazione dati e i tuoi dati effettivi.

L’utilizzo dell’agente Data Insights per rispondere a domande incentrate sui dati in Analysis Workspace consente di risparmiare tempo prezioso, evitandoti di dover creare manualmente le visualizzazioni in Analysis Workspace e acquisire familiarità con i componenti per le visualizzazioni dei dati.

![Agente Data Insights nell’Assistente IA](assets/cja-ai-asst-da.gif)

## Funzioni incluse ed escluse

| Funzione | Inclusa | Esclusa |
| --- | --- | --- |
| **Tipi di visualizzazione** | <ul><li>A linee</li><li>A più linee</li><li>Tabella a forma libera</li><li>A barre</li><li>Ad anello</li><li>Numero di riepilogo</li></ul> | <ul><li>Flusso</li><li>Fallout</li><li>Tabella coorte</li><li>Superfici, Superfici sovrapposte</li><li>Barre sovrapposte</li><li>Bullet</li><li>Combinato</li><li>Istogramma</li><li>Barre orizzontali, Barre orizzontali sovrapposte</li><li>Riepilogo delle metriche chiave</li><li>A dispersione</li><li>Variazione di riepilogo</li><li>Testo</li><li>Mappa ad albero</li><li>Venn</li><li>Analisi guidata: crescita attiva, tendenze di conversione, coinvolgimento, impatto sul primo utilizzo, frequenza, funnel, crescita netta, impatto sullle versioni, conservazione, timeline, tendenze</li></ul> |
| **Azioni Workspace e funzionalità agente** | <ul><li>Creare e aggiornare le visualizzazioni<p>Genera una tabella a forma libera e la visualizzazione associata (ad es. a linee, a barre, ad anello, ecc.).<p>Ad esempio, *Qual è il profitto per le varie SKU da febbraio a maggio?*</p></li><li>Porre domande di follow-up<p>Rispondi a un prompt nel contesto di eventuali prompt precedenti. Ad esempio:</p> <ul><li>Prompt 1: *Eventi di tendenza da marzo.*</li><li>Prompt 2: *Mostra invece i dati da marzo ad aprile*</li></ul> </li><li>Rilevamento di prompt esclusi dall’ambito<p>Se invii un prompt che non rientra nell’ambito di azione dell’agente Data Insights, ad esempio *Esporta questo progetto*, l’agente risponde informandoti che la domanda è esclusa dal suo ambito.</p></li></ul> | <ul><li>Condividere</li><li>Esportare</li><li>Scaricare</li><li>Gestire le preferenze utente</li><li>Gestire la visualizzazione dati</li><li>App delle dashboard di Analytics</li><li>Attribuzione</li><li>Riepilogo o risposta in linea<p>L’agente Data Insights non può rispondere in linea nella barra della chat con una risposta di riepilogo per un prompt dell’utente. Esempi di prompt esclusi dall’ambito dell’agente: *Fai un riepilogo degli insight dall’ultimo prompt* e *Riepiloga i punti principali che emergono dalla visualizzazione a linee.*</p></li></ul> |
| **Domande chiarificatrici** | Se poni una domanda troppo generica o priva del contesto necessario affinché l’agente Data Insights possa rispondere, l’agente Data Insights risponde con una domanda chiarificatrice o con opzioni suggerite. <p>Alcuni esempi di domande chiarificatrici relative ai componenti:</p><ul><li>Metrica: *Quale metrica “entrate” intendevi?*</li><li>Dimensione: *Quali delle seguenti “aree geografiche” ti interessano?*</li><li>Segmento: *Quale segmento “Account” volevi applicare?*</li><li>Intervallo date: *Per “ultimo mese”, intendi l’ultimo mese completo o gli ultimi 30 giorni?*</li></ul><p>Esempio di domanda chiarificatrice relativa a elementi dimensionali:</p> <ul><li>Quale “nome negozio” intendi? (es.: Negozio #5274, Negozio #2949 e così via.)</li></ul> | Le domande chiarificatrici sono limitate ai componenti e agli elementi dimensionali. L’agente Data Insights non è in grado di chiarire elementi quali visualizzazioni dati, visualizzazioni, granularità dei dati, confronto e ambito. Quando non è possibile utilizzare una domanda chiarificatrice, per impostazione predefinita l’agente considera ciò che è più probabile che tu chieda. Se restituisce una visualizzazione o una granularità dei dati imprevista, puoi porre una domanda di follow-up o regolare la visualizzazione e i dati. |
| **Verificabilità e correttezza dei dati** | La verificabilità e la correttezza dei dati possono essere confermate visualizzando la tabella a forma libera e la visualizzazione dei dati generate. <p>Ad esempio, se chiedi all’agente Data Insights la *tendenza degli ordini dell’ultimo mese*, puoi verificare se la metrica corretta (“ordini”) e l’intervallo di date (“ultimo mese”) sono selezionati nel pannello, nella visualizzazione dati e nella tabella a forma libera appena generati. | L’agente Data Insights non risponde informandoti su quali componenti o visualizzazioni sono stati aggiunti.</p> |
| **Meccanismi di feedback** | <ul><li>Pollice in su</li><li>Pollice in giù</li><li>Segnalazione</li></ul> |  |


## Gestire l’accesso all’agente Data Insights {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="Abilita per Data Insights Agent"
>abstract="Questa opzione abilita la visualizzazione dati per l’utilizzo con Data Insights Agent. Data Insights Agent è un agente di conversazione di intelligenza artificiale generativo accessibile dall’Assistente di intelligenza artificiale in Customer Journey Analytics. Consente di analizzare rapidamente i dati con messaggi di testo. Crea visualizzazioni pertinenti in Analysis Workspace utilizzando i componenti della visualizzazione dati e i tuoi dati effettivi."

<!-- markdownlint-enable MD034 -->

I seguenti parametri regolano l’accesso all’agente Data Insights in Customer Journey Analytics:

* **Accesso alla soluzione**: l’agente Data Insights è disponibile per tutta la clientela di Customer Journey Analytics come parte di un programma di accesso limitato fino al 30 novembre 2025. Non è disponibile in Adobe Analytics.

* **Accesso contrattuale**: se non sei in grado di utilizzare l’agente Data Insights nell’Assistente IA, contatta l’amministratore della tua organizzazione o il team Adobe Account. Prima che la tua organizzazione possa utilizzare l’agente Data Insights, devi accettare alcuni termini legali relativi all’IA generativa.

* **Autorizzazioni**: per consentire agli utenti di accedere all’agente Data Insights, è necessario concedere le autorizzazioni necessarie in [!UICONTROL Adobe Admin Console].

  Per concedere le autorizzazioni, un [amministratore del profilo di prodotto](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html?lang=it) deve completare i seguenti passaggi in [!UICONTROL Admin Console]:
   1. In **[!UICONTROL Admin Console]**, seleziona la scheda **[!UICONTROL Products]** per visualizzare la pagina **[!UICONTROL All products and services]**.
   1. Seleziona **[!UICONTROL Customer Journey Analytics]**.
   1. Nella scheda **[!UICONTROL Product Profiles]**, seleziona il titolo del profilo di prodotto per il quale desideri fornire accesso a [!UICONTROL AI Assistant: Product Knowledge].
   1. Nel profilo di prodotto specifico, seleziona la scheda **[!UICONTROL Permissions]**.

      ![Scheda Autorizzazioni in Admin Console](assets/ai-assistant-permissions-tab.png)

   1. Nella riga **[!UICONTROL Reporting Tools]** della tabella fornita, seleziona l’icona di modifica ![Modifica](/help/assets/icons/Edit.svg).
   1. Cerca o scorri fino ad **[!UICONTROL AI Assistant: Product Knowledge]**, quindi seleziona l’icona con il segno più ![AddCircle](/help/assets/icons/AddCircle.svg) accanto a questa autorizzazione.

      L’autorizzazione **[!UICONTROL AI Assistant: Product Knowledge]** viene aggiunta alla colonna **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](assets/ai-assistant-permissions.png).

   1. Seleziona la scheda **[!UICONTROL Data View Tools]**, quindi seleziona l’icona con il segno più ![AddCircle](/help/assets/icons/AddCircle.svg) accanto all’autorizzazione **[!UICONTROL Data Insights Agent]**.

      L’autorizzazione **[!UICONTROL Data Insights Agent]** viene aggiunta alla colonna **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](assets/ai-assistant-permissions-dataviewtools.png).

   1. Seleziona la scheda **[!UICONTROL Data Views]** per scegliere le visualizzazioni dati che desideri abilitare per l’agente Data Insights.

      >[!IMPORTANT]
      >
      >Quando abiliti le visualizzazioni dati, prendi in considerazione quanto segue:
      >* Puoi abilitare un massimo di 50 visualizzazioni dati per organizzazione IMS. Se abiliti più di 50 visualizzazioni dati in tutti i profili di prodotto per una determinata organizzazione, l’agente Data Insights utilizzerà le 50 visualizzazioni dati più utilizzate.
      >* L’agente Data Insights può fare riferimento alle visualizzazioni dati incluse nel corso dello stesso giorno in cui vengono abilitate in Admin Console.

   1. Cerca o scorri fino alle visualizzazioni dati che desideri abilitare, quindi seleziona l’icona con il segno più ![AddCircle](/help/assets/icons/AddCircle.svg) accanto al nome di ciascuna visualizzazione dati.

      Ogni visualizzazione dati aggiunta è visibile nella colonna **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](assets/ai-assistant-permissions-dataviews.png).

   1. Seleziona **[!UICONTROL Save]** per salvare le modifiche.

  Per ulteriori informazioni sul controllo degli accessi, consulta [Controllo degli accessi](/help/technotes/access-control.md#access-control).

## Accedere all’agente Data Insights nell’Assistente IA

1. Passa a [experience.adobe.com](https://experience.adobe.com/) e accedi con il tuo Adobe ID.

2. Seleziona **Customer Journey Analytics** dalla pagina Home di Experience Cloud.

3. Seleziona **[!UICONTROL Blank project]** nel banner nella parte superiore della pagina dei progetti per aprire un nuovo progetto vuoto.

4. Assicurati che la visualizzazione dati selezionata per il pannello sia abilitata per l’utilizzo con l’agente Data Insights, come descritto in [Gestire l’accesso all’agente Data Insights in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

5. Seleziona l’icona della chat dell’Assistente IA nell’area in alto a destra della pagina.

   Se l’icona della chat non è visibile, contatta l’amministratore in modo che possa abilitare le seguenti funzioni in Admin Console:

   * Strumenti di reporting: **[!UICONTROL AI Assistant: Product Knowledge]**

   * Strumenti di visualizzazione dati: **[!UICONTROL Data Insights Agent]**

   Per ulteriori dettagli, consulta [Gestire l’accesso all’agente Data Insights in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![Icona Assistente IA](/help/assets/ai-asst-icon.png)

6. Nella finestra di dialogo **[!UICONTROL Ask about Customer Journey Analytics]** nella parte inferiore della pagina, fai una domanda sulla visualizzazione dati utilizzando l’agente Data Insights.

   Per ulteriori informazioni, consulta gli esempi seguenti.

### Esempio 1

Supponiamo che ti interessino gli ordini ricevuti dalla tua azienda a luglio.

**Prompt:** inserisci *“Tendenza degli ordini di luglio.”*

![Prompt IA](/help/assets/ai-asst-prompt1.png)

**Risposta:** l’agente Data Insights raccoglie insight esaminando i dati nella visualizzazione dati, incluse le metriche e i componenti. Traduce il prompt nelle dimensioni e nelle metriche corrette per l’intervallo di dati specificato.

Come puoi vedere, ha generato automaticamente un grafico a linee e una tabella a forma libera per mostrare gli ordini di luglio.

![Risposta al prompt: grafico a linee e tabella a forma libera](/help/assets/ai-asst-result.png)

### Esempio 2

Successivamente, desideri vedere un confronto delle entrate per area geografica.

**Prompt:** nella finestra del prompt, immetti *“Mostra le entrate per area geografica”.*

**Risposta:** l’agente Data Insights comprende che per “area geografica” intendi “area geografica del cliente”. Produce quindi un grafico a barre che presenta al meglio le entrate per area geografica:

![Grafico a barre](/help/assets/ai-asst-result2.png)

### Esempio 3

In seguito, oltre a comprendere le entrate per area geografica, desideri anche visualizzarne i dati relativi al profitto per area geografica. Invece di ripetere il prompt precedente, puoi chiedere all’agente Data Insights di aggiornare la visualizzazione e la tabella a forma libera più recenti.

**Prompt:** nella finestra del prompt, digita *“Aggiungi il profitto”.*

**Risposta:** anche in questo caso il grafico **[!UICONTROL Bar]** fornisce la risposta più concisa, ma questa volta è stata aggiunta alla tabella a forma libera una colonna per la metrica “profitto”:

![Grafico a barre](/help/assets/ai-asst-result4.png)

### Esempio 4

Infine, esaminiamo entrate per categoria di prodotto.

**Prompt:** nella finestra del prompt, immetti *“Proporzione delle entrate per categoria di prodotto”.*

**Risposta:** per rispondere alla domanda, l’agente Data Insights sceglie nuovamente la visualizzazione più appropriata, in questo caso **[!UICONTROL Donut]**.

![Anello](/help/assets/ai-asst-result3.png)

## Accedere a Data Insights Agent nelle applicazioni Experience Cloud

Adobe Experience Platform Agent Orchestrator consente di accedere alle funzionalità di Data Insights Agent in più applicazioni Adobe Experience Cloud, ad esempio Adobe Journey Optimizer e Real-Time CDP.

Agent Orchestrator interpreta la richiesta, determina quali agenti specializzati sono necessari e li orchestra per fornire la risposta giusta. Tiene traccia del contesto nelle interazioni a più turni, in modo da poter sfruttare naturalmente le query precedenti.

Per ulteriori informazioni, vedere [Adobe Experience Platform Agent Orchestrator](http://www.adobe.com/go/agent-orchestrator-home).

## Esempi di prompt per le visualizzazioni dati

Di seguito sono riportati alcuni esempi di prompt comuni e di visualizzazioni utilizzate dall’agente Data Insights per rispondere a tali prompt.

| Prompt di esempio | Visualizzazione prevista |
| --- | --- |
| Mostra i profitti di [Mese] | A linee<p>Per impostazione predefinita, la richiesta di una tendenza o metrica per un determinato intervallo di tempo restituisce una visualizzazione a linee. |
| Tendenza degli ordini di [Mese] | A linee |
| Mostra le entrate per area geografica di [Mese] | A barre |
| Percentuale di entrate per categoria di prodotto | Ad anello |
| Ordini per giorno della settimana, da gennaio a maggio | A barre |
| Mostra gli ordini per genere, da marzo a giugno | A barre |
| Quali sono i profitti delle diverse SKU da febbraio a maggio | A barre |
| Entrate per nome di negozio nel mese di [Mese] | A barre |
| Quali sono state le 10 SKU migliori in base al profitto nel mese di [Mese]? | A barre |
| Percentuale di acquisti per mese dell’anno | Ad anello |
| Profitto totale nel mese di [Mese] | Numero di riepilogo<p>Quando si chiede il “totale” di una metrica per un determinato intervallo di tempo, viene restituita una visualizzazione di tipo Numero di riepilogo. |


## Best practice per i prompt

L’agente Data Insights elabora il contesto fornito da ogni prompt dell’utente e tenta di rispondere con la visualizzazione e i componenti più appropriati in una tabella a forma libera.

Le risposte possono variare in base alle parole e alle frasi specifiche utilizzate nel prompt, e lievi modifiche nel linguaggio usato possono portare a risultati diversi.

Per ottenere i migliori risultati, considera le seguenti linee guida:

* **Formula prompt specifici:** includi termini esatti per limitare l’ambito della risposta. Di seguito è riportato un esempio di un prompt specifico: “Vendite del mese scorso in California”

* **Utilizza metriche, dimensioni e segmenti chiari:** con metriche (ad esempio “Entrate”), dimensioni (ad esempio “nome sito web”), segmenti (ad esempio “utenti iPhone”) e intervalli di date (ad esempio “ultimi tre mesi”) specifici, l’agente Data Insights potrà focalizzarsi sui dati giusti.

* **Fai domande dirette:** con domande dirette, sarà più facile ottenere informazioni chiare e pertinenti dall’agente Data Insights. Di seguito è riportato un esempio di una domanda diretta in un prompt: “Quali sono le entrate medie per categoria di prodotto quest’anno?”

Rivedi la seguente tabella con alcuni esempi di termini e frasi che puoi utilizzare nei prompt con l’agente Data Insights, e i tipi di risposte che puoi aspettarti.

Questi esempi sono progettati per aiutarti a capire in che modo parole o strutture specifiche possono influenzare l’output dell’agente Data Insight, e a ottenere informazioni più precise e significative. L’agente Data Insights utilizza l’intelligenza artificiale generativa, pertanto le visualizzazioni o i dati selezionati possono variare leggermente per prompt simili.

| Risultato desiderato | Termini e frasi di esempio |
| --- | --- |
| Visualizzazione Numero di riepilogo | <ul><li>Totale</li></ul> |
| Confrontare i componenti | <ul><li>Confronto</li><li>rispetto a</li><li>Contrasto</li><li>Su base settimanale</li><li>Su base mensile</li><li>Su base trimestrale</li><li>Su base annua</li></ul> |
| Visualizzazione Anello | <ul><li>Proporzione</li><li>Quota di</li><li>Distribuzione</li><li>Percentuale</li><li>Contributo</li><li>Porzione</li><li>Parti</li></ul> |
| Visualizzazione a linee | <ul><li>Tendenza</li><li>[Metrica] in [Intervallo di tempo]</li></ul> |
| Visualizzazione a barre | <ul><li>[Metrica] per [Dimensione]</li></ul> |

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


## Best practice della configurazione

Di seguito sono riportate le best practice per la configurazione di Customer Journey Analytics (visualizzazione dati, metriche calcolate, segmenti e altro ancora) per garantire che l’agente Data Insights possa individuare i componenti corretti e restituire risposte più chiare senza dover richiedere ulteriori informazioni.

* **Bilanciare i componenti necessari**. Non aggiungere tutti i campi dei set di dati come componenti metriche o dimensione alla visualizzazione dati. In particolare, quelli che certamente non utilizzerai nell’analisi. In compenso, non limitarti strettamente solo ai campi che ritieni necessari per l’analisi. Una visualizzazione dati troppo limitata riduce la flessibilità dell’analisi e la funzionalità dell’agente Data Insights.
* **Utilizzare sempre nomi descrittivi per la visualizzazione**. Assicurati che tutti i campi definiti nella visualizzazione dati, come componente metrica o dimensione, abbiano un nome di componente descrittivo. Il processo di ridenominazione dei campi con un nome descrittivo è particolarmente importante per i campi dei set di dati del connettore di origine di Adobe Analytics. Questi campi hanno spesso nomi non descrittivi non identificabili, come `eVar41` o `prop25`.
* **Utilizzare nomi distintivi**. I nomi distintivi sono particolarmente rilevanti quando utilizzi lo stesso campo sia come componente metrica che come componente dimensione nella visualizzazione dati. Oppure quando utilizzi un campo in più componenti dello stesso tipo (ad esempio in due metriche diverse), ciascuno con impostazioni di componenti diverse.
* **Utilizzare una convenzione per la denominazione dei componenti**. Puoi utilizzare una convenzione per la denominazione dei componenti per raggrupparli. Ad esempio, **[!UICONTROL Orders | Product]** e **[!UICONTROL Orders | Customer]** possono distinguere tra diverse metriche di ordine che potrebbero esistere nei tuoi dati.
* **Utilizzare il dizionario dei dati**. Aggiungi una descrizione e altri dati rilevanti per i componenti nel dizionario dei dati. L’agente Data Insight attualmente non utilizza la descrizione e i tag del dizionario dati, ma potrebbe farlo in futuro.
* **Utilizzare le metriche calcolate approvate**. Concorda un processo per utilizzare solo metriche calcolate approvate come componenti nella visualizzazione dati ed evitare di utilizzare metriche calcolate sperimentali.
* **Condividere i segmenti richiesti**. Assicurati di condividere e rendere visibili i segmenti necessari per i prompt dell’agente Data Insights.
* **Standardizza i nomi dei componenti nelle visualizzazioni dati**. Se utilizzi gli stessi campi come componente in più visualizzazioni dati, assicurati di utilizzare un singolo nome descrittivo e un singolo identificatore per quel componente. Un singolo nome e identificatore consente all’agente Data Insights di cambiare visualizzazione dati senza perdere il contesto.

>[!MORELIKETHIS]
>
>[Impostazioni dei componenti](/help/data-views/component-settings/overview.md)
>&#x200B;>[Dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md)
>&#x200B;>[Approvare la metrica calcolata](/help/components/calc-metrics/cm-workflow/cm-approving.md)
>&#x200B;>[Condividere i segmenti](/help/components/segments/seg-share.md)
>
