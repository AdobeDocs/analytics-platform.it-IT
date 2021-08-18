---
title: Best practice di attribuzione
description: Quali sono le best practice per decidere su un modello di attribuzione?
source-git-commit: 3839639858edbd019ef467ca5fb1791f48864100
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---


# Best practice di attribuzione

La scelta del modello di attribuzione corretto per l’organizzazione dipende da una serie di considerazioni. Questo articolo esplora una metodologia e alcune best practice generali.

## Passaggio 1: Analisi esplorativa

>[!NOTE]
>Questa analisi deve essere eseguita prima di scegliere un modello di attribuzione.

Questa fase consiste inizialmente nel comprendere il comportamento del cliente e definire le metriche di conversione. In base alle metriche di conversione, strumenti come [Feed dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) (per dati non elaborati) o Analysis Workspace facilitano la comprensione di

* Quanti clienti toccano diversi canali di marketing prima della conversione?
* La proporzione/distribuzione di questi comportamenti.

Ad esempio, se il 50% dei clienti tocca 3 canali prima della conversione, esiste un’interazione tra questi 3 canali?
Puoi quindi eseguire un’analisi funnel superiore e inferiore per espandere la comprensione.

### Analisi Upper funnel

L’analisi dell’imbuto superiore analizza i canali utilizzati per creare brand o consapevolezza del prodotto. Ad esempio, l&#39;obiettivo della maggior parte degli annunci TV è la brand awareness. È possibile utilizzare il modello di attribuzione [&quot;Decadimento nel tempo&quot;](/help/analysis-workspace/attribution/models.md), dal momento che le persone dimenticheranno il tuo annuncio TV nel tempo.

### Analisi a basso funnel

In questa analisi, il presupposto è che le persone già sanno del tuo marchio e che tu vuoi che convergano. Utilizza notifiche e-mail o push o annunci Facebook.

## Passaggio 2: Attribuzione basata su regole

Lo scopo di questo passaggio è quello di convalidare le tue ipotesi.

**Esempio 1**

Supponiamo che la tua ipotesi sia &quot;Il mio canale di primo contatto ha un impatto maggiore sulla conversione rispetto al mio canale di ultimo contatto. Quindi, per testare questa ipotesi, utilizza il modello di attribuzione [&quot;A forma di J inversa&quot;](/help/analysis-workspace/attribution/models.md). Questo modello attribuisce il 60% del credito al primo punto di contatto.

**Esempio 2**

La tua ipotesi potrebbe essere: &quot;Nel nostro settore (come quello dei viaggi), la finestra di attribuzione è 60 o 90 giorni, non 30 giorni, perché i clienti fanno molta ricerca prima di acquistare un prodotto. Successivamente, cambierai l&#39; [intervallo di lookback](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#lookback-windows) in 90 giorni.

## Passaggio 3: Utilizzare l’attribuzione algoritmica

Poiché è molto difficile convalidare un gran numero di ipotesi e combinazioni possibili, puoi utilizzare l&#39; [attribuzione algoritmica](/help/analysis-workspace/attribution/algorithmic.md) per lasciare questo lavoro agli algoritmi incorporati. Se hai già trovato il modello di attribuzione perfetto che risponde a tutte le tue domande ed è perfetto, allora ovviamente non devi fare questo passo.

## Altre considerazioni

* Potrebbe essere necessario utilizzare i servizi di uno scienziato dei dati invece di affidarsi solo ad Analysis Workspace.
* Puoi fare affidamento sui dati non elaborati, come nei feed di dati di Adobe.
* Prendi in considerazione l’utilizzo di [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en), ad esempio, se desideri tenere in considerazione i dati relativi alle impression.

