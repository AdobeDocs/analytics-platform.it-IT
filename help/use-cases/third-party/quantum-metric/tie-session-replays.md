---
title: La sessione della metrica quantistica viene ripetuta sui dati in Customer Journey Analytics
description: La sessione della metrica quantistica dei collegamenti viene ripetuta con i dati di CJA per comprendere meglio "il perché" dietro "cosa".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 82d7702c57fdff86fa1f4b70d75e7ff7f019ec86
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# La sessione della metrica quantistica viene ripetuta sui dati in Customer Journey Analytics

Collegando le ripetizioni della sessione della metrica quantistica ai dati di CJA, i clienti possono capire meglio &quot;il perché&quot; di &quot;cosa&quot;.  Workspace può essere utilizzato per scoprire le sessioni con attrito, quindi puoi fare clic sugli ID sessione con collegamento ipertestuale per esplorare la ripetizione della sessione in Metrica quantistica.  Questi dati consentono di visualizzare il comportamento all’interno di una sessione e di comprendere meglio cosa causa attrito per i consumatori.  Attraverso le ripetizioni delle sessioni associate a CJA, puoi acquisire un contesto critico sul comportamento del cliente nella tua esperienza.

## Prerequisiti

Questo caso d’uso richiede la raccolta dell’ID di sessione della metrica quantistica insieme al resto dell’implementazione. Per informazioni su come modificare l&#39;implementazione, consulta [Raccolta degli ID di sessione della metrica quantistica in Customer Journey Analytics](collect-session-id.md).

## Passaggio 1: configurare Workspace per la dimensione ID sessione

Crea una tabella a forma libera in Workspace e configurala in modo che i valori ID sessione siano collegati direttamente alla metrica quantistica.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passare a Customer Journey Analytics e selezionare **[!UICONTROL Workspace]** nel menu principale.
1. Seleziona un progetto esistente o crea un progetto.
1. Crea una [tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Trascina la dimensione ID sessione nell’area di lavoro di Workspace.
1. Fare clic con il pulsante destro del mouse sull&#39;intestazione di colonna della dimensione, quindi selezionare **[!UICONTROL Create hyperlinks for all dimension items]**.
1. Seleziona **[!UICONTROL Create a custom URL]**.
1. Incolla la seguente struttura URL:

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. Fai clic su **[!UICONTROL Create]**.

Ogni ID sessione è ora un collegamento cliccabile. Questi collegamenti ti portano alla metrica quantistica in una nuova scheda, che ti consente di analizzare più dettagliatamente quella particolare sessione. Per ulteriori informazioni sull&#39;aggiunta di collegamenti ipertestuali a elementi dimensionali di Analysis Workspace, vedere [Creare collegamenti ipertestuali in una tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).

## Passaggio 2 Visualizzazione delle sessioni da Customer Journey Analytics

Dopo aver creato il rapporto Workspace con collegamenti selezionabili, puoi utilizzare i filtri in Customer Journey Analytics per identificare sessioni interessanti da analizzare ulteriormente in Metrica quantistica.
La tabella restituisce tutte le sessioni in quel segmento e puoi fare clic su una di esse per approfondire l’analisi in QM.  Ulteriori informazioni sulla ripetizione della sessione della metrica quantistica su [https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay). Per ulteriori risorse, contatta il rappresentante dell&#39;Assistenza clienti per la metrica quantistica o invia una richiesta tramite il [portale delle richieste dei clienti](https://community.quantummetric.com/s/public-support-page) per la metrica quantistica.

