---
title: Domande frequenti su Cross-Channel Analytics
description: Domande frequenti per Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 100%

---

# Domande frequenti

## Come posso usare CCA per vedere come le persone si spostano da un canale all’altro?

Puoi utilizzare una visualizzazione Flusso con la dimensione ID set di dati.

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) e crea un progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra e trascina una visualizzazione Flusso sull’area di lavoro a destra.
3. Fai clic sulla scheda Componenti a sinistra e trascina la dimensione “ID set di dati” nella posizione centrale abilitata “Dimensione o elemento”.
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

Se desideri rinominare gli elementi dimensione ID set di dati, puoi utilizzare un set di dati di ricerca.

## Quanto tempo fa CCA restringe i visitatori?

L’intervallo di lookback per la rekeing dipende dalla frequenza di dati [ripetizione](replay.md) desiderata. Ad esempio, se imposti CCA per riprodurre i dati una volta alla settimana, l’intervallo di lookback per la rekeying è di 7 giorni. Se imposti CCA per riprodurre i dati ogni giorno, l’intervallo di lookback per la rekeying è di 1 giorno.

## Come vengono gestiti i dispositivi condivisi?

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Ad esempio, un dispositivo condiviso da casa, PC condivisi in una libreria o un chiosco in un punto vendita.

L’ID transitorio sostituisce l’ID persistente, pertanto i dispositivi condivisi vengono considerati persone separate (anche se provengono dallo stesso dispositivo).

## In che modo CCA gestisce le situazioni in cui una singola persona dispone di un numero elevato di ID persistenti?

In alcune situazioni, un singolo utente può associarsi a un numero elevato di ID persistenti. Alcuni esempi includono la cancellazione frequente dei cookie del browser o l’utilizzo della modalità privata/incognita del browser.

Il numero di ID persistenti è irrilevante a favore dell’ID transitorio. Un singolo utente può appartenere a qualsiasi numero di dispositivi senza influire sulla capacità di CCA di eseguire unioni tra dispositivi.

## Una volta contattato il mio Account Manager con le informazioni desiderate, quanto tempo ci vuole per rendere disponibile il set di dati reimpostato?

L’unione live è disponibile circa 1 settimana dopo l’attivazione di Cross-Channel Analytics da parte di Adobe. La disponibilità del backfill dipende dalla quantità di dati esistenti. I set di dati di piccole dimensioni (meno di 1 milione di eventi al giorno) in genere richiedono un paio di giorni, mentre i set di dati di grandi dimensioni (1 miliardo di eventi al giorno) possono richiedere una settimana o più.

## In che modo Cross-Channel Analytics gestisce le richieste RGPD e CCPA?

Adobe gestisce le richieste RGPD e CCPA in conformità alle leggi locali e internazionali. Adobe offre [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) per inviare richieste di accesso e cancellazione dei dati. Le richieste si applicano sia ai set di dati originali che a quelli reimpostati.

## Cosa succede se il campo ID persistente in uno o più eventi è vuoto?

Se il campo `Persistent ID` è vuoto in un evento in un set di dati unito con unione basata sul campo, CCA compila `Stitched ID` per tale evento in uno dei due modi seguenti:
* Se il campo `Transient ID` non è vuoto, CCA utilizza il valore in `Transient ID` come `Stitched ID`.
* Se il campo `Transient ID` è vuoto, CCA lascia anche `Stitched ID` vuoto. In questo caso, `Persistent ID`, `Transient ID` e `Stitched ID` saranno tutti vuoti durante l’evento. Eventi come questo vengono eliminati da CJA in qualsiasi connessione CJA utilizzando il set di dati unito in cui `Stitched ID` è stato scelto come `Person ID`.

## Come si confrontano le metriche nei set di dati con unione di CJA con metriche simili nei set di dati non uniti di CJA e con il tradizionale Adobe Analytics?

Alcune metriche in CJA sono simili alle metriche nella versione tradizionale di Analytics, ma altre sono piuttosto diverse, a seconda del confronto. La tabella seguente confronta diverse metriche comuni:

| **Dati uniti CJA** | **Dati non uniti CJA** | **Adobe Analytics tradizionale** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Persone** = numero di elementi distinti `Person ID` dove `Stitched ID` viene scelto come `Person ID`. **Persone** può essere superiore o inferiore a **Visitatori unici** in Adobe Analytics tradizionale, a seconda del risultato del processo di unione. | **Persone** = numero di elementi distinti `Person ID` in base alla colonna selezionata come `Person ID`. **Persone** nei set di dati di Adobe Analytics Connector (ADC) è simile a **Visitatori unici** in Adobe Analytics tradizionale se `endUserIDs. _experience. aaid.id` viene scelto come `Person ID` in CJA. | **Visitatori unici** = numero di ID visitatore distinti. Tieni presente che **Visitatori unici** potrebbe non essere lo stesso del conteggio di valori univoci **ECID**. | Consulta [Persone](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=it). |
| **Sessioni**: è definito in base alle impostazioni di sessionizzazione specificate nella visualizzazione dati CJA. Il processo di unione può combinare sessioni singole da più dispositivi in una singola sessione. | **Sessioni**: è definito in base alle impostazioni di sessionizzazione specificate nella visualizzazione dati CJA. | **Visite**: consulta [Visite](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=it). | **Visite**: è definito in base alle impostazioni di sessionizzazione specificate in [Suite di rapporti virtuali CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=it). |
| **Eventi** = conteggio delle righe nei dati uniti in CJA. In generale, questo dovrebbe essere vicino a **Occorrenze** in Adobe Analytics tradizionale. Nota, tuttavia, le domande frequenti sopra relative alle righe con un vuoto `Persistent ID`. | **Eventi** = conteggio delle righe nei dati non uniti in CJA. In generale, questo dovrebbe essere vicino a **Occorrenze** in Adobe Analytics tradizionale. Tuttavia, se uno qualsiasi degli eventi dispone di un valore vuoto `Person ID` nei dati non uniti nel data lake di AEP, questi eventi verranno ignorati (non inclusi) in CJA. | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it). | **Occorrenze**: consulta [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en). |

Altre metriche possono essere simili in CJA e nella versione tradizionale di Adobe Analytics. Ad esempio, il conteggio totale per gli [eventi personalizzati](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=it) (eventi 1-100) di Adobe Analytics in genere dovrebbe essere molto vicino in Adobe Analytics e CJA tradizionali (sia che siano uniti o meno). Tuttavia, questo potrebbe non essere sempre vero a causa di [differenze di funzionalità](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=it)  come la deduplicazione di eventi tra CJA e il tradizionale Adobe Analytics.
