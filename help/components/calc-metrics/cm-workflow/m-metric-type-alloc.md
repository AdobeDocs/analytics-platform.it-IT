---
description: Scopri il tipo di metrica e l’attribuzione
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 304b8d85767d89ee60a6fb37a128194f60ca89d4
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 92%

---

# Tipo di metrica e attribuzione

Puoi configurare il tipo di metrica e il [modello di attribuzione](#attribution-models) per una metrica in una definizione di metrica calcolata.

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg) nel componente metrica.
1. Nella finestra di dialogo popup:

   ![Tipo di metrica e attribuzione](assets/cm-type-alloc.png)

   * Specifica il **[!UICONTROL Metric type]**:

     | Tipi di metriche | Definizione |
     |---|---|
     | **[!UICONTROL Standard]** | Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singolo elemento di riga. <p>Ad esempio, ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** prende gli ordini per quell’elemento di riga specifico e lo divide per il numero di sessioni per quell’elemento di riga specifico. |
     | **[!UICONTROL Grand total]** | Utilizza **[!UICONTROL Grand total]** per il periodo di reporting in ogni elemento di riga. Se una formula è costituita da una singola metrica Totale complessivo, la metrica calcolata visualizza lo stesso numero Totale complessivo su ogni elemento di riga. Le metriche del totale complessivo sono utili quando desideri creare metriche calcolate che si confrontano con i dati totali. <p>Ad esempio, ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]** mostra la proporzione degli ordini rispetto a tutte le sessioni, non solo le sessioni rispetto all’elemento di riga specifico. In questo esempio, specifica **[!UICONTROL Grand Total]** per la metrica ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** nella metrica calcolata, che la trasformerà automaticamente in ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]**. |

   * Specifica **[!UICONTROL Attribution]**.

      1. Puoi:

         * Disabilitare **[!UICONTROL Use non-default attribution model]** per utilizzare il modello di attribuzione colonna predefinito, ovvero Ultimo contatto, con un intervallo di lookback di 30 giorni.
         * Abilitare **[!UICONTROL Use non-default attribution model]**. Nella finestra di dialogo **[!UICONTROL Column attribution model]**

            * Seleziona **[!UICONTROL Model]** dai [modelli di attribuzione](#attribution-models).
            * Seleziona **[!UICONTROL Container]** dalle opzioni [container](#container).
            * Seleziona **[!UICONTROL Lookback window]** dalle opzioni dell&#39;[intervallo di lookback](#lookback-window). Se si seleziona **[!UICONTROL Custom Time]**, è possibile definire il periodo di tempo in **[!UICONTROL Minute(s)]** fino a **[!UICONTROL Quarter(s)]**.

      1. Seleziona **[!UICONTROL Apply]** per applicare il modello di attribuzione non predefinito. Seleziona Annulla per annullare.

     Se hai già definito un modello di attribuzione non predefinito, seleziona **[!UICONTROL Edit]** per modificare la selezione.

Consulta [Esempio](#example) per un esempio di utilizzo di un modello di attribuzione, un contenitore e un intervallo di lookback.


## Modelli di attribuzione {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Usa modello di attribuzione non predefinito"
>abstract="Abilita un modello di attribuzione non predefinito per la metrica selezionata."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modello"
>abstract="Seleziona un modello di attribuzione per la metrica."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Ultimo contatto"
>abstract="Il 100% del credito va all’ultimo valore di dimensione visualizzato da un visitatore."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Primo contatto"
>abstract="Il 100% del credito va al primo valore di dimensione visualizzato da un visitatore."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Lineare"
>abstract="Il credito è distribuito in modo uniforme tra tutti i valori di dimensione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Partecipazione"
>abstract="Il 100% del credito va a ogni valore di dimensione visualizzato da un visitatore.<br/>I totali delle colonne sono sovrastimati."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Stesso contatto"
>abstract="Il credito viene assegnato solo ai valori di dimensione che si verificano nello stesso evento come la conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Stesso contatto"
>abstract="Il credito viene assegnato solo ai valori di dimensione che si verificano nello stesso evento come la conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="A forma di U"
>abstract="Il 40% del credito va al primo valore di dimensione, il 40% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Curva J"
>abstract="Il 60% del credito va all’ultimo valore di dimensione, il 20% al primo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="Curva J"
>abstract="Il 60% del credito va all’ultimo valore di dimensione, il 20% al primo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J inversa"
>abstract="Il 60% del credito va al primo valore di dimensione, il 20% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="J inversa"
>abstract="Il 60% del credito va al primo valore di dimensione, il 20% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Decadimento nel tempo"
>abstract="Il merito maggiore viene attribuito ai valori di dimensione più vicini nel tempo a una conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personalizzato"
>abstract="Definisci una ponderazione di attribuzione basata sulla posizione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personalizzato"
>abstract="Definisci una ponderazione di attribuzione basata sulla posizione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algoritmico"
>abstract="Il credito è determinato dinamicamente su un algoritmo statistico."

{{attribution-models-details}}


## Contenitore {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Contenitore"
>abstract="Seleziona un contenitore per impostare l’ambito desiderato per l’attribuzione."

{{attribution-container}}


## Intervallo di lookback {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Intervallo di lookback"
>abstract="Questa impostazione determina la finestra di attribuzione dei dati che verrà applicata a per ogni conversione."

{{attribution-lookback-window}}




## Esempio

{{attribution-example}}

>[!MORELIKETHIS]
>
>[Impostazioni dei componenti di attribuzione](/help/data-views/component-settings/attribution.md)
>>[Metrica di partecipazione](participation-metric.md)
>

