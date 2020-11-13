---
title: Panoramica di Analytics tra canali
description: Ri-chiave gli ID visitatore da più set di dati per unire i visitatori.
translation-type: tm+mt
source-git-commit: b57895d037f8db3ffc418312b95fc43dd0280dc9
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 14%

---


# Panoramica di Analytics tra canali

**IQ viaggio: Analisi** tra canali una funzione che consente di ri-chiave dell&#39;ID persona di un dataset, consentendo una combinazione perfetta di più set di dati. CCA controlla i dati utente provenienti da sessioni autenticate e non autenticate per generare un ID unito. Utilizzando l&#39;analisi tra canali, potete rispondere a domande come:

* Quante persone iniziano la loro esperienza in un canale, poi la finiscono in un altro?
* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando si combinano set di dati con ID di persona simili, l&#39;attribuzione viene trasferita su dispositivi e canali. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L&#39;utente ha un problema con l&#39;ordine, quindi il team di assistenza clienti riceve una chiamata per risolverlo. Con Analytics tra canali, puoi attribuire gli eventi call center all’annuncio che avevano originariamente fatto clic.

## Prerequisiti

>[!IMPORTANT]
>
>Se non vengono soddisfatti tutti i prerequisiti, potrebbe non essere possibile creare una connessione CCA o risultati negativi durante la combinazione di set di dati.

Prima di utilizzare l&#39;analisi tra canali, accertatevi che l&#39;organizzazione sia preparata con i seguenti elementi:

* Un dataset in Adobe Experience Platform deve avere due colonne che aiutano a identificare i visitatori:
   * Un **ID persistente**, un identificatore presente su ogni riga. Ad esempio, un ID visitatore generato da una libreria  Adobe Analytics AppMeasurement.
   * Un **ID transitorio**, un identificatore presente solo su alcune righe. Ad esempio, un nome utente o un indirizzo e-mail con hash quando un visitatore si autentica. Puoi utilizzare praticamente qualsiasi identificatore che desideri, purché sia presente almeno una volta sullo stesso evento di un determinato ID persistente.
* Un altro dataset, come i dati del call center, che contiene un ID transitorio su ogni riga. Questo ID persona deve essere formattato in modo simile all’ID transitorio nell’altro set di dati.
* Questa funzione consente di unire set di dati che possono includere l&#39;unione di dati utente autenticati e non autenticati. Prima di unire i set di dati, accertatevi di rispettare le leggi e le normative applicabili, compreso il recupero delle autorizzazioni necessarie per l&#39;utente finale.

## Limitazioni

Analytics tra canali è una funzione innovativa e affidabile, ma presenta dei limiti sulle modalità di utilizzo.

* Le attuali capacità di rekeying sono limitate a un solo passaggio (ID persistente a ID transitorio). Non è supportata la reimpostazione in più passaggi (ad esempio, ID persistente per un ID transitorio e quindi per un altro ID transitorio).
* Sono supportati solo i set di dati evento. Altri set di dati, ad esempio set di dati di ricerca, non sono supportati.
* Le mappe ID personalizzate utilizzate nella tua organizzazione non sono supportate.
* Il grafico Co-op  Adobe e il grafico Privato non sono supportati.

## Abilita analisi tra canali

Una volta che l&#39;organizzazione soddisfa tutti i prerequisiti e ne ha compreso i limiti, potete seguire questi passaggi per iniziare a usarla in CJA.

1. Importa i dati desiderati in Adobe Experience Platform. Consultate [Creare uno schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html) e [Assimilare i dati](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) nella documentazione di Adobe Experience Platform.
1. Contatta il tuo Account Manager  Adobe che include quanto segue:
   * Richiesta per abilitare l&#39;analisi tra canali
   * L&#39;ID del set di dati per il set di dati da rechiave
   * Il nome della colonna dell&#39;ID persistente per il set di dati desiderato (Identificatore che viene visualizzato su ogni riga)
   * Il nome della colonna dell&#39;ID transitorio per il set di dati desiderato (il collegamento dell&#39;identificatore persona tra i set di dati)
   * La vostra preferenza per [riprodurre ](replay.md) la frequenza e la lunghezza di lookback. Le opzioni includono una riproduzione una volta alla settimana con una finestra di lookback di 7 giorni, o una ripetizione ogni giorno con una finestra di lookback di 1 giorno.
1. L&#39;Account Manager  Adobe consente l&#39;analisi tra canali al ricevimento della richiesta. Una volta attivato, in Adobe Experience Platform viene visualizzato un nuovo set di dati a chiave contenente una nuova colonna ID persona. Il responsabile dell&#39;account  Adobe può fornire il nuovo ID dataset e il nome della colonna ID persona.
1. [Create una ](../create-connection.md) connessione in CJA utilizzando il set di dati appena generato e qualsiasi altro set di dati da includere. Scegliete l’ID persona corretto per ogni set di dati.
1. [Crea una ](/help/data-views/create-dataview.md) visualizzazione dati in base alla connessione.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una volta impostata la visualizzazione dei dati, l&#39;analisi in CJA è come qualsiasi altra analisi nella CJA, eccetto ora i dati funzionano tra canali e dispositivi.
