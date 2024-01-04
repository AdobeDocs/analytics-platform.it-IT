---
description: Utilizza la visualizzazione delle linee per rappresentare set di dati con tendenze (basati sul tempo)
title: Linee
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 84%

---

# Linee

>[!NOTE]
>
>La visualizzazione Linee sarà presto disponibile [sottotitoli intelligenti](/help/analysis-workspace/visualizations/intelligent-captions.md).

La visualizzazione delle linee rappresenta le metriche con linee che mostrano come cambiano i valori nel tempo. Un grafico a linee può essere usato solo con una dimensione temporale.

![Visualizzazione delle linee](assets/line-viz.png)

Fai clic sull’icona dell’ingranaggio in alto a destra della visualizzazione delle linee per accedere alle [**impostazioni di visualizzazione**](freeform-analysis-visualizations.md) disponibili. Le impostazioni sono suddivise in categorie:

* **Generali**: impostazioni comuni tra i tipi di visualizzazione
* **Asse**: impostazioni che influiscono sull’asse x o y della visualizzazione delle linee
* **Sovrapposizioni**: opzioni per aggiungere ulteriore contesto alla serie mostrata nella visualizzazione delle linee.

![Impostazioni di visualizzazione](assets/viz-settings-modal.png)

## Modifica granularità

Nelle [impostazioni di visualizzazione](freeform-analysis-visualizations.md), un elenco a discesa di granularità permette di cambiare una visualizzazione con tendenza (ad esempio un grafico a linee o a barre) da base giornaliera a settimanale, mensile e così via. La granularità viene aggiornata anche nella tabella dell’origine dati.

## Mostra minimo o massimo

In **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show min/max]** puoi sovrapporre un’etichetta di valore minimo e massimo per evidenziare rapidamente picchi e valli in una metrica. Nota: i valori minimo/massimo sono derivati dai punti di dati visibili nella visualizzazione e non dall’intero insieme di valori all’interno di una dimensione.

![Una sovrapposizione con l’etichetta di valore minimo e massimo.](assets/min-max-labels.png)

## Mostra la sovrapposizione della linea di tendenza

In **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show trendline]**, puoi scegliere di aggiungere alla serie di linee una linea di tendenza di regressione o di media mobile. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati.

>[!TIP]
>
>Si consiglia di applicare le linee di tendenza ai dati che non includono la data odierna (dati parziali) o date future, in quanto queste potrebbero distorcere la linea di tendenza. Tuttavia, se devi includere date future, rimuovi gli zeri dai dati per evitare distorsioni per quei giorni. A questo scopo, vai alla tabella dell’origine dati della visualizzazione, scegli la colonna della metrica desiderata, quindi abilita **[!UICONTROL Column Settings]** > **[!UICONTROL Interpret zero as no value]**.

![Linee di tendenza lineare](assets/show-linear-trendline.png)

Tutte le linee di tendenza del modello di regressione sono adattabili utilizzando i minimi quadrati ordinari:

| Modello | Descrizione |
| --- | --- |
| Lineare | Crea una linea retta di adattamento per set di dati lineari semplici ed è utile quando i dati aumentano o diminuiscono a una velocità costante. Equazione: `y = a + b * x` |
| Logaritmico | Crea una linea curva di adattamento ed è utile quando il tasso di variazione nei dati aumenta o diminuisce rapidamente e poi si livella. Una linea di tendenza logaritmica può utilizzare valori negativi e positivi. Equazione: `y = a + b * log(x)` |
| Esponenziale | Crea una linea curva ed è utile quando i dati aumentano o diminuiscono a ritmi costantemente crescenti. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: `y = a + e^(b * x)` |
| Potenza | Crea una linea curva ed è utile per i set di dati che confrontano misurazioni che aumentano a una velocità specifica. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: `y = a * x^b` |
| Quadratico | Trova l’adattamento ottimale per un set di dati a forma di parabola (concava verso l’alto o verso il basso). Equazione: `y = a + b * x + c * x^2` |
| Media mobile | Crea una linea di tendenza uniforme in base a un insieme di medie. Anche nota come media continua, la media mobile utilizza un numero specifico di punti di dati (determinati da una selezione di periodi), ne calcola la media e utilizza tale media come punto sulla linea. Alcuni esempi includono la media mobile di 7 giorni o una media mobile di 4 settimane. |
