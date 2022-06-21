---
title: Domande frequenti su Cross-Channel Analytics
description: Domande frequenti per Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 5eede8eeb5d7e8632dc0d7d580f01ccc7ac8106c
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 58%

---

# Domande frequenti

## Come posso usare CCA per vedere come le persone si spostano da un canale all’altro?

Puoi utilizzare una visualizzazione Flusso con la dimensione ID set di dati.

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) e crea un progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra e trascina una visualizzazione Flusso sull’area di lavoro a destra.
3. Fai clic sulla scheda Componenti a sinistra e trascina la dimensione &quot;ID set di dati&quot; nella posizione centrale etichettata &quot;Dimension o elemento&quot;.
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

Se desideri rinominare gli elementi dimensione ID set di dati, puoi utilizzare un set di dati di ricerca.

## Quanto tempo fa CCA restringe i visitatori?

L’intervallo di lookback per la rekeing dipende dalla frequenza di dati [ripetizione](replay.md) desiderata. Ad esempio, se imposti CCA per riprodurre i dati una volta alla settimana, l’intervallo di lookback per la rekeying è di sette giorni. Se imposti CCA per riprodurre i dati ogni giorno, l’intervallo di lookback per la rekeying è un giorno.

## Come vengono gestiti i dispositivi condivisi?

In alcune situazioni, è possibile che più persone accedano dallo stesso dispositivo. Ad esempio, un dispositivo condiviso da casa, PC condivisi in una libreria o un chiosco in un punto vendita.

L’ID transitorio sostituisce l’ID persistente, pertanto i dispositivi condivisi vengono considerati persone separate (anche se provengono dallo stesso dispositivo).

## In che modo CCA gestisce le situazioni in cui una singola persona ha molti ID persistenti?

In alcune situazioni, un singolo utente può associarsi a molti ID persistenti. Alcuni esempi includono la cancellazione frequente dei cookie del browser o l’utilizzo della modalità privata/incognita del browser.

Il numero di ID persistenti è irrilevante a favore dell’ID transitorio. Un singolo utente può appartenere a qualsiasi numero di dispositivi senza influire sulla capacità di CCA di eseguire unioni tra dispositivi.

## Una volta contattato il mio Account Manager con le informazioni desiderate, quanto tempo ci vuole per rendere disponibile il set di dati reimpostato?

L’unione in tempo reale è disponibile circa una settimana dopo l’attivazione dell’analisi cross-channel da parte dell’Adobe. La disponibilità del backfill dipende dalla quantità di dati esistenti. I set di dati di piccole dimensioni (meno di 1 milione di eventi al giorno) in genere richiedono un paio di giorni, mentre i set di dati di grandi dimensioni (1 miliardo di eventi al giorno) possono richiedere una settimana o più.

## Qual è la differenza tra Analytics tra dispositivi diversi (una funzione nella versione tradizionale di Analytics) e Analytics tra canali?

[Analisi multidispositivo](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it) è una funzione specifica del tradizionale Adobe Analytics che consente di comprendere come le persone operano tra i dispositivi. Offre due flussi di lavoro per collegare i dati dei dispositivi: unione basata sui campi e grafico del dispositivo.

[Analisi cross-channel](../overview.md) è una funzione specifica di CJA che consente di comprendere come le persone operano su entrambi i dispositivi e canali. È un ID persona di un set di dati, che consente di combinarlo facilmente con altri set di dati. Questa funzione funziona in modo simile alla combinazione basata sul campo di CDA, ma l’implementazione è diversa rispetto alla diversa architettura dei dati tra Analytics tradizionale e CJA.

## In che modo Cross-Channel Analytics gestisce le richieste RGPD e CCPA?

Adobe gestisce le richieste RGPD e CCPA in conformità alle leggi locali e internazionali. Adobe offre [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) per inviare richieste di accesso e cancellazione dei dati. Le richieste si applicano sia ai set di dati originali che a quelli reimpostati.

## Cosa succede se il campo ID persistente in uno o più eventi è vuoto?

Se il campo `Persistent ID` è vuoto in un evento in un set di dati unito con unione basata sul campo, CCA compila `Stitched ID` per tale evento in uno dei due modi seguenti:

* Se il campo `Transient ID` non è vuoto, CCA utilizza il valore in `Transient ID` come `Stitched ID`.
* Se il campo `Transient ID` è vuoto, CCA lascia anche `Stitched ID` vuoto. In questo caso, `Persistent ID`, `Transient ID`e `Stitched ID` sono tutti vuoti nell’evento. Questi tipi di eventi vengono eliminati da qualsiasi connessione CJA utilizzando il set di dati in cui viene unione `Stitched ID` è stato scelto come `Person ID`.

## Come si confrontano le metriche nei set di dati con unione di CJA con metriche simili nei set di dati non uniti di CJA e con il tradizionale Adobe Analytics?

Alcune metriche in CJA sono simili alle metriche nella versione tradizionale di Analytics, ma altre sono piuttosto diverse, a seconda del confronto. La tabella seguente confronta diverse metriche comuni:

| **Dati uniti CJA** | **Dati non uniti CJA** | **Adobe Analytics tradizionale** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Persone** = numero di elementi distinti `Person ID` dove `Stitched ID` viene scelto come `Person ID`. **Persone** può essere superiore o inferiore a **Visitatori unici** in Adobe Analytics tradizionale, a seconda del risultato del processo di unione. | **Persone** = numero di elementi distinti `Person ID` in base alla colonna selezionata come `Person ID`. **Persone** in Adobe Source Connector datasets è simile a **Visitatori unici** in Adobe Analytics tradizionale se `endUserIDs._experience.aaid.id` viene scelto come `Person ID` in CJA. | **Visitatori unici** = numero di ID visitatore distinti. **Visitatori unici** potrebbe non essere lo stesso del conteggio di valori univoci **ECID** s. | Consulta [Persone](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=it). |
| **Sessioni**: Definito in base alle impostazioni della sessione nella visualizzazione dati di CJA. Il processo di unione può combinare sessioni singole da più dispositivi in una singola sessione. | **Sessioni**: Definito in base alle impostazioni di sessione specificate nella visualizzazione dati di CJA. | **Visite**: consulta [Visite](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=it). | **Visite**: Definito in base alle impostazioni di sessione specificate nel [Suite di rapporti virtuali CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=it). |
| **Eventi** = conteggio delle righe nei dati uniti in CJA. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Nota, tuttavia, le domande frequenti sopra relative alle righe con un vuoto `Persistent ID`. | **Eventi** = conteggio delle righe nei dati non uniti in CJA. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Tuttavia, se uno qualsiasi degli eventi dispone di un valore vuoto `Person ID` nei dati non uniti nel data lake di Experience Platform, questi eventi non sono inclusi in CJA. | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it). | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Altre metriche possono essere simili in CJA e nella versione tradizionale di Adobe Analytics. Ad esempio, il conteggio totale per Adobe Analytics [eventi personalizzati](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=it) 1-100 è generalmente paragonabile tra Adobe Analytics tradizionale e CJA (sia cucito che non cucito). [Differenze di funzionalità](/help/getting-started/aa-vs-cja/cja-aa.md)), ad esempio la deduplicazione degli eventi tra CJA e il tradizionale Adobe Analytics, può causare discrepanze tra i due prodotti.

## CCA può usare i campi mappa identità?

No, al momento CCA non può utilizzare i campi di Identity Map.
