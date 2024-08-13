---
title: Panoramica delle visualizzazioni dati
description: Una visualizzazione dati specifica come interpretare gli elementi dei dati nella connessione di Customer Journey Analytics, ad esempio metriche, dimensioni, sessioni e così via.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0e4e4621abe02c022981e458282543908b2396c2
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 42%

---

# Panoramica delle visualizzazioni dati

Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una [connessione](/help/connections/create-connection.md). Specifica tutte le dimensioni e le metriche disponibili in Analysis Workspace, e da quali colonne tali dimensioni e metriche ottengono i loro dati. Le visualizzazioni dati sono definite in preparazione alle attività di reporting in Analysis Workspace.

>[!NOTE]
>
>Le impostazioni selezionate o modificate in una visualizzazione dati sono retroattive e non distruttive. In altre parole, non modificano in modo permanente i dati sottostanti.

Puoi creare diverse visualizzazioni dati per una stessa connessione, con set di componenti molto diversi (dimensioni o metriche). Oppure crea visualizzazioni dati con impostazioni diverse per timeout visita, attribuzione e così via. Ad esempio, puoi avere una visualizzazione dati in cui tutte le dimensioni sono impostate su [!UICONTROL Last Touch] e, contemporaneamente, un’altra visualizzazione dati (basata sullo stesso set di dati) con tutte le dimensioni impostate su [!UICONTROL First Touch].

I progetti Workspace in Customer Journey Analytics si basano sulle visualizzazioni dati.

>[!IMPORTANT]
>
>Puoi aggiungere fino a 5.000 metriche e 5.000 dimensioni a una singola visualizzazione dati.

## Funzionalità delle visualizzazioni dati {#capabilities}

Le visualizzazioni dati consentono di modificare spontaneamente le impostazioni degli elementi dello schema, senza dover modificare lo schema in Adobe Experience Platform, né reimplementare l’ambiente Customer Journey Analytics.

* Puoi cambiare un componente da metrica a dimensione e viceversa. Puoi creare metriche da campi stringa o dimensioni da campi numerici. Questa funzionalità semplifica il lavoro, perché non è necessario creare un campo numerico nello schema XDM per ogni metrica desiderata. Potrai infatti crearlo spontaneamente nella finestra di dialogo delle visualizzazioni dati. Di seguito sono riportati alcuni esempi:
   * **Crea una o più dimensioni e/o una dimensione da un singolo campo schema**. Si tratta di una relazione uno-a-molti. Ad esempio, puoi creare una o più metriche Ricavi e/o una o più dimensioni Ricavi da un singolo campo dello schema.
   * **Utilizza un campo stringa come metrica**: quando compili uno schema in Experience Platform con un set di dati, potresti non sapere ancora quali elementi schema saranno necessari. Ad esempio, potresti non esserti reso conto di aver bisogno di una metrica per *Errori su una pagina*. e quindi non aver creato l’elemento schema numerico corrispondente. Utilizzando un elemento stringa come metrica, ora è possibile utilizzare le impostazioni delle visualizzazioni dati per specificare che, ogni volta che una stringa contiene la parola `error`, può essere utilizzata come metrica.
   * **Utilizza un campo numerico come dimensione**: ad esempio, se desideri estrarre la metrica Ricavi dalla dimensione Ricavi, quest&#39;ultima mostra ogni valore come un elemento dimensione. E il numero di istanze per ogni elemento dimensione come metrica.

* Puoi creare più metriche con diversi modelli di attribuzione o diversi intervalli di lookback dallo stesso campo schema.

* Puoi modificare l’ID di un componente per garantire la compatibilità tra più visualizzazioni dati. L’ID componente viene utilizzato dall’API di reporting per identificare una specifica metrica o dimensione. Poiché puoi creare arbitrariamente molte metriche o dimensioni da un campo XDM, puoi definire un ID componente personalizzato. Di conseguenza, una metrica utilizzata in un progetto Workspace può essere utilizzata in modo compatibile tra le visualizzazioni dati (e l’API). Anche se le metriche si basano su campi completamente diversi, da connessioni diverse, visualizzazioni dati o da uno schema XDM diverso.

* Puoi specificare il nome descrittivo del componente, che viene visualizzato in Analysis Workspace. Per impostazione predefinita, questo nome viene ereditato dal nome visualizzato dello schema, ma ora è possibile sovrascriverlo per una visualizzazione dati specifica.

* Puoi visualizzare ulteriori informazioni relative allo schema sui componenti. Ad esempio:

   * il tipo di set di dati (evento, profilo, ricerca, riepilogo) da cui proviene il componente,
   * tipo di schema (stringa, numero intero, ecc.) è originario di, e
   * il percorso dello schema (il campo XDM su cui si basa).

* Puoi assegnare tag a un componente per facilitarne la ricerca in Workspace.

* Puoi nascondere un componente nei rapporti. Alcune impostazioni di metriche e dimensioni richiedono di configurare una seconda metrica o dimensione (ad esempio, deduplica di metriche o di acquisti). Nascondere un componente consente di definire un componente che può essere utilizzato nelle impostazioni di un altro componente senza essere esposto nei rapporti.

* Puoi applicare la formattazione a una metrica, ad esempio per visualizzare valori decimali, ora, percentuale o valuta; specificare cifre decimali; mostrare in verde o in rosso una tendenza in crescita; e specificare opzioni di valuta.

* Puoi creare una metrica o dimensione in base a solo alcuni valori nel campo schema. Ad esempio, se desideri una metrica Errori, puoi creare una metrica dal campo del nome della pagina ma includere solo pagine che contengono la parola `error`. La metrica Errori creata in questo modo supporta i filtri, può essere inserita nelle metriche calcolate e funziona con attribuzione, flusso, abbandono, ecc.

* Per le dimensioni, puoi includere o escludere automaticamente solo determinati valori all’interno di un campo specifico. Ad esempio, se uno sviluppatore ha inviato un valore errato di `dev mistake` in un campo, puoi facilmente escluderlo dai rapporti utilizzando una regola di esclusione. La dimensione si comporta come se il valore errato non fosse mai esistito nei dati.

* Puoi rinominare i contenitori in una visualizzazione dati e far sì che i contenitori rinominati siano visualizzati in qualsiasi progetto Workspace basato su tale visualizzazione dati.

## Prerequisiti per le visualizzazioni dati {#prerequisites}

* Prima di poter creare visualizzazioni dati, devi [impostare una o più connessioni ai set di dati di Experience Platform](/help/connections/create-connection.md).
* Per creare o gestire una visualizzazione dati, è necessario un [set di autorizzazioni in Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview).
* Se utilizzi il [connettore di origine di Adobe Analytics](/help/data-ingestion/analytics.md) o hai conoscenze di base di Adobe Analytics, potresti voler capire in che modo i campi negli schemi e nei set di dati si relazionano alle controparti di Adobe Analytics. Per ulteriori informazioni, consulta [Mappatura campi in Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics).

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

Se si elimina una visualizzazione dati in [!UICONTROL Customer Journey Analytics], un messaggio di errore indica che i progetti [!UICONTROL Workspace] che dipendono dalla visualizzazione dati eliminata non funzionano più.

## Passaggi successivi

* [Creare le visualizzazioni dati](/help/data-views/create-dataview.md)
* [Casi d’uso per le visualizzazioni dati](/help/use-cases/data-views/data-views-usecases.md)
