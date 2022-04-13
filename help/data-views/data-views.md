---
title: Panoramica delle visualizzazioni dati
description: Una visualizzazione dati specifica come si desidera interpretare gli elementi dei dati nella connessione CJA, ad esempio metriche, dimensioni, sessioni, ecc.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 4%

---

# Panoramica delle visualizzazioni dati

Una visualizzazione dati è un contenitore specifico del Customer Journey Analytics che consente di determinare come interpretare i dati da un [connection](/help/connections/create-connection.md). Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione al reporting in Analysis Workspace.

>[!NOTE]
>
>Tutte le impostazioni selezionate o modificate in una visualizzazione dati sono retroattive e non distruttive. In altre parole, non cambiano definitivamente i dati sottostanti .

Puoi creare diverse visualizzazioni dati per la stessa connessione, con set di componenti molto diversi (dimensioni/metriche). Oppure crea visualizzazioni dati con impostazioni diverse per timeout visita, attribuzione, ecc. Ad esempio, puoi avere una visualizzazione dati in cui tutte le dimensioni sono impostate su [!UICONTROL Last Touch], e contemporaneamente, un’altra visualizzazione dati (basata sullo stesso set di dati) con tutte le dimensioni impostate su [!UICONTROL First Touch].

I progetti Workspace in Customer Journey Analytics si basano sulle visualizzazioni dati.

## Funzionalità di visualizzazione dati {#capabilities}

Le visualizzazioni dati consentono di modificare spontaneamente le impostazioni degli elementi dello schema, senza dover modificare lo schema in Adobe Experience Platform o reimplementare l’ambiente CJA.

* **Puoi cambiare un componente da una metrica a un Dimension e viceversa**. Puoi creare metriche dai campi stringa o dimensioni dai campi numerici. Questo semplifica la vita, perché non è necessario creare un campo numerico nello schema XDM per ogni metrica desiderata. Puoi invece crearlo spontaneamente nella finestra di dialogo delle visualizzazioni dati. Di seguito sono riportati alcuni esempi:
   * **Creare una o più dimensioni e/o una dimensione da un singolo campo schema**. È una relazione uno-a-molti. Ad esempio, puoi creare una o più metriche Revenue e/o una o più dimensioni Revenue da un singolo campo di schema.
   * **Utilizzare un campo stringa come metrica**: Quando si compila uno schema in Experience Platform con un set di dati, è possibile che non si sappia in anticipo quali elementi dello schema sono necessari. Ad esempio, potresti non aver realizzato che era necessaria una metrica per &quot;Errori su una pagina&quot;. Di conseguenza, non è stato creato un elemento schema numerico per questo effetto. Utilizzando un elemento stringa come metrica, ora puoi utilizzare le impostazioni delle visualizzazioni dati per specificare che ogni volta che una stringa contiene la parola &quot;errore&quot;, può essere utilizzata come metrica.
   * **Utilizzare un campo numerico come dimensione**: Ad esempio, se desideri estrarre la metrica Ricavo dalla dimensione Ricavo, la dimensione Ricavo mostra ogni valore come un elemento dimensione ($100, $175, $1.000, ecc.) e il numero di istanze per ogni elemento della dimensione. Le entrate come metrica si comportano come sempre.

* **Puoi creare più metriche con diversi modelli di attribuzione o con diversi intervalli di lookback** dallo stesso campo schema.

* **Puoi modificare l’ID di un componente** - viene utilizzato per la compatibilità tra più visualizzazioni dati. L’ID componente è ciò che l’API di reporting utilizza per identificare una metrica o una dimensione specifica. Poiché puoi creare arbitrariamente molte metriche o dimensioni da un campo XDM, ti offriremo la possibilità di definire il tuo ID componente. Di conseguenza, una metrica utilizzata in un progetto Workspace può essere compatibile tra le visualizzazioni dati (e l’API), anche se si basa su campi completamente diversi, da connessioni o viste dati diverse o da uno schema diverso in XDM.

* **Puoi specificare il nome del componente descrittivo che verrà visualizzato in Analysis Workspace**. Per impostazione predefinita, questo nome viene ereditato dal nome visualizzato dello schema, ma ora è possibile sovrascriverlo per questa visualizzazione dati specifica.

* **Puoi visualizzare ulteriori informazioni relative allo schema sui componenti** , ad esempio: da quale tipo di set di dati (evento, profilo, ricerca) proviene; quale tipo di schema (stringa, numero intero, ecc.) proveniva da; e il relativo percorso dello schema (il campo XDM su cui si basa).

* **È possibile assegnare tag a un componente** per facilitarne la ricerca in Workspace.

* **Puoi nascondere un componente nel reporting**. Alcune impostazioni di metriche e dimensioni richiedono una seconda metrica o dimensione per la configurazione (ad esempio, la deduplicazione metrica o la deduplicazione degli acquisti). Ciò ti consente di definire una metrica o una dimensione che può essere utilizzata nelle impostazioni di un’altra metrica o dimensione senza essere esposta direttamente nel reporting (ad esempio l’ID acquisto).

* **È possibile applicare la formattazione a una metrica**, ad esempio la visualizzazione di valori decimali, ora, percentuale o valuta; specificare le cifre decimali; mostrare una tendenza all’aumento come verde o rosso; e specifica delle opzioni di valuta.

* È possibile **creare una metrica o una dimensione in base solo ad alcuni valori nel campo schema**. Ad esempio, se desideri una metrica di &quot;errori&quot;, puoi creare una metrica dal campo del nome della pagina ma includere solo pagine che contengono la parola &quot;errore&quot;. La metrica degli errori creata da questo elemento è supportata da filtri, è inserita nelle metriche calcolate e funziona con attribuzione, flusso, fallout, ecc.

* Per le dimensioni, potete **includere o escludere automaticamente solo determinati valori all&#39;interno di un campo specifico**. Ad esempio, se uno sviluppatore ha inviato un valore errato di `dev mistake` in un campo, puoi facilmente escluderlo dal reporting utilizzando una regola di esclusione che si comporta come se non fosse mai esistita nei dati.

* È possibile **rinomina i contenitori** in una visualizzazione dati e far sì che i contenitori rinominati siano visualizzati in qualsiasi progetto Workspace basato su tale visualizzazione dati.

## Prerequisiti per le visualizzazioni dati {#prerequisites}

* Prima di poter creare visualizzazioni dati, devi [impostare una o più connessioni ai set di dati di Experience Platform](/help/connections/create-connection.md).
* Per creare o gestire una visualizzazione dati, è necessario un [set di autorizzazioni in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it#admin-access-permissions).

## Impostazioni della visualizzazione dati sostituibili in Workspace {#settings-override}

Alcune impostazioni di visualizzazione dati possono essere ignorate in Analysis Workspace a livello di progetto, altre no.

* [!UICONTROL Lookback window]
* Attribuzione metrica
* Indica se gli utenti visualizzano o meno la [!UICONTROL No Value] riga in un report

## Impostazioni della visualizzazione dati non modificabili in Workspace {#settings-no-override}

* [!UICONTROL Component type]
* Formattazione delle metriche
* Nome della visualizzazione dati
* Assegnazione dei Dimension

## Eliminare le visualizzazioni dati {#delete}

Se elimini una visualizzazione dati in [!UICONTROL Customer Journey Analytics], un messaggio di errore indicherà che [!UICONTROL Workspace] i progetti che dipendono da questa visualizzazione dati eliminata non funzioneranno più.

## Passaggi successivi

* [Creare visualizzazioni dati](/help/data-views/create-dataview.md)
* [Casi d’uso per le visualizzazioni dati](/help/data-views/data-views-usecases.md)
