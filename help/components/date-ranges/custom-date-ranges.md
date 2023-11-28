---
description: Crea intervalli di date personalizzati in Analysis Workspace e salvali come componenti Tempo.
keywords: Analysis Workspace
title: Creazione di intervalli di date personalizzati
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 85%

---

# Creazione di intervalli di date personalizzati

Crea intervalli di date personalizzati in Analysis Workspace e salvali come componenti Tempo.

**[!UICONTROL Components]** (Componenti) > **[!UICONTROL New Date Range]** (Nuovo intervallo di dati)

Un intervallo di date si applica a livello del pannello. Per aggiungere al progetto un intervallo di date, fai clic su **Panels** (Pannelli) > *`<select panel>`* e specifica un nuovo intervallo di date.

## Intervallo di date per “Due mesi fa” 

Il seguente intervallo di date personalizzato mostra un intervallo per “due mesi fa”, con una visualizzazione del riepilogo delle modifiche che mostra i cambiamenti direzionali.

![Generatore di intervalli di date che mostra Usa date continue per due mesi fa](assets/date-range-two-months-ago.png)

L’intervallo di date personalizzato viene visualizzato nella parte superiore del pannello dei componenti [!UICONTROL Date Range] (Intervallo date) all’interno del progetto:

![Pannello del componente Intervallo date con freccia rivolta a Due mesi fa.](assets/date-range-panel-two-months-ago.png)

Puoi trascinare l’intervallo di date personalizzato all’interno di una colonna vicino a un intervallo di date continuo mensile personalizzato, utilizzando l’impostazione predefinita Mese precedente per un confronto. Aggiungi una visualizzazione di riepilogo delle modifiche e seleziona i totali da ogni colonna per mostrare il cambiamento direzionale:

![Variazione sintetica che mostra e aumenta del 14,45%.](assets/date-range-two-months-table.png)

## Utilizzare un intervallo di date continuo di 7 giorni

Un intervallo di date si applica a livello del pannello. Per aggiungere al progetto un intervallo di date, fai clic su **Azioni** > **Aggiungi pannello** e specifica un nuovo intervallo di date.

Nel Generatore intervalli di date, puoi creare un intervallo di date personalizzato che viene visualizzato nel pannello Componenti insieme agli altri intervalli di date.

Ad esempio, puoi creare un intervallo di date che specifica una finestra di 7 giorni che termina una settimana fa:

![Generatore di intervalli di date che mostra un intervallo di date che specifica una finestra continua di 7 giorni.](assets/create_date_range.png)

Seleziona *`rolling daily`*.

* Le impostazioni Inizio corrispondono a *`current day minus 14 days`* (data attuale meno 14 giorni).

* Le impostazioni Fine corrispondono a *`current day minus 7 days`* (data attuale meno 7 giorni).

L’intervallo di date può diventare un componente da trascinare in qualsiasi tabella a forma libera.
