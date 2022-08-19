---
description: Scopri come analizzare i risultati dei test A/B nel pannello Sperimentazione CJA .
title: Pannello sperimentale
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 57a52c21b1850574e5d85ab560fb5399f9b37631
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 6%

---

# Pannello sperimentale

>[!NOTE]
>
>Questa funzionalità è attualmente in [fase di test](/help/release-notes/releases.md).

La **[!UICONTROL Experimentation]** consente agli analisti di confrontare diverse varianti di esperienza utente, marketing o messaggistica per determinare quale sia meglio per determinare un risultato specifico. Puoi valutare l’incremento e l’affidabilità di qualsiasi esperimento A/B da qualsiasi piattaforma di sperimentazione: online, offline, dalle soluzioni di Adobe, Adobe Journey Optimizer e persino i dati BYO (risorse disponibili).

>[!IMPORTANT]
>
>A questo punto, [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) (A4T) dati inviati in Adobe Experience Platform tramite il connettore sorgente di Analytics **impossibile** essere analizzati nella [!UICONTROL Experimentation] pannello. Ci attendiamo una soluzione a questo problema nel 2023.

## Controllo degli accessi

Il pannello Sperimentazione è disponibile per l’uso da parte di tutti gli utenti del Customer Journey Analytics (CJA). Non sono necessari diritti di amministratore o altre autorizzazioni. Tuttavia, la configurazione (passaggi 1 e 2 di seguito) richiede azioni che solo gli amministratori possono eseguire.

## Passaggio 1: Creare una connessione per sperimentare i set di dati

Dopo che i dati dell&#39;esperimento sono stati [acquisito](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) in Adobe Experience Platform, [creare una connessione in CJA](/help/connections/create-connection.md) a uno o più set di dati di prova.

## Passaggio 2: Aggiungere etichette di contesto nelle visualizzazioni dati

Nelle impostazioni delle visualizzazioni dati di CJA, gli amministratori possono aggiungere [etichette di contesto](/help/data-views/component-settings/overview.md) a una dimensione o a una metrica e ai servizi CJA come [!UICONTROL Experimentation] possono utilizzare queste etichette per i loro scopi. Per il pannello Sperimentazione vengono utilizzate due etichette predefinite:

* [!UICONTROL Experiment]
* [!UICONTROL Variant]

Nella visualizzazione dati che contiene dati di sperimentazione, scegli due dimensioni, una con i dati di sperimentazione e una con i dati della variante. Quindi etichettate queste dimensioni con il **[!UICONTROL Experiment]** e **[!UICONTROL Variant]** etichette.

![etichetta di contesto](assets/context-label.png)

Senza queste etichette presenti, il pannello Esperimento non funziona, in quanto non ci saranno esperimenti con cui lavorare.

## Passaggio 3: Configurare il pannello Esperimento

1. In CJA Workspace, trascina il pannello Sperimentazione in un progetto.

![pannello sperimentale](assets/experiment.png)

>[!IMPORTANT]
>Se la configurazione necessaria nelle visualizzazioni dati di CJA non è stata completata, riceverai un messaggio a tal fine prima di procedere.

1. Configura le impostazioni di input del pannello.

   | Impostazione | Definizione |
   | --- | --- |
   | **[!UICONTROL Experiment]** | Un insieme di varianti di un’esperienza che è stata esposta agli utenti finali per determinare quale è meglio mantenere in perpetuità. Un esperimento è costituito da due o più varianti, una delle quali è considerata la variante di controllo. Questa impostazione è precompilata con le dimensioni etichettate con  **[!UICONTROL Experiment]** etichetta nelle visualizzazioni dati e i dati degli ultimi 3 mesi sugli esperimenti. |
   | **[!UICONTROL Control Variant]** | Una delle due o più modifiche nell&#39;esperienza di un utente finale che vengono confrontate allo scopo di identificare l&#39;alternativa migliore. Una variante deve essere selezionata come controllo e una sola variante può essere considerata come variante di controllo. Questa impostazione è precompilata con le dimensioni etichettate con  **[!UICONTROL Variant]** nelle visualizzazioni dati. Questa impostazione richiama i dati della variante associati all&#39;esperimento. |
   | **[!UICONTROL Success Metrics]** | La metrica o le metriche con cui un utente confronta le varianti. La variante con il risultato più auspicabile per la metrica di conversione (sia essa più alta o più bassa) è dichiarata la &quot;variante con le prestazioni migliori&quot; di un esperimento. Puoi aggiungere fino a 5 metriche. |
   | **[!UICONTROL Normalizing Metric]** | La base ([!UICONTROL People], [!UICONTROL Sessions]oppure [!UICONTROL Events]) in cui verrà eseguito un test. Ad esempio, un test può confrontare i tassi di conversione di diverse varianti quando **[!UICONTROL Conversion rate]** è calcolato come segue **[!UICONTROL Conversions per session]** o **[!UICONTROL Conversions per person]**. |

1. Fai clic su **[!UICONTROL Build]**.

## Passaggio 4: Interpretare l’output del pannello

Il pannello Sperimentazione restituisce un set completo di dati e visualizzazioni per consentirti di comprendere meglio le prestazioni degli esperimenti. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate. In qualsiasi momento, puoi modificare il pannello facendo clic sulla matita di modifica in alto a destra.

Viene inoltre visualizzato un riepilogo del testo che indica se l’esperimento è conclusivo o meno e riepiloga il risultato. La conclusione si basa sulla rilevanza statistica. (Vedi &quot;Metodologia statistica&quot; di seguito.) Puoi visualizzare i numeri di riepilogo per la variante con le prestazioni migliori con l’incremento e l’affidabilità più elevati.

>[!NOTE]
>
>Incremento e affidabilità sono anche funzioni metriche calcolate avanzate in CJA, per creare metriche di incremento e affidabilità personalizzate.

![uscita sperimentale](assets/exp-output1.png)

Per ogni metrica di successo selezionata, verrà visualizzata una tabella a forma libera e una tendenza del tasso di conversione:

![uscita sperimentale](assets/exp-output2.png)

La [!UICONTROL Line] il grafico [!UICONTROL Control] contro [!UICONTROL Control Variant] prestazioni:

![uscita sperimentale](assets/exp-output3.png)


## Metodologia statistica

Da seguire.



