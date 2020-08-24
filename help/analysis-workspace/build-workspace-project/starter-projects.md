---
description: Modelli in Workspace
title: Modelli
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: tm+mt
source-git-commit: 43487b0dc9d0246fc4750fcc0175055899a198b5
workflow-type: tm+mt
source-wordcount: '1407'
ht-degree: 99%

---


# Modelli

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Puoi scegliere di creare un progetto da:

* **Progetto vuoto (predefinito)**: per le istruzioni consulta [Creazione di un progetto di Analysis Workspace](/help/analysis-workspace/home.md).
* **Modello standard**: questi modelli vengono creati da Adobe e vengono forniti con il prodotto.
* **Modello personalizzato**: questi modelli possono essere creati, condivisi o eliminati da utenti con diritti di amministratore o da non amministratori, a condizione che dispongano dell’autorizzazione [!UICONTROL Analysis Workspace: Save as Template] in Admin Console. [Ulteriori informazioni...](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Creare un modello personalizzato {#create-custom-template}

Gli utenti con diritti di amministratore possono trasformare qualunque progetto che creano in un modello personalizzato effettuando le seguenti operazioni:

1. Apri il progetto.
1. Vai a **[!UICONTROL Project]** > **[!UICONTROL Save As Template]**.

   ![](assets/save_project_template.png)

   Il progetto viene salvato con il nome corrente, seguito dalla parola (Modello) tra parentesi. Gli amministratori possono cambiare questo nome modificando il modello.

   >[!NOTE]
   >
   >Per impostazione predefinita, i modelli di progetto sono visibili a tutti gli utenti dell’organizzazione. Puoi utilizzare dei tag per organizzare i modelli. (Vai a **[!UICONTROL Project]** (Progetto) > **[!UICONTROL Project Info & Settings]** (Informazioni e impostazioni progetto) per modificare tag e descrizioni.)

### Azioni eseguibili sui modelli personalizzati

![](assets/custom_templates.png)

| Azione | Descrizione |
|--- |--- |
| Modificare un modello | Consente a un amministratore di modificare il modello cambiandone l’origine dati e modificando componenti, visualizzazioni, intervalli di date ecc.  Sono disponibili due modi per modificare un modello personalizzato:<ul><li>Visualizza l’elenco dei modelli personalizzati in Analysis Workspace, selezionane uno e fai clic su Modifica modello, oppure</li><li>In Analytics, vai a Componenti > Progetti, quindi applica il filtro Modelli. Fai clic sul nome del modello da modificare.</li></ul>**Nota:** dopo aver modificato un modello, a seconda della situazione, puoi scegliere Salva o Salva con nome. Queste sono le differenze tra le due opzioni:<ul><li>**Salva:** aggiorna il modello personalizzato per tutti gli utenti. Quando un altro utente crea un progetto basato su questo modello personalizzato, vedrà le modifiche che hai apportato.</li><li>**Salva con nome:** crea una copia del modello personalizzato con le modifiche apportate. Per verificare che sia attiva la modalità di modifica, controlla che la voce di menu Condividi > Condividi progetto sia disabilitata.</li></ul> |
| Cercare nei modelli | Nella finestra di dialogo Modelli personalizzati, fai clic su Cerca modelli. |
| Ordinare i modelli | Puoi organizzare i modelli in ordine alfabetico, per rilevanza e per data di creazione.  Nella finestra di dialogo Modelli personalizzati, fai clic su Ordina. |
| Applicare tag a un modello | Apri il modello e vai a Progetto > Informazioni e impostazioni progetto. Fai clic su Aggiungi tag. |
| Modificare la descrizione di un modello | Apri il modello e vai a Progetto > Informazioni e impostazioni progetto. Fai doppio clic sulla descrizione e modificala. |


## Modelli standard

La prima volta che si apre un’Workspace i modelli sono disponibili nella barra a sinistra. I modelli di Analysis Workspace coprono i casi d’uso più comuni. Sono raggruppati in base all’applicazione verticale a cui fanno riferimento e sono compilati con dimensioni, segmenti, metriche e visualizzazioni, a seconda della suite per rapporti selezionata.

Puoi usare questi modelli precompilati così come sono o adattarli alle tue esigenze (ad esempio, aggiungendo o sostituendo metriche o visualizzazioni) e salvarli con un nuovo nome.

[Modelli standard in Analysis Workspace su YouTube](https://www.youtube.com/watch?v=aRgYwPneVXg&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=6) (2:46)

Di seguito sono riportati i modelli disponibili e le domande che ogni modello può rispondere.

### Formazione

Questi modelli standard illustrano la terminologia e i passaggi comuni per lo svolgimento della prima analisi in Workspace. Sono disponibili come modello standard nel modale Nuovo progetto e sostituiscono il progetto di esempio attuale per i nuovi utenti che non hanno altri progetti nel loro elenco.

* **Esercitazione - analisi delle ricerche interne**: l’esercitazione di Internal Search (ricerca interna) consente di comprendere cosa cercano e non trovano i visitatori sul sito web o sull’app. L’analisi di questo tipo di dati può far emergere opportunità di ottimizzazione dei contenuti.

* **Esercitazione - analisi di marketing**: questa esercitazione mostra come creare un’analisi di marketing per i dirigenti che individui anche quali sono le dimensioni e le metriche personalizzate più importanti.

### Pubblicità

>[!IMPORTANT]
>
>I modelli pubblicitari sono disponibili solo se la suite di rapporti è abilitata per Advertising Cloud.

* **Motori di ricerca a pagamento**: questo modello suddivide le tendenze pubblicitarie, le piattaforme di annunci, le parole chiave, gli account, le campagne e molto altro.

### Commercio

* **Magento: Marketing e Commercio**: questo modello suddivide la conversione e-commerce in base all’attribuzione del canale di marketing, oltre a fornire informazioni dettagliate in base a parole chiave di ricerca, pagina di destinazione, posizione geografica e altro ancora. Per visualizzare un video introduttivo, vedi:

>[!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw)

### Media

* **Consumo audio**: quali contenuti vengono maggiormente consumati e coinvolgono maggiormente gli utenti?
* **Recency - Frequenza - Fedeltà**: Chi sono i miei lettori più fedeli?

### Mobile

>[!IMPORTANT]
>
>I modelli per dispositivi mobili sono disponibili solo se la suite per rapporti è abilitata per i dispositivi mobili.

* **Messaggistica:** si focalizza sulle prestazioni di messaggi in-app e push.
* **Posizione:** include una mappa che mostra i dati della posizione.
* **Metriche chiave:** controlla le metriche chiave della tua app.
* **Utilizzo app:** quanti utenti, avvii e primi avvii sono stati registrati per l’app, e quanto dura in media una sessione?
* **Acquisizione:** scopri le prestazioni dei collegamenti per acquisizione mobile.
* **Prestazioni:** quali sono le prestazioni dell’app e dove vengono riscontrati problemi dagli utenti?
* **Fidelizzazione:** chi sono i miei utenti più fedeli e cosa fanno?
* **Percorsi:** Quali sono i pattern di utilizzo principali per la l’app?

### Vendita al dettaglio

* **Prestazione campagna:** quali campagne generano maggior fatturato?
* **Prodotti:** quali prodotti hanno prestazioni migliori?

### Web

* **Acquisizione:** quali fattori generano maggior traffico verso il sito Web?
* **Consumo di contenuti:** quali sono le aree del sito più visitate?
* **Fidelizzazione:** che tipi di utenti hanno più probabilità di diventare utenti fedeli del sito?
* **Tecnologia:** quali tecnologie vengono usate per accedere al sito?

### Persone

>[!NOTE]
>
>Il modello Persone e la metrica Persone corrispondente sono disponibili per l’uso unicamente nell’ambito di [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/it-IT/device-co-op/using/data/people.html).

Questo modello è basato sulla metrica Persone, che è una versione deduplicata della metrica Visitatori unici. La metrica Persone misura la frequenza con cui i consumatori che utilizzano più dispositivi interagiscono con il tuo marchio. Il modello consente di:

* Segmentare i dati relativi a USA/Canada rispetto al resto del mondo. Device Co-op attualmente è disponibile solo nel Nord America.
* Affiancare e confrontare le metriche Persone e Visitatori unici.
* Visualizzare il “tasso di compressione”, una metrica calcolata che mostra lo scarto della metrica Persone come percentuale di Visitatori unici.
* Confrontare i totali dei diversi tipi di dispositivi utilizzati dalla clientela.
* Verificare la media dei dispositivi pro capite.
* Scoprire come raggruppare i segmenti con la metrica Persone.
* Capire in che modo l’uso di Experience Cloud ID nel tuo ambiente riesca a ottimizzare l’efficacia della metrica Persone.

### Modello di Journey IQ: Cross-Device Analytics

<!--This content is mirrored in the CDA doc.-->

Questo modello consente di visualizzare dati vitali delle prestazioni tra dispositivi. È disponibile solo per i clienti che hanno accesso a [Cross-Device Analytics](https://docs.adobe.com/content/help/it-IT/analytics/components/cda/cda-home.html) (CDA).

* **Nota speciale per i membri del Co-op Graph**: mostra quale parte della suite di rapporti contiene i visitatori nelle aree in cui è supportato il grafico Co-op e le aree in cui non è supportato.
* **Identificazione degli utenti**: mostra la frequenza con cui i visitatori del sito vengono identificati utilizzando metodi basati su Cross-Device Analytics.
* **Misurazione della dimensione dell’audience**: mostra un confronto tra “Dispositivi unici” e “Persone”. La proporzione di questi due numeri è nota come “compressione tra dispositivi”, una metrica calcolata visibile in questo pannello. Questa metrica di compressione dipende da un’ampia gamma di fattori:
   * **Utilizzo del grafico Co-op o del grafico Private**: in generale, le organizzazioni che utilizzano Device Co-op godono di tassi di compressione migliori rispetto alle organizzazioni che utilizzano il grafico Private.
   * **Tasso di accesso**: più utenti accedono al sito, più Adobe è in grado di identificare e unire i visitatori tra i dispositivi. I siti con un tasso di accesso basso hanno anche tassi di compressione bassi.
   * **Copertura di Experience Cloud ID**: è possibile unire solo i visitatori con un ECID. Una percentuale inferiore di visitatori del sito che utilizza un ECID è correlata a tassi di compressione più bassi.
   * **Utilizzo di più dispositivi**: se i visitatori del sito non utilizzano più dispositivi le percentuali di compressione potrebbero essere più basse.
   * **Granularità del reporting**: la compressione per giorno è generalmente inferiore della compressione per mese o per anno. Le possibilità che una sola persona utilizzi più dispositivi si riducono maggiormente in un singolo giorno che nell’arco di un mese intero. Segmentazione, filtraggio o utilizzo di dimensioni di suddivisione possono mostrare inoltre un tasso di compressione più basso.
* **Segmenti basati sulle persone**: contiene un elenco a discesa dei segmenti che consente di visualizzare dati specifici per il dispositivo. Questo pannello incoraggia la sperimentazione con i segmenti per vedere in che modo i rapporti possono essere influenzati dall’inclusione o esclusione di tipi di dispositivi.
* **Analisi del percorso tra dispositivi**: fornisce rapporti di flusso e di fallout in base al tipo di dispositivo.
* **Attribuzione tra dispositivi**: combina le funzioni di Journey IQ e Attribution IQ.
* **Altri suggerimenti e trucchi**: argomenti utili che riguardano CDA e permettono di ottenere il massimo dal suo utilizzo.