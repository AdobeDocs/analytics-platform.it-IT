---
title: Panoramica sull’unione delle identità
description: Panoramica dell’unione delle identità
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 9774e0e3af024823a03dbcd8d6766877f55e95d8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 93%

---

# Panoramica sull’unione delle identità

>[!NOTE]
>
>Per utilizzare le funzionalità descritte in questa sezione, devi disporre del pacchetto **Select** o superiore (per [unione basata sui campi](fbs.md)) o del pacchetto **Prime** o superiore (per [unione basata sui grafi](gbs.md)). In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

L’unione delle identità è una funzione potente che migliora l’idoneità di un set di dati evento per l’analisi cross-channel. L’analisi cross-channel è un caso d’uso principale che Customer Journey Analytics può gestire e consente di combinare ed eseguire facilmente rapporti su più set di dati da canali diversi, basati su un identificatore comune (ID persona).

Quando combini set di dati con ID persona simili, l’attribuzione viene riportata su dispositivi e canali diversi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente incontra un problema con il proprio ordine, quindi invia al team di assistenza clienti una chiamata per aiutarti a risolverlo. Con l’analisi cross-channel puoi attribuire gli eventi call center all’annuncio su cui è stato fatto clic originariamente.

Sfortunatamente, non tutti i set di dati basati su eventi che fanno parte della connessione in Customer Journey Analytics hanno dati a sufficienza per supportare questa attribuzione così come viene fornita dalla soluzione. In particolare, i set di dati di esperienze basati su web o dispositivi mobili spesso non dispongono di informazioni sull’ID effettivo di una persona per tutti gli eventi.

L’unione delle identità consente di reimpostare le identità all’interno delle righe di un set di dati, in modo che l’ID persona (ID di unione) sia disponibile per ogni evento. Durante l’unione delle identità, vengono esaminati i dati utente provenienti da sessioni autenticate e non autenticate per determinare il valore dell’ID transitorio comune (ID persona) che può essere utilizzato come ID di unione. Questa reimpostazione consente di risolvere record diversi con un singolo ID di unione per l’analisi a livello di persona anziché a livello di dispositivo o cookie.

Customer Journey Analytics supporta due tipi di unione delle identità: [unione basata sui campi](fbs.md) e [unione basata sui grafi](gbs.md).

## Prerequisiti

>[!IMPORTANT]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di condurre una corretta analisi cross-channel.

Prima di utilizzare l’unione delle identità, assicurati che la tua organizzazione sia preparata con quanto segue:

- L’unione delle identità include l’unione di dati utente autenticati e non autenticati. Prima di attivare l’unione delle identità per un set di dati evento, assicurati di rispettare le leggi e normative applicabili, incluso l’ottenimento delle autorizzazioni necessarie per l’utente finale. Per ulteriori informazioni, consulta [Definire i campi di identità nell’interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity).

- Importa i dati desiderati in Adobe Experience Platform:

   - Per i dati di Adobe Analytics, consulta [Utilizzo dei dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Per altri tipi di dati, consulta [Creare uno schema](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/create-schema-ui) e [Acquisire i dati](https://experienceleague.adobe.com/it/docs/experience-platform/ingestion/home) nella documentazione di Adobe Experience Platform.

Per trarre vantaggio dall’analisi cross-channel, è necessario combinare uno o più set di dati con unione delle identità con altri set di dati (ad esempio, con i dati del call center) durante la definizione della connessione Customer Journey Analytics. La configurazione della connessione presuppone che gli altri set di dati contengano già un ID persona su ogni riga, simile all’ID di unione.


## Limitazioni

>[!IMPORTANT]
>
>
>- Applica eventuali modifiche apportate allo schema del set di dati evento di origine anche al nuovo schema del set di dati con unione delle identità.
>
>- Se rimuovi il set di dati di origine, il set di dati con unione delle identità non può più essere elaborato e viene rimosso dal sistema.
>
>- Le etichette di utilizzo dei dati non vengono propagate automaticamente allo schema del set di dati con unione delle identità. Se hai applicato delle etichette di utilizzo dei dati allo schema del set di dati di origine, devi applicarle manualmente anche allo schema del set di dati con unione delle identità. Per ulteriori informazioni, consulta [Gestione delle etichette di utilizzo dei dati in Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview).

L’unione delle identità è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata.

- Sono supportati solo i set di dati evento. Altri set di dati, come i set di dati di ricerca, non sono supportati.
- L’unione delle identità non trasforma in alcun modo il campo utilizzato per l’unione. L’unione delle identità utilizza il valore nel campo specificato così come esiste nel set di dati non uniti all’interno del data lake.
- Il processo di unione delle identità distingue tra maiuscole e minuscole. Ad esempio, se nel campo è presente a volte “Bob” e altre volte “BOB”, questi ID verranno trattati come due persone separate.

Assicurati di non confondere l’unione delle identità con:

- L’unione di due o più set di dati. L’unione delle identità si applica a un solo set di dati. L’unione di più set di dati si verifica in seguito alla configurazione di una connessione Customer Journey Analytics e alla selezione dello stesso ID persona nei set di dati selezionati nella connessione.

- L’unione di due set di dati. L’unione di due set di dati viene spesso utilizzata per ricerche o classificazioni in Analysis Workspace. L’unione delle identità utilizzi questa stessa funzionalità, ma con un processo che va oltre la semplice unione.


## Set di dati di Journey Optimizer

L’unione supporta i seguenti set di dati di Journey Optimizer generati automaticamente:

- Eventi dei passaggi del Percorso di AJO
- Set di dati evento attività in entrata AJO
- Set di dati superfici AJO
- Set di dati evento feedback messaggi AJO* Tracciamento push AJO Set di dati evento esperienza
- Set di dati evento esperienza di tracciamento e-mail AJO
- Set di dati evento feedback Ccn AJO
- Set di dati evento feedback attività AJO Live
- Set di dati evento decisione ExD AJO

>[!MORELIKETHIS]
>
>[Unione delle identità basata sui campi](fbs.md)
>&#x200B;>[Unione delle identità basata sui grafi](gbs.md)
>&#x200B;>[Utilizzare l’unione delle identità](use-stitching.md)
>&#x200B;>[Convalidare l’unione delle identità](validate.md)
>&#x200B;>[Domande frequenti sull’unione delle identità](faq.md)

