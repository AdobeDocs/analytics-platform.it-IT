---
description: Come interagire con le righe statiche nelle tabelle.
title: Righe statiche e dinamiche
uuid: caf033ef-d252-4f8a-802e-7edbbac5c8c0
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 91%

---


# Righe statiche e dinamiche

>[!NOTE] Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Le tabelle di Analysis Workspace generano righe “dinamiche” quando una dimensione viene trascinata nella tabella. Di conseguenza, tutti gli elementi che corrispondono alla dimensione, per una metrica specifica, vengono inseriti nella tabella.

Ad esempio, quando la dimensione Browser viene trascinata nella tabella, tutti i suoi elementi dimensioni (ad esempio, browser Android, Mobile Safari, Firefox, ecc.) vengono inseriti nella tabella stessa.

Invece, ogni volta che selezioni e trascini manualmente una metrica specifica, un segmento, un intervallo di dati o un singolo elemento dimensionale in una tabella, ottieni una riga o un elenco “statici” oppure impostati come hardcoded. Ora puoi interagire con una riga statica nei seguenti modi:

* Fai clic sull’icona Anteprima nelle righe statiche per visualizzare un’anteprima dei segmenti, delle metriche, e degli intervalli di date.
* Fai clic sull’icona “x” per eliminare la riga dalla tabella.
* Limita il numero di righe che vengono visualizzate e attivano il paging.
* Aggiungi “vari elementi dimensionali”. Ad esempio, puoi aggiungere un elemento dalla dimensione di browser e un altro elemento dalla dimensione di un prodotto.

   Di seguito, riportiamo un’immagine esemplificativa:

   ![](assets/static_rows.png)

Inoltre, (solo) in modalità di riga statica, puoi modificare le modalità di calcolo dei totali della colonna. Basta fare clic sull’icona a ingranaggio e scegliere tra queste 2 opzioni:

![](assets/column-totals.png)

| Opzione | Descrizione |
|---|---|
| (Impostazione predefinita) Calcola i totali, sommando i valori presenti in ciascuna colonna. | Questa opzione consente di calcolare solo le righe presenti nella tabella (calcolo lato client). |
| Calcola i totali, basandosi su tutte le righe per ciascuna metrica. | Questa opzione include tutti gli elementi di questa dimensione anche quelli non elencati nella tabella (calcolo lato server). |

