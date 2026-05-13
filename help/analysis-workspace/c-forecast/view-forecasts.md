---
description: Scopri come visualizzare le previsioni in una tabella o in un grafico a linee.
title: Visualizza previsioni
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
TQID: https://experienceleague.adobe.com/fihJQOI-CyvGccQsB0VxvwR-iV0OkJSMENaiciYrgFc
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: d13dba12-733d-4914-8d92-d643658bbe5d
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 372
ht-degree: 2%

---

# Visualizzare le previsioni

È possibile visualizzare le previsioni in una tabella a forma libera o in un grafico a linee.

## Visualizzare le previsioni in una tabella

È possibile visualizzare le previsioni in una tabella a forma libera di serie temporali. Quando [!UICONTROL Mostra previsione] è abilitato per la tabella a forma libera nelle [preferenze utente](../user-preferences.md), la previsione viene visualizzata automaticamente per la prima colonna di metriche aggiunta alla tabella. Per qualsiasi colonna aggiuntiva:

1. Seleziona l&#39;icona delle impostazioni della colonna ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) nell&#39;intestazione della colonna, quindi accertati che **[!UICONTROL Mostra previsione]** sia selezionato nell&#39;elenco delle opzioni. Per ulteriori informazioni, consulta la sezione [Impostazioni delle colonne](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Fare clic all&#39;esterno del menu **[!UICONTROL Impostazioni colonna]** per salvare l&#39;impostazione e visualizzare la tabella aggiornata.

Le previsioni sono indicate nella tabella come segue:

![Mostra previsione nella tabella](assets/show-forecast-table.png)

* Il valore di previsione e la percentuale per ogni cella vengono visualizzati in **grigio scuro**.
* Per indicare un valore di previsione, nell&#39;angolo superiore destro della cella viene visualizzato il simbolo di previsione ![ForecastAnalytics](/help/assets/icons/ForecastAnalytics.svg).


## Visualizza previsioni in un grafico a linee

Un grafico a linee è l’unica visualizzazione che consente di visualizzare le previsioni.

1. Seleziona l&#39;icona delle impostazioni ![Impostazioni colonna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) nell&#39;intestazione della visualizzazione, quindi accertati che **[!UICONTROL Mostra previsione]** sia selezionato nell&#39;elenco delle opzioni.

1. (facoltativo) Per consentire alle previsioni di scalare correttamente il grafico, selezionare **[!UICONTROL Consenti scalabilità previsione sull&#39;asse Y]**. Questa opzione non è selezionata per impostazione predefinita perché a volte può rendere un grafico meno leggibile.

1. Fare clic all&#39;esterno del menu **[!UICONTROL Impostazioni]** per visualizzare il grafico a linee aggiornato.

Le previsioni vengono visualizzate nel grafico a linee come segue:

![Mostra previsione nel grafico a linee](assets/show-forecast-linechart.png)

* I valori correnti per le metriche nel grafico a linee sono indicati da una barra verticale. Se passi il cursore del mouse su quella linea verticale, viene visualizzato un pop-up con l’ultima data corrente.
* I valori previsti per una o più metriche vengono visualizzati a destra della barra verticale utilizzando linee tratteggiate. Puoi passare il cursore sopra qualsiasi punto dati per una metrica. Verrà visualizzata una finestra a comparsa con:
   * data della previsione
   * valore previsto per la metrica
   * limite superiore del valore previsto per la metrica
   * limite inferiore del valore previsto per la metrica
* L&#39;area ombreggiata mostra la fascia di affidabilità della previsione.
