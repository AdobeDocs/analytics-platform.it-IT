---
title: Panoramica di Cross-Channel Analytics
description: Reimposta ID visitatore da più set di dati per unire i visitatori.
exl-id: 69763313-de27-4487-8e32-8277f1f693d8
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 3f20520a2021d9b6066b0492ed11a1a4619ab1d4
workflow-type: tm+mt
source-wordcount: '1196'
ht-degree: 96%

---

# Panoramica di Cross-Channel Analytics

**Journey IQ: Cross-Channel Analytics** è una funzione che consente di reimpostare l’ID persona di un set di dati, consentendo una combinazione perfetta di più set di dati. CCA esamina i dati utente provenienti da sessioni autenticate e non autenticate per generare un ID unico. Utilizzando Cross-Channel Analytics, potrai rispondere a domande quali:

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
   * A **ID transitorio**, un identificatore presente solo su alcune righe. Ad esempio, un nome utente o un indirizzo e-mail con hash quando un visitatore si autentica. Puoi utilizzare virtualmente qualsiasi identificatore desiderato, purché sia presente almeno una volta sullo stesso evento di un determinato ID persistente.
* Un altro set di dati, ad esempio i dati del call center, che contiene un ID transitorio su ogni riga. Questo ID persona deve essere formattato in modo simile all’ID transitorio nell’altro set di dati.
* Questa funzione ti consente di unire set di dati che possono includere l’unione di dati utente autenticati e non autenticati. Prima di unire i set di dati, assicurati di rispettare le leggi e le normative applicabili, incluso l’ottenimento delle autorizzazioni necessarie per l’utente finale.

## Limitazioni 

>[!IMPORTANT]
>
>Tieni presente che qualsiasi modifica allo schema del set di dati dell’evento globale deve essere applicata anche nel nuovo schema del set di dati uniti, altrimenti interromperà il set di dati uniti.
>
>Inoltre, se rimuovi il set di dati di origine, il set di dati uniti non elabora più i dati e viene rimosso dal sistema.

Cross-Channel Analytics è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata.

* Le attuali funzionalità di rekeying sono limitate a un solo passaggio (ID persistente a ID transitorio). La reimpostazione in più passaggi (ad esempio, ID persistente in un ID transitorio e quindi in un altro ID transitorio) non è supportata.
* Sono supportati solo i set di dati evento. Altri set di dati, come i set di dati di ricerca, non sono supportati.
* Le mappe ID personalizzate utilizzate nell&#39;organizzazione non sono supportate.
* Il grafico Co-op di Adobe e il grafico Private non sono supportati.
* Cross-Channel Analytics non trasforma in alcun modo il campo utilizzato per l’unione. L’unione basata sui campi utilizza il valore nel campo specificato così come esiste nel set di dati non uniti all’interno del data lake. Il processo di creazione dei punti distingue tra maiuscole e minuscole. Ad esempio, se a volte nel campo viene visualizzata la parola “Bob” e a volte viene visualizzata la parola “BOB”, queste verranno trattate come due persone separate.
* Dato che l’unione basata sui campi distingue tra maiuscole e minuscole per i set di dati di Analytics generati tramite il connettore origine di Analytics, Adobe consiglia di rivedere eventuali regole VISTA o regole di elaborazione applicabili al campo ID transitorio per assicurarsi che nessuna di queste regole introduca nuove forme dello stesso ID. Ad esempio, assicurati che le regole VISTA o di elaborazione non introducano lettere minuscole nel campo ID transitorio solo per una parte degli eventi.
* L’unione basata sui campi non combina o concatena i campi.
* Il campo ID transitorio deve contenere un singolo tipo di ID (cioè ID da un singolo spazio dei nomi). Ad esempio, il campo ID transitorio non deve contenere una combinazione di ID di accesso e ID e-mail.
* Se si verificano più eventi con la stessa marca temporale per lo stesso ID persistente, ma con valori diversi nel campo ID transitorio, l’unione basata sui campi sceglierà in base all’ordine alfabetico. Quindi, se l’ID persistente A ha due eventi con la stessa marca temporale e uno degli eventi specifica Bob e l’altro specifica Ann, l’unione basata sul campo sceglierà Ann.
* Cross-Channel Analytics tiene traccia di ogni valore ID persistente per 1 anno (TTL = 1 anno). Se un dispositivo non ha attività per più di un anno e riavvia l’attività, i nuovi eventi saranno associati a una persona anonima fino a quando l’utente non viene nuovamente identificato (ad esempio tramite un nuovo accesso).
* Se un dispositivo è condiviso da più persone e il numero totale di transizioni tra gli utenti supera i 50.000, CCA non unisce più i dati per quel dispositivo.


## Abilitare Cross-Channel Analytics

Quando l’organizzazione soddisfa tutti i prerequisiti e ne comprende i limiti, puoi seguire questi passaggi per iniziare a utilizzarla in CJA.

1. Importa i dati desiderati in Adobe Experience Platform. Consulta [Creare uno schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) e [Inserire dati](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=it) nella documentazione di Adobe Experience Platform.
1. Contatta l’Assistenza clienti di Adobe con le seguenti informazioni:
   * Richiesta per abilitare Cross-Channel Analytics
   * ID set di dati per il set di dati da ridigitare
   * Nome della colonna dell’ID persistente per il set di dati desiderato (identificatore visualizzato su ogni riga)
   * Nome della colonna dell’ID transitorio per il set di dati desiderato (collegamento dell’identificatore della persona tra i set di dati)
   * Preferenza di [ripetizione](replay.md) frequenza e lunghezza del lookback. Le opzioni includono una ripetizione una volta alla settimana con un intervallo di lookback di 7 giorni, o una ripetizione ogni giorno con un intervallo di lookback di 1 giorno
   * Nome della sandbox.
1. Dopo aver ricevuto la richiesta, l’Assistenza clienti Adobe collabora con i tecnici Adobe per abilitare Cross-Channel Analytics. Una volta abilitato, in Adobe Experience Platform compare un nuovo set di dati ridigitato contenente una nuova colonna ID persona. L’Assistenza clienti Adobe può fornire il nuovo ID set di dati e il nome della colonna ID persona.
1. Quando è attivato per la prima volta, Adobe fornisce la compilazione dei dati uniti che risale all’inizio del mese precedente (fino a 60 giorni). Per eseguire questa compilazione, l’ID transitorio deve esistere nei dati non uniti che risalgono al periodo precedente.
1. [Crea una connessione](../create-connection.md) in CJA utilizzando il set di dati appena generato e tutti gli altri set di dati che desideri includere. Scegli l’ID persona corretto per ogni set di dati.
1. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) in base alla connessione.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una volta configurata la visualizzazione dati, Analysis in CJA è esattamente come qualsiasi altra analisi in CJA, tranne per il fatto che ora i dati funzionano tra canali e dispositivi.
