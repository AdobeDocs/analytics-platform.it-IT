---
title: Best practice di attribuzione
description: Quali sono le best practice per la scelta di un modello di attribuzione?
feature: Attribution
exl-id: d612dc79-24e4-4d50-bccd-dfb58328bd4e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 90%

---

# Best practice di attribuzione

La scelta del modello di attribuzione corretto per l’organizzazione dipende da una serie di considerazioni. Questo articolo esplora una metodologia e alcune best practice generali.

## Passaggio 1: analisi esplorativa

>[!NOTE]
>Questa analisi deve essere eseguita prima di scegliere un modello di attribuzione.

Questa fase consiste inizialmente nel comprendere il comportamento del cliente e definire le metriche di conversione. In base alle metriche di conversione, strumenti come Analysis Workspace e l’estrazione di origini dati da più canali (come i dati delle impression) possono facilitare la comprensione di

* Quanti clienti toccano diversi canali di marketing prima della conversione?
* La proporzione/distribuzione di questi comportamenti.

Ad esempio, se il 50% dei clienti tocca 3 canali prima della conversione, esiste un’interazione tra questi 3 canali?
Per comprendere meglio la situazione, puoi quindi eseguire un’analisi upper funnel o lower funnel.

### Analisi upper funnel

L’analisi upper funnel esamina i canali utilizzati per creare awareness del brand o del prodotto. Ad esempio, la maggior parte degli annunci TV hanno come obiettivo la brand awareness. Con il passare del tempo, le persone si dimenticheranno del tuo annuncio TV, e potresti quindi usare il [modello di attribuzione Time decay (Decadimento temporale)](/help/analysis-workspace/attribution/models.md).

### Analisi lower funnel

In questa analisi, il presupposto è che le persone conoscano già il tuo marchio e che il tuo obiettivo sia la conversione. Utilizza notifiche e-mail o push o annunci Facebook.

## Passaggio 2: attribuzione basata su regole

Lo scopo di questo passaggio è quello di convalidare le tue ipotesi.

**Esempio 1**

Supponiamo che l’ipotesi sia “il primo canale di contatto ha un impatto maggiore sulla conversione rispetto all’ultimo”. Per testare questa ipotesi, utilizza il [modello di attribuzione “a J inversa”](/help/analysis-workspace/attribution/models.md). Questo modello attribuisce il 60% del credito al primo punto di contatto.

**Esempio 2**

L’ipotesi potrebbe essere: “nel nostro settore (ad es., viaggi), la finestra di attribuzione è 60 o 90 giorni, non 30 giorni, perché i clienti fanno molta ricerca prima di acquistare un prodotto”. Potresti quindi cambiare l’[intervallo di lookback](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#lookback-windows) impostandolo su 90 giorni.

## Passaggio 3: utilizzare l’attribuzione algoritmica

Poiché è molto difficile convalidare un numerose ipotesi e combinazioni possibili, puoi utilizzare l’[attribuzione algoritmica](/help/analysis-workspace/attribution/algorithmic.md) e lasciare che siano gli algoritmi incorporati a fare i calcoli necessari. Se hai già trovato il modello di attribuzione perfetto che risponde e si adatta a tutte le domande, allora ovviamente non devi fare questo passaggio.

## Altre considerazioni

* Potrebbe essere necessario avvalersi anche di un data scientist, invece di affidarsi solo ad Analysis Workspace.
