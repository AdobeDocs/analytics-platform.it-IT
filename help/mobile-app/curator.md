---
description: Istruzioni per la configurazione delle scorecard delle dashboard.
title: Guida per la creazione di dashboard di Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 6a2e32f6bdac3b47a74e262c0b0e0f4f93b2dc4d
workflow-type: tm+mt
source-wordcount: '2290'
ht-degree: 93%

---


# Guida del curatore per le dashboard di Analytics

Le informazioni riportate di seguito spiegano ai curatori di dati di Adobe Analytics come configurare e presentare dashboard per gli utenti esecutivi. Il video “Generatore di Scorecard per i dashboard di Analytics” illustra queste informazioni:

>[!VIDEO](https://video.tv.adobe.com/v/34544)

## Introduzione

Le dashboard di Analytics forniscono informazioni ovunque e in qualsiasi momento in base ai dati del Customer Journey Analytics. L’app consente agli utenti di accedere da dispositivi mobili a scorecard intuitive che crei e condividi dall’interfaccia utente desktop del Customer Journey Analytics. Le scorecard sono una raccolta di metriche chiave e di altri componenti presentati in un layout a tessere che puoi toccare per visualizzare raggruppamenti più dettagliati e rapporti sulle tendenze. Puoi personalizzare le scorecard in base ai dati che ritieni più importanti. Le dashboard di Analytics sono supportate sia sui sistemi operativi iOS che su quelli Android.

## Ulteriori informazioni su questa guida

Questa guida ha lo scopo di aiutare i curatori di dati di Customer Journey Analytics a configurare le scorecard per i loro utenti esecutivi sulle dashboard. I curatori possono essere amministratori organizzativi o persone con altri ruoli responsabili della configurazione delle scorecard dell’app, il che consente agli utenti esecutivi di visualizzare una rappresentazione generale di importanti dati riassuntivi in modo semplice e veloce sui propri dispositivi mobili. Sebbene gli utenti esecutivi siano gli utenti finali delle dashboard di Analytics, questa guida aiuterà i curatori dei dati a configurare l’app in modo efficace per questi utenti.

## Glossario dei termini

La tabella seguente descrive i termini per comprendere il pubblico, le funzioni e il funzionamento delle dashboard del Customer Journey Analytics.

| Termine | Definizione |
| --- | --- |
| Consumatore | Personalizzazione esecutiva che visualizza metriche chiave e informazioni da CJA su un dispositivo mobile |
| Curatore | Persona con accesso ai dati che trova e distribuisce informazioni da CJA e configura le scorecard da visualizzare per il consumatore |
| Cura | L’atto di creare o modificare una scorecard mobile contenente metriche, dimensioni e altri componenti pertinenti per il consumatore |
| Scorecard | Una vista delle dashboard contenente una o più tessere |
| Tessera | Una rappresentazione di una metrica all’interno di una vista Scorecard |
| Raggruppamento | Una vista secondaria accessibile toccando una tessera nella scorecard. Questa vista mostra maggiori informazioni sulla metrica visualizzata sulla tessera e, opzionalmente, riporta informazioni su dimensioni di raggruppamento aggiuntive |
| Intervallo date | L’intervallo date primario per la generazione di rapporti delle dashboard |
| Intervallo date di confronto | L’intervallo date che viene confrontato con l’intervallo date primario |

## Creare una scorecard per utenti esecutivi

Una scorecard mostra le visualizzazioni dei dati chiave per gli utenti esecutivi in un layout a tessere, come mostrato di seguito:

![Esempio di scorecard](assets/intro_scorecard.png)

In qualità di curatore di questa scorecard, puoi usare lo strumento di creazione delle scorecard per configurare quali tessere visualizzerà il consumatore sulla scorecard. Puoi anche configurare in che modo le viste dettagliate, o Raggruppamenti, possono essere regolati una volta che le tessere vengono toccate. L’interfaccia del Creatore di scorecard è mostrata di seguito:

![Creatore di scorecard](assets/scorecard_builder.png)

Per creare la scorecard, dovrai fare quanto segue:

1. Accedi al modello [!UICONTROL Blank Mobile Scorecard].
2. Configura la scorecard con i dati e salvala.

### Accedi al modello [!UICONTROL Blank Mobile Scorecard]

Puoi accedere al modello [!UICONTROL Blank Mobile Scorecard] in uno dei seguenti modi:

**Creare un nuovo progetto**

1. Apri CJA e fai clic sulla scheda **[!UICONTROL Workspace]** .
2. Fai clic su **[!UICONTROL Create New Project]** e seleziona il modello di progetto **[!UICONTROL Blank Mobile Scorecard]**.
3. Fai clic su **[!UICONTROL Create]**.

![Template Scorecard](assets/new_template.png)

**Aggiungere un progetto**

Dalla schermata **[!UICONTROL Projects]**, sotto la scheda **[!UICONTROL Components]** , fai clic su **[!UICONTROL Add]** e seleziona **[!UICONTROL Mobile Scorecard]**.

![Aggiunta di progetti](assets/add_project.png)

**Utilizzare gli strumenti di [!DNL Analytics]**

In [!DNL Analytics], fai clic sul menu **[!UICONTROL Tools]** e seleziona **[!UICONTROL Analytics dashboards (Mobile App)]**. Nella schermata successiva, fai clic sul pulsante **[!UICONTROL Create new scorecard]**.

### Configura la scorecard con i dati e salvala

Per implementare il template della scorecard:

1. Alla voce **[!UICONTROL Properties]** (nella barra a destra), specifica la **[!UICONTROL Project report suite]** della quale desideri utilizzare i dati.

   ![Selezione di suite di rapporti](assets/properties_save.png)

1. Per aggiungere una nuova tessera alla scorecard, trascina una metrica dal pannello a sinistra e rilasciala nella zona **[!UICONTROL Drag and Drop Metrics Here]**. È anche possibile inserire una metrica tra due tessere utilizzando un flusso di lavoro simile.

   ![Aggiungere tessere](assets/build_list.png)


   *Da ogni tessera, è possibile accedere a una vista dettagliata che visualizza informazioni aggiuntive sulla metrica, come gli elementi principali di un elenco di dimensioni correlate.*


1. Per aggiungere una dimensione correlata a una metrica, trascina una dimensione dal pannello di sinistra e rilasciala su una tessera. Ad esempio, per aggiungere le dimensioni appropriate (come **[!DNL DMA Region]**, in questo esempio) alla metrica **[!UICONTROL Unique Visitors]**, trascinale sulla tessera; le dimensioni che aggiungi verranno visualizzate nella sezione breakdown delle **[!UICONTROL Properties]** specifiche della tessera. Puoi aggiungere più dimensioni a ogni tessera.

   ![Aggiunta di dimensioni](assets/layer_dimensions.png)

   Puoi anche aggiungere una dimensione a tutte le tessere rilasciandola sull’area di lavoro della scorecard.

   Quando fai clic su una tessera nel Creatore di scorecard, la barra di destra mostra le proprietà e le caratteristiche associate a quella tessera. In questa barra puoi assegnare un nuovo **[!UICONTROL Title]** alla tessera e, in alternativa, configurarla specificando i componenti invece di trascinarli dalla barra di sinistra.

   Inoltre, se fai clic sulle tessere, un pop-up dinamico mostrerà come la vista Raggruppamento viene visualizzata dall’utente esecutivo nell’app. Se non è stata applicata alcuna dimensione alla tessera, la dimensione di raggruppamento sarà **ore** o **giorni**, a seconda dell’intervallo date predefinito.

   ![Vista_Raggruppamento](assets/break_view.png)

   Ogni dimensione aggiunta alla tessera viene visualizzata in un elenco a discesa nella vista dettagliata dell’app. L’utente esecutivo può quindi scegliere tra le opzioni elencate nell’elenco a discesa.

1. Per applicare segmenti alle singole tessere, trascina un segmento dal pannello di sinistra e rilascialo direttamente sulla tessera. Se vuoi applicare il segmento a tutte le tessere della scorecard, rilascia la tessera sopra la scorecard. Oppure, puoi anche applicare i segmenti selezionandoli nel menu del filtro sotto gli intervalli di date. Puoi [configurare e applicare filtri per le scorecard](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=it) nello stesso modo che utilizzeresti in Adobe Analytics Workspace.

   ![Creare segmenti per il filtro](assets/segment_ui.png)

1. Allo stesso modo, per rimuovere un componente applicato all’intera scorecard, fai clic in qualsiasi punto della scorecard al di fuori delle tessere, quindi fai clic sulla **x** che compare quando passi il mouse sul componente, come mostrato di seguito per il segmento **[!DNL Mobile Customers]**:

   ![Rimuovere_componenti](assets/new_remove.png)

1. Nelle **[!UICONTROL Properties]** della scorecard puoi inoltre specificare opzionalmente quanto segue:

   * **[!UICONTROL Default date range]**. Gli intervalli che specifichi qui saranno gli stessi applicati al primo accesso dell’utente esecutivo alla scorecard nell’app.

   * **[!UICONTROL Comparison date range]**

   * Eventuali **[!UICONTROL Segments]** da applicare a tutta la scorecard

1. Per dare un nome alla scorecard, fai clic sullo spazio del nome in alto a sinistra dello schermo e digita il nuovo nome.

   ![Assegnare_un_nome_alle_scorecard](assets/new_name.png)

## Condividere la scorecard

Per condividere la scorecard con un utente esecutivo:

1. Fai clic sul menu **[!UICONTROL Share]** e seleziona **[!UICONTROL Share scorecard]**.

2. Nel modulo **[!UICONTROL Share mobile scorecard]**, compila i campi:

   * Inserendo il nome della scorecard
   * Inserendo una descrizione della scorecard
   * Aggiungendo tag rilevanti
   * Specificando i destinatari della scorecard

3. Fai clic su **[!UICONTROL Share]**.

![Condividere_scorecard](assets/new_share.png)

Dopo che hai condiviso una scorecard, i destinatari possono accedervi sulle loro dashboard di Analytics. Se apporti successive modifiche alla scorecard nel Creatore di scorecard, queste verranno automaticamente aggiornate nella scorecard condivisa. Gli utenti esecutivi vedranno poi i cambiamenti dopo aver aggiornato la scorecard nella loro app.

Se aggiorni la scorecard aggiungendo nuovi componenti, ti consigliamo di condividerla nuovamente e di selezionare l’opzione **[!UICONTROL Share embedded components]** (condividi componenti incorporati) per assicurarti che gli utenti esecutivi abbiano accesso a queste modifiche.

## Impostare gli utenti esecutivi con l’app

In alcuni casi, gli utenti esecutivi potrebbero aver bisogno di ulteriore assistenza per accedere all’app e utilizzarla. Questa sezione offre informazioni per aiutarti a fornire tale assistenza.

### Aiutare gli utenti esecutivi ad accedere

Per aiutare gli utenti esecutivi ad accedere alle tue scorecard nell’app, assicurati che:

* Il sistema operativo per dispositivi mobili sui loro dispositivi sia iOS versione 10 o superiore o Android versione 4.4 (KitKat) o superiore
* Abbiano un accesso valido ad Adobe Analytics
* Tu abbia creato correttamente le scorecard per dispositivi mobili a essi destinate e condiviso con essi tali scorecard
* Abbiano accesso all’Analysis Workspace e alla suite di rapporti su cui si basa la scorecard
* Abbiano accesso ai Componenti che la scorecard include. Nota che puoi selezionare un’opzione quando condividi le scorecard per **[!UICONTROL Share embedded components]**.

### Aiutare gli utenti esecutivi a utilizzare l’app

Per aiutare gli utenti esecutivi:

1. Aiutali a scaricare e installare l’app. Per farlo, indica ai tuoi utenti esecutivi i seguenti passaggi per estendere l’accesso, a seconda che utilizzino un dispositivo iOS o Android.

   **Per gli utenti esecutivi su iOS:**

   * Fai clic sul seguente collegamento (disponibile anche in Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

      [Collegamento per iOS](https://apple.co/2zXq0aN)
   **Per gli utenti esecutivi su Android:**

   * Fai clic sul seguente collegamento (disponibile anche in Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

      [Collegamento per Android](https://bit.ly/2LM38Oo)
   Una volta scaricata e installata, gli utenti esecutivi possono accedere all’app utilizzando le loro credenziali esistenti di Adobe Analytics; supportiamo sia gli ID Adobe che quelli Enterprise/Federated.

   ![Schermata di benvenuto dell’app](assets/welcome.png)

2. Aiutali ad accedere alla tua scorecard. Dopo che gli utenti esecutivi effettuano l’accesso all’app, viene visualizzata la schermata **[!UICONTROL Choose a company]**. Questa schermata elenca le aziende di accesso a cui appartiene l’utente esecutivo. Per aiutarli a trovare la scorecard:

   * Toccare il nome dell’azienda di accesso o dell’organizzazione Experience Cloud che si applica alla scorecard che hai condiviso. L’elenco delle scorecard mostra quindi tutte le scorecard che sono state condivise con l’utente esecutivo da quell’azienda di accesso.
   * Aiutateli a ordinare l’elenco in base a **[!UICONTROL Most recently modified]**, se applicabile.
   * Toccare il nome della scorecard per visualizzarla.

   ![Scegliere un’azienda](assets/accesscard.png)

   Se l’utente esecutivo effettua l’accesso e vede un messaggio che dice che non è stato condiviso nulla:

   * L’utente esecutivo può aver selezionato l’istanza di Analytics sbagliata

   * La scorecard potrebbe non essere stata condivisa con l’utente esecutivo

      ![Niente di condiviso](assets/nothing.png)


   * Verifica che l’utente esecutivo possa accedere alla giusta istanza di Analytics e che la scorecard sia stata condivisa.


3. Spiega all’utente esecutivo come vengono visualizzate le tessere nelle scorecard condivise (la prima scorecard sottostante è impostata in modalità scura; consulta **[!UICONTROL Preferences]** di seguito se pensi che l’utente esecutivo preferisca questa opzione di visualizzazione):

   ![Spiegare le tessere](assets/newexplain.png)

   ![Esempio di scorecard](assets/intro_scorecard.png)

   Ulteriori informazioni sulle tessere:

   * La granularità dei grafici sparkline dipende dalla lunghezza dell’intervallo date:
      * Un giorno mostra una tendenza oraria
      * Più di un giorno e meno di un anno mostra una tendenza giornaliera
      * Un anno o più mostra una tendenza settimanale
   * La formula della variazione percentuale del valore è metrica totale (intervallo date attuale) – metrica totale (intervallo date di confronto)/metrica totale (intervallo date di confronto).
   * È possibile trascinare lo schermo verso il basso per aggiornare la scorecard.


4. Toccare una tessera per mostrare come funziona un raggruppamento dettagliato della tessera.

   ![Vista Raggruppamento](assets/sparkline.png)

   * Tocca un punto qualsiasi di una sparkline per visualizzare i dati associati a tale punto sulla linea.

   * È inclusa una tabella per visualizzare i dati delle dimensioni aggiunte alla tessera. Tocca la freccia giù per selezionare le dimensioni. Se non è stata aggiunta alcuna dimensione alla tessera, nella tabella vengono visualizzati i dati relativi al grafico.

5. Per modificare gli intervalli date per la tua scorecard:

   ![Modificare le date](assets/changedate.png)

   * Puoi modificare allo stesso modo anche gli intervalli date all’interno della vista raggruppamento mostrata sopra.

   * A seconda dell’intervallo che si tocca (**Giorno**, **Settimana**, **Mese** o **Anno**), si vedranno due opzioni per gli intervalli date: l’intervallo di tempo attuale o quello immediatamente prima. Tocca una di queste due opzioni per selezionare il primo intervallo. Nell’elenco **[!UICONTROL COMPARE TO]**, tocca una delle opzioni che vengono mostrate per confrontare i dati di questo periodo di tempo con il primo intervallo date selezionato. Tocca **[!UICONTROL Done]** in alto a destra. Il campo **[!UICONTROL Date Ranges]** e le tessere della scorecard vengono aggiornati con i dati più recenti di confronto dei nuovi intervalli selezionati.

6. Per lasciare un feedback su questa app:

   1. Tocca l’icona dell’utente in alto a destra della schermata dell’app.
   2. Nella schermata **[!UICONTROL Settings]**, tocca l’opzione **[!UICONTROL Feedback]**.
   3. Tocca per visualizzare le opzioni per lasciare un feedback.

      ![Schermata Settings](assets/settings.png)

7. Per modificare le preferenze, tocca l’opzione **[!UICONTROL Preferences]** mostrata sopra. Nelle preferenze, puoi attivare l’accesso biometrico oppure la modalità scura dell’app come illustrato di seguito:

   ![Modalità scura](assets/darkmode.png)

**Per segnalare un bug**:

Toccare l’opzione e scegliere una sottocategoria del bug. Nel modulo per la segnalazione di un bug, fornisci il tuo indirizzo e-mail nel campo superiore e la tua descrizione del bug nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata con le informazioni del tuo account, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare la segnalazione, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.


![Segnalare un bug](assets/newbug.png)

**Per suggerire un miglioramento**:

Toccare l’opzione e scegliere una sottocategoria del suggerimento. Nel modulo di suggerimento, fornisci il tuo indirizzo e-mail nel campo superiore e la tua descrizione del bug nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata con le informazioni del tuo account, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare il suggerimento, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.

**Per fare una domanda**:

Tocca l’opzione e fornisci il tuo indirizzo e-mail nel campo superiore e la tua domanda nel campo sotto di esso. Al messaggio viene automaticamente allegata una schermata, ma puoi cancellarla, se lo desideri, toccando la **X** nell’immagine allegata. Ci sono anche delle opzioni per effettuare una registrazione dello schermo, aggiungere altre schermate o allegare file. Per inviare la domanda, toccare l’icona dell’aeroplano di carta in alto a destra del modulo.

>[!IMPORTANT]
>
>A partire da ottobre 2020, Adobe ha gradualmente introdotto una serie di miglioramenti per ottimizzare le prestazioni dell’app &quot;Adobe Analytics dashboards&quot;. Questi miglioramenti sono incentrati sulla memorizzazione nella cache dei dati Analytics storici utilizzati per popolare le scorecard con le date (escluso il giorno corrente). I dati verranno memorizzati nella cache fino a 24 ore in un account di archiviazione cloud pubblico Microsoft Azure protetto. Se preferisci non utilizzare queste funzioni di miglioramento delle prestazioni, contatta il tuo Customer Success Manager.
