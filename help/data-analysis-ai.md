---
description: Come porre domande sull’analisi dei dati nella documentazione del Customer Journey Analytics
title: Assistente di IA per l’analisi dei dati nel Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: 376ad62c3883eef675f9b1df639e8c46ee259229
workflow-type: tm+mt
source-wordcount: '1587'
ht-degree: 3%

---


# Assistente di IA per l’analisi dei dati nel Customer Journey Analytics - Alpha

L’Assistente di IA per l’analisi dei dati è un agente di conversazione di IA generativa che può aiutarti a rispondere in modo più rapido ed efficiente alle domande che potresti avere sui tuoi dati di Analysis Workspace nel Customer Journey Analytics.

Quando fai una domanda in AI Assistant, quest’ultimo analizza tutti i componenti della visualizzazione dati, compresi i diversi tipi di metriche e componenti, e traduce il messaggio nella dimensione, nella metrica e nell’intervallo di date corretti per l’analisi. Invece di dover acquisire familiarità con i componenti della visualizzazione dati e quindi trascinare e rilasciare tali componenti nella combinazione migliore per rispondere alla domanda, puoi semplicemente digitare la domanda nell’Assistente AI.

![Assistente di IA per l&#39;analisi dei dati](assets/cja-ai-asst-da.gif)

## Funzionalità interne ed esterne all&#39;ambito per la versione di Alpha

### Funzioni di Alpha nell’ambito

| Funzionalità supportata | Descrizione |
| --- | --- |
| **Creare e aggiornare visualizzazioni** | Genera una tabella a forma libera e la relativa visualizzazione (ad esempio linea, barra, anello, ecc.).<p>Esempio: *Qual è il profitto tra SKU da febbraio a maggio?* |
| **Tipi di visualizzazione supportati** | <ul><li>A linee</li><li>Multiriga</li><li>A forma libera</li><li>Barre</li><li>Ad anello</li><li>Numero di riepilogo</li></ul> |
| **Rilevamento prompt fuori ambito** | Se si invia una richiesta che non rientra nell&#39;ambito, ad esempio &quot;esporta questo progetto&quot;, l&#39;Assistente risponde informando che la domanda non rientra nell&#39;ambito. |
| **Domande chiarificatrici** | Se poni una domanda che non ha abbastanza contesto per cui l’Assistente IA deve rispondere o è troppo generica, l’Assistente IA risponde con una domanda chiarificatrice e/o con opzioni suggerite. Esempi: <p>**Componenti**<ul><li>Metrica: *Quale metrica &quot;ricavi&quot; intendevi usare?*</li><li>Dimension: *Su quale delle seguenti &quot;aree&quot; desideri concentrarti?*</li><li>Filtro: *Quale filtro &quot;Account&quot; desideri applicare?*</li><li>Intervallo date: *Per &quot;ultimo mese&quot;, intendevi l&#39;ultimo mese completo o gli ultimi 30 giorni?*</li></ul>**Elementi Dimension**: quale &quot;nome archivio&quot; intendevi? (ad esempio #5274 store, #2949 store, ecc.) |
| **Turno multiplo** | L’Assistente AI risponde a un prompt con il contesto dei prompt precedenti, consentendo agli utenti di aggiornare le visualizzazioni e porre domande di follow-up.Esempio: <ul><li>Prompt 1: *Eventi di tendenza da marzo.*</li><li>Prompt 2: *Visualizza i dati da marzo ad aprile*</li></ul> |
| **Verificabilità** | La verificabilità e la correttezza dei dati possono essere confermate tramite la tabella a forma libera generata e la visualizzazione dei dati. Ad esempio, se un utente chiede *Trend ordini del mese scorso*, puoi confermare che la metrica corretta (&quot;ordini&quot;) e l&#39;intervallo di date (&quot;mese scorso&quot;) siano stati selezionati nel pannello, nella visualizzazione dati e nella tabella a forma libera appena generati. |
| **Feedback** | <ul><li>Miniature in alto</li><li>Miniature giù</li><li>Contrassegno</li></ul> |

### Funzioni di Alpha fuori ambito

| Funzione non supportata | Descrizione |
| --- | --- |
| **Riepilogo o risposta in linea** | L’Assistente IA non può rispondere in linea nella barra della chat con una risposta di riepilogo di un prompt utente.Esempio di prompt fuori ambito:<ul><li>*Visualizza un riepilogo delle informazioni contenute nell&#39;ultimo prompt.*</li><li>*Riepiloga gli elementi di rilievo dalla visualizzazione delle linee.*</li></ul> |
| **Domande chiarificatrici** | Le domande più chiare sono limitate ai componenti e agli elementi dimensionali. L’Assistente AI non è in grado di chiarire visualizzazioni, granularità, confronto, ambito di dati e così via. Senza chiarire le domande, l’Assistente utilizza per impostazione predefinita ciò che probabilmente stai chiedendo. Se restituisce una visualizzazione o una granularità dei dati impreviste, puoi utilizzare la funzionalità multi-turn/update per regolare la visualizzazione e i dati. |
| **Azioni/funzionalità Workspace** | L’Assistente AI non può intraprendere azioni per un utente in Workspace a parte la creazione e l’aggiornamento delle visualizzazioni. Ad esempio, non può effettuare le seguenti operazioni:<ul><li>Pulsanti dell’interfaccia utente per le azioni contestuali (aggiungi al grafico, nuovo pannello, nuova tabella)</li><li>Condividi</li><li>Esportazione</li><li>Scaricare</li><li>Gestire le preferenze utente</li><li>Cura</li><li>Gestire la visualizzazione dati</li><li>App delle dashboard di Analytics</li><li>Attribuzione</li></ul> |
| **Tipi di visualizzazione non supportati** | <ul><li>Flusso</li><li>Fallout (abbandono)</li><li>Tabella coorte</li><li>Superfici, Superfici sovrapposte</li><li>Barre sovrapposte</li><li>Bullet</li><li>Combinato</li><li>Istogramma</li><li>Barre orizzontali, barre orizzontali sovrapposte</li><li>Riepilogo delle metriche chiave</li><li>A dispersione</li><li>Variazione di riepilogo</li><li>Testo</li><li>Mappa ad albero</li><li>Venn</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Accedere e utilizzare l’Assistente di Data Analysis AI

1. Vai a [experience.adobe.com](https://experience.adobe.com/) e accedi con il tuo Adobe ID.

2. Seleziona **Customer Journey Analytics** dalla Home Experience Cloud

3. Fai clic su **[!UICONTROL Blank project]** nel banner nella parte superiore della pagina dei progetti per aprire un nuovo progetto vuoto.

4. Assicurati che la visualizzazione dati selezionata per il pannello sia quella abilitata per l’utilizzo dell’Assistente AI per i test di Alpha (in caso di dubbi, contatta l’utente nel canale Slack di Alpha)

5. Fai clic sull’icona della chat dell’Assistente AI in alto a destra.

   ![Icona Assistente IA](/help/assets/ai-asst-icon.png)

6. Nella finestra di dialogo **[!UICONTROL Ask about Customer Journey Analytics]** in basso, fai una domanda di analisi dei dati nell&#39;Assistente AI.

### Esempio 1

Ad esempio, supponiamo che tu sia interessato agli ordini ricevuti dalla tua azienda in luglio.

1. Immetti *&quot;Trend ordini in luglio.&quot;*

   ![prompt IA](/help/assets/ai-asst-prompt1.png)

2. L’Assistente AI ora raccoglie informazioni approfondite esaminando i dati nella visualizzazione dati, incluse le metriche e i componenti. Traduce il prompt nelle dimensioni, nelle metriche e nell’intervallo di dati corretti.

   Come puoi vedere, ha generato automaticamente un grafico a linee e una tabella a forma libera che mostra gli ordini per luglio.

   ![Risposta alla richiesta - grafico a linee e tabella a forma libera](/help/assets/ai-asst-result.png)

### Esempio 2

Ora vuoi vedere come si confrontano i ricavi per regione.

1. Nella finestra del prompt, immettere *&quot;Mostra ricavi per area.&quot;*

2. L’Assistente AI capisce in modo intelligente che per &quot;area&quot; si intende &quot;area del cliente&quot;. Produce un grafico a barre che mostra al meglio i ricavi per area:

   ![Grafico a barre](/help/assets/ai-asst-result2.png)

### Esempio 3

Quindi, oltre a comprendere i ricavi per regione, è necessario visualizzare anche i dati relativi ai profitti per regione. Invece di dover ridigitare l’ultimo prompt, puoi chiedere all’Assistente IA di aggiornare la visualizzazione e la tabella a forma libera più recenti.

1. Nella finestra del prompt, digitare *&quot;Aggiungi profitto.&quot;*

2. Il grafico **[!UICONTROL Bar]** fornisce ancora la risposta più concisa, ma la metrica di profitto è stata aggiunta come colonna nella tabella a forma libera:

   ![Grafico a barre](/help/assets/ai-asst-result4.png)

### Esempio 4

Infine, vediamo i ricavi per categoria di prodotto.

1. Nella finestra del prompt, immettere *&quot;Proporzione di ricavi per categoria di prodotto&quot;.*

2. Anche in questo caso, l&#39;Assistente di IA per l&#39;analisi dei dati sceglie la visualizzazione più appropriata, in questo caso la visualizzazione **[!UICONTROL Donut]**, per rispondere alla domanda.

   ![Anello](/help/assets/ai-asst-result3.png)

## Esempio di prompt di analisi dei dati

Di seguito sono riportati alcuni esempi di prompt comuni e di quale visualizzazione l’Assistenza IA utilizza per rispondere a tali prompt.

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

L’Assistente AI elabora il contesto fornito da ogni prompt utente e tenta di rispondere in modo intelligente con la visualizzazione più appropriata e con i componenti di una tabella a forma libera. Tuttavia, la risposta dell’Assistente AI può variare in base alle parole e alle frasi specifiche utilizzate in un prompt, pertanto lievi modifiche nella lingua possono portare a risultati diversi. Ecco come trarne il massimo vantaggio: <ul><li>Sii specifico: includi termini esatti (come &quot;vendite del mese scorso in California&quot;) per limitare la risposta.</li><li>Utilizzare metriche e filtri chiari: l’aggiunta di metriche specifiche (come &quot;Ricavi&quot;), dimensioni (ad esempio &quot;nome sito web&quot;), filtri (ad esempio &quot;utenti iPhone&quot;) e intervalli di date (come &quot;ultimi tre mesi&quot;) consente all’Assistente AI di concentrarsi sui dati giusti.</li><li>Domande dirette: formulare domande direttamente, come &quot;Qual è il reddito medio per categoria di prodotto quest&#39;anno?&quot; consente all’Assistente AI di fornire informazioni chiare e pertinenti.</li></ul>

Consulta la seguente tabella di termini e frasi di esempio da utilizzare nei prompt con l’Assistente di IA per l’analisi dei dati in CJA, insieme ai tipi di risposte che è possibile aspettarsi. Questi esempi sono progettati per aiutarti a comprendere in che modo parole o strutture specifiche possono influenzare l’output dell’Assistente AI, garantendo informazioni più precise e preziose. Tieni presente che l’Assistente AI utilizza l’intelligenza artificiale generativa, pertanto le visualizzazioni o i dati selezionati possono variare leggermente in base a prompt simili.

| Risultato desiderato | Termini e frasi di esempio |
| --- | --- |
| Visualizzazione Numero di riepilogo | <ul><li>Totale</li></ul> |
| Confronta componenti | <ul><li>Confronta</li><li>VS</li><li>Contrasto</li><li>Settimana per settimana</li><li>Su base mensile</li><li>Trimestre su trimestre</li><li>Anno su Anno</li></ul> |
| Visualizzazione ad anello | <ul><li>Proporzione</li><li>Quota di</li><li>Distribuzione</li><li>Percento</li><li>Contributo</li><li>Porzione</li><li>Parti</li></ul> |
| Visualizzazione a linee | <ul><li>Tendenza</li><li>[Metrica] in [Intervallo di tempo]</li></ul> |
| Visualizzazione a barre | <ul><li>[Metrica] per [dimensione]</li></ul> |

## Alpha di aspettative relative ai test e feedback richiesto

Dopo aver posto ciascuna domanda, rivedi attentamente la risposta fornita dall’assistente. È fondamentale valutare in modo completo le visualizzazioni generate prima di fornire un feedback. Quando valuti la risposta dall’Assistente AI, considera quanto segue:

* Risposta o modello della barra di chat: valuta la risposta testuale fornita dall’Assistente. La risposta è appropriata dato il contesto dei prompt?

* Visualizzazione/grafico: valuta la visualizzazione. È la visualizzazione appropriata/prevista per la domanda o ti saresti aspettato una visualizzazione diversa?

* Tabella a forma libera: valuta la tabella a forma libera. I dati della tabella a forma libera sono corretti? I dati vengono suddivisi dove richiesto? I filtri applicati sono quelli richiesti o previsti?

* Messaggio di errore/Fuori ambito: se viene visualizzato un messaggio di errore generico che indica che la domanda non rientra nell’ambito, indica se ritieni che il messaggio fuori ambito sia appropriato, tenuto conto del prompt. Il prompt è stato effettivamente incluso nell&#39;ambito?

**Per ogni risposta, immetti un pollice in alto o un pollice in basso, in base alla risposta**

Dopo aver selezionato i pollici verso l&#39;alto o verso il basso, effettuare una selezione per le relative caselle di feedback a selezione multipla. Se si desidera fornire un feedback aggiuntivo, aggiungere note nella casella di testo aperta.

## Domande e contatti

* Invia domande e feedback nel canale Slack di Alpha: #aep-cja-ai-assistant-testers ???


