---
title: Cos’è una visualizzazione dati in un Customer Journey Analytics?
description: Una visualizzazione dati specifica come si desidera interpretare gli elementi dei dati nella connessione CJA, ad esempio metriche, dimensioni, sessioni, ecc.
translation-type: tm+mt
source-git-commit: c1f5048e33d52a71db9811c22f49c237ac583817
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 2%

---


# Cos’è una visualizzazione dati?

Una visualizzazione dati si trova sopra un Customer Journey Analytics (CJA) [connessione](/help/connections/create-connection.md). Una connessione combina uno o più set di dati da Adobe Experience Platform e la collega a CJA. La visualizzazione dati specifica come si desidera interpretare gli elementi dei dati nella connessione, come metriche, dimensioni, sessioni, ecc. Le visualizzazioni dati sono definite in preparazione alla generazione di rapporti sui dati in Workspace.

Se in precedenza hai utilizzato Adobe Analytics tradizionale, una visualizzazione dati è simile a una suite di rapporti virtuali in quanto è una visualizzazione &quot;filtrata&quot; dei dati.

Puoi creare diverse visualizzazioni dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Puoi anche creare più visualizzazioni dati per un singolo set di dati. Ad esempio, puoi avere una visualizzazione dati in cui tutte le dimensioni sono impostate su [!UICONTROL Last Touch] e, contemporaneamente, un’altra visualizzazione dati (basata sullo stesso set di dati) con tutte le dimensioni impostate su [!UICONTROL First Touch].

I progetti Workspace in Customer Journey Analytics si basano sulle visualizzazioni dati.

## Novità nelle visualizzazioni dati

L’ultimo aggiornamento delle visualizzazioni dati offre molta più flessibilità nelle operazioni che puoi eseguire con le visualizzazioni dati. Questi miglioramenti consentono di **modificare spontaneamente le impostazioni degli elementi dello schema nelle visualizzazioni dati, senza dover modificare lo schema in Adobe Experience Platform o reimplementare l&#39;ambiente CJA**.

* **Puoi cambiare un componente da Metrica a Dimension e viceversa**. Puoi creare metriche dai campi stringa o dimensioni dai campi numerici. In questo modo la tua vita diventa più semplice, in quanto non devi creare un campo numerico nello schema XDM per ogni metrica desiderata. Puoi invece crearlo spontaneamente nella finestra di dialogo delle visualizzazioni dati. Di seguito sono riportati alcuni esempi:
   * **Crea una o più dimensioni e/o una dimensione da un singolo campo** schema. È una relazione uno-a-molti. Ad esempio, puoi creare una o più metriche Revenue e/o una o più dimensioni Revenue da un singolo campo di schema.
   * **Utilizza un campo stringa come metrica**: Quando si compila uno schema in Experience Platform con un set di dati, è possibile che non si sappia in anticipo quali elementi dello schema sono necessari. Ad esempio, potresti non aver realizzato che era necessaria una metrica per &quot;Errori su una pagina&quot;. Di conseguenza, non è stato creato un elemento schema numerico per questo effetto. Utilizzando un elemento stringa come metrica, ora puoi utilizzare le impostazioni delle visualizzazioni dati per specificare che ogni volta che una stringa contiene la parola &quot;errore&quot;, può essere utilizzata come metrica.
   * **Utilizzare un campo numerico come dimensione**: Ad esempio, se desideri estrarre la metrica Ricavo dalla dimensione Ricavo, la dimensione Ricavo mostra ogni valore come un elemento dimensione ($100, $175, $1.000, ecc.) e il numero di istanze per ogni elemento della dimensione. Le entrate come metrica si comportano come sempre.

* **Puoi creare più metriche con diversi modelli di attribuzione o con diverse** finestre di lookback dallo stesso campo dello schema.

* **Puoi modificare l’ID di un componente** , utilizzato per garantire la compatibilità tra più dati. L’ID componente è ciò che l’API di reporting utilizza per identificare una metrica o una dimensione specifica. Poiché puoi creare arbitrariamente molte metriche o dimensioni da un campo XDM, ti offriremo la possibilità di definire il tuo ID componente. Di conseguenza, una metrica utilizzata in un progetto Workspace può essere compatibile tra le visualizzazioni dati (e l’API), anche se si basa su campi completamente diversi, da connessioni o viste dati diverse o da uno schema diverso in XDM.

* **Puoi specificare il nome del componente descrittivo che verrà visualizzato in Analysis Workspace**. Per impostazione predefinita, questo nome viene ereditato dal nome visualizzato dello schema, ma ora è possibile sovrascriverlo per questa visualizzazione dati specifica. (La cura dei componenti funziona anche nelle suite di rapporti virtuali in Adobe Analytics tradizionale).

* **Puoi visualizzare ulteriori informazioni relative allo schema sui componenti** , ad esempio: da quale tipo di set di dati (evento, profilo, ricerca) proviene; quale tipo di schema (stringa, numero intero, ecc.) proveniva da; e il relativo percorso dello schema (il campo XDM su cui si basa).

* **Puoi assegnare tag a un** componente per facilitarne la ricerca in Workspace.

* **Puoi nascondere un componente nel reporting**. Alcune impostazioni di metriche e dimensioni in DV2 richiedevano una seconda metrica o dimensione per la configurazione (ad esempio, la deduplicazione metrica o la deduplicazione degli acquisti). Ciò ti consente di definire una metrica o una dimensione che può essere utilizzata nelle impostazioni di un’altra metrica o dimensione senza essere esposta direttamente nel reporting (ad esempio l’ID acquisto).

* **È possibile applicare la formattazione a una metrica** , ad esempio la visualizzazione di decimali, ore, percentuali o valute; specificare le cifre decimali; mostrare una tendenza all’aumento come verde o rosso; e specifica delle opzioni di valuta.

* È possibile **creare una metrica o una dimensione in base solo ad alcuni valori nel campo schema**. Ad esempio, se desideri una metrica di &quot;errori&quot;, puoi creare una metrica dal campo del nome della pagina ma includere solo pagine che contengono la parola &quot;errore&quot;. La metrica degli errori creata da questo elemento è supportata da filtri, è inserita nelle metriche calcolate e funziona con attribuzione, flusso, fallout, ecc.

* Per le dimensioni, è possibile **includere o escludere automaticamente solo determinati valori all&#39;interno di un campo specifico**. Ad esempio, se uno sviluppatore ha inviato un valore errato di `dev mistake` in un campo, puoi facilmente escluderlo dal reporting utilizzando una regola di esclusione e si comporta come se non fosse mai esistito nei dati.

* Puoi **rinominare i contenitori** in una visualizzazione dati e far sì che i contenitori rinominati siano visualizzati in qualsiasi progetto Workspace basato su tale visualizzazione dati.

## Prerequisito

* Prima di poter creare visualizzazioni dati, devi [impostare una o più connessioni ai set di dati di Experience Platform](/help/connections/create-connection.md).
* Per creare o gestire una visualizzazione dati, è necessario un [set di autorizzazioni in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#admin-access-permissions).

## Visualizzare informazioni su un componente

Fai clic sull’icona (i) info in Workspace per visualizzare il campo dello schema su cui è basato un componente e le relative impostazioni, ad esempio una descrizione.

## Impostazioni di visualizzazione dati modificabili in Workspace

Alcune impostazioni di visualizzazione dati possono essere ignorate in Analysis Workspace a livello di progetto, altre no.

* Intervallo di lookback
* Attribuzione metrica
* Indica se gli utenti visualizzano o meno la riga &quot;Nessun valore&quot; in un rapporto

## Impostazioni di visualizzazione dati non modificabili in Workspace

* Tipo di componente
* Formattazione delle metriche
* Nome della visualizzazione dati
* Assegnazione dei Dimension

## Eliminare le visualizzazioni dati

Se elimini una visualizzazione dati in [!UICONTROL Customer Journey Analytics], un messaggio di errore indica che eventuali progetti Workspace dipendenti da questa visualizzazione dati eliminata non funzioneranno più.
