---
title: Utilizzare le mappe di calore della metrica quantistica con Customer Journey Analytics
description: Comprendi meglio il coinvolgimento a livello di pagina e ottimizza le pagine in base al comportamento del consumatore utilizzando i dati della mappa di calore della metrica quantistica.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: a0f82948895f3eac86cf00df1dec8abc2f723fc2
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 1%

---

# Utilizzare le mappe di calore della metrica quantistica con Customer Journey Analytics

Il collegamento della mappatura di calore delle metriche quantistiche ai dati di CJA consente di comprendere meglio il coinvolgimento a livello di pagina e di ottimizzare le pagine in base al comportamento dei consumatori. Workspace può essere utilizzato per comprendere i flussi di utenti e vedere quali percorsi i consumatori seguono da una pagina all’altra. Quindi puoi fare clic su URL pagina con collegamento ipertestuale per creare una mappa visiva del modo in cui gli utenti interagiscono con il contenuto.

La tabella restituisce tutte le sessioni in quel segmento e puoi fare clic su una di esse per approfondire l’analisi in QM.  Per ulteriori informazioni sulla ripetizione della sessione della metrica quantistica, consulta https://www.quantummetric.com/platform/session-replay

## Prerequisiti

Questo caso d’uso richiede la raccolta dell’ID di sessione della metrica quantistica insieme al resto dell’implementazione. Per informazioni su come modificare l&#39;implementazione, consulta [Raccolta degli ID di sessione della metrica quantistica in Customer Journey Analytics](collect-session-id.md).

Devi avere diritto al pacchetto **UX Ops** della metrica Quantum per accedere alle funzionalità della mappa di calore della metrica Quantum.

## Crea una tabella a forma libera in Workspace e configurala in modo che i valori ID sessione siano collegati direttamente alla metrica quantistica.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passare a Customer Journey Analytics e selezionare **[!UICONTROL Workspace]** nel menu principale.
1. Seleziona un progetto esistente o crea un progetto.
1. Crea una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Trascina la dimensione URL della pagina nell’area di lavoro di Workspace.
1. Fare clic con il pulsante destro del mouse sull&#39;intestazione di colonna della dimensione, quindi selezionare **[!UICONTROL Create hyperlinks for all dimension items]**.
1. Seleziona **[!UICONTROL Create a custom URL]**.
1. Incolla la seguente struttura URL:

   ```
   $value?qm-visible=true
   ```

1. Fai clic su **[!UICONTROL Create]**.

1. Fai clic su Crea, quindi verifica uno dei collegamenti per vedere se si apre nell’URL con l’estensione QM aperta. Nota: si aprirà in una scheda separata in modo da non perdere il lavoro.


## Visualizzazione delle mappe di calore facendo clic sui collegamenti all’interno di Customer Journey Analytics

Dopo aver trovato una pagina per la quale desideri esplorare la mappatura termica, puoi applicarla al pannello in cui si trova l’URL. La tabella restituisce un URL che consente di esplorare le mappe di calore per la pagina in questione, la profondità di scorrimento e le zone chiave per l’interazione.  Per ulteriori informazioni sulle mappe di calore delle metriche quantistiche, consulta https://www.quantummetric.com/platform/interaction-heatmaps


