---
title: Panoramica sull’unione
description: Panoramica sull’unione.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: 73496ea3c8341d9db7e879a4f5ae4f35893c605d
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 31%

---

# Panoramica sull’unione

L’unione di identità (o semplicemente unione) è una funzione potente che eleva l’idoneità di un set di dati evento per l’analisi cross-channel. L’analisi cross-channel è un caso d’uso principale che il Customer Journey Analytics può gestire e consente di combinare ed eseguire facilmente rapporti su più set di dati da canali diversi, in base a un identificatore comune (ID persona).

Quando combini set di dati con ID persona simili, l’attribuzione viene riportata su dispositivi e canali diversi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente incontra un problema con il proprio ordine, quindi invia al team di assistenza clienti una chiamata per aiutarti a risolverlo. Con l’analisi cross-channel, puoi attribuire gli eventi del call center all’annuncio su cui hanno fatto clic originariamente.

Sfortunatamente, non tutti i set di dati basati su eventi che fanno parte della connessione nel Customer Journey Analytics sono sufficientemente compilati con dati per supportare questa attribuzione pronta all’uso. In particolare, i set di dati di esperienza basati su web o dispositivi mobili spesso non dispongono di un ID persona effettivo disponibile su tutti gli eventi.

L’unione consente di reimpostare le identità all’interno delle righe di un set di dati, assicurandosi che l’ID persona (ID unione) sia disponibile su ogni evento. L’unione esamina i dati utente provenienti da sessioni autenticate e non autenticate per determinare il valore ID transitorio comune che può essere utilizzato come ID unione. Questo consente di risolvere record diversi in un singolo ID unito per l’analisi a livello di persona, anziché a livello di dispositivo o cookie.

Puoi trarre vantaggio dall’analisi cross-channel se combini uno o più set di dati uniti con altri set di dati, come i dati del call center, nell’ambito della definizione della connessione di Customer Journey Analytics. Ciò presuppone che gli altri set di dati contengano già un ID persona su ogni riga, simile all’ID unito.


## Prerequisiti

>[!IMPORTANT]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di condurre correttamente l’analisi cross-channel.

Prima di utilizzare le unioni, assicurati che l’organizzazione sia preparata con quanto segue:

* Importa i dati desiderati in Adobe Experience Platform:

   * Per i dati di Adobe Analytics, consulta [Utilizzo dei dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * Per altri tipi di dati, consulta la sezione [Creare uno schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) e [Inserire i dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=it) nella documentazione di Adobe Experience Platform.

* Il set di dati dell’evento in Adobe Experience Platform a cui desideri applicare l’unione deve avere due colonne che aiutino a identificare i visitatori:

   * Un **ID persistente**, un identificatore presente su ogni riga. Ad esempio, un ID visitatore generato da una libreria di AppMeasurement Adobe Analytics o un ECID generato dal servizio Adobe Experience Cloud Identity.
   * A **ID transitorio**, un identificatore presente solo su alcune righe. Ad esempio, un nome utente o un indirizzo e-mail con hash quando un visitatore si autentica. Puoi utilizzare virtualmente qualsiasi identificatore che ti piace. L’unione considererà questo campo come contenente le informazioni dell’ID persona effettivo. Per risultati di unione migliori, un ID transitorio deve essere inviato all’interno degli eventi del set di dati almeno una volta per ogni ID persistente.
Se prevedi di includere questo set di dati all’interno di una connessione di Customer Journey Analytics, è preferibile che anche gli altri set di dati abbiano un identificatore comune simile.

* L’unione include l’unione di dati utente autenticati e non autenticati. Prima di attivare l’unione su un set di dati evento, assicurati di rispettare le leggi e le normative applicabili, incluso l’ottenimento delle autorizzazioni necessarie per l’utente finale.


## Utilizzare l’unione

Quando l&#39;organizzazione soddisfa tutti i prerequisiti e comprende [limitazioni](#limitations), per iniziare a utilizzare l’unione nel Customer Journey Analytics, segui la procedura riportata di seguito:

### Richiedi supporto

1. Contatta l’Assistenza clienti di Adobe con le seguenti informazioni:

   * Richiesta per abilitare l’unione.
   * ID set di dati per il set di dati da ridigitare.
   * Nome della colonna dell’ID persistente per il set di dati desiderato (identificatore visualizzato su ogni riga).
   * Nome della colonna dell’ID transitorio per il set di dati desiderato (collegamento dell’identificatore della persona tra i set di dati).
   * Preferenza di [ripetizione](explained.md) frequenza e lunghezza del lookback. Le opzioni includono una ripetizione una volta alla settimana con un intervallo di lookback di 7 giorni, o una ripetizione ogni giorno con un intervallo di lookback di 1 giorno.
   * Nome della sandbox.


2. L’Assistenza clienti Adobe collabora con il team di progettazione Adobe per abilitare l’unione dopo la ricezione della richiesta. Una volta abilitato, in Adobe Experience Platform compare un nuovo set di dati ridigitato contenente una nuova colonna ID persona. L’Assistenza clienti Adobe può fornire il nuovo ID set di dati e il nome della colonna ID persona.

3. Quando CCA è attivato per la prima volta, Adobe fornisce la retrocompilazione dei dati uniti che risalgono all’inizio del mese precedente (fino a 60 giorni). Per eseguire questa retrocompilazione, l’ID transitorio deve esistere nei dati non uniti che risalgono al periodo precedente.

4. [Creare una connessione](/help/connections/create-connection.md) in Customer Journey Analytics utilizzando il set di dati appena generato e tutti gli altri set di dati che desideri includere. Scegli l’ID persona corretto per ogni set di dati.

5. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) in base alla connessione.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una volta configurata la visualizzazione dati, l’analisi cross-channel nel Customer Journey Analytics è esattamente come qualsiasi altra analisi nel Customer Journey Analytics, tranne per il fatto che ora i dati funzionano tra canali e dispositivi.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## Limitazioni

>[!IMPORTANT]
>
>Applica le modifiche apportate allo schema del set di dati dell’evento globale anche al nuovo schema del set di dati uniti, altrimenti interrompe il set di dati uniti.
>
>Inoltre, se rimuovi il set di dati di origine, il set di dati uniti non elabora più i dati e viene rimosso dal sistema.

L’unione è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata.

* Le attuali funzionalità di rekeying sono limitate a un solo passaggio (ID persistente a ID transitorio). La reimpostazione in più passaggi (ad esempio, ID persistente in un ID transitorio e quindi in un altro ID transitorio) non è supportata.
* Sono supportati solo i set di dati evento. Altri set di dati, come i set di dati di ricerca, non sono supportati.
* Le mappe ID personalizzate utilizzate nell’organizzazione non sono supportate.
* L’unione non trasforma in alcun modo il campo utilizzato per l’unione. L’unione utilizza il valore nel campo specificato così come esiste nel set di dati non uniti all’interno del data lake. Il processo di unione distingue tra maiuscole e minuscole. Ad esempio, se a volte nel campo viene visualizzata la parola &quot;Bob&quot; e a volte viene visualizzata la parola &quot;BOB&quot;, questi ID vengono trattati come due persone separate.
* L’unione distingue tra maiuscole e minuscole. Per i set di dati generati tramite il connettore di origine di Analytics, l’Adobe consiglia di rivedere eventuali regole VISTA o regole di elaborazione applicabili al campo ID transitorio. Questa revisione assicura che nessuna di queste regole introduca nuove forme dello stesso ID. Ad esempio, assicurati che le regole VISTA o di elaborazione non introducano lettere minuscole nel campo ID transitorio solo per una parte degli eventi.
* L’unione non combina o concatena i campi.
* Il campo ID transitorio deve contenere un singolo tipo di ID ( ID da un singolo spazio dei nomi). Ad esempio, il campo ID transitorio non deve contenere una combinazione di ID di accesso e ID e-mail.
* Se si verificano più eventi con la stessa marca temporale per lo stesso ID persistente, ma con valori diversi nel campo ID transitorio, l’unione seleziona l’ID in base all’ordine alfabetico. Quindi, se l’ID persistente A ha due eventi con la stessa marca temporale e uno degli eventi specifica Bob e l’altro specifica Ann, l’unione seleziona Ann.
* Se un dispositivo è condiviso da più persone e il numero totale di transizioni tra gli utenti supera le 50.000, il Customer Journey Analytics non unisce più i dati per tale dispositivo.

Non confondere l’unione con:

* Unione di due o più set di dati. L’unione si applica solo a un set di dati. L’unione di set di dati si verifica in seguito alla configurazione di una connessione di Customer Journey Analytics e alla selezione dello stesso ID persona nei set di dati selezionati nella connessione.

* Unione di due set di dati. In Customer Journey Analytics, un join viene spesso utilizzato per ricerche o classificazioni in Analysis Workspace. Sebbene l’unione utilizzi la funzionalità di unione, il processo stesso coinvolge molto di più dei join.

