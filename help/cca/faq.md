---
title: Domande frequenti su Cross-Channel Analytics
description: Domande frequenti per Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 94%

---

# Domande frequenti

## Come posso usare CCA per vedere come le persone si spostano da un canale all’altro?

Puoi utilizzare una visualizzazione Flusso con la dimensione ID set di dati.

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) e crea un progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra e trascina una visualizzazione Flusso sull’area di lavoro a destra.
3. Fai clic sulla scheda Componenti a sinistra e trascina la dimensione “ID set di dati” nella posizione centrale denominata “Dimension or item” (Dimensione o elemento).
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

Se desideri rinominare gli elementi dimensione ID set di dati, puoi utilizzare un set di dati di ricerca.

## Quanto tempo fa CCA restringe le persone?

L’intervallo di lookback per la rekeying dipende dalla frequenza di dati [ripetizione](replay.md) desiderata. Ad esempio, se imposti CCA perché riproduca i dati una volta alla settimana, l’intervallo di lookback per la reimpostazione delle chiavi è di sette giorni. Se imposti CCA perché riproduca i dati ogni giorno, l’intervallo di lookback per la reimpostazione delle chiavi è di un giorno.

## Come vengono gestiti i dispositivi condivisi?

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Ad esempio, un dispositivo condiviso da casa, PC condivisi in una libreria o un chiosco in un punto vendita.

L’ID transitorio sostituisce l’ID persistente, pertanto i dispositivi condivisi vengono considerati persone separate (anche se provengono dallo stesso dispositivo).

## In che modo CCA gestisce le situazioni in cui una singola persona dispone di più ID persistenti?

In alcune situazioni, un singolo utente può essere associato a più ID persistenti. Alcuni esempi includono la cancellazione frequente dei cookie del browser o l’utilizzo della modalità privata/incognita del browser.

Il numero di ID persistenti è irrilevante a favore dell’ID transitorio. Un singolo utente può appartenere a qualsiasi numero di dispositivi senza influire sulla capacità di CCA di eseguire unioni tra dispositivi.

## Una volta contattato il mio Adobe Account Team con le informazioni desiderate, quanto tempo ci vuole per rendere disponibile il set di dati reimpostato?

L’unione live è disponibile circa una settimana dopo l’attivazione di Cross-Channel Analytics da parte di Adobe. La disponibilità del backfill dipende dalla quantità di dati esistenti. I set di dati di piccole dimensioni (meno di 1 milione di eventi al giorno) in genere richiedono un paio di giorni, mentre i set di dati di grandi dimensioni (1 miliardo di eventi al giorno) possono richiedere una settimana o più.

## Qual è la differenza tra Analytics tra dispositivi (una funzione nella versione tradizionale di Analytics) e Cross-Channel Analytics?

[Analytics tra dispositivi](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it) è una funzione specifica della versione tradizionale di Adobe Analytics che consente di comprendere il modo in cui le persone operano tra i dispositivi. Offre due flussi di lavoro per collegare i dati dei dispositivi: unione basata sui campi e grafico dei dispositivi.

[Cross-Channel Analytics](/help/cca/overview.md) è una funzione specifica di CJA che consente di comprendere il modo in cui le persone operano sia sui dispositivi che sui canali. Reimposta l’ID persona di un set di dati, consentendo di combinare facilmente quest’ultimo con altri set di dati. Questa funzione opera in modo simile all’unione basata sui campi di CDA, ma l’implementazione è diversa a causa della diversa architettura dei dati tra Analytics tradizionale e CJA.

## In che modo Cross-Channel Analytics gestisce le richieste RGPD e CCPA?

Adobe gestisce le richieste RGPD e CCPA in conformità alle leggi locali e internazionali. Adobe offre [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) per inviare richieste di accesso e cancellazione dei dati. Le richieste si applicano sia ai set di dati originali che a quelli reimpostati.

## Cosa succede se il campo ID persistente in uno o più eventi è vuoto?

Se il campo `Persistent ID` è vuoto in un evento in un set di dati unito con unione basata sul campo, CCA compila `Stitched ID` per tale evento in uno dei due modi seguenti:

* Se il campo `Transient ID` non è vuoto, CCA utilizza il valore in `Transient ID` come `Stitched ID`.
* Se il campo `Transient ID` è vuoto, CCA lascia anche `Stitched ID` vuoto. In questo caso, `Persistent ID`, `Transient ID` e `Stitched ID` sono tutti vuoti durante l’evento. Questi tipi di eventi vengono eliminati da qualsiasi connessione CJA utilizzando il set di dati unito in cui `Stitched ID` è stato scelto come `Person ID`.

## Come si confrontano le metriche nei set di dati con unione di CJA con metriche simili nei set di dati non uniti di CJA e con il tradizionale Adobe Analytics?

Alcune metriche in CJA sono simili alle metriche nella versione tradizionale di Analytics, ma altre sono piuttosto diverse, a seconda del confronto. La tabella seguente confronta diverse metriche comuni:

| **Dati uniti CJA** | **Dati non uniti CJA** | **Adobe Analytics tradizionale** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Persone** = numero di elementi distinti `Person ID` dove `Stitched ID` viene scelto come `Person ID`. **Persone** può essere superiore o inferiore a **Visitatori unici** in Adobe Analytics tradizionale, a seconda del risultato del processo di unione. | **Persone** = numero di elementi distinti `Person ID` in base alla colonna selezionata come `Person ID`. **Persone** nei set di dati del connettore di origine di Analytics è simile a **Visitatori unici** in Adobe Analytics tradizionale se `endUserIDs._experience.aaid.id` viene scelto come `Person ID` in CJA. | **Visitatori univoci** = numero di ID persona distinti. **Visitatori unici** potrebbe non essere lo stesso del conteggio di valori univoci **ECID**. | Consulta [Persone](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=it). |
| **Sessioni**: definito in base alle impostazioni di sessione nella visualizzazione dati di CJA. Il processo di unione può combinare sessioni singole da più dispositivi in una singola sessione. | **Sessioni**: definito in base alle impostazioni di sessione specificate nella visualizzazione dati di CJA. | **Visite**: consulta [Visite](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=it). | **Visite**: definito in base alle impostazioni di sessione specificate nella [suite di rapporti virtuali CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=it). |
| **Eventi** = conteggio delle righe nei dati uniti in CJA. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Nota, tuttavia, le domande frequenti sopra relative alle righe con un vuoto `Persistent ID`. | **Eventi** = conteggio delle righe nei dati non uniti in CJA. Questa metrica è in genere vicina a **Occorrenze** in Adobe Analytics tradizionale. Tuttavia, se uno qualsiasi degli eventi dispone di un `Person ID` vuoto nei dati non uniti nel data lake di Experience Platform, questi eventi non inclusi in CJA. | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it). | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it). |

Altre metriche possono essere simili in CJA e nella versione tradizionale di Adobe Analytics. Ad esempio, il conteggio totale degli [eventi personalizzati](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=it) di Adobe Analytics 1-100 in genere è comparabile in Adobe Analytics tradizionale e CJA (sia che siano uniti o meno). La [differenze di funzionalità](/help/getting-started/aa-vs-cja/cja-aa.md), ad esempio la deduplicazione degli eventi tra CJA e Adobe Analytics tradizionale, può causare discrepanze tra i due prodotti.

## CCA può usare i campi Identity Map?

No, attualmente CCA non può utilizzare i campi Identity Map.
