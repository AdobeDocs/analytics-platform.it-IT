---
title: Aggiungere eventi di attrito della metrica quantistica a Customer Journey Analytics
description: Aggiungi gli eventi di attrito raccolti da Quantum Metric ai dati comportamentali di Customer Journey Analytics per aggiungere profondità agli approfondimenti in CJA.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
TQID: https://experienceleague.adobe.com/mJkJFAjgA0UNGgzwLLfIPrs1Z-GGByvS8f3B16CANeg
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 685
ht-degree: 1%

---

# Aggiungere eventi di attrito della metrica quantistica a Customer Journey Analytics

La metrica quantistica raccoglie eventi di attrito come la lentezza di caricamento delle pagine, gli errori di caricamento delle pagine, i clic di rabbia e altro ancora. Questi eventi possono essere trasmessi in Customer Journey Analytics come eventi complementari nel percorso di utenti. Con questi dati combinati, puoi comprendere meglio l’impatto dell’attrito sulle metriche a valle.

## Prerequisiti:

Questo caso d’uso ha due requisiti:

* Devi avere diritto al pacchetto **Dev Ops** della metrica Quantum.
* È necessario utilizzare i tag in Raccolta dati di Adobe Experience Platform.

## Passaggio 1: creare un campo schema per accogliere gli eventi di attrito della metrica quantistica

Questo caso d’uso richiede un campo schema dedicato a cui inviare i dati. Puoi creare questo campo in qualsiasi posizione desiderata nello schema e denominarlo come preferisci. I valori di esempio vengono forniti se l’organizzazione non ha una preferenza sul nome o sulla posizione.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a **[!UICONTROL Raccolta dati]** > **[!UICONTROL Schemi]**.
1. Seleziona lo schema desiderato dall’elenco.
1. Seleziona l&#39;icona ![Aggiungi campo](/help/assets/icons/AddCircle.svg) accanto all&#39;oggetto desiderato. Ad esempio, accanto a `Implementation Details`.
1. A destra, immetti il [!UICONTROL Nome] desiderato. Ad esempio: `qmErrorName`.
1. Immettere il [!UICONTROL nome visualizzato] desiderato. Ad esempio: `Quantum Metric error name`.
1. Selezionare [!UICONTROL Tipo] come **[!UICONTROL Stringa]**.
1. Seleziona **[!UICONTROL Salva]**.

## Passaggio 2: acquisire eventi di attrito utilizzando l’estensione tag Quantum Metric

Consulta [Estensione della metrica quantistica](https://experienceleague.adobe.com/it/docs/experience-platform/destinations/catalog/analytics/quantum-metric) nella guida Destinazioni di Adobe Experience Platform per istruzioni su come impostare i tag per includere i dati della metrica quantistica. L’utilizzo di questa estensione passa più righe in un set di dati esistente.

Utilizza i tag nella raccolta dati di Adobe Experience Platform per impostare manualmente il nome dell’evento di attrito in modo che possa essere incluso nell’oggetto XDM e analizzato. Un modo per farlo è nel codice personalizzato della regola:

```js
_satellite.setVar('qm_error_name','error rage click');
return true;
```

Quindi, aggiungi l’elemento dati impostato dinamicamente all’oggetto XDM:

![Schermata del nome dell&#39;errore della metrica quantistica](assets/error-name.png)

## Passaggio 3: aggiungere una o più dimensioni e metriche alla visualizzazione dati in Customer Journey Analytics

Modifica la visualizzazione dati esistente per aggiungere l’ID sessione come dimensione disponibile in Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a Customer Journey Analytics e seleziona **[!UICONTROL Visualizzazioni dati]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu principale.
1. Seleziona la visualizzazione dati esistente desiderata.
1. Individuate l&#39;elenco del campo evento di attrito della metrica Quantum a sinistra e trascinatelo nell&#39;area delle metriche al centro.
1. Nel riquadro di destra, impostare l&#39;impostazione [Includi/Escludi valori](/help/data-views/component-settings/include-exclude-values.md) sugli eventi di attrito desiderati di cui tenere traccia. Puoi aggiungere più eventi di attrito alla stessa metrica per combinarli. Puoi anche trascinare un’altra copia del campo degli eventi di attrito nell’area delle metriche per tracciare altri eventi di attrito come metrica separata.
1. Dopo aver creato tutte le dimensioni e le metriche desiderate, fare clic su **[!UICONTROL Salva]**.
1. Per un elenco completo degli eventi di errore, consulta la documentazione sulle metriche quantitative. Se hai altre domande, contatta il rappresentante dell&#39;Assistenza clienti per la metrica quantistica o invia una richiesta tramite il [portale delle richieste dei clienti per la metrica quantistica](https://community.quantummetric.com/s/public-support-page).

## Passaggio 4: utilizzare la dimensione e le metriche con il resto dei dati in Analysis Workspace

Con i dati evento di attrito della metrica quantistica raccolti insieme al resto dei dati del visitatore, puoi utilizzarli esattamente come faresti con qualsiasi altra dimensione o metrica in Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a Customer Journey Analytics e seleziona **[!UICONTROL Workspace]** nel menu principale.
1. Seleziona un progetto esistente o crea un progetto.
1. Crea una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Trascina le dimensioni e le metriche desiderate nell’area di lavoro di Workspace per l’analisi.

![Grafico di attrito](assets/friction-graph.png)

Le possibili idee di analisi includono:

* Dati dell’evento di attrito di tendenza nel tempo
* In una visualizzazione Abbandono o funnel, aggiungi gli eventi Customer Journey Analytics come alcuni passaggi e gli eventi di attrito della metrica quantistica come altri. Questo rapporto consente di vedere dove i visitatori si trovano più comunemente nei guai.
* Crea e applica un segmento per i visitatori che sperimentano eventi di attrito per un’analisi più approfondita
