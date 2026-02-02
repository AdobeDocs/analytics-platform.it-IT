---
title: Seleziona Un Intervallo Di Dati In Report Builder
description: Scopri come selezionare un intervallo di date in Report Builder.
role: User
feature: Report Builder
type: Documentation
exl-id: 7252214f-a7d6-451b-99c9-d39e8e47120b
solution: Customer Journey Analytics
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 7%

---

# Selezionare un intervallo di date

Per modificare l’intervallo di date di un blocco di dati esistente:

- Seleziona **[!UICONTROL Modifica un blocco di dati]**, oppure
- Seleziona il collegamento **[!UICONTROL Intervallo date]** in **[!UICONTROL Modifica rapida]**.

Utilizza le seguenti opzioni per modificare un intervallo di date per un blocco di dati.

## Calendario

L&#39;opzione **[!UICONTROL Calendario]** consente di creare date statiche o continue utilizzando le opzioni seguenti:

### Intervallo date

Nel campo intervallo di date viene visualizzato l’intervallo di date corrente per la richiesta di blocco di dati. Puoi immettere le date direttamente oppure utilizzare ![Calendario](/help/assets/icons/Calendar.svg) per specificare un intervallo di date.

![Calendario intervallo date](assets/date-range-calendar.png){zoomable="yes"}

### Predefiniti

Utilizza il menu a discesa dei predefiniti per selezionare un predefinito. Potete anche immettere del testo per cercare dei predefiniti.

![Predefiniti per intervalli di date](assets/date-range-presets.png){zoomable="yes"}

Il menu a discesa dei predefiniti include un set standard di intervalli di date predefiniti e componenti per intervalli di date per una visualizzazione dati salvata o condivisa con te.

### Date di rotazione

Per definire le date di rotazione:

![Date di rotazione USA](assets/date-range-rolling-date.png){zoomable="yes"}

1. Selezionare **[!UICONTROL Utilizza date continue]** per definire la logica per una definizione di data continua. Puoi selezionare il testo tra parentesi (ad esempio **[!UICONTROL inizio fisso - giorno continuo]**) per estendere il pannello e specificare i dettagli per **[!UICONTROL Inizio]** e **[!UICONTROL Fine]**.

1. Seleziona **[!UICONTROL Inizio di]**, **[!UICONTROL Fine di]** o **[!UICONTROL Giorno fisso]**.

   - Dopo aver selezionato **[!UICONTROL Inizio di]** o **[!UICONTROL Fine di]**, puoi creare un&#39;espressione completa. Ad esempio: **[!UICONTROL Fine di]** **[!UICONTROL anno corrente]** **[!UICONTROL più]** `1` **[!UICONTROL giorno]**. Seleziona il valore appropriato per ogni singola parte dell’espressione.

      - Seleziona un valore corrente. Ad esempio, **[!UICONTROL anno corrente]**.
      - Selezionare un valore per un calcolo aggiuntivo facoltativo. Ad esempio, **[!UICONTROL più]**.
      - Dopo aver specificato un calcolo aggiuntivo, specifica un valore. Ad esempio: `1`.
      - Dopo aver specificato un calcolo aggiuntivo, seleziona il periodo di tempo da utilizzare per il calcolo. Ad esempio, **[!UICONTROL giorno]**.

   - Dopo aver selezionato **[!UICONTROL Giorno fisso]**, specificare un giorno fisso o utilizzare il selettore per selezionare un giorno.

1. Seleziona **[!UICONTROL nascondi]** per nascondere i dettagli del calcolo delle date di rotazione.


### Espressioni personalizzate

L’opzione di espressione personalizzata consente di modificare l’intervallo di date creando un’espressione personalizzata oppure di immettere una formula aritmetica.

![Espressione personalizzata intervallo di date](assets/date-range-custom-expression.png){zoomable="yes"}

1. Seleziona **[!UICONTROL Utilizza date continue]**.

1. Selezionare **[!UICONTROL Usa espressione personalizzata]**.

   Quando si seleziona **[!UICONTROL Usa espressione personalizzata]**, i controlli standard dell&#39;intervallo di date continuo sono disattivati.

1. Immetti un&#39;[espressione personalizzata](#create-a-custom-expression).

1. Utilizza **[!UICONTROL Anteprima data]** per verificare l&#39;intervallo di date risultante.

#### Creare un’espressione personalizzata

1. Immetti un [riferimento data](#date-references).

1. Aggiungi un operatore [date](#date-operators) facoltativo per spostare la data nel passato o nel futuro.

È possibile immettere un&#39;espressione personalizzata che includa più operatori, ad esempio `tm-11m-1d`.

#### Riferimenti data

Nella tabella seguente sono elencati alcuni esempi di riferimenti di date.

| Riferimento data | Tipo | Descrizione |
|----------------|--------------|----------------------------|
| `1/1/10` | Data statica | Immesso in formato data ISO |
| `td` | Data continua | Inizio del giorno corrente |
| `tw` | Data continua | Inizio della settimana corrente |
| `tm` | Data continua | Inizio del mese corrente |
| `tq` | Data continua | Inizio del trimestre corrente |
| `ty` | Data continua | Inizio dell&#39;anno corrente |

#### Operatori di data

Nella tabella seguente sono elencati alcuni esempi di operatori di date.

| Operatore data | Unità | Descrizione |
|----------------|---------|--------------------|
| `+6d` | Giorno | Aggiungi 6 giorni alla data di riferimento |
| `+1w` | Settimana | Aggiungi una settimana intera alla data di riferimento |
| `-2m` | Mese | Sottrarre 2 mesi interi alla data di riferimento |
| `-4q` | Trimestre | Sottrarre 4 trimestri alla data di riferimento |
| -`1y` | Anno | Sottrai un anno alla data di riferimento |

#### Espressioni data

Nella tabella seguente sono elencati alcuni esempi di espressioni di data.

| Espressione data | Significato |
|-----------------|--------------------------------------|
| `td` | Oggi |
| `td-1w` | Primo giorno della settimana scorsa |
| `tm-1d` | Ultimo giorno del mese precedente |
| `td-52w` | Lo stesso giorno, 52 settimane fa |
| `tm-11m-1d` | Ultimo giorno dello stesso mese lo scorso anno |
| `"2020-09-06"` | Data specifica, 9 settembre 2020 |



## Intervallo di date dalla cella

L&#39;intervallo di date può essere specificato nelle celle del foglio di lavoro. Utilizza l&#39;opzione **[!UICONTROL Intervallo date dalla cella]** per scegliere la data di inizio e di fine del blocco di dati dalle celle selezionate. Quando selezioni l&#39;opzione **[!UICONTROL From cell]**, nel pannello vengono visualizzati **[!UICONTROL From]** e **[!UICONTROL To]** campi in cui puoi immettere una posizione di cella o utilizzare ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) per scegliere la cella selezionata corrente.

![Selezionare dalla cella Sheet1!H4 a Sheet1!I4](./assets/date-range-from-cell.png){zoomable="yes"}


## Escludi oggi

Seleziona **[!UICONTROL Escludi oggi]** per escludere oggi da un intervallo di date selezionato. Il giorno corrente è escluso da tutte le modalità utilizzate per definire un intervallo di date: calendario, date continue o espressioni personalizzate.


## Intervalli di date validi

Nell’elenco seguente sono descritti i formati di intervalli di date validi.

- Le date di inizio e fine devono essere nel formato seguente: AAAA-MM-GG

- La data di inizio deve essere precedente o uguale alla data di fine. Entrambe le date possono essere impostate sul futuro.

- Quando si utilizzano date continue, la data di inizio deve essere oggi o nel passato. Il giorno di inizio deve essere nel passato se si seleziona **[!UICONTROL Escludi oggi]**.

- Puoi creare un intervallo di date statico impostato per il futuro. Ad esempio, potrebbe essere necessario impostare una data futura per il lancio di una campagna di marketing la prossima settimana. Questa opzione crea in anticipo un monitoraggio della cartella di lavoro per una campagna.

## Modificare l’intervallo di date

Puoi modificare l’intervallo di date di un blocco di dati esistente.

1. Seleziona una cella nel blocco di dati.

- Selezionare **[!UICONTROL Modifica blocco dati]** nel pannello **[!UICONTROL Comandi]** oppure
- Seleziona il collegamento **[!UICONTROL Intervallo date]** nel pannello **[!UICONTROL Modifica rapida]**.

1. Modifica l’intervallo di date utilizzando una qualsiasi delle opzioni di selezione della data disponibili.

1. Seleziona **[!UICONTROL Applica]**.

Report Builder applica il nuovo intervallo di date a tutti i blocchi di dati della selezione.
