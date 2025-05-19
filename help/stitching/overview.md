---
title: Panoramica sull’unione
description: Panoramica di unione
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 1a697ce0372d1cb544940778850714a198a000ec
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 15%

---

# Panoramica sull’unione

>[!NOTE]
>
>Per utilizzare le funzionalità descritte in questa sezione, è necessario disporre del pacchetto **Select** o versione successiva (per [unione basata sui campi](fbs.md)) o del pacchetto **Prime** o versione successiva (per [unione basata sui grafici](gbs.md)). In caso di dubbi sul pacchetto di Customer Journey Analytics di cui disponi, contatta l’amministratore.

L’unione di identità (o semplicemente unione) è una funzione potente che eleva l’idoneità di un set di dati evento per l’analisi cross-channel. L’analisi cross-channel è un caso d’uso principale che Customer Journey Analytics può gestire e che consente di combinare ed eseguire rapporti in modo semplice su più set di dati da canali diversi, in base a un identificatore comune (ID persona).

Quando combini set di dati con ID persona simili, l’attribuzione viene riportata su dispositivi e canali diversi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente incontra un problema con il proprio ordine, quindi invia al team di assistenza clienti una chiamata per aiutarti a risolverlo. Con l’analisi cross-channel, puoi attribuire gli eventi del call center all’annuncio su cui hanno fatto clic originariamente.

Sfortunatamente, non tutti i set di dati basati su eventi che fanno parte della connessione in Customer Journey Analytics sono sufficientemente compilati con dati per supportare questa attribuzione pronta all’uso. In particolare, i set di dati di esperienza basati su web o dispositivi mobili spesso non dispongono di un ID persona effettivo disponibile su tutti gli eventi.

L’unione consente di reimpostare le identità all’interno delle righe di un set di dati, assicurandosi che l’ID persona (ID unione) sia disponibile su ogni evento. L’unione esamina i dati utente provenienti da sessioni autenticate e non autenticate per determinare il valore ID transitorio comune (ID persona) che può essere utilizzato come ID unione. Questa reimpostazione consente di risolvere record diversi in un singolo ID unito per l’analisi a livello di persona, anziché a livello di dispositivo o cookie.

Customer Journey Analytics supporta due tipi di unione: [unione basata sui campi](fbs.md) e [unione basata sui grafici](gbs.md).

## Prerequisiti

>[!IMPORTANT]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di condurre correttamente l’analisi cross-channel.

Prima di utilizzare le unioni, assicurati che l’organizzazione sia preparata con quanto segue:

- L’unione include l’unione di dati utente autenticati e non autenticati. Prima di attivare l’unione su un set di dati evento, assicurati di rispettare le leggi e le normative applicabili, incluso l’ottenimento delle autorizzazioni necessarie per l’utente finale. Consulta [Definire i campi di identità nell’interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity) per ulteriori informazioni.

- Importa i dati desiderati in Adobe Experience Platform:

   - Per i dati di Adobe Analytics, vedi [Utilizzo dei dati della suite di rapporti di Adobe Analytics in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Per altri tipi di dati, consulta la sezione [Creare uno schema](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/create-schema-ui) e [Inserire i dati](https://experienceleague.adobe.com/it/docs/experience-platform/ingestion/home) nella documentazione di Adobe Experience Platform.

Puoi trarre vantaggio dall’analisi cross-channel se combini uno o più set di dati uniti con altri set di dati, come i dati del call center, nell’ambito della definizione della connessione Customer Journey Analytics. Questa configurazione della connessione presuppone che gli altri set di dati contengano già un ID persona su ogni riga, simile all’ID unito.


## Limitazioni

>[!IMPORTANT]
>
>
>- Applica le modifiche apportate allo schema del set di dati dell’evento di origine anche al nuovo schema del set di dati uniti, altrimenti interrompe il set di dati uniti.
>
>- Se rimuovi il set di dati di origine, il set di dati uniti non elabora più i dati e viene rimosso dal sistema.
>
>- Le etichette di utilizzo dei dati non vengono propagate automaticamente allo schema del set di dati uniti. Se hai applicato le etichette di utilizzo dei dati allo schema del set di dati di origine, devi applicarle manualmente allo schema del set di dati uniti. Per ulteriori informazioni, vedere [Gestione delle etichette di utilizzo dei dati in Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview).

L’unione è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata.

- Sono supportati solo i set di dati evento. Altri set di dati, come i set di dati di ricerca, non sono supportati.
- L’unione non trasforma in alcun modo il campo utilizzato per l’unione. L’unione utilizza il valore nel campo specificato così come esiste nel set di dati non uniti all’interno del data lake.
- Il processo di unione distingue tra maiuscole e minuscole. Ad esempio, se a volte nel campo viene visualizzata la parola &quot;Bob&quot; e a volte viene visualizzata la parola &quot;BOB&quot;, questi ID vengono trattati come due persone separate.

Assicurati di non confondere l’unione con:

- Unione di due o più set di dati. L’unione si applica solo a un set di dati. L’unione di set di dati si verifica in seguito alla configurazione di una connessione Customer Journey Analytics e alla selezione dello stesso ID persona nei set di dati selezionati nella connessione.

- Unione di due set di dati. In Customer Journey Analytics, un join viene spesso utilizzato per ricerche o classificazioni in Analysis Workspace. Sebbene l’unione utilizzi la funzionalità di unione, il processo stesso non coinvolge solo i join.

>[!MORELIKETHIS]
>
>[Unione basata sui campi](fbs.md)
>[Unione basata su grafico](gbs.md)
>[Usa unione](use-stitching.md)
>[Convalida unione](validate.md)
>[Domande frequenti sull&#39;unione](faq.md)

