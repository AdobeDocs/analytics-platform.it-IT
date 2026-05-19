---
title: Utilizzare le mappe di calore della metrica quantistica con Customer Journey Analytics
description: Comprendi meglio il coinvolgimento a livello di pagina e ottimizza le pagine in base al comportamento del consumatore utilizzando i dati della mappa di calore della metrica quantistica.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
autotag-review: '2026-05-19T09:50:41.180Z'
TQID: 'https://experienceleague.adobe.com/EvPGghY3E7eoiJb6TcWnaOhneS6oQJj4bcwU3K2v3Ng'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 1%

---

# Utilizzare le mappe di calore della metrica quantistica con Customer Journey Analytics

Il collegamento della mappatura di calore delle metriche quantistiche ai dati di CJA consente di comprendere meglio il coinvolgimento a livello di pagina e di ottimizzare le pagine in base al comportamento dei consumatori. Workspace può essere utilizzato per comprendere i flussi di utenti e vedere quali percorsi i consumatori seguono da una pagina all’altra. Quindi puoi fare clic su URL pagina con collegamento ipertestuale per creare una mappa visiva del modo in cui gli utenti interagiscono con il contenuto. Collegando Quantum Metric Heatmapping a CJA, ora puoi associare le interazioni a livello di pagina ai risultati di business, portando l’analisi al livello successivo.

La tabella restituisce tutte le sessioni in quel segmento e puoi fare clic su una di esse per approfondire l’analisi in QM.  Per ulteriori informazioni sulla ripetizione della sessione della metrica quantistica, consulta https://www.quantummetric.com/platform/session-replay

## Prerequisiti

Devi avere diritto al pacchetto **UX Ops** della metrica Quantum per accedere alle funzionalità della mappa di calore della metrica Quantum.

## Passaggio 1: configurare i collegamenti in Analysis Workspace

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passa a Customer Journey Analytics e seleziona **[!UICONTROL Workspace]** nel menu principale.
1. Seleziona un progetto esistente o crea un progetto.
1. Crea una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Trascina la dimensione URL della pagina nell’area di lavoro di Workspace.
1. Fare clic con il pulsante destro del mouse sull&#39;intestazione della colonna della dimensione, quindi selezionare **[!UICONTROL Crea collegamenti ipertestuali per tutti gli elementi della dimensione]**.
1. Selezionare **[!UICONTROL Crea un URL personalizzato]**.
1. Incolla la seguente struttura URL:

   ```
   $value?qm-visible=true
   ```

1. Fai clic su **[!UICONTROL Crea]**.
1. Verifica uno dei collegamenti per vedere se si apre nell’URL con l’estensione Quantum Metric visibile. Questi collegamenti si aprono in una nuova scheda in modo che il progetto Workspace rimanga aperto.

![Mappa di calore](assets/heatmap.png)

## Passaggio 2: visualizzare le mappe di calore facendo clic sui collegamenti in Customer Journey Analytics

Dopo aver trovato una pagina da esplorare con la mappatura di calore, puoi applicarla al pannello desiderato. La tabella restituisce un URL che consente di esplorare le mappe di calore, la profondità di scorrimento e le zone chiave per l’interazione utilizzando la metrica quantistica. Per ulteriori informazioni, consulta [Panoramica del prodotto della mappa di calore della metrica quantistica](https://www.quantummetric.com/platform/interaction-heatmaps). Puoi anche contattare il rappresentante dell&#39;Assistenza clienti per la metrica quantistica o inviare una richiesta tramite il [portale delle richieste dei clienti per la metrica quantistica](https://community.quantummetric.com/s/public-support-page).
