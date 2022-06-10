---
title: Panoramica delle visualizzazioni dati
description: Una visualizzazione dati determina come interpretare gli elementi dei dati nella connessione CJA, ad esempio metriche, dimensioni, sessioni, ecc.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '1031'
ht-degree: 100%

---

# Panoramica delle visualizzazioni dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una [connessione](/help/connections/create-connection.md). Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

>[!NOTE]
>
>Le impostazioni selezionate o modificate in una visualizzazione dati sono retroattive e non distruttive. In altre parole, non cambiano in modo permanente i dati sottostanti.

Puoi creare diverse visualizzazioni dati per una stessa connessione, con set di componenti molto diversi (dimensioni o metriche). Puoi anche creare visualizzazioni dati con impostazioni diverse per timeout visita, attribuzione ecc. Ad esempio, puoi avere una visualizzazione dati in cui tutte le dimensioni sono impostate su [!UICONTROL Last Touch] e, contemporaneamente, un’altra visualizzazione dati (basata sullo stesso set di dati) con tutte le dimensioni impostate su [!UICONTROL First Touch].

I progetti Workspace in Customer Journey Analytics si basano sulle visualizzazioni dati.

## Funzionalità delle visualizzazioni dati {#capabilities}

Le visualizzazioni dati consentono di modificare spontaneamente le impostazioni degli elementi dello schema, senza dover intervenire sullo schema in Adobe Experience Platform né reimplementare l’ambiente CJA.

* **Puoi cambiare un componente da metrica a dimensione e viceversa**. Puoi creare metriche da campi stringa o dimensioni da campi numerici. Questo semplifica il lavoro, poiché non è necessario creare un campo numerico nello schema XDM per ogni metrica desiderata. Potrai infatti crearlo spontaneamente nella finestra di dialogo delle visualizzazioni dati. Di seguito sono riportati alcuni esempi:
   * **Crea una o più dimensioni e/o una dimensione da un singolo campo schema**. Si tratta di una relazione uno-a-molti. Ad esempio, puoi creare una o più metriche Ricavi e/o una o più dimensioni Ricavi da un singolo campo dello schema.
   * **Utilizza un campo stringa come metrica**: quando compili uno schema in Experience Platform con un set di dati, potresti non sapere ancora quali elementi schema saranno necessari. Ad esempio, potresti non esserti reso conto di aver bisogno di una metrica per “Errori su una pagina” e quindi non aver creato l’elemento schema numerico corrispondente. Utilizzando un elemento stringa come metrica, ora con le impostazioni delle visualizzazioni dati puoi specificare che, ogni volta che una stringa contiene la parola “errore”, può essere utilizzata come metrica.
   * **Utilizza un campo numerico come dimensione**: ad esempio, se desideri estrarre la metrica Ricavi dalla dimensione Ricavi, quest’ultima mostra ogni valore come un elemento dimensione ($ 100, $ 175, $ 1.000 ecc.) e il numero di istanze per ogni elemento dimensione. La metrica Ricavi si comporterà come sempre.

* **Puoi creare più metriche con diversi modelli di attribuzione o diversi intervalli di lookback** dallo stesso campo schema.

* **Puoi modificare l’ID di un componente**: viene utilizzato per compatibilità tra più visualizzazioni dati. L’ID componente viene utilizzato dall’API di reporting per identificare una specifica metrica o dimensione. Poiché puoi creare arbitrariamente molte metriche o dimensioni da un campo XDM, hai la possibilità di definire un tuo ID componente. Pertanto, una metrica utilizzata in un progetto Workspace può essere compatibile tra più visualizzazioni dati (e l’API), anche se si basa su campi completamente diversi, da connessioni o viste dati diverse o da uno schema XDM diverso.

* **Puoi specificare il nome descrittivo del componente, che verrà visualizzato in Analysis Workspace**. Per impostazione predefinita, questo nome viene ereditato dal nome visualizzato dello schema, ma ora è possibile sovrascriverlo per una visualizzazione dati specifica.

* **Puoi visualizzare ulteriori informazioni relative allo schema sui componenti**, ad esempio: da quale tipo di set di dati (evento, profilo, ricerca) e di schema (stringa, numero intero, ecc.) proviene, e il percorso del relativo schema (il campo XDM su cui si basa).

* **Puoi assegnare tag a un componente** per facilitarne la ricerca in Workspace.

* **Puoi nascondere un componente nei rapporti**. Alcune impostazioni di metriche e dimensioni richiedono di configurare una seconda metrica o dimensione (ad esempio, deduplica di metriche o di acquisti). Questo consente di definire una metrica o dimensione che può essere utilizzata nelle impostazioni di un’altra metrica o dimensione senza essere esposta direttamente nei rapporti (ad esempio, l’ID acquisto).

* **Puoi applicare la formattazione a una metrica**, ad esempio per visualizzare valori decimali, ora, percentuale o valuta; specificare quante cifre decimali includere; mostrare in verde o in rosso una tendenza in crescita; e specificare opzioni di valuta.

* Puoi **creare una metrica o dimensione in base a solo alcuni valori nel campo schema**. Ad esempio, se desideri una metrica di “errori”, puoi creare una metrica dal campo del nome della pagina e includere solo le pagine che contengono la parola “errore”. La metrica degli errori creata da questo elemento è supportata dai filtri, può essere inserita nelle metriche calcolate e funziona con attribuzione, flusso, abbandono, ecc.

* Per le dimensioni, puoi **includere o escludere automaticamente solo determinati valori all’interno di un campo specifico**. Ad esempio, se uno sviluppatore ha inviato un valore `dev mistake` errato in un campo, puoi facilmente escluderlo dai rapporti tramite una regola di esclusione, e si comporterà come se non fosse mai esistito nei dati.

* Puoi **rinominare i contenitori** di una visualizzazione dati e far sì che i contenitori rinominati siano visualizzati in qualsiasi progetto Workspace basato su tale visualizzazione dati.

## Prerequisiti per le visualizzazioni dati {#prerequisites}

* Prima di poter creare visualizzazioni dati, devi [impostare una o più connessioni ai set di dati di Experience Platform](/help/connections/create-connection.md).
* Per creare o gestire una visualizzazione dati, è necessario un [set di autorizzazioni in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it#admin-access-permissions).

## Impostazioni delle visualizzazioni dati che possono essere ignorate in Workspace {#settings-override}

Alcune impostazioni delle visualizzazioni dati possono essere ignorate in Analysis Workspace a livello di progetto, altre no.

* [!UICONTROL Lookback window]
* Attribuzione delle metriche
* Se gli utenti possono vedere o meno l’elemento riga [!UICONTROL No Value] in un rapporto

## Impostazioni delle visualizzazioni dati che non possono essere ignorate in Workspace {#settings-no-override}

* [!UICONTROL Component type]
* Formattazione delle metriche
* Nome delle visualizzazioni dati
* Assegnazione delle dimensioni

## Eliminare le visualizzazioni dati {#delete}

Se elimini una visualizzazione dati in [!UICONTROL Customer Journey Analytics], un messaggio di errore segnala che i progetti [!UICONTROL Workspace] che dipendono dalla visualizzazione dati eliminata non funzioneranno più.

## Passaggi successivi

* [Creare le visualizzazioni dati](/help/data-views/create-dataview.md)
* [Casi d’uso per le visualizzazioni dati](/help/data-views/data-views-usecases.md)
