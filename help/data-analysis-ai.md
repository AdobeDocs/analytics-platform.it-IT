---
description: Come porre domande sull’analisi dei dati nella documentazione del Customer Journey Analytics
title: Assistente di IA per l’analisi dei dati nel Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: e723339831bf835b43096affd4e0f15f41462f54
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 4%

---


# Assistente di IA per l’analisi dei dati nel Customer Journey Analytics - Alpha

L’Assistente all’intelligenza artificiale di Data Analysis è un agente di conversazione intelligente e sensibile al contesto che può aiutarti a rispondere in modo più rapido ed efficiente alle domande che potresti avere sui tuoi dati di Analysis Workspace nel Customer Journey Analytics.

L’Assistente esamina tutti i dati di una visualizzazione dati, compresi i diversi tipi di metriche e componenti, e traduce il prompt nella dimensione, nella metrica e nell’intervallo di date corretti per questa analisi. Invece di dover acquisire familiarità con i componenti della visualizzazione dati e quindi trascinare e rilasciare tali componenti nella combinazione migliore per rispondere alla domanda, puoi semplicemente digitare la domanda nell’Assistente AI.

## Funzionalità interne ed esterne all&#39;ambito per la versione di Alpha

Funzioni nell&#39;ambito:

| Funzionalità supportata | Descrizione |
| --- | --- |
| Creare e aggiornare visualizzazioni | Genera una tabella a forma libera e la relativa visualizzazione (ad esempio linea, barra, anello, ecc.).<p>Esempio: *Qual è il profitto tra SKU da febbraio a maggio?* |
| Tipi di visualizzazione supportati | Visualizzazioni con linee, multiriga, a forma libera, a barre, ad anello e numero di riepilogo |
| Rilevamento di prompt fuori ambito | Se si invia una richiesta che non rientra nell&#39;ambito, ad esempio &quot;esporta questo progetto&quot;, l&#39;Assistente risponde informando che la domanda non rientra nell&#39;ambito. |
| Domande chiarificatrici | Se poni una domanda che non ha abbastanza contesto per cui l’Assistente IA deve rispondere o è troppo generica, l’Assistente IA risponde con una domanda chiarificatrice e/o con opzioni suggerite. Esempi: <p>**Componenti**<ul><li>Metrica: *Quale metrica &quot;ricavi&quot; intendevi usare?*</li><li>Dimension: *Su quale delle seguenti &quot;aree&quot; desideri concentrarti?*</li><li>Filtro: *Quale filtro &quot;Account&quot; desideri applicare?*</li><li>Intervallo date: *Per &quot;ultimo mese&quot;, intendevi l&#39;ultimo mese completo o gli ultimi 30 giorni?*</li></ul>**Elementi Dimension**: quale &quot;nome archivio&quot; intendevi? (ad esempio #5274 store, #2949 store, ecc.) |
| Multi-turn | L’Assistente AI risponde a un prompt con il contesto dei prompt precedenti, consentendo agli utenti di aggiornare le visualizzazioni e porre domande di follow-up. Esempio: *Visualizza i dati da marzo ad aprile.* |
| Feedback | <ul><li>Miniature in alto</li><li>Miniature giù</li><li>Contrassegno</li></ul> |

Funzioni fuori ambito:

| Funzione non supportata | Descrizione |
| --- | --- |
| Riepilogo o risposta in linea | L’Assistente IA non può rispondere in linea nella barra della chat con una risposta di riepilogo di un prompt utente.Esempio di prompt fuori ambito:<ul><li>*Visualizza un riepilogo delle informazioni contenute nell&#39;ultimo prompt.*</li><li>*Riepiloga gli elementi di rilievo dalla visualizzazione delle linee.*</li></ul> |
| Domande chiarificatrici | Le domande più chiare sono limitate ai componenti e agli elementi dimensionali. L’Assistente AI non è in grado di chiarire visualizzazioni, granularità, confronto, ambito di dati e così via. Senza chiarire le domande, l’Assistente utilizza per impostazione predefinita ciò che probabilmente stai chiedendo. Se restituisce una visualizzazione o una granularità dei dati impreviste, puoi utilizzare la funzionalità multi-turn/update per regolare la visualizzazione e i dati. |
| Azioni/funzionalità Workspace | L’Assistente AI non può intraprendere azioni per un utente in Workspace a parte la creazione e l’aggiornamento delle visualizzazioni. Ad esempio, non può effettuare le seguenti operazioni:<ul><li>Pulsanti dell’interfaccia utente per le azioni contestuali (aggiungi al grafico, nuovo pannello, nuova tabella)</li><li>Condividi</li><li>Esportazione</li><li>Scaricare</li><li>Gestire le preferenze utente</li><li>Cura</li><li>Gestire la visualizzazione dati</li><li>App delle dashboard di Analytics</li><li>Attribuzione</li></ul> |
| Tipi di visualizzazione non supportati | <ul><li>Flusso</li><li>Fallout (abbandono)</li><li>Tabella coorte</li><li>Superfici, Superfici sovrapposte</li><li>Barre sovrapposte</li><li>Bullet</li><li>Combinato</li><li>Istogramma</li><li>Barre orizzontali, barre orizzontali sovrapposte</li><li>Riepilogo delle metriche chiave</li><li>A dispersione</li><li>Variazione di riepilogo</li><li>Testo</li><li>Mappa ad albero</li><li>Venn</li></ul> |
| Spiegabilità e verificabilità | Descrizione o citazione trasparente del modo in cui l’Assistente AI ha generato una risposta e in cui è possibile verificare che la risposta sia corretta. |

## Accesso alle funzioni nell’interfaccia utente del Customer Journey Analytics

[È necessaria anche questa sezione per l&#39;Alpha?]

I seguenti parametri regolano l’accesso alla funzione dell’Assistente di IA per l’analisi dei dati:

* **Accesso alla soluzione**: l&#39;Assistente di IA per l&#39;analisi dei dati è disponibile per i clienti Customer Journey Analytics Prime e Ultimate. Non è disponibile in Adobe Analytics.

È disponibile anche in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP e in altre app di Experience Platform.

* **Accesso contrattuale**: se non sei in grado di utilizzare l&#39;Assistente AI, contatta l&#39;amministratore della tua organizzazione o il rappresentante dell&#39;account Adobe. Prima che la tua organizzazione possa utilizzare l’Assistente di IA per l’analisi dei dati, devi accettare alcuni termini legali relativi a GenAI.

* **Autorizzazioni**: in [!UICONTROL Adobe Admin Console], l&#39;autorizzazione [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** determina l&#39;accesso a questo strumento. Un [amministratore del profilo di prodotto](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html) deve seguire questi passaggi in [!UICONTROL Admin Console]:
   1. Passa a **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Selezionare il titolo del profilo di prodotto per il quale si desidera fornire l&#39;accesso a [!UICONTROL AI Assistant: Product Knowledge].
   1. Nel profilo di prodotto specifico, selezionare **[!UICONTROL Permissions]**.
   1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare **[!UICONTROL Reporting Tools]**.
   1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) per aggiungere **Assistente IA: analisi dei dati** a **[!UICONTROL Included permission items]**.

      ![Aggiungi autorizzazione](assets/ai-assistant-permissions.png).

   1. Selezionare **[!UICONTROL Save]** per salvare le autorizzazioni.

Per ulteriori informazioni, vedere [Controllo dell&#39;accesso](/help/technotes/access-control.md#access-control).

## Accedere e utilizzare l’Assistente di Data Analysis AI

1. Vai a questo collegamento per aprire Workspace nell’organizzazione IMS di Labs (in fase) e accedi con il tuo Adobe ID.

1. Fai clic su **[!UICONTROL Blank project]** nel banner nella parte superiore della pagina dei progetti per aprire un nuovo progetto vuoto.

1. Fai clic sull’icona della chat dell’Assistente AI in alto a destra.

   ![Icona Assistente IA](/help/assets/ai-asst-icon.png)

1. Nella finestra di dialogo **[!UICONTROL Ask about Customer Journey Analytics]** in basso, fai la prima domanda di analisi dei dati nell&#39;Assistente AI.

   Ad esempio, supponiamo che tu sia interessato agli ordini ricevuti dalla tua azienda in luglio. Potresti inserire &quot;Mostra ordini in luglio&quot;.

   ![prompt IA](/help/assets/ai-asst-prompt1.png)


## Esempio di prompt di analisi dei dati

Di seguito sono riportati alcuni esempi di risposta dell’Assistente IA ai prompt e delle visualizzazioni previste:

| Esempio di prompt | Visualizzazione prevista |
| --- | --- |
| Mostra profitti in [Mese] | A linee<p>La richiesta di una tendenza o di una metrica per un determinato intervallo di tempo restituirà, per impostazione predefinita, una visualizzazione delle linee. |
| Andamento ordini in [Mese] | A linee |
| Mostra ricavi per area geografica in [Mese] | Barre |
| Quota di ricavi per categoria di prodotto | Ad anello |
| Ordini per giorno della settimana da gennaio a maggio | Barre |
| Mostra ordini per genere da marzo a giugno | Barre |
| Qual è il profitto tra SKU da febbraio a maggio | Barre |
| Ricavi per nome archivio in [Mese] | Barre |
| Quali sono stati i miei 10 migliori sku in base al profitto in [Mese]? | Barre |
| Percentuale di acquisti per mese dell&#39;anno | Ad anello |
| Profitto totale in [Mese] | Numero di riepilogo<p>Se si richiede il &quot;totale&quot; di una metrica in un determinato intervallo di tempo, viene restituita una visualizzazione del numero di riepilogo. |


## Best practice per la richiesta di informazioni

Da definire

## Alpha di aspettative relative ai test e feedback richiesto

Da definire

## Domande e contatti

E-mail `taylorb@adobe.com` (PM)
Invia domande e feedback nel canale Slack di Alpha




