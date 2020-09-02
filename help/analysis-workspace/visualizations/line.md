---
description: Utilizzare la visualizzazione delle linee per rappresentare set di dati con tendenze (basati sul tempo)
title: Linee
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 4f163e32787a732526511aeda5f6c1e32becb490
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 20%

---


# Linee

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

La visualizzazione Linea rappresenta le metriche utilizzando una linea per mostrare come cambiano i valori in un determinato periodo di tempo. Un grafico a linee può essere usato solo con una dimensione temporale.

![Visualizzazione linee](assets/line-viz.png)

>[!IMPORTANT]
>
>Alcune impostazioni di visualizzazione Linea, come [!UICONTROL Show trendline], sono attualmente in fase di test limitati. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/landing/an-releases.html)

Fai clic sull&#39;icona a forma di ingranaggio in alto a destra della visualizzazione Linea per accedere [**Impostazioni di visualizzazione**](freeform-analysis-visualizations.md) disponibile. Le impostazioni sono suddivise in categorie:

* **Generale**: Impostazioni comuni tra i tipi di visualizzazione
* **Asse**: Impostazioni che influiscono sull’asse x o y della visualizzazione linea
* **Sovrapposizioni**: Opzioni per aggiungere ulteriore contesto alla serie mostrata nella visualizzazione a linee.

![Impostazioni visualizzazione](assets/viz-settings-modal.png)

## Modificare la granularità

Nelle [impostazioni di visualizzazione](freeform-analysis-visualizations.md), un elenco a discesa di granularità permette di cambiare una visualizzazione con tendenza (ad esempio un grafico a linee) da base giornaliera a settimanale, mensile e così via. La granularità viene aggiornata anche nella tabella dell&#39;origine dati.

## Mostra min o max

Sotto **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show min/max]**, potete sovrapporre un&#39;etichetta di valore minimo e massimo per evidenziare rapidamente picchi e valli in una metrica. Nota: I valori min/max sono derivati dai punti di dati visibili nella visualizzazione, non dall’intero insieme di valori all’interno di una dimensione.

![Mostra min/max](assets/min-max-labels.png)

## Mostra sovrapposizione linea di tendenza

Sotto **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show trendline]**, è possibile scegliere di aggiungere una tendenza di regressione alla serie di linee. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati.

![Linea di tendenza lineare](assets/show-linear-trendline.png)

Tutti i modelli sono adattabili utilizzando i minimi quadrati ordinari:

| Modello | Descrizione |
| --- | --- |
| Lineare | Crea una linea retta adatta per set di dati lineari semplici ed è utile quando i dati aumentano o diminuiscono a una velocità costante. Equazione: `y = a + b * x` |
| Logaritmico | Crea una linea curva di adattamento ottimale ed è utile quando il tasso di variazione nei dati aumenta o diminuisce rapidamente e poi si livella. Una linea di tendenza logaritmica può usare valori negativi e positivi. Equazione: `y = a + b * log(x)` |
| Esponenziale | Crea una linea curva ed è utile quando i dati aumentano o scendono a ritmi costantemente crescenti. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: `y = a + e^(b * x)` |
| Alimentazione | Crea una linea curva ed è utile per i set di dati che confrontano misurazioni che aumentano a una velocità specifica. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: `y = a * x^b` |
| Quadratico | Trova la soluzione ottimale per un set di dati a forma di parabola (concavo verso l’alto o il basso). Equazione: `y = a + b * x + c * x^2` |
