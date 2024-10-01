---
title: Panoramica degli intervalli di date
description: Scopri cosa sono gli intervalli di date e come utilizzarli nel reporting.
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 4%

---

# Panoramica degli intervalli di date

In un progetto Workspace, in genere si utilizza il [calendario in un pannello](/help/analysis-workspace/c-panels/panels.md#calendar) per specificare l&#39;intervallo di date per le visualizzazioni in tale pannello.

I componenti dell’intervallo di date consentono di definire e modificare le impostazioni del calendario per il pannello.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## Utilizzare intervalli di date

Puoi utilizzare un componente intervallo di date per ridefinire il calendario del pannello.

In alternativa, puoi utilizzare un intervallo di date in una tabella a forma libera come metrica o dimensione.

![Utilizzo intervallo di date](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Metrica**. Ad esempio, per confrontare una dimensione per due mesi diversi per una metrica specifica.
- **Dimension**. Confrontare una metrica su diversi elementi dimensionali per la dimensione Intervallo date.

>[!NOTE]
>
>Quando si utilizzano intervalli di date in una tabella a forma libera, gli intervalli di date hanno la precedenza sul calendario specificato per il pannello a cui appartiene la tabella a forma libera.
>

L&#39;intervallo di date viene utilizzato come [qualsiasi componente](/help/components/overview.md#analysis-workspace-components). Trascina l&#39;intervallo di date dal pannello dei componenti ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Date ranges]** e rilascia il componente in:

- **[!UICONTROL Calendar]**: ![Cambiare](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** la configurazione del calendario corrente con l&#39;intervallo di date.
- **Intestazione colonna metrica**: ![Cambia](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** la metrica, ![Aggiungi ](/help/assets/icons/Add.svg)**[!UICONTROL Add]**l&#39;intervallo di date come metrica o ![Filtra](/help/assets/icons/Filter.svg)**[!UICONTROL Filter]**la metrica utilizzando il componente intervallo di date.
- **Intestazione colonna Dimension**: ![Passare](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** alle dimensioni correnti. La nuova dimensione è ora **[!UICONTROL Date ranges]**. Una volta che la dimensione è Intervalli di date, puoi ![Aggiungere ](/help/assets/icons/Add.svg)**[!UICONTROL Add]**intervalli di date aggiuntivi come elementi dimensione.
- **Elemento Dimension**: ![Suddividi](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** l&#39;elemento dimensione specifico in base all&#39;intervallo di date.

Puoi anche aggiungere una colonna di intervalli di date direttamente in una visualizzazione a forma libera:

1. In una colonna di metriche, seleziona dal menu di scelta rapida:

   - **[!UICONTROL Add time period column]** (Autenticazione): Puoi scegliere tra le opzioni suggerite basate sul calendario corrente o creare un [intervallo di date personalizzato](#custom-date-ranges).
   - **[!UICONTROL Compare time periods]** (Autenticazione): Puoi scegliere tra un&#39;opzione suggerita basata sul calendario corrente o creare un [intervallo di date personalizzato](#custom-date-ranges).

1. In base alla selezione, alla tabella a forma libera vengono aggiunte colonne aggiuntive di intervalli di date.

## Intervalli di date predefiniti

Analysis Workspace fornisce una serie di intervalli di date predefiniti.


| Giorno | Settimana | Mese | Trimestre | Anno |
|---|---|---|---|---|
| Oggi | Questa settimana | Questo mese | Questo trimestre | Quest&#39;anno |
| Ieri | Questa settimana (escluso oggi) | Questo mese (escluso oggi) | Questo trimestre (escluso oggi) | Quest&#39;anno (escluso oggi) |
| 2 giorni fa | 2 settimane fa | 2 mesi fa |   |  |
| 3 giorni fa | 3 settimane fa | 3 mesi fa |  | |
| Ultimi 7 giorni | Ultima settimana | Ultimo mese | Ultimo trimestre | L’anno scorso |
| Ultimi 14 giorni | Ultime 2 settimane intere | Ultimi 2 mesi interi | Ultimi 4 trimestri interi | |
| Ultimi 30 giorni | Ultime 3 settimane intere | Ultimi 3 mesi interi | | |
| Ultimi 60 giorni | Ultime 4 settimane intere | Ultimi 6 mesi interi | | |
| Ultimi 90 giorni | Ultime 12 settimane intere | Ultimi 12 mesi interi | | |
| Ultimi 7 giorni interi | Ultime 52 settimane intere | Ultimi 13 mesi interi | | |
| Ultimi 14 giorni interi | | | | |
| Ultimi 30 giorni interi | | | | |
| Ultimi 90 giorni interi | | | | |

<table style="table-layout:fixed">

## Intervalli di date personalizzati

Puoi creare intervalli di date personalizzati. Consulta [Crea intervallo di date](/help/components/date-ranges/create.md) per le varie opzioni disponibili per la creazione di intervalli di date. Puoi quindi generare, modificare e salvare intervalli di date nel generatore di intervalli di date [](create.md#date-range-builder).

Utilizza il [gestore degli intervalli di date](manage.md) per gestire gli intervalli di date.
