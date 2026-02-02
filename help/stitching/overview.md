---
title: Panoramica sull’unione delle identità
description: Scopri i concetti, i vantaggi, i prerequisiti e le limitazioni dell’unione di identità.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 71%

---

# Panoramica sull’unione delle identità

>[!NOTE]
>
>Per utilizzare le funzionalità descritte in questa sezione, è necessario disporre del pacchetto Customer Journey Analytics **Select** o versione successiva (per [unione basata sui campi](fbs.md)) o del pacchetto Customer Journey Analytics **Prime** o versione successiva (per [unione basata sui grafici](gbs.md)). In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

L’unione delle identità è una funzione potente che migliora l’idoneità di un set di dati evento per l’analisi cross-channel. L’analisi cross-channel è un caso d’uso principale che può essere gestito da Customer Journey Analytics. Questa funzione ti consente di combinare ed eseguire rapporti in modo semplice su più set di dati da canali diversi, in base a un identificatore comune (ID persona).

Quando combini set di dati con ID persona simili, l’attribuzione viene trasferita su dispositivi e canali diversi. Ad esempio, un utente visita il sito tramite un annuncio sul computer desktop. L’utente acquista un prodotto ma poi incontra un problema con l’ordine. Quindi l’utente invia una chiamata al team del servizio clienti per aiutarlo a risolverlo. Con l’analisi cross-channel puoi attribuire gli eventi call center all’annuncio su cui l&#39;utente ha fatto clic originariamente.

Sfortunatamente, non tutti i set di dati basati su eventi che fanno parte della connessione in Customer Journey Analytics dispongono di dati sufficienti per supportare questa attribuzione predefinita. In particolare, i set di dati delle esperienze basate su web o dispositivi mobili spesso non dispongono di informazioni sull’ID effettivo di una persona per tutti gli eventi.

L’unione ricalcola le identità all’interno delle righe di un set di dati per garantire che l’ID persona (ID unione) sia disponibile su ogni evento. Durante l’unione delle identità, vengono esaminati i dati utente provenienti da sessioni autenticate e non autenticate per determinare il valore dell’ID persona comune che può essere utilizzato come ID unito. Questa reimpostazione delle chiavi risolve diversi record in un singolo ID unito per l’analisi a livello di persona, anziché a livello di dispositivo o cookie.

Customer Journey Analytics supporta due tipi di unione delle identità: [unione basata sui campi](fbs.md) e [unione basata sui grafi](gbs.md).

## Prerequisiti

>[!IMPORTANT]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di condurre una corretta analisi cross-channel.

Prima di utilizzare l’unione delle identità, assicurati che la tua organizzazione sia preparata con quanto segue:

- L’unione delle identità include l’unione di dati utente autenticati e non autenticati. Prima di attivare l’unione su un set di dati evento, assicurati di rispettare le leggi e le normative applicabili, incluso l’ottenimento delle autorizzazioni necessarie per l’utente finale.

- Importa i dati desiderati in Adobe Experience Platform:

   - Per i dati di Adobe Analytics, consulta [Utilizzo dei dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Per altri tipi di dati, consulta [Creare uno schema](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/create-schema-ui) e [Acquisire i dati](https://experienceleague.adobe.com/it/docs/experience-platform/ingestion/home) nella documentazione di Adobe Experience Platform.

Per trarre vantaggio dall’analisi cross-channel, è necessario combinare uno o più set di dati con unione delle identità con altri set di dati (ad esempio, con i dati del call center) durante la definizione della connessione Customer Journey Analytics. La configurazione della connessione presuppone che gli altri set di dati contengano già un ID persona su ogni riga, simile all’ID di unione.

## Abilitare l’unione delle identità

Le unioni delle identità possono essere abilitate in due modi:

- [Richiesta di abilitare l&#39;unione](/help/stitching/use-stitching.md) (obsoleto). Una volta approvato, viene creato un set di dati duplicato per il set di dati per il quale è stata richiesta l’unione. Questo set di dati duplicato contiene una colonna aggiuntiva con l’identificatore unito. Per utilizzare i dati uniti in Customer Journey Analytics, è necessario creare una nuova connessione o modificare una connessione esistente che includa il set di dati uniti.
- [Abilitare l&#39;unione nell&#39;interfaccia Connessioni](/help/stitching/use-stitching-ui.md). Quando configuri l’unione per un set di dati nell’interfaccia Connessioni, l’unione si verifica all’istante durante l’acquisizione di dati da tale set di dati in Customer Journey Analytics.

## Limitazioni

L’unione delle identità è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata.

- Sono supportati solo i set di dati evento. Altri set di dati, come i set di dati di ricerca, non sono supportati.
- L’unione delle identità non trasforma in alcun modo il campo utilizzato per l’unione. L’unione delle identità utilizza il valore nel campo specificato così come esiste nel set di dati non uniti all’interno del data lake.
- Il processo di unione delle identità distingue tra maiuscole e minuscole. Ad esempio, i valori di identità `Bob` e `BOB` vengono trattati come due persone separate.

Assicurati di non confondere l’unione delle identità con:

- L’unione di due o più set di dati. L’unione delle identità si applica a un solo set di dati. L’unione di più set di dati si verifica in seguito alla configurazione di una connessione Customer Journey Analytics e alla selezione dello stesso ID persona nei set di dati selezionati nella connessione.

- L’unione di due set di dati. L’unione di due set di dati viene spesso utilizzata per ricerche o classificazioni in Analysis Workspace. L’unione delle identità utilizzi questa stessa funzionalità, ma con un processo che va oltre la semplice unione.


## Set di dati di Journey Optimizer

L’unione supporta i seguenti set di dati di Journey Optimizer generati automaticamente:

- Eventi passaggio percorso AJO
- Set di dati evento di attività in entrata AJO
- Set di dati di superfici AJO
- Set di dati evento di feedback messaggi di AJO* Set di dati evento esperienza di tracciamento push di AJO
- Set di dati evento esperienza di tracciamento e-mail AJO
- Set di dati evento di feedback BBC di AJO
- Set di dati evento di feedback attività live di AJO
- Set di dati evento di decisione ExD di AJO

>[!MORELIKETHIS]
>
>[Unione delle identità basata sui campi](fbs.md)
>[Unione delle identità basata su grafo](gbs.md)
>[Utilizzare l’unione delle identità](use-stitching.md)
>[Convalidare l’unione delle identità](validate.md)
>[Domande frequenti sull’unione delle identità](faq.md)

