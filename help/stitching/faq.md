---
title: Domande frequenti sull’unione delle identità
description: Scopri le domande frequenti sull’unione.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 332c9240399e429d971855ab1aa685bd4d07b86e
workflow-type: tm+mt
source-wordcount: '2149'
ht-degree: 84%

---

# Domande frequenti

Di seguito sono riportate alcune domande frequenti sull’unione delle identità:

## Spostarsi tra i canali

+++ Come posso usare l’unione delle identità per scoprire come le persone si spostano da un canale all’altro?

Puoi utilizzare una visualizzazione Flusso con la dimensione ID set di dati.

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e crea un progetto Workspace vuoto.
2. Seleziona la scheda **[!UICONTROL ** Visualizzazioni **]** a sinistra e trascina una visualizzazione **[!UICONTROL **&#x200B; Flusso &#x200B;**]** sull’area di lavoro a destra.
3. Seleziona la scheda **[!UICONTROL ** Componenti **]** a sinistra e trascina la dimensione **[!UICONTROL ** ID set di dati **]** nella posizione centrale denominata **[!UICONTROL **&#x200B; Dimensione o elemento &#x200B;**]**.
4. Questo rapporto di flusso è interattivo. Per espandere i flussi alle pagine successive o precedenti, seleziona uno qualsiasi dei valori. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

Se desideri rinominare gli elementi dimensione ID set di dati, puoi utilizzare un set di dati di ricerca.

+++

## Ripetizione

+++ Quanto indietro nel tempo vanno i profili di ripetizione dell’unione delle identità?

L’intervallo di lookback per la reimpostazione dipende dalla frequenza di ripetizione dei dati desiderata. Ad esempio, se imposti l’unione delle identità perché ripeta i dati una volta alla settimana, l’intervallo di lookback per la reimpostazione è di sette giorni. Se imposti l’unione delle identità perché ripeta i dati ogni giorno, l’intervallo di lookback per la reimpostazione è di un giorno.

+++

## Dispositivi condivisi

+++ Come vengono gestiti i dispositivi condivisi?

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Alcuni esempi includono un dispositivo condiviso a casa, PC condivisi in una biblioteca o un chiosco in un punto vendita.

L’ID persona sostituisce l’ID persistente, pertanto i dispositivi condivisi vengono considerati persone separate, anche se provengono dallo stesso dispositivo.

Per ulteriori dettagli, consulta il caso d’uso [Dispositivi condivisi](/help/use-cases/stitching/shared-devices.md).

+++

## Molti ID persistenti

+++ In che modo l’unione delle identità gestisce le situazioni in cui una singola persona dispone di molti ID persistenti?

In alcune situazioni, un singolo utente può essere associato a più ID persistenti. Un esempio è dato da una persona che cancella frequentemente i cookie del browser o utilizza la modalità privata/in incognito del browser.

Per l’unione delle identità basata sui campi, il numero di ID persistenti è irrilevante a favore dell’ID persona. Un singolo utente può appartenere a un numero qualsiasi di dispositivi senza influire sulla capacità di Customer Journey Analytics di eseguire l’unione delle identità tra dispositivi diversi.

Per le unioni basate su grafico, una singola persona può avere molti ID persistenti nel grafico delle identità. L’unione delle identità basata su grafo utilizza l’ID persistente basato sullo spazio dei nomi specificato. Se ci sono più ID persistenti per lo stesso spazio dei nomi, viene utilizzato il primo ID persistente lessicografico.

+++

## Processo di unione delle identità

+++ Una volta contattato il mio team Adobe Account con le informazioni desiderate, quanto tempo ci vuole per rendere disponibile il set di dati reimpostato?

L’unione delle identità live è disponibile circa una settimana dopo l’abilitazione dell’unione delle identità da parte di Adobe. La disponibilità del backfill dipende dalla quantità di dati esistenti. I set di dati di piccole dimensioni (meno di 1 milione di eventi al giorno) in genere richiedono un paio di giorni, mentre i set di dati di grandi dimensioni (1 miliardo di eventi al giorno) possono richiedere una settimana o più.

+++

## Cross-device analytics rispetto all’analisi cross-channel

+++ Qual è la differenza tra cross-device analytics (una funzione nella versione tradizionale di Analytics) e l’analisi cross-channel?

[Cross-device analytics](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview) è una funzione specifica della versione tradizionale di Adobe Analytics che consente di comprendere il modo in cui le persone operano tra i dispositivi. Offre due flussi di lavoro per collegare i dati dei dispositivi: unione basata sui campi e grafo dei dispositivi.

L’analisi cross-channel è una funzione specifica di Customer Journey Analytics che consente di comprendere il modo in cui le persone operano sia sui dispositivi che sui canali. Unisce le identità di un ID persona di un set di dati, consentendo di combinare facilmente quest’ultimo con altri set di dati. Questa funzione opera in modo simile all’unione delle identità basata sui campi di Cross-Device Analytics, anche se l’implementazione è diversa a causa della diversa architettura dei dati tra Analytics e Customer Journey Analytics. Per ulteriori informazioni, consulta [Unione delle identità](overview.md) e il caso d’uso [Analisi cross-channel](../use-cases/cross-channel/cross-channel.md).

+++

## Privacy

+++ In che modo l’unione delle identità gestisce le richieste di privacy?

Adobe gestisce le richieste di privacy in conformità alle leggi locali e internazionali applicabili. Adobe offre [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/it/docs/experience-platform/privacy/home) per inviare richieste di accesso e cancellazione dei dati. Le richieste si applicano sia ai set di dati originali che a quelli reimpostati.

>[!IMPORTANT]
>
>Il processo di annullamento unione delle identità, come parte delle richieste di privacy, cambia all’inizio del 2025. Il processo di annullamento unione delle identità corrente riunisce gli eventi utilizzando la versione più recente delle identità note. Questa riassegnazione degli eventi a un’altra identità potrebbe comportare conseguenze legali indesiderate. Per risolvere questi problemi, a partire dal 2025 il nuovo processo di annullamento dell’unione delle identità aggiorna gli eventi oggetto della richiesta di privacy con l’ID persistente.
> 

Ai fini illustrativi, immagina i seguenti dati per le identità, gli eventi prima e dopo l’unione delle identità.

| Mappa delle identità | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ECID | Roberto | CustID |
|  | 2 | ts2 | 123 | ECID | Alessandro | CustID |


| Set di dati degli eventi | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| | 2 | ts1 | 123 | ECID | Roberto | CustID |
| | 3 | ts2 | 123 | ECID | Alessandro | CustID |


| Set di dati di unione identità | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona | ID risultante | spazio dei nomi di unione identità |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | Roberto | CustID |
| | 2 | ts1 | 123 | ECID | Roberto | CustID | Roberto | CustID |
| | 3 | ts2 | 123 | ECID | Alessandro | CustID | Alessandro | CustID |


**Processo corrente per le richieste di privacy**

Quando viene ricevuta una richiesta di privacy per un cliente con CustID Roberto, le righe contenenti voci barrate vengono eliminate. Gli altri eventi vengono riuniti utilizzando la mappa delle identità. Ad esempio, il primo ID di unione identità nel set di dati di unione identità è aggiornato con **Alessandro**.

| Mappa delle identità | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Roberto~~ | ~~CustID~~ |
|  | 2 | ts2 | 123 | ECID | Alessandro | CustID |


| Set di dati degli eventi | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Roberto~~ | ~~CustID~~ |
| | 3 | ts2 | 123 | ECID | Alessandro | CustID |


| Set di dati di unione identità | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona | ID risultante | spazio dei nomi di unione identità |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | **Alessandro** | CustID |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Roberto~~ | ~~CustID~~ | ~~Roberto~~ | ~~CustID~~ |
| | 3 | ts2 | 123 | ECID | Alessandro | CustID | Alessandro | CustID |


**Nuovo processo per la richiesta di privacy**

Quando viene ricevuta una richiesta di privacy per un cliente con CustID Roberto, le righe contenenti voci barrate vengono eliminate. Gli altri eventi vengono riuniti utilizzando l’ID persistente. Ad esempio, il primo ID di unione identità nel set di dati di unione identità è aggiornato con **123**.

| Mappa delle identità | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Roberto~~ | ~~CustID~~ |
|  | 2 | ts2 | 123 | ECID | Alessandro | CustID |


| Set di dati degli eventi | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Roberto~~ | ~~CustID~~ |
| | 3 | ts2 | 123 | ECID | Alessandro | CustID |


| Set di dati di unione identità | ID | marca temporale | ID persistente | spazio dei nomi persistente | ID persona | spazio dei nomi persona | ID risultante | spazio dei nomi di unione identità |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ECID | | | **123** | ECID |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ECID~~ | ~~Roberto~~ | ~~CustID~~ | ~~Roberto~~ | ~~CustID~~ |
| | 3 | ts2 | 123 | ECID | Alessandro | CustID | Alessandro | CustID |

+++

## Valori ID persistente vuoti

+++ Cosa succede se il campo ID persistente in uno o più eventi è vuoto?

Se il campo ID persistente è vuoto in un evento in un set di dati unito, l’ID risultante per tale evento viene determinato in uno dei due modi seguenti:

* Se il campo ID persona non è vuoto, Customer Journey Analytics utilizza il valore in ID persona come ID risultante.
* Se il campo ID persona è vuoto, Customer Journey Analytics lascia vuoto anche l’ID risultante. In questo caso, l’ID persistente, l’ID persona e l’ID risultante sono tutti vuoti nell’evento. Questi tipi di eventi vengono eliminati da qualsiasi connessione Customer Journey Analytics che utilizza il set di dati unito in cui l’ID risultante è stato scelto come ID persona.

+++


## Valori ID persona non definiti

+++ Cosa succede se il campo ID persona in uno o più eventi dispone di valori segnaposto come `Undefined`?

Presta attenzione alla “compressione persona” che si verifica quando l’unione delle identità viene applicata a dati che utilizzano valori segnaposto per ID transitori. Nella tabella di esempio seguente, gli ID persona non definiti provenienti da un set di dati originato da un sistema CRM vengono compilati con il valore “Non definito”, dando luogo a una rappresentazione errata delle persone.

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio | ID risultante (dopo la ripetizione) |
|---|---|---|---|---|
| 1 | 12/05/2023 12:01 | 123 | - | **Corrado** |
| 2 | 12/05/2023 12:02 | 123 | Corrado | **Corrado** |
| 3 | 12/05/2023 12:03 | 456 | Non definito | **Non definito** |
| 4 | 12/05/2023 12:04 | 456 | - | **Non definito** |
| 5 | 12/05/2023 12:05 | 789 | Non definito | **Non definito** |
| 6 | 12/05/2023 12:06 | 012 | Non definito | **Non definito** |
| 7 | 12/05/2023 12:07 | 012 | - | **Non definito** |
| 8 | 12/05/2023 12:03 | 789 | Non definito | **Non definito** |
| 9 | 12/05/2023 12:09 | 456 | - | **Non definito** |
| 10 | 12/05/2023 12:02 | 123 | - | **Corrado** |
| | | **4 dispositivi** | **2 persone**:<br/>eventi 1, 4, 7, 9, 10 rilasciati | **2 persone**:<br/>Corrado, non autenticato (compresso a una persona) |

+++

## Confronto delle metriche

+++ Come si confrontano le metriche nei set di dati di unione identità di Customer Journey Analytics con le metriche simili nei set di dati di identità non unite di Customer Journey Analytics e con Adobe Analytics?

Alcune metriche in Customer Journey Analytics sono simili alle metriche in Analytics, mentre altre sono piuttosto diverse, a seconda del confronto. La tabella seguente confronta diverse metriche comuni:

| **Dati uniti di Customer Journey Analytics** | **Dati non uniti di Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Persone** = numero di ID persona distinti in cui l&#39;ID risultante viene scelto come ID persona. **Persone** può essere superiore o inferiore a **Visitatori univoci** in Adobe Analytics tradizionale, a seconda del risultato del processo di unione delle identità. | **Persone** = numero di ID persona distinti in base alla colonna selezionata come ID persona. **Persone** nei set di dati del connettore di origine di Analytics è simile a **Visitatori univoci** in Adobe Analytics tradizionale se `endUserIDs._experience.aaid.id` viene utilizzato come ID persona in Customer Journey Analytics. | **Visitatori univoci** = numero di ID visitatore distinti. Il numero di **Visitatori univoci** potrebbe essere diverso dal conteggio di valori **ECID** distinti. | Consulta [Persone](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/people). |
| **Sessioni**: definite in base alle impostazioni di sessione nella visualizzazione dati di Customer Journey Analytics. Il processo di unione può combinare sessioni singole da più dispositivi in una singola sessione. | **Sessioni**: definite in base alle impostazioni di sessione specificate nella visualizzazione dati di Customer Journey Analytics. | **Visite**: consulta [Visite](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/visits). | **Visite**: definito in base alle impostazioni di sessione specificate nella [suite di rapporti virtuali CDA](https://experienceleague.adobe.com/en/docs/analytics/components/cda/setup). |
| **Eventi** = numero di righe nei dati uniti in Customer Journey Analytics. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Tieni presente, tuttavia, le domande frequenti di cui sopra relative alle righe con un ID persistente vuoto. | **Eventi** = numero di righe nei dati non uniti in Customer Journey Analytics. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Tieni presente, tuttavia, che se uno qualsiasi degli eventi dispone di un ID persona vuoto nei dati di identità non unite nel data lake di Experience Platform, questi eventi non vengono inclusi in Customer Journey Analytics. | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences). | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences). |

Altre metriche possono essere simili in Customer Journey Analytics e in Adobe Analytics. Ad esempio, il numero totale degli [eventi personalizzati](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/custom-events) 1-100 di Adobe Analytics in genere è comparabile in Adobe Analytics tradizionale e in Customer Journey Analytics (identità uniti o non unite). Le [differenze di funzionalità](/help/getting-started/aa-vs-cja/cja-aa.md), ad esempio la deduplicazione degli eventi tra Customer Journey Analytics e Adobe Analytics, possono causare discrepanze tra i due prodotti.

+++

## Mappa delle identità

+++ Customer Journey Analytics può utilizzare i campi della mappa delle identità?

Sì, Customer Journey Analytics può utilizzare i campi della mappa delle identità per l’unione delle identità [basata sui campi](/help/stitching/fbs.md#identitymap) e [basata su grafo](/help/stitching/gbs.md#identitymap).

+++

## Passare all’unione delle identità basata su grafo

+++ Sarà necessario riacquisire i dati per passare dall’unione delle identità basata sui campi all’unione delle identità basata su grafo?

Non è necessario riacquisire i dati in Experience Platform. Tuttavia, i dati devono essere riconfigurati in Customer Journey Analytics. Segui questi passaggi:

1. Imposta il nuovo set di dati di unione delle identità basata su grafo utilizzando l’unione delle identità basata su grafo.
1. Crea una nuova connessione temporanea con un intervallo di tempo molto ridotto per i dati.
1. Configura il nuovo set di dati basato su grafo come parte di questa connessione temporanea.
1. Con questa nuova connessione temporanea verifica se l’unione delle identità basata su grafo funziona correttamente.
1. Se l’unione delle identità basata su grafo funziona come previsto, richiedi una retrocompilazione aggiuntiva per il set di dati basato su grafo, quindi sostituisci il set di dati basato sui campi nella connessione originale con il nuovo set di dati basato su grafo.
1. Rimuovi la connessione temporanea.

+++

## Interruzioni nel reporting

+++ I rapporti esistenti verrebbero interrotti?

No, se segui i passaggi descritti in precedenza. In caso contrario, chiedi supporto aggiuntivo ad Adobe Consulting.

+++

## Abilitare un set di dati per Identity Service

+++ Come abilitare un set di dati solo per Identity Service? 

Assicurati che sia abilitato un set di dati affinché il servizio Identity possa utilizzarlo nell’unione basata su grafico.

Non devi disporre della licenza per Real-Time Customer Data Platform per utilizzare l’unione delle identità basata su grafo. L’unione delle identità basata su grafo si basa su un grafo identità disponibile e non sui profili cliente in tempo reale.

Per verificare un set di dati esistente e abilitare il set di dati solo per Identity Service, utilizza una richiesta `PATCH` all&#39;endpoint `/datasets` che utilizza solo il tag `unifiedIdentity`. Ad esempio:

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedIdentity", "value": ["enabled:true"] }
      ]'
```

Qualsiasi utilizzo del tag `unifiedProfile` nella richiesta, anche se non disponi della licenza per Real-Time Customer Data Profile, restituisce un errore.

Per ulteriori informazioni, consulta [Creare un set di dati abilitato per profilo e identità](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset).

+++ 


## Valori dello spazio dei nomi uniti

+++ Perché i valori dello spazio dei nomi uniti non sempre corrispondono al valore dello spazio dei nomi dell’identità che potresti utilizzare all’interno di un altro set di dati all’interno della connessione CJA?

Per impostazione predefinita, i valori dello spazio dei nomi uniti sono minuscoli. `custEmail` diventa `custemail`. Se si dispone di un altro set di dati con valore dello spazio dei nomi dell&#39;identità `custEmail`, i due valori non corrispondono. Per ovviare a questo comportamento nei rapporti, puoi utilizzare la funzione del campo derivato [lowercase()](/help/data-views/derived-fields/derived-fields.md#lowercase) per far corrispondere i valori dello spazio dei nomi delle identità.

+++
