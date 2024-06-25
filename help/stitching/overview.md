---
title: Panoramica sull’unione
description: Panoramica sull’unione.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 83e568d686a541bb6472a33dc0a7400cf6e8de2a
workflow-type: tm+mt
source-wordcount: '3712'
ht-degree: 11%

---

# Unione

{{select-package}}

L’unione di identità (o semplicemente unione) è una funzione potente che eleva l’idoneità di un set di dati evento per l’analisi cross-channel. L’analisi cross-channel è un caso d’uso principale che il Customer Journey Analytics può gestire e consente di combinare ed eseguire rapporti in modo semplice su più set di dati da canali diversi, in base a un identificatore comune (ID persona).

Quando combini set di dati con ID persona simili, l’attribuzione viene riportata su dispositivi e canali diversi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente incontra un problema con il proprio ordine, quindi invia al team di assistenza clienti una chiamata per aiutarti a risolverlo. Con l’analisi cross-channel, puoi attribuire gli eventi del call center all’annuncio su cui hanno fatto clic originariamente.

Sfortunatamente, non tutti i set di dati basati su eventi che fanno parte della connessione nel Customer Journey Analytics sono sufficientemente compilati con dati per supportare questa attribuzione pronta all’uso. In particolare, i set di dati di esperienza basati su web o dispositivi mobili spesso non dispongono di un ID persona effettivo disponibile su tutti gli eventi.

L’unione consente di reimpostare le identità all’interno delle righe di un set di dati, assicurandosi che l’ID persona (ID unione) sia disponibile su ogni evento. L’unione esamina i dati utente provenienti da sessioni autenticate e non autenticate per determinare il valore ID transitorio comune (ID persona) che può essere utilizzato come ID unione. Questa reimpostazione consente di risolvere record diversi in un singolo ID unito per l’analisi a livello di persona, anziché a livello di dispositivo o cookie.

Il Customer Journey Analytics supporta due tipi di unione: unione basata sui campi e unione basata sui grafici.

## Prerequisiti

>[!IMPORTANT]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di condurre correttamente l’analisi cross-channel.

Prima di utilizzare le unioni, assicurati che l’organizzazione sia preparata con quanto segue:

- L’unione include l’unione di dati utente autenticati e non autenticati. Prima di attivare l’unione su un set di dati evento, assicurati di rispettare le leggi e le normative applicabili, incluso l’ottenimento delle autorizzazioni necessarie per l’utente finale. Consulta [Definire i campi di identità nell’interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity) per ulteriori informazioni.

- Importa i dati desiderati in Adobe Experience Platform:

   - Per i dati di Adobe Analytics, consulta [Utilizzo dei dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Per altri tipi di dati, consulta la sezione [Creare uno schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) e [Inserire i dati](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) nella documentazione di Adobe Experience Platform.

Puoi trarre vantaggio dall’analisi cross-channel se combini uno o più set di dati uniti con altri set di dati, come i dati del call center, nell’ambito della definizione della connessione di Customer Journey Analytics. Questa configurazione della connessione presuppone che gli altri set di dati contengano già un ID persona su ogni riga, simile all’ID unito.


## Limitazioni

>[!IMPORTANT]
>
>- Nessun supporto per l’utilizzo di `identityMap` come ID persistente. Devi definire un identificatore specifico nel set di dati (ad esempio, `ECID`) come ID persistente.
>
>- Applica le modifiche apportate allo schema del set di dati dell’evento di origine anche al nuovo schema del set di dati uniti, altrimenti interrompe il set di dati uniti.
>
>- Se rimuovi il set di dati di origine, il set di dati uniti non elabora più i dati e viene rimosso dal sistema.
>
>- Le etichette di utilizzo dei dati non vengono propagate automaticamente allo schema del set di dati uniti. Se hai applicato le etichette di utilizzo dei dati allo schema del set di dati di origine, devi applicarle manualmente allo schema del set di dati uniti. Consulta [Gestione delle etichette di utilizzo dei dati in Experienci Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) per ulteriori informazioni.

L’unione è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata.

- Sono supportati solo i set di dati evento. Altri set di dati, come i set di dati di ricerca, non sono supportati.
- L’unione non trasforma in alcun modo il campo utilizzato per l’unione. L’unione utilizza il valore nel campo specificato così come esiste nel set di dati non uniti all’interno del data lake.
- Il processo di unione distingue tra maiuscole e minuscole. Ad esempio, se a volte nel campo viene visualizzata la parola &quot;Bob&quot; e a volte viene visualizzata la parola &quot;BOB&quot;, questi ID vengono trattati come due persone separate.

Assicurati di non confondere l’unione con:

- Unione di due o più set di dati. L’unione si applica solo a un set di dati. L’unione di set di dati si verifica in seguito alla configurazione di una connessione di Customer Journey Analytics e alla selezione dello stesso ID persona nei set di dati selezionati nella connessione.

- Unione di due set di dati. In Customer Journey Analytics, un join viene spesso utilizzato per ricerche o classificazioni in Analysis Workspace. Sebbene l’unione utilizzi la funzionalità di unione, il processo stesso non coinvolge solo i join.


## Unione basata sui campi

Specifica un set di dati evento, nonché l’ID persistente (cookie) e l’ID transitorio (ID persona) per quel set di dati. L’unione basata sui campi crea una nuova colonna ID unita nel nuovo set di dati uniti e aggiorna questa colonna ID unita in base alle righe che hanno un ID transitorio per quello specifico ID persistente. <br/>È possibile utilizzare l’unione basata sui campi quando si utilizza il Customer Journey Analytics come soluzione indipendente (senza avere accesso al servizio Experienci Platform Identity e al grafo delle identità associato). Oppure, quando non desideri utilizzare il grafico delle identità disponibile.

![Unione basata sui campi](/help/stitching/assets/fbs.png)

### Funzionamento dell’unione basata sui campi

L’unione esegue almeno due passaggi sui dati in un determinato set di dati.

- **Unione live**: tenta di unire ogni hit (evento) nel momento in cui arriva. Gli hit da dispositivi che sono &quot;nuovi&quot; al set di dati (non sono mai stati autenticati) in genere non vengono uniti a questo livello. Gli hit da dispositivi già riconosciuti vengono uniti immediatamente.

- **Ripeti unione**: &quot;riproduce&quot; i dati in base a identificatori univoci (ID transitori) appresi. In questa fase vengono uniti gli hit da dispositivi precedentemente sconosciuti (ID persistenti) (a ID transitori). Adobe offre due intervalli di ripetizione:
   - **Giornaliero**: i dati vengono riprodotti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le ripetizioni sono molto più frequenti, ma i visitatori non autenticati devono autenticarsi lo stesso giorno in cui visitano il sito.
   - **Ogni settimana**: i dati vengono ripetuti una volta alla settimana con l’intervallo di lookback selezionato (consulta [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di una settimana non vengono rielaborati fino alla successiva riproduzione settimanale.

- **Privacy**: quando vengono ricevute richieste relative alla privacy, oltre a rimuovere l’identità richiesta, qualsiasi unione di tale identità tra eventi non autenticati deve essere annullata.

I dati oltre l’intervallo di lookback non vengono riprodotti. Un visitatore deve effettuare l’autenticazione all’interno di un intervallo di lookback specificato affinché una visita non autenticata e una visita autenticata siano identificate insieme. Una volta riconosciuto, il dispositivo è live stitched da quel momento in poi.

#### Passaggio 1: live stitching

L’unione live tenta di unire ogni evento al momento della raccolta su dispositivi e canali noti.

+++ Dettagli

Prendi in considerazione l’esempio seguente, in cui Bob registra eventi diversi come parte di un set di dati evento.

*Dati visualizzati il giorno in cui vengono raccolti:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 dispositivi** | | **4 persone**:<br/>`246`, `Bob`, `3579`, `81911` |

Gli eventi non autenticati e autenticati sui nuovi dispositivi vengono conteggiati come persone separate (temporaneamente). Gli eventi non autenticati sui dispositivi riconosciuti sono live stitched.

L’attribuzione funziona quando la variabile personalizzata di identificazione è associata a un dispositivo. Nell’esempio precedente, tutti gli eventi ad eccezione di 1, 8, 9 e 10 sono live stitched (utilizzano tutti `Bob` identificatore). L’unione live &quot;risolve&quot; l’ID unione per gli eventi 4, 6 e 12.

I dati ritardati (dati con una marca temporale di oltre 24 ore) vengono gestiti in base al massimo impegno, dando priorità all’unione dei dati correnti per ottenere la massima qualità.

+++

#### Passaggio 2: ripetere l’unione

A intervalli regolari (una volta alla settimana o una volta al giorno, a seconda dell’intervallo di lookback scelto), la ripetizione dell’unione ricalcola i dati storici in base ai dispositivi riconosciuti. Se un dispositivo invia inizialmente i dati mentre non è autenticato e poi effettua l’accesso, la ripetizione dell’unione collega tali eventi non autenticati alla persona corretta.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra numeri diversi in base alla ripetizione dei dati.

*Gli stessi dati dopo la ripetizione:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) | ID unione (dopo la riproduzione) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Freccia su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Freccia su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 dispositivi** | | **4 persone**:<br/>`246`, `Bob`, `3579`, `81911` | **2 persone**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

L’attribuzione funziona quando la variabile personalizzata di identificazione è associata a un dispositivo. Nell’esempio precedente, l’evento 1 e 10 vengono uniti in seguito alla ripetizione, lasciando separati solo gli eventi 8 e 9. E riducendo la metrica delle persone (cumulativa) a 2.

+++

#### Passaggio 3: richiesta di accesso a dati personali

Quando ricevi una richiesta di accesso a dati personali, l’ID unione viene eliminato in tutti i record relativi all’oggetto della richiesta di accesso a dati personali.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra l’effetto che una richiesta di privacy per Bob ha sui dati dopo l’elaborazione. Le righe in cui Bob è autenticato vengono rimosse (2, 3, 5, 7 e 11) insieme alla rimozione di Bob come ID transitorio per altre righe.

*Gli stessi dati dopo una richiesta di privacy per Bob:*

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo unione live) | ID unione (dopo la riproduzione) | ID transitorio (ID accesso) | ID unione (dopo la richiesta di privacy) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Freccia su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Freccia a destra](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Freccia giù](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Freccia su](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 dispositivi** | | **4 persone**:<br/>246 `Bob`, `3579`, `81911` | **2 persone**:<br/>Bob, `3579` |  | **3 persone**:<br/>`246`, `3579`, `81911` |

+++

### Prerequisiti

I seguenti prerequisiti si applicano in modo specifico all’unione basata sui campi:

- Il set di dati dell’evento in Adobe Experience Platform, a cui desideri applicare l’unione, deve avere due colonne che aiutino a identificare i visitatori:

   - A **ID persistente**, un identificatore disponibile su ogni riga. Ad esempio, un ID visitatore generato da una libreria di AppMeasurement Adobe Analytics o un ECID generato dal servizio Adobe Experience Cloud Identity.
   - A **ID transitorio**, un identificatore disponibile solo su alcune righe. Ad esempio, un nome utente o un indirizzo e-mail con hash quando un visitatore si autentica. Puoi utilizzare virtualmente qualsiasi identificatore che ti piace. L’unione considera questo campo come contenente le informazioni dell’ID persona effettivo. Per risultati di unione migliori, un ID transitorio deve essere inviato all’interno degli eventi del set di dati almeno una volta per ogni ID persistente. Se prevedi di includere questo set di dati all’interno di una connessione di Customer Journey Analytics, è preferibile che anche gli altri set di dati abbiano un identificatore comune simile.

- Entrambe le colonne (ID persistente e ID transitorio) devono essere definite come un campo di identità con uno spazio dei nomi identità nello schema per il set di dati da unire. Quando si utilizza l’unione di identità in Real-time Customer Data Platform, utilizzando [`identityMap` gruppo di campi](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), è comunque necessario aggiungere campi di identità con uno spazio dei nomi di identità. Questa identificazione dei campi di identità è necessaria in quanto l’unione di Customer Journey Analytics non supporta `identityMap` gruppo di campi. Quando si aggiunge un campo di identità nello schema, utilizzando anche `identityMap` gruppo di campi, non impostare il campo di identità aggiuntivo come identità primaria. L&#39;impostazione di un campo di identità aggiuntivo come identità primaria interferisce con `identityMap` gruppo di campi utilizzato per Real-time Customer Data Platform.

### Limitazioni

Le seguenti limitazioni si applicano in modo specifico all’unione basata sui campi:

- Le attuali funzionalità di rekeying sono limitate a un solo passaggio (ID persistente a ID transitorio). La reimpostazione in più passaggi (ad esempio, ID persistente in un ID transitorio e quindi in un altro ID transitorio) non è supportata.
- Se un dispositivo è condiviso da più persone e il numero totale di transizioni tra gli utenti supera le 50.000, il Customer Journey Analytics non unisce più i dati per tale dispositivo.
- Le mappe ID personalizzate utilizzate nell’organizzazione non sono supportate.
- L’unione distingue tra maiuscole e minuscole. Per i set di dati generati tramite il connettore di origine di Analytics, l’Adobe consiglia di rivedere eventuali regole VISTA o regole di elaborazione applicabili al campo ID transitorio. Questa revisione assicura che nessuna di queste regole introduca nuove forme dello stesso ID. Ad esempio, assicurati che le regole VISTA o di elaborazione non introducano lettere minuscole nel campo ID transitorio solo per una parte degli eventi.
- L’unione non combina o concatena i campi.
- Il campo ID transitorio deve contenere un singolo tipo di ID (ID da un singolo spazio dei nomi). Ad esempio, il campo ID transitorio non deve contenere una combinazione di ID di accesso e ID e-mail.
- Se si verificano più eventi con la stessa marca temporale per lo stesso ID persistente, ma con valori diversi nel campo ID transitorio, l’unione seleziona l’ID in base all’ordine alfabetico. Quindi, se l’ID persistente A ha due eventi con la stessa marca temporale e uno degli eventi specifica Bob e l’altro specifica Ann, l’unione seleziona Ann.
- Presta attenzione agli scenari in cui gli ID transitori contengono valori segnaposto, ad esempio `Undefined`. Consulta la [Domande frequenti](faq.md) per ulteriori informazioni.


## Unione basata su grafico

Specifica un set di dati evento, nonché l’ID persistente (cookie) e lo spazio dei nomi dell’ID transitorio (ID persona) per tale set di dati. L’unione basata su grafico crea una nuova colonna per l’ID unione nel nuovo set di dati uniti. Quindi utilizza l’ID persistente per eseguire query sul grafo delle identità dal servizio Identity di Experienci Platform, utilizzando lo spazio dei nomi specificato, per aggiornare l’ID unito.

![Unione basata su grafico](/help/stitching/assets/gbs.png)

### Funzionamento dell’unione basata su grafico

L’unione esegue almeno due passaggi sui dati in un determinato set di dati.

- **Unione live**: tenta di unire ogni hit (evento) nel momento in cui arriva, utilizzando l’ID persistente per cercare l’id transitorio per lo spazio dei nomi selezionato eseguendo una query sul grafico delle identità. Se l’ID transitorio è disponibile dalla ricerca, viene immediatamente unito.

- **Ripeti unione**: &quot;riproduce&quot; i dati in base alle identità aggiornate dal grafico delle identità. In questa fase, gli hit da dispositivi precedentemente sconosciuti (ID persistenti) vengono uniti in quanto il grafo delle identità ha risolto l’identità per uno spazio dei nomi. Adobe offre due intervalli di ripetizione:
   - **Giornaliero**: i dati vengono riprodotti ogni giorno con un intervallo di lookback di 24 ore. Questa opzione offre un vantaggio in quanto le ripetizioni sono molto più frequenti, ma i visitatori non autenticati devono autenticarsi lo stesso giorno in cui visitano il sito.
   - **Ogni settimana**: i dati vengono ripetuti una volta alla settimana con l’intervallo di lookback (consulta [opzioni](#options)). Questa opzione offre un vantaggio che consente alle sessioni non autenticate un tempo di autenticazione molto più lungo. Tuttavia, i dati non uniti che hanno meno di una settimana non vengono rielaborati fino alla successiva riproduzione settimanale.

- **Privacy**: quando vengono ricevute richieste relative alla privacy, oltre a rimuovere l’identità richiesta dal set di dati di origine, è necessario annullare eventuali unioni di tale identità tra eventi non autenticati. Inoltre, l’identità deve essere rimossa dal grafo delle identità per evitare future unioni basate su grafo per tale identità specifica.

I dati oltre l’intervallo di lookback non vengono riprodotti. Un visitatore deve effettuare l’autenticazione all’interno di un intervallo di lookback specificato affinché una visita non autenticata e una visita autenticata siano identificate insieme. Una volta riconosciuto, il dispositivo è live stitched da quel momento in poi.

Considera i due grafici di identità seguenti per l’ID persistente `246` e `3579`, come questi grafici di identità vengono aggiornati nel tempo e come questi aggiornamenti influiscono sui passaggi nell’unione basata su grafico.

![Grafico identità 246](assets/identity-graph-246.svg)
![Grafico identità 3579](assets/identity-graph-3579.svg)

Puoi visualizzare un grafico delle identità nel tempo per un profilo specifico utilizzando [Visualizzatore grafico identità](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Vedi anche [Logica di collegamento del servizio Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) per comprendere meglio la logica utilizzata per collegare le identità.

#### Passaggio 1: live stitching

L’unione live tenta di unire ogni evento, al momento della raccolta, alle informazioni note in quel momento provenienti dal grafico delle identità.

+++ Dettagli

| | Tempo | ID persistente<br/>`ECID` | Namespace<br/>`Email` ![Grafico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID unione (dopo unione live) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non definito* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non definito* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Puoi vedere come viene risolto l’ID unione per ogni evento. In base al tempo, all’ID persistente e alla ricerca del grafico delle identità per lo spazio dei nomi specificato (nello stesso momento).
Quando la ricerca viene risolta in più di un ID unito (come per l’evento 7), viene selezionato il primo ID lessicografico restituito dal grafo delle identità (`a.b@yahoo.co.uk` nell&#39;esempio).

+++

#### Passaggio 2: ripetere l’unione

A intervalli regolari (in base all’intervallo di lookback scelto), l’unione ripetuta ricalcola i dati storici in base alla versione più recente del grafico delle identità, al momento dell’intervallo.

+++ Dettagli

Con un’unione di ripetizione che si verifica alle 16:30 del 2023-05-13, con una configurazione dell’intervallo di lookback di 24 ore, alcuni eventi dell’esempio vengono ricollegati (indicati da ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Tempo | ID persistente<br/>`ECID` | Namespace<br/>`Email` ![Grafico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID unione<br/>(dopo unione live) | ID unione<br/>(dopo la riproduzione 24 ore) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Con la ripetizione dell’unione che si verifica alle 16:30 23-05-13, con una configurazione dell’intervallo di lookback di 7 giorni, tutti gli eventi dell’esempio vengono ricollegati.


| | Tempo | ID persistente<br/>`ECID` | Namespace<br/>`Email` ![Grafico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID unione<br/>(dopo unione live) | ID unione<br/>(dopo la ripetizione 7 giorni) |
|---|---|---|---|---|---|
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *non definito* | `246` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Riproduci](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

#### Passaggio 3: richiesta di accesso a dati personali

Quando ricevi una richiesta di accesso a dati personali, l’ID unione viene eliminato in tutti i record relativi all’oggetto della richiesta di accesso a dati personali.

+++ Dettagli

La tabella seguente rappresenta gli stessi dati di cui sopra, ma mostra l’effetto che ha una richiesta di accesso a dati personali (ad esempio alle 18:00 del 5 maggio 2023) per gli eventi di esempio.

| | Tempo | ID persistente<br/>`ECID` | Namespace<br/>`Email` ![Grafico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID unione (dopo la richiesta di privacy) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246`  ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246`  ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246`  ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

### Prerequisiti

I seguenti prerequisiti si applicano in modo specifico all’unione basata su grafico:

- Il set di dati evento in Adobe Experience Platform, a cui desideri applicare l’unione, deve avere una colonna che identifica un visitatore su ogni riga, la **ID persistente**. Ad esempio, un ID visitatore generato da una libreria di AppMeasurement Adobe Analytics o un ECID generato dal servizio Adobe Experience Cloud Identity.
- il grafo delle identità di Experience Cloud Identity Service deve contenere uno spazio dei nomi (ad esempio `Email`, o `Phone`) da utilizzare durante l&#39;unione per risolvere **ID transitorio**. Consulta [Servizio Experienci Platform Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home) per ulteriori informazioni.


### Limitazioni

Le seguenti limitazioni si applicano in modo specifico all’unione basata su grafico:

- Le marche temporali non vengono prese in considerazione quando si esegue una query per l’ID transitorio utilizzando lo spazio dei nomi specificato. Pertanto, è possibile che un ID persistente sia unito a un ID transitorio di un record che ha una marca temporale precedente.
- Nessun supporto per dispositivi condivisi. Quando vengono restituite più identità, eseguendo una query sul grafico delle identità utilizzando uno spazio dei nomi, viene utilizzata la prima identità lessicografica.
- Esiste un limite rigido di tre mesi per la retrocompilazione delle identità nel grafico delle identità. Puoi utilizzare le identità di backfill nel caso in cui non utilizzi un’applicazione di Experience Platform, come Real-time Customer Data Platform, per compilare il grafico delle identità.
- Il [Guardrail del servizio Identity](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) applica. Vedi, ad esempio, quanto segue [limiti statici](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Numero massimo di identità in un grafico: 50.
   - Numero massimo di collegamenti a un’identità per una singola acquisizione batch: 50.
   - Numero massimo di identità in un record XDM per l’acquisizione del grafico: 20.
   - Numero minimo di identità in un record XDM per l’acquisizione del grafico: 2.


## Utilizzare l’unione

Una volta che la tua organizzazione avrà raggiunto tutti [prerequisiti](#prerequisites) e comprende le [limitazioni](#limitations) e metodo di unione specifico ([basato sul campo](#limitations-1) e [basato su grafico](#limitations-2)), puoi seguire questi passaggi per iniziare a utilizzare l’unione nel Customer Journey Analytics.

### Opzioni

Selezionate le opzioni per l&#39;unione. Il pacchetto Customer Journey Analytics determina le opzioni disponibili per la durata della retrocompilazione iniziale, l’intervallo di lookback, la frequenza di ripetizione e il numero massimo di set di dati consentiti per l’unione.

| | Customer Journey Analytics<br/>Seleziona | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Durata retrocompilazione unione una tantum | 13 mesi | 13 mesi | 25 mesi |
| Intervallo di lookback e frequenza di ripetizione | <li>1 giorno, ogni giorno</li><li>fino a 7 giorni, settimanalmente</li> | <li>1 giorno, ogni giorno</li><li>fino a 14 giorni, settimanalmente</li> | <li>1 giorno, ogni giorno</li><li>fino a 30 giorni, settimanalmente</li> |
| Numero massimo di set di dati consentiti per l’unione | 5 | 10 | 15 |

### Richiedi supporto

1. Contatta l’Assistenza clienti di Adobe con le seguenti informazioni:

   - Richiesta per abilitare l’unione.
   - ID del set di dati per il set di dati da reimpostare.
   - Il nome della colonna (percorso identità e spazio dei nomi) dell’ID persistente per il set di dati desiderato (l’identificatore visualizzato su ogni riga).
   - Per l’unione basata sui campi, il nome della colonna dell’ID transitorio per il set di dati desiderato (l’identificatore della persona, che funge anche da collegamento tra i set di dati nel contesto di una connessione). Per l’unione basata su grafico, lo spazio dei nomi delle identità da utilizzare per eseguire query sul grafo delle identità.
   - Preferenza di intervallo di lookback e frequenza di ripetizione. Consulta il pacchetto di Customer Journey Analytics per [opzioni](#options) disponibile.
   - Nome della sandbox.


2. L’Assistenza clienti Adobe collabora con il team di progettazione Adobe per abilitare l’unione dopo la ricezione della richiesta. Una volta abilitato, in Adobe Experience Platform viene visualizzato un nuovo set di dati reimpostato contenente una nuova colonna ID unita. L’Assistenza clienti Adobe può fornire l’ID del nuovo set di dati.

3. Quando è attivato per la prima volta, Adobe fornisce la retrocompilazione dei dati uniti. Consulta il pacchetto di Customer Journey Analytics per [opzione](#options) disponibile.

4. Se desideri utilizzare il nuovo set di dati uniti in un’analisi cross-channel, devi aggiungere il nuovo set di dati uniti a un [connessione](../connections/overview.md) nel Customer Journey Analytics. Quindi aggiungi tutti gli altri set di dati necessari per l’analisi cross-channel e seleziona l’ID persona corretto per ciascun set di dati.

5. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) in base alla connessione.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una volta configurata la visualizzazione dati, puoi eseguire l’analisi dei rapporti di Customer Journey Analytics su canali e dispositivi diversi.

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

