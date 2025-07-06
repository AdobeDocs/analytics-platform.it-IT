---
title: Best practice di attribuzione
description: Scopri le best practice per decidere quale modello di attribuzione utilizzare.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 65%

---

# Best practice di attribuzione

La scelta del modello di attribuzione corretto per l’organizzazione dipende da una serie di considerazioni. Questo articolo esplora una metodologia e alcune best practice generali:

* [Analisi esplorativa](#exploratory-analysis)
* [Attribuzioni basate su regole](#rule-base-attribution)
* [Utilizzare l’attribuzione algoritmica](#use-algorithmic-attribution)

## Analisi esplorativa

>[!NOTE]
>Questa analisi deve essere eseguita prima di scegliere un modello di attribuzione.

Questa fase consiste inizialmente nel comprendere il comportamento del cliente e definire le metriche di conversione. In base alle metriche di conversione, strumenti come [Feed dati](https://experienceleague.adobe.com/it/docs/analytics/export/analytics-data-feed/data-feed-overview) (per dati non elaborati) o Analysis Workspace facilitano la comprensione di

* Quanti clienti toccano diversi canali di marketing prima della conversione
* La proporzione/distribuzione di questi comportamenti

Ad esempio, se il 50% dei clienti tocca 3 canali prima della conversione, esiste un’interazione tra questi 3 canali?
Per comprendere meglio la situazione, puoi quindi eseguire un’analisi upper funnel o lower funnel.

### Analisi upper funnel

I canali di analisi upper funnel sono utilizzati per creare awareness del brand o del prodotto. Ad esempio, la maggior parte degli annunci TV hanno come obiettivo la brand awareness. È possibile utilizzare il [modello di attribuzione Decadimento nel tempo](/help/analysis-workspace/attribution/models.md), poiché nel tempo le persone si dimenticheranno del tuo annuncio TV.

### Analisi lower funnel

Nell’analisi lower funnel, il presupposto è che le persone conoscano già il tuo marchio e che il tuo obiettivo sia la conversione. Utilizza notifiche e-mail o push o annunci Facebook.

## Attribuzione basata su regole

Lo scopo di questo passaggio è quello di convalidare le tue ipotesi.

**Esempio 1**

Supponiamo che l&#39;ipotesi sia: &quot;*Il mio canale di primo contatto ha un impatto maggiore sulla conversione rispetto al mio canale di ultimo contatto.*&quot;

In questo caso, per testare questa ipotesi si utilizza il [modello di attribuzione a forma di J inversa](/help/analysis-workspace/attribution/models.md). Questo modello attribuisce il 60% del credito al primo punto di contatto.

**Esempio 2**

Supponiamo che l&#39;ipotesi sia: *&quot;In un settore specifico (ad esempio, il settore dei viaggi), la finestra di attribuzione è di 60 o 90 giorni, non di 30 giorni, perché i clienti effettuano molte ricerche prima di acquistare un prodotto.*&quot;

In questo caso, è necessario cambiare l’[intervallo di lookback](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/models) impostandolo su 90 giorni.

## Utilizzare l’attribuzione algoritmica

Se non disponi ancora di un modello di attribuzione che fornisca risposte soddisfacenti a tutte le domande, puoi utilizzare l’[attribuzione algoritmica](/help/analysis-workspace/attribution/algorithmic.md). Poiché è molto difficile convalidare un numero elevato di ipotesi e combinazioni possibili, l’attribuzione algoritmica utilizza algoritmi incorporati per allocare credito tra gli elementi dimensionali.

## Altre considerazioni

* Potrebbe essere necessario avvalersi anche di un data scientist, invece di affidarsi solo ad Analysis Workspace.
* Puoi fare affidamento sui dati non elaborati, come nei feed di dati di Adobe.
* È consigliabile utilizzare [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview), ad esempio, se si desidera considerare i dati relativi alle impression.
