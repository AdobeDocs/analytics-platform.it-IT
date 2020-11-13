---
title: Domande frequenti su Analytics tra canali
description: Domande frequenti per Analytics multicanale
translation-type: tm+mt
source-git-commit: dd4e7e5cd04db6483f0e4a1f3161f23f8a5a8294
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---


# Domande frequenti

## Come posso usare CCA per vedere come le persone si spostano da un canale all&#39;altro?

Puoi utilizzare una visualizzazione Flusso con la dimensione ID del set di dati.

1. Accedete a [analytics.adobe.com](https://analytics.adobe.com) e create un progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul quadro a destra.
3. Fare clic sulla scheda Componenti a sinistra, quindi trascinare la dimensione &#39;ID set di dati&#39; nella posizione centrale abilitata &#39;Dimension o elemento&#39;.
4. Questo rapporto di flusso è interattivo. Fate clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Per espandere o comprimere le colonne, usate il menu di scelta rapida. All’interno dello stesso rapporto di flusso possono essere utilizzate dimensioni diverse.

Se si desidera rinominare gli elementi dimensione ID set di dati, è possibile utilizzare un set di dati di ricerca.

## Quanto tempo fa CCA reagisce ai visitatori?

La finestra di lookback per la rekeying dipende dalla frequenza desiderata di dati [replay](replay.md). Ad esempio, se configurate CCA per riprodurre i dati una volta alla settimana, la finestra di lookback per la rekeying è di 7 giorni. Se configurate CCA per riprodurre i dati ogni giorno, la finestra di lookback per la rekeying è di 1 giorno.

## Come vengono gestiti i dispositivi condivisi?

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Alcuni esempi includono un dispositivo condiviso a casa, PC condivisi in una libreria o un chiosco in un punto vendita.

L’ID transitorio sostituisce l’ID persistente, pertanto i dispositivi condivisi sono considerati persone separate (anche se provengono dallo stesso dispositivo).

## In che modo CCA gestisce le situazioni in cui una singola persona dispone di un numero elevato di ID persistenti?

In alcune situazioni, un singolo utente può associarsi a un numero elevato di ID persistenti. Alcuni esempi includono la cancellazione frequente dei cookie del browser o l&#39;utilizzo della modalità privata/incognito del browser.

Il numero di ID persistenti è irrilevante a favore dell’ID transitorio. Un singolo utente può appartenere a un numero qualsiasi di dispositivi senza che ciò influisca sulla capacità di CCA di cucire tra i dispositivi.

## Una volta contattato il mio Account Manager con le informazioni desiderate, quanto tempo ci vuole affinché il set di dati rekeyed diventi disponibile?

La cucitura in diretta è disponibile circa una settimana dopo  Adobe che consente l&#39;analisi tra canali. La disponibilità del backfill dipende dalla quantità di dati esistenti. I set di dati di piccole dimensioni (meno di 1 milione di eventi al giorno) in genere richiedono un paio di giorni, mentre i set di dati di grandi dimensioni (1 miliardo di eventi al giorno) possono richiedere una settimana o più.

## In che modo Analytics multicanale gestisce le richieste GDPR e CCPA?

 Adobe gestisce le richieste GDPR e CCPA in conformità alle leggi locali e internazionali.  Adobe offre la [ Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) per inviare richieste di accesso ed eliminazione dei dati. Le richieste si applicano sia ai set di dati originali che ai set di dati ripetuti.
