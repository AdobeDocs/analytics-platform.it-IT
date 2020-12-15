---
description: Utilizzare la visualizzazione delle linee per rappresentare set di dati con tendenza (basati sul tempo)
title: Linee
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 4f163e32787a732526511aeda5f6c1e32becb490
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 94%

---


# Linee

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

La visualizzazione delle linee rappresenta le metriche con linee che mostrano come cambiano i valori nel tempo. Un grafico a linee può essere usato solo con una dimensione temporale.

![Visualizzazione delle linee](assets/line-viz.png)

>[!IMPORTANT]
>
>Alcune impostazioni di visualizzazione delle linee, come [!UICONTROL Show trendline], sono attualmente in fase di test. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/landing/an-releases.html)

Fai clic sull’icona dell’ingranaggio in alto a destra della visualizzazione delle linee per accedere alle [**impostazioni di visualizzazione**](freeform-analysis-visualizations.md) disponibili. Le impostazioni sono suddivise in categorie:

* **Generali**: impostazioni comuni tra i tipi di visualizzazione
* **Asse**: impostazioni che influiscono sull’asse x o y della visualizzazione delle linee
* **Sovrapposizioni**: opzioni per aggiungere ulteriore contesto alla serie mostrata nella visualizzazione delle linee.

![Impostazioni di visualizzazione](assets/viz-settings-modal.png)

## Modifica granularità

Nelle [impostazioni di visualizzazione](freeform-analysis-visualizations.md), un elenco a discesa di granularità permette di cambiare una visualizzazione con tendenza (ad esempio un grafico a linee o a barre) da base giornaliera a settimanale, mensile e così via. La granularità viene aggiornata anche nella tabella dell’origine dati.

## Mostra minimo o massimo

In **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show min/max]** puoi sovrapporre un’etichetta di valore minimo e massimo per evidenziare rapidamente picchi e valli in una metrica. Nota: I valori min/max sono derivati dai punti di dati visibili nella visualizzazione, non dall’intero insieme di valori all’interno di una dimensione.

![Mostra minimo/massimo](assets/min-max-labels.png)

## Mostra la sovrapposizione della linea di tendenza

In **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show trendline]** puoi scegliere di aggiungere una linea di tendenza di regressione alla serie di linee. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati.

![Linee di tendenza lineare](assets/show-linear-trendline.png)

Tutti i modelli sono adattabili utilizzando il metodo dei minimi quadrati:

| Modello | Descrizione |
| --- | --- |
| Lineare | Crea una linea retta di adattamento per set di dati lineari semplici ed è utile quando i dati aumentano o diminuiscono a una velocità costante. Equazione: `y = a + b * x` |
| Logaritmico | Crea una linea curva di adattamento ed è utile quando il tasso di variazione nei dati aumenta o diminuisce rapidamente e poi si livella. Una linea di tendenza logaritmica può utilizzare valori negativi e positivi. Equazione: `y = a + b * log(x)` |
| Esponenziale | Crea una linea curva ed è utile quando i dati aumentano o diminuiscono a ritmi costantemente crescenti. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: `y = a + e^(b * x)` |
| Potenza | Crea una linea curva ed è utile per i set di dati che confrontano misurazioni che aumentano a una velocità specifica. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: `y = a * x^b` |
| Quadratico | Trova l’adattamento per un set di dati a forma di parabola (concava verso l’alto o verso il basso). Equazione: `y = a + b * x + c * x^2` |
