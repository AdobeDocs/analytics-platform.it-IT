---
title: Aggiungere eventi di attrito della metrica quantistica a Customer Journey Analytics
description: Aggiungi profondità agli approfondimenti in Customer Journey Analytics utilizzando gli eventi di attrito raccolti in Quantum Metric.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 10a70743d292e50ca5aea3225897e7097fa4fc8a
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Aggiungere eventi di attrito della metrica quantistica a Customer Journey Analytics

La metrica quantistica raccoglie eventi di attrito come la lentezza di caricamento delle pagine, gli errori di caricamento delle pagine, i clic di rabbia e altro ancora. Questi eventi possono essere trasmessi in Customer Journey Analytics come eventi complementari nel percorso di utenti. Con questi dati combinati, puoi comprendere meglio l’impatto dell’attrito sulle metriche a valle.

## Prerequisiti:

Questo caso d’uso ha due requisiti:

* Devi avere diritto al pacchetto **Dev Ops** della metrica Quantum.
* È necessario utilizzare i tag in Raccolta dati di Adobe Experience Platform.

## Passaggio 1: acquisire eventi di attrito utilizzando l’estensione tag Quantum Metric

Il team CSM della metrica quantistica può aiutarti a determinare gli elementi dello schema adatti da aggiungere e a modificare l’implementazione per raccogliere i dati desiderati da utilizzare in Customer Journey Analytics. Contatta il tuo Customer Success Manager Quantum Metric per ulteriori informazioni.

In ultima analisi, è necessario iniziare a tracciare il nome dell’evento di attrito in un campo.

## Passaggio 2: confermare i campi del set di dati inclusi

Verifica che i set di dati nella connessione abbiano ora l’ID sessione della metrica quantistica nel set di dati desiderato.

## Passaggio 3: aggiungere una o più dimensioni e metriche alla visualizzazione dati in Customer Journey Analytics

Modifica la visualizzazione dati esistente per aggiungere l’ID sessione come dimensione disponibile in Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passare a Customer Journey Analytics e selezionare **[!UICONTROL Data views]** nel menu principale.
1. Seleziona la visualizzazione dati esistente desiderata.
1. Individuate l&#39;elenco del campo evento di attrito della metrica Quantum a sinistra e trascinatelo nell&#39;area delle metriche al centro.
1. Nel riquadro di destra, impostare l&#39;impostazione [Includi/Escludi valori](/help/data-views/component-settings/include-exclude-values.md) sugli eventi di attrito desiderati di cui tenere traccia. Puoi aggiungere più eventi di attrito alla stessa metrica per combinarli. Puoi anche trascinare un’altra copia del campo degli eventi di attrito nell’area delle metriche per tracciare altri eventi di attrito come metrica separata.
1. Dopo aver creato tutte le dimensioni e le metriche desiderate, fare clic su **[!UICONTROL Save]**.

## Passaggio 4: utilizzare la dimensione e le metriche con il resto dei dati in Analysis Workspace

Con i dati evento di attrito della metrica quantistica raccolti insieme al resto dei dati del visitatore, puoi utilizzarli esattamente come faresti con qualsiasi altra dimensione o metrica in Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passare a Customer Journey Analytics e selezionare **[!UICONTROL Workspace]** nel menu principale.
1. Seleziona un progetto esistente o crea un progetto.
1. Crea una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Trascina le dimensioni e le metriche desiderate nell’area di lavoro di Workspace per l’analisi.

Le possibili idee di analisi sono:

* Dati dell’evento di attrito di tendenza nel tempo
* In una visualizzazione di abbandono o funnel, aggiungi eventi Customer Journey Analytics come alcuni passaggi ed eventi di attrito della metrica quantistica come altri. Questo rapporto consente di vedere dove i visitatori si trovano più comunemente nei guai.
* Crea e applica un filtro per i visitatori che sperimentano eventi di attrito per un’analisi più approfondita
