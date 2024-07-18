---
description: Scopri come visualizzare le previsioni in una tabella o in un grafico a linee.
title: Come visualizzare le previsioni in Analysis Workspace
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
source-git-commit: fea1b12a594a820ab2e55f850ca95c5a373184f0
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 3%

---

# Visualizzare previsioni in Analysis Workspace

È possibile visualizzare le previsioni in una tabella a forma libera o in un grafico a linee.

## Visualizzare le previsioni in una tabella

È possibile visualizzare le previsioni in una tabella a forma libera di serie temporali. Quando [!UICONTROL Show forecast] è abilitato per la tabella a forma libera in [preferenze utente](../user-preferences.md), la previsione viene visualizzata automaticamente per la prima colonna di metriche aggiunta alla tabella. Per qualsiasi colonna aggiuntiva:

1. Seleziona l&#39;icona delle impostazioni della colonna ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) nell&#39;intestazione della colonna, quindi accertati che **[!UICONTROL Show forecast]** sia selezionato nell&#39;elenco delle opzioni. Per ulteriori informazioni, consulta la sezione [Impostazioni delle colonne](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Fare clic all&#39;esterno del menu **[!UICONTROL Column settings]** per salvare l&#39;impostazione e visualizzare la tabella aggiornata.

Le previsioni sono indicate nella tabella come segue:

![Mostra previsione nella tabella](assets/show-forecast-table.png)

* Il valore di previsione e la percentuale per ogni cella vengono visualizzati in **grigio scuro**.
* Per indicare un valore di previsione, un simbolo di previsione <img src="./assets/forecast.svg" alt="Simbolo previsione" width="20" /> viene visualizzato nell&#39;angolo superiore destro della cella.


## Visualizza previsioni in un grafico a linee

Un grafico a linee è l’unica visualizzazione che consente di visualizzare le previsioni.

1. Seleziona l&#39;icona delle impostazioni ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) nell&#39;intestazione della visualizzazione, quindi accertati che **[!UICONTROL Show forecast]** sia selezionato nell&#39;elenco delle opzioni.

1. (facoltativo) Per consentire alle previsioni di scalare correttamente il grafico, selezionare **[!UICONTROL Allow forecast to scale Y-axis]**. Questa opzione non è selezionata per impostazione predefinita perché a volte può rendere un grafico meno leggibile.

1. Fare clic all&#39;esterno del menu **[!UICONTROL Settings]** per visualizzare il grafico a linee aggiornato.

Le previsioni vengono visualizzate nel grafico a linee come segue:

![Mostra previsione nel grafico a linee](assets/show-forecast-linechart.png)

* I valori correnti per le metriche nel grafico a linee sono indicati da una barra verticale. Se passi il cursore del mouse su quella linea verticale, viene visualizzato un pop-up con l’ultima data corrente.
* I valori previsti per una o più metriche vengono visualizzati a destra della barra verticale utilizzando linee tratteggiate. Puoi passare il cursore sopra qualsiasi punto dati per una metrica. Verrà visualizzata una finestra a comparsa con:
   * data della previsione
   * valore previsto per la metrica
   * limite superiore del valore previsto per la metrica
   * limite inferiore del valore previsto per la metrica
* L&#39;area ombreggiata mostra la fascia di affidabilità della previsione.
