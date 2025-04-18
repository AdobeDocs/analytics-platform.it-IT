---
title: La sessione della metrica quantistica viene ripetuta sui dati in Customer Journey Analytics
description: La sessione della metrica quantistica dei collegamenti viene ripetuta con i dati di CJA per comprendere meglio "il perché" dietro "cosa".
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---

# La sessione della metrica quantistica viene ripetuta sui dati in Customer Journey Analytics

Collegando le ripetizioni della sessione della metrica quantistica ai dati di CJA, i clienti possono capire meglio &quot;il perché&quot; di &quot;cosa&quot;.  Workspace può essere utilizzato per scoprire le sessioni con attrito, quindi puoi fare clic sugli ID sessione con collegamento ipertestuale per esplorare la ripetizione della sessione in Metrica quantistica.  Questi dati consentono di visualizzare il comportamento all’interno di una sessione e di comprendere meglio cosa causa attrito per i consumatori.  Attraverso le ripetizioni delle sessioni associate a CJA, puoi acquisire un contesto critico sul comportamento del cliente nella tua esperienza.

## Prerequisiti

Questi passaggi presuppongono l’utilizzo di tag in Raccolta dati di Adobe Experience Platform. Puoi adattare questi metodi di raccolta dati a un’implementazione manuale di Web SDK se la tua organizzazione non utilizza i tag.

Per ulteriori informazioni, consulta la documentazione dell&#39;estensione tag [Quantum Metric](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric).

## Passaggio 1: acquisire l’ID della sessione della metrica quantistica utilizzando l’estensione dei tag della metrica quantistica

Segui questi passaggi per aggiungere l’ID sessione della metrica quantistica ai dati inviati a Adobe Experience Platform.

1. Utilizza l’estensione Quantum Metric nell’interfaccia utente dei tag per inviare dati a Quantum Metric.
1. Crea quattro elementi dati:
   1. Uno che acquisisce l&#39;ID sessione della metrica quantistica dal cookie della metrica quantistica denominato `QuantumMetricSessionID`
   1. Estrae l&#39;ID sessione della metrica quantistica da `localStorage`. A volte questo elemento dati viene caricato più rapidamente del cookie impostato nell’altro elemento dati.
   1. Utilizzare l&#39;Assistente agli elementi dati o il JavaScript personalizzato per estrarre il nodo `s` dall&#39;elemento dati `localStorage`.
   1. Uno che utilizza la logica per cercare prima l’elemento dati del cookie e, se trovato, restituirlo a un percorso oggetto XDM. Se non è definito, provare a cercare nell&#39;elemento dati dell&#39;oggetto `localStorage` estratto.
1. Invia l’elemento dati ID sessione della metrica quantistica finale all’oggetto XDM inviato in ogni evento.

>[!NOTE]
>A volte il Web SDK viene eseguito più rapidamente del codice della metrica quantistica. In questi casi, l’ID sessione viene inviato all’hit successivo. Se un visitatore non viene recapitato, l’ID sessione non viene raccolto in queste istanze.

## Passaggio 2: confermare i campi del set di dati inclusi

Verifica che i set di dati nella connessione abbiano ora l’ID sessione della metrica quantistica nel set di dati desiderato.

## Passaggio 3: aggiungere l’ID sessione della metrica quantistica come dimensione disponibile

Modifica la visualizzazione dati esistente per aggiungere l’ID sessione come dimensione disponibile in Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passare a Customer Journey Analytics e selezionare **[!UICONTROL Data views]** nel menu principale.
1. Seleziona la visualizzazione dati esistente desiderata.
1. Individuate l&#39;elenco del campo ID sessione della metrica quantistica a sinistra e trascinatelo nell&#39;area delle dimensioni al centro.
1. Nel riquadro di destra, impostare l&#39;impostazione [persistenza](/help/data-views/component-settings/persistence.md) su &#39;Sessione&#39;.
1. Fai clic su **[!UICONTROL Save]**.

## Passaggio 4: configurare Workspace per la dimensione ID sessione

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

Ogni ID sessione è ora un collegamento cliccabile. Per ulteriori informazioni sull&#39;aggiunta di collegamenti ipertestuali a elementi dimensionali di Analysis Workspace, vedere [Creare collegamenti ipertestuali in una tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).

## Passaggio 5: visualizzare le sessioni da Customer Journey Analytics

Dopo aver trovato un segmento di istanza che desideri esplorare le ripetizioni di sessione, puoi applicarlo al pannello che include i collegamenti ID sessione e filtrare per segmento. La tabella restituisce tutte le sessioni in quel segmento e puoi fare clic su una di esse per approfondire l’analisi in Metrica quantistica.

Per ulteriori informazioni, consulta [la guida aziendale alla ripetizione della sessione](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) sulla metrica quantistica. Puoi anche contattare il rappresentante dell&#39;Assistenza clienti per la metrica quantistica o inviare una richiesta tramite il [portale delle richieste dei clienti per la metrica quantistica](https://community.quantummetric.com/s/public-support-page).
