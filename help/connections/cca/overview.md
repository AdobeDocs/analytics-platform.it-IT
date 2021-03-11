---
title: Panoramica di Analytics tra canali
description: Ri-chiave ID visitatore da più set di dati per unire i visitatori.
translation-type: tm+mt
source-git-commit: cc78a3941a4179be0dbf46055fea60df8e7e8b97
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 12%

---


# Panoramica di Analytics tra canali

**IQ percorso: Cross-Channel** Analytics è una funzione che consente di reimpostare l’ID persona di un set di dati, consentendo una combinazione perfetta di più set di dati. CCA esamina i dati utente provenienti da sessioni autenticate e non autenticate per generare un ID vincolato. Utilizzando Cross-Channel Analytics puoi rispondere a domande quali:

* Quante persone iniziano la loro esperienza in un canale, poi la finiscono in un altro?
* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando combini set di dati con ID persona simili, l’attribuzione viene riportata su dispositivi e canali diversi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente incontra un problema con il proprio ordine, quindi invia al team di assistenza clienti una chiamata per aiutarti a risolverlo. Con Cross-Channel Analytics puoi attribuire gli eventi del call center all’annuncio che hanno fatto clic originariamente.

## Prerequisiti

>[!IMPORTANT]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di creare una connessione CCA o risultati errati quando si combinano i set di dati.

Prima di utilizzare Cross-Channel Analytics, assicurati che l’organizzazione sia preparata con quanto segue:

* Un set di dati in Adobe Experience Platform deve avere due colonne che aiutano a identificare i visitatori:
   * Un **ID persistente**, un identificatore presente su ogni riga. Ad esempio, un ID visitatore generato da una libreria Adobe Analytics AppMeasurement.
   * Un **ID transitorio**, un identificatore presente solo su alcune righe. Ad esempio, un nome utente o un indirizzo e-mail con hash quando un visitatore si autentica. Puoi utilizzare virtualmente qualsiasi identificatore desiderato, purché sia presente almeno una volta sullo stesso evento di un determinato ID persistente.
* Un altro set di dati, ad esempio i dati del call center, che contiene un ID transitorio su ogni riga. Questo ID persona deve essere formattato in modo simile all’ID transitorio nell’altro set di dati.
* Questa funzione ti consente di unire set di dati che possono includere l’unione di dati utente autenticati e non autenticati. Prima di unire i set di dati, assicurati di rispettare le leggi e le normative applicabili, incluso l’ottenimento delle autorizzazioni necessarie per l’utente finale.

## Limitazioni

Analisi cross-channel è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata.

* Le attuali funzionalità di rekeying sono limitate a un solo passaggio (ID persistente a ID transitorio). La reimpostazione in più passaggi (ad esempio, ID persistente in un ID transitorio e quindi in un altro ID transitorio) non è supportata.
* Sono supportati solo i set di dati evento. Altri set di dati, come i set di dati di ricerca, non sono supportati.
* Le mappe ID personalizzate utilizzate nell&#39;organizzazione non sono supportate.
* Il grafico Co-op di Adobe e il grafico Private non sono supportati.
* Cross-Channel Analytics non trasforma in alcun modo il campo utilizzato per l’unione. L’unione basata sui campi utilizza il valore nel campo specificato così come esiste nel set di dati non uniti all’interno del data lake. Ad esempio, se a volte nel campo viene visualizzata la parola &quot;Bob&quot; e a volte viene visualizzata la parola &quot;BOB&quot;, queste verranno trattate come due persone separate.


## Abilitare analisi cross-channel

Una volta che l’organizzazione soddisfa tutti i prerequisiti e ne comprende i limiti, puoi seguire questi passaggi per iniziare a utilizzarla in CJA.

1. Importa i dati desiderati in Adobe Experience Platform. Consulta [Creare uno schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html) e [Inserire dati](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) nella documentazione di Adobe Experience Platform.
1. Contatta il tuo Adobe Account Manager che include quanto segue:
   * Una richiesta per abilitare Cross-Channel Analytics
   * ID set di dati per il set di dati da reimpostare
   * Nome della colonna dell’ID persistente per il set di dati desiderato (Identificatore visualizzato su ogni riga)
   * Il nome della colonna dell’ID transitorio per il set di dati desiderato (il collegamento dell’identificatore della persona tra i set di dati)
   * La tua preferenza per [riproduci](replay.md) frequenza e lunghezza del lookback. Le opzioni includono una riproduzione una volta alla settimana con un intervallo di lookback di 7 giorni o una riproduzione giornaliera con un intervallo di lookback di 1 giorno.
1. Adobe Account Manager collaborerà con l’ingegneria Adobe per abilitare Cross-Channel Analytics dopo aver ricevuto la richiesta. Una volta abilitato, in Adobe Experience Platform viene visualizzato un nuovo set di dati retrato contenente una nuova colonna ID persona. Il tuo Adobe Account Manager può fornire il nuovo ID set di dati e il nome della colonna ID persona.
1. Quando è attivata per la prima volta, in Adobe viene fornito un backfill dei dati uniti che risalgono all’inizio del mese precedente (fino a 60 giorni). Per eseguire questa operazione di backfill, l’ID transitorio deve esistere nei dati non uniti fino a quel momento.
1. [Crea una ](../create-connection.md) connessione in CJA utilizzando il set di dati appena generato e tutti gli altri set di dati che desideri includere. Scegli l’ID persona corretto per ogni set di dati.
1. [Crea una ](/help/data-views/create-dataview.md) visualizzazione dati in base alla connessione.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una volta configurata la visualizzazione dati, Analysis in CJA è esattamente come qualsiasi altra analisi in CJA, tranne per il fatto che ora i dati funzionano tra canali e dispositivi.
