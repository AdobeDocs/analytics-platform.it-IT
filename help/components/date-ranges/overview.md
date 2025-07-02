---
description: Utilizza il calendario e gli intervalli di dati per specificare intervalli di date in Analysis Workspace.
title: Panoramica sugli intervalli di date
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 96%

---

# Panoramica degli intervalli di date

In un progetto Workspace, in genere si utilizza il [calendario in un pannello](/help/analysis-workspace/c-panels/panels.md#calendar) per specificare l’intervallo di date per le visualizzazioni in tale pannello.

I componenti intervallo di date consentono di definire e sovrascrivere le impostazioni del calendario per il pannello.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## Utilizzare intervalli di date

Puoi utilizzare un componente intervallo di date per ridefinire il calendario del pannello.

In alternativa, in una tabella a forma libera puoi utilizzare un intervallo di date come metrica o dimensione.

![Utilizzo di intervalli di date](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Metrica**. Ad esempio, per confrontare una dimensione per due mesi diversi per una metrica specifica.
- **Dimensione**. Per confrontare una metrica su diversi elementi dimensionali per la dimensione Intervallo date.

>[!NOTE]
>
>Quando si utilizzano intervalli di date in una tabella a forma libera, gli intervalli di date sovrascrivono il calendario specificato per il pannello a cui appartiene la tabella a forma libera.
>

Utilizza l’intervallo di date come [useresti qualsiasi componente](/help/components/overview.md#analysis-workspace-components). Trascina l’intervallo di date dal ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Date ranges]** del pannello dei componenti in:

- **[!UICONTROL Calendar]**: ![scambia](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** la configurazione del calendario corrente con l’intervallo di date.
- **Intestazione colonna Metrica**: ![sostituisci](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** la metrica, ![aggiungi ](/help/assets/icons/Add.svg)**[!UICONTROL Add]**&#x200B;l’intervallo di date come metrica o ![filtra](/help/assets/icons/Filter.svg)**[!UICONTROL Filter]**&#x200B;la metrica utilizzando il componente intervallo di date.
- **Intestazione colonna Dimensione**: ![sostituisci](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** le dimensioni correnti. La nuova dimensione è ora **[!UICONTROL Date ranges]**. Una volta che la dimensione è Intervalli di date, puoi ![aggiungere ](/help/assets/icons/Add.svg)**[!UICONTROL Add]**&#x200B;ulteriori intervalli di date come elementi dimensione.
- **Elemento dimensione**: ![raggruppa](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** l’elemento dimensione specifico in base all’intervallo di date.

Puoi anche aggiungere una colonna di intervalli di date direttamente in una visualizzazione tabella a forma libera:

1. In una colonna di metrica, seleziona dal menu di scelta rapida:

   - **[!UICONTROL Add time period column]**. Puoi scegliere tra le opzioni suggerite basate sul calendario corrente o creare un [intervallo di date personalizzato](#custom-date-ranges).
   - **[!UICONTROL Compare time periods]**. Puoi scegliere tra un’opzione suggerita basata sul calendario corrente o creare un [intervallo di date personalizzato](#custom-date-ranges).

1. In base alla selezione, alla tabella a forma libera vengono aggiunte altre colonne di intervalli di date.

## Intervalli di date predefiniti

Analysis Workspace fornisce una serie di intervalli di date predefiniti.


| Giorno | Settimana | Mese | Trimestre | Anno |
|---|---|---|---|---|
| Oggi | Questa settimana | Questo mese | Questo trimestre | Quest’anno |
| Ieri | Questa settimana (escluso oggi) | Questo mese (escluso oggi) | Questo trimestre (escluso oggi) | Quest’anno (escluso oggi) |
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

Puoi creare intervalli di date personalizzati. Consulta [Crea intervallo di date](/help/components/date-ranges/create.md) per le varie opzioni disponibili per la creazione di intervalli di date. Puoi quindi creare, modificare e salvare intervalli di date nel [Generatore di intervalli di date](create.md#date-range-builder).

Utilizza [Gestione intervallo di date](manage.md) per gestire gli intervalli di date.
