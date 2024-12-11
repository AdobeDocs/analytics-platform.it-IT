---
title: Domande frequenti sull’unione
description: Domande frequenti sull’unione
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: ae0e7a906700522d7babc1d573a0b4cdbf1be6fc
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 27%

---

# Domande frequenti

Di seguito sono riportate alcune domande frequenti sull’unione:

## Spostarsi tra i canali

+++ Come posso utilizzare l’unione per vedere come le persone si spostano da un canale all’altro?

Puoi utilizzare una visualizzazione Flusso con la dimensione ID set di dati.

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e crea un progetto Workspace vuoto.
2. Seleziona la scheda **[!UICONTROL ** Visualizzazioni **]** a sinistra e trascina una visualizzazione **[!UICONTROL ** Flusso **]** nell&#39;area di lavoro a destra.
3. Seleziona la scheda **[!UICONTROL ** Componenti **]** a sinistra e trascina la dimensione **[!UICONTROL ** ID set di dati **]** nella posizione centrale con etichetta **[!UICONTROL ** Dimension o elemento **]**.
4. Questo rapporto di flusso è interattivo. Per espandere i flussi alle pagine successive o precedenti, selezionare uno qualsiasi dei valori. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

Se desideri rinominare gli elementi dimensione ID set di dati, puoi utilizzare un set di dati di ricerca.

+++

### Riproduci

+++ Quanto indietro nel tempo va l’unione dei visitatori di ripetizione?

L’intervallo di lookback per la rekeying dipende dalla frequenza di dati ripetizione desiderata. Ad esempio, se imposti l’unione per riprodurre i dati una volta alla settimana, l’intervallo di lookback per la reimpostazione delle chiavi è di sette giorni. Se imposti l’unione per riprodurre i dati ogni giorno, l’intervallo di lookback per la reimpostazione delle chiavi è di un giorno.

+++

## Dispositivi condivisi

+++ Come vengono gestiti i dispositivi condivisi?

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Ad esempio, un dispositivo condiviso da casa, PC condivisi in una libreria o un chiosco in un punto vendita.

L’ID transitorio sostituisce l’ID persistente, pertanto i dispositivi condivisi vengono considerati persone separate (anche se provengono dallo stesso dispositivo).

+++

## Molti ID persistenti

+++ In che modo l’unione gestisce le situazioni in cui una singola persona dispone di più ID persistenti?

In alcune situazioni, un singolo utente può essere associato a più ID persistenti. Un esempio è la cancellazione frequente dei cookie del browser o l’utilizzo della modalità privata/in incognito del browser.

Per l’unione basata sui campi, il numero di ID persistenti è irrilevante a favore dell’ID transitorio. Un singolo utente può appartenere a qualsiasi numero di dispositivi senza influire sulla capacità di Customer Journey Analytics di eseguire unioni tra dispositivi.

Per l’unione basata su grafico, una singola persona può avere molti ID persistenti nel grafico delle identità. L’unione basata su grafico utilizza l’ID persistente basato sullo spazio dei nomi specificato. Se per lo stesso spazio dei nomi sono presenti più ID persistenti, viene utilizzato il primo ID persistente lessicografico.

+++

## Processo di unione

+++ Una volta contattato il mio team Adobe Account con le informazioni desiderate, quanto tempo ci vuole per rendere disponibile il set di dati reimpostato?

L’unione live è disponibile circa una settimana dopo l’attivazione di Adobe. La disponibilità del backfill dipende dalla quantità di dati esistenti. I set di dati di piccole dimensioni (meno di 1 milione di eventi al giorno) in genere richiedono un paio di giorni, mentre i set di dati di grandi dimensioni (1 miliardo di eventi al giorno) possono richiedere una settimana o più.

+++

## Analisi cross-device e cross-channel

+++ Qual è la differenza tra l’analisi cross-device (una funzione nella versione tradizionale di Analytics) e l’analisi cross-channel?

[Analisi cross-device](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it) è una funzionalità specifica della versione tradizionale di Adobe Analytics che consente di comprendere il modo in cui le persone operano tra i dispositivi. Offre due flussi di lavoro per collegare i dati dei dispositivi: unione basata sui campi e grafico dei dispositivi.

L’analisi cross-channel è un caso di utilizzo specifico del Customer Journey Analytics che consente di comprendere il modo in cui le persone operano sia sui dispositivi che sui canali. Unisce l’ID persona di un set di dati, consentendo di combinare facilmente tale set di dati con altri set di dati. Questa funzione opera in modo simile all’unione basata sui campi di analisi cross-device, ma l’implementazione è diversa a causa della diversa architettura dei dati tra Analytics tradizionale e Customer Journey Analytics. Per ulteriori informazioni, vedi [Stitching](overview.md) e il caso di utilizzo [Cross-Channel Analysis](../use-cases/cross-channel/cross-channel.md).

+++

## Privacy

+++ In che modo Stitching gestisce le richieste di privacy?

Adobe gestisce le richieste di accesso ai dati personali in conformità alle leggi locali e internazionali. Adobe offre [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) per inviare richieste di accesso e cancellazione dei dati. Le richieste si applicano sia ai set di dati originali che a quelli reimpostati.

>[!IMPORTANT]
>
>Il processo di separazione, come parte delle richieste di accesso a dati personali, cambia all’inizio del 2025. Il processo di rimozione delle unioni corrente riavvia gli eventi utilizzando la versione più recente delle identità note. Questa riassegnazione degli eventi a un’altra identità potrebbe avere conseguenze legali indesiderate. Per risolvere questi problemi, a partire dal 2025 il nuovo processo di rimozione delle unioni aggiorna gli eventi che sono oggetto della richiesta di privacy con l’ID persistente.
> 

Per illustrare, immagina i seguenti dati per le identità, gli eventi prima e dopo l’unione.

| Mappa delle identità | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Set di dati degli eventi | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Set di dati uniti | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio | ID unione | Spazio dei nomi unito |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Processo corrente per la richiesta di accesso a dati personali**

Quando viene ricevuta una richiesta di accesso a dati personali per un cliente con CustID Bob, le righe contenenti voci barrate vengono eliminate. Altri eventi vengono ripristinati utilizzando la mappa delle identità. Ad esempio, il primo ID unito nel set di dati unito è aggiornato a **Alex**.

| Mappa delle identità | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio |
|:---:|---|---|---|---|---|---|
| ![EliminaStruttura](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~IDCust~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Set di dati degli eventi | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![EliminaStruttura](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~IDCust~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Set di dati uniti | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio | ID unione | Spazio dei nomi unito |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![EliminaStruttura](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~IDCust~~ | ~~Bob~~ | ~~IDCust~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Nuovo processo per la richiesta di accesso a dati personali**

Quando viene ricevuta una richiesta di accesso a dati personali per un cliente con CustID Bob, le righe contenenti voci barrate vengono eliminate. Altri eventi vengono ricomposti utilizzando l’ID persistente. Ad esempio, il primo ID unito nel set di dati unito è stato aggiornato a **123**.

| Mappa delle identità | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio |
|:---:|---|---|---|---|---|---|
| ![EliminaStruttura](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~IDCust~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Set di dati degli eventi | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![EliminaStruttura](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~IDCust~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Set di dati uniti | ID | timestamp | ID persistente | spazio dei nomi persistente | id transitorio | spazio dei nomi transitorio | ID unione | Spazio dei nomi unito |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![EliminaStruttura](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~IDCust~~ | ~~Bob~~ | ~~IDCust~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Valori ID persistenti vuoti

+++ Cosa succede se il campo ID persistente in uno o più eventi è vuoto?

Se il campo ID persistente è vuoto in un evento in un set di dati unito, l’ID unito per tale evento in viene determinato in uno dei due modi seguenti:

* Se il campo ID transitorio non è vuoto, il Customer Journey Analytics utilizza il valore in ID transitorio come ID unito.
* Se il campo ID transitorio è vuoto, anche Customer Journey Analytics lascia vuoto l’ID unione. In questo caso, ID persistente, ID transitorio e ID vincolato sono tutti vuoti durante l’evento. Questi tipi di eventi vengono eliminati da qualsiasi connessione di Customer Journey Analytics che utilizza il set di dati unito in cui l’ID unito è stato scelto come ID persona.

+++


## Valori ID transitori non definiti

+++ Cosa succede se il campo ID transitorio in uno o più eventi contiene valori segnaposto, come `Undefined`?

Presta attenzione alla &quot;compressione della persona&quot; che si verifica quando l’unione viene applicata a dati che utilizzano valori segnaposto per ID transitori. Nella tabella di esempio seguente, gli ID persona non definiti provenienti da un set di dati originato da un sistema di gestione delle relazioni con i clienti vengono compilati con il valore &quot;Non definito&quot;, dando luogo a una rappresentazione errata delle persone.

| Evento | Marca temporale | ID persistente (ID cookie) | ID transitorio (ID accesso) | ID unione (dopo la riproduzione) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | Non definito | **Non definito** |
| 4 | 2023-05-12 12:04 | 456 | - | **Non definito** |
| 5 | 2023-05-12 12:05 | 789 | Non definito | **Non definito** |
| 6 | 2023-05-12 12:06 | 012 | Non definito | **Non definito** |
| 7 | 2023-05-12 12:07 | 012 | - | **Non definito** |
| 8 | 2023-05-12 12:03 | 789 | Non definito | **Non definito** |
| 9 | 2023-05-12 12:09 | 456 | - | **Non definito** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 dispositivi** | **2 persone**:<br/>Eventi 1, 4, 7, 9, 10 eliminati | **2 persone**:<br/>Cory, non autenticato (compresso a una persona) |

+++

## Confronto delle metriche

+++ In che modo le metriche nei set di dati con unione di Customer Journey Analytics si confrontano con metriche simili nei set di dati senza unione di Customer Journey Analytics e con Adobe Analytics?

Alcune metriche in Customer Journey Analytics sono simili alle metriche nella versione tradizionale di Analytics, ma altre sono diverse, a seconda del confronto. La tabella seguente confronta diverse metriche comuni:

| **Dati uniti di Customer Journey Analytics** | **Dati non uniti di Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Persone** = numero di ID persona distinti in cui l&#39;ID unione viene scelto come ID persona. **Persone** può essere superiore o inferiore a **Visitatori unici** in Adobe Analytics tradizionale, a seconda del risultato del processo di unione. | **Persone** = numero di ID persona distinti in base alla colonna selezionata come ID persona. **Persone** nei set di dati del connettore di origine di Analytics è simile a **Visitatori univoci** in Adobe Analytics tradizionale se `endUserIDs._experience.aaid.id` viene utilizzato come ID persona nel Customer Journey Analytics. | **Visitatori unici** = numero di ID visitatore distinti. **Visitatori unici** potrebbe non essere lo stesso del conteggio di valori univoci **ECID**. | Consulta [Persone](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=it). |
| **Sessioni**: definite in base alle impostazioni di sessione nella visualizzazione dati di Customer Journey Analytics. Il processo di unione può combinare sessioni singole da più dispositivi in una singola sessione. | **Sessioni**: definite in base alle impostazioni di sessione specificate nella visualizzazione dati di Customer Journey Analytics. | **Visite**: consulta [Visite](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=it). | **Visite**: definito in base alle impostazioni di sessione specificate nella [suite di rapporti virtuali CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=it). |
| **Eventi** = numero di righe nei dati uniti in Customer Journey Analytics. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Nota, tuttavia, le domande frequenti sopra relative alle righe con un ID persistente vuoto. | **Eventi** = numero di righe nei dati non uniti in Customer Journey Analytics. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Tuttavia, se uno qualsiasi degli eventi dispone di un ID persona vuoto nei dati non uniti nel data lake di Experience Platform, questi eventi non vengono inclusi nel Customer Journey Analytics. | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it). | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it). |

Altre metriche possono essere simili in Customer Journey Analytics e Adobe Analytics. Ad esempio, il conteggio totale per gli [eventi personalizzati](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=it) 1-100 di Adobe Analytics è comparabile tra Adobe Analytics tradizionale e Customer Journey Analytics (sia che siano uniti o meno). [Differenze nelle funzionalità](/help/getting-started/aa-vs-cja/cja-aa.md)) come la deduplicazione degli eventi tra Customer Journey Analytics e Adobe Analytics possono causare discrepanze tra i due prodotti.

+++

## Mappa delle identità

+++ Il Customer Journey Analytics può utilizzare i campi di Identity Map?

No, al momento il Customer Journey Analytics non può utilizzare i campi Identity Map per l’unione.

+++

## Passa all’unione basata su grafico

+++ Sarà necessario riacquisire i dati per passare dall’unione basata sui campi all’unione basata sui grafici?

Non è necessario riacquisire i dati in Experience Platform, tuttavia dovranno essere riconfigurati in Customer Journey Analytics. Segui questi passaggi:

1. Imposta il nuovo set di dati uniti basato su grafico.
1. Configura il nuovo set di dati come parte di una nuova connessione nel Customer Journey Analytics.
1. Cambia la visualizzazione dati esistente per utilizzare la nuova connessione (e come tale il nuovo set di dati unificato basato su grafico)
1. Rimuovi la vecchia connessione che utilizzava il set di dati unito basato sui campi.

+++

## Interruzione nel reporting

+++ Verrebbero interrotti i rapporti esistenti?

No, se segui i passaggi descritti in precedenza. In caso contrario, chiedi supporto aggiuntivo ad Adobe Consulting.

+++


