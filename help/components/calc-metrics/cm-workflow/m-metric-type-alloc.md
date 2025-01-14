---
description: Scopri il tipo di metrica e l’attribuzione
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 41%

---

# Tipo di metrica e attribuzione

È possibile configurare il tipo di metrica e il [modello di attribuzione](#attribution-models) per una metrica in una definizione di metrica calcolata.

1. Selezionare ![Impostazione](/help/assets/icons/Setting.svg) nel componente metrica.
1. Nella finestra di dialogo a comparsa:

   ![Tipo di metrica e attribuzione](assets/cm-type-alloc.png)

   * Specificare **[!UICONTROL Metric type]**:

     | Tipi di metriche | Definizione |
     |---|---|
     | **[!UICONTROL Standard]** | Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singola riga. <p>Ad esempio, ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** prende gli ordini per quell&#39;elemento riga specifico e lo divide per il numero di sessioni per quell&#39;elemento riga specifico. |
     | **[!UICONTROL Grand total]** | Utilizza **[!UICONTROL Grand total]** per il periodo di reporting in ogni elemento di riga. Se una formula è costituita da una singola metrica Totale complessivo, la metrica calcolata visualizza lo stesso numero Totale complessivo su ogni riga. Le metriche del totale complessivo sono utili quando si desidera creare metriche calcolate che si confrontano con i dati totali. <p>Ad esempio, ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]** mostra la proporzione degli ordini rispetto a tutte le sessioni, non solo le sessioni rispetto all&#39;elemento riga specifico. In questo esempio si specifica **[!UICONTROL Grand Total]** per la metrica ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** nella metrica calcolata, che la trasformerà automaticamente in ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]**. |

   * Specificare **[!UICONTROL Attribution]**.

      1. Puoi effettuare le seguenti operazioni:

         * Disabilita **[!UICONTROL Use non-default attribution model]** per utilizzare il modello di attribuzione colonna predefinito, ovvero Ultimo contatto, con un intervallo di lookback di 30 giorni.
         * Abilita **[!UICONTROL Use non-default attribution model]**. Nella finestra di dialogo **[!UICONTROL Column attribution model]**

            * Seleziona **[!UICONTROL Model]** dai modelli di attribuzione.
            * Seleziona **[!UICONTROL Lookback window]**. Se si seleziona **[!UICONTROL Custom Time]**, è possibile definire il periodo di tempo in **[!UICONTROL Minute(s)]** fino a **[!UICONTROL Quarter(s)]**. Per ulteriori informazioni, vedere [Intervallo di lookback](#lookback-window)

      1. Selezionare **[!UICONTROL Apply]** per applicare il modello di attribuzione non predefinito. Seleziona Annulla per annullare.

     Se hai già definito un modello di attribuzione non predefinito, seleziona **[!UICONTROL Edit]** per modificare la selezione.

Consulta [Esempio](#example) per un esempio di utilizzo di un modello di attribuzione e di un intervallo di lookback.


## Attribuzione {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Usa modello di attribuzione non predefinito"
>abstract="Abilita un modello di attribuzione non predefinito per la metrica selezionata."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modello"
>abstract="Seleziona un modello di attribuzione per la metrica."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Ultimo contatto"
>abstract="Il 100% del credito va all’ultimo valore di dimensione visualizzato da un visitatore."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Primo contatto"
>abstract="Il 100% del credito va al primo valore di dimensione visualizzato da un visitatore."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Lineare"
>abstract="Il credito è distribuito in modo uniforme tra tutti i valori di dimensione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Partecipazione"
>abstract="Il 100% del credito va a ogni valore di dimensione visualizzato da un visitatore.<br/>I totali delle colonne sono sovrastimati."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Stesso contatto"
>abstract="Il credito viene assegnato solo ai valori di dimensione che si verificano nello stesso evento come la conversione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="A forma di U"
>abstract="Il 40% del credito va al primo valore di dimensione, il 40% all’ultimo, il 20% condiviso dal centro."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Curva J"
>abstract="Il 60% del credito va all’ultimo valore di dimensione, il 20% al primo, il 20% condiviso dal centro."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J inversa"
>abstract="Il 60% del credito va al primo valore di dimensione, il 20% all’ultimo, il 20% condiviso dal centro."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Decadimento nel tempo"
>abstract="Il merito maggiore viene attribuito ai valori di dimensione più vicini nel tempo a una conversione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personalizzato"
>abstract="Definisci una ponderazione di attribuzione basata sulla posizione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algoritmico"
>abstract="Il credito è determinato dinamicamente su un algoritmo statistico."

<!-- markdownlint-enable MD034 -->


{{attribution-models-details}}


### Intervallo di lookback {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Intervallo di lookback"
>abstract="Questa impostazione determina la finestra di attribuzione dei dati che verrà applicata a per ogni conversione."

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### Esempio di attribuzione {#attribution-example}

Prendi in considerazione l’esempio seguente:

1. Il 15 settembre, una persona arriva sul tuo sito tramite un annuncio pubblicitario di ricerca a pagamento, poi se ne va.
1. Il 18 settembre, la persona ritorna sul tuo sito tramite un collegamento social media ricevuto da un amico. Aggiunge diversi articoli al carrello, ma non acquista nulla.
1. Il 24 settembre, il team marketing gli invia un’e-mail con un coupon da utilizzare su alcuni degli elementi nel carrello. Applica il coupon, ma visita diversi altri siti per vedere se sono disponibili altri coupon. Ne trova un altro tramite un annuncio pubblicitario, quindi completa un acquisto dal valore di 50 $.

A seconda dell’intervallo di lookback e del modello di attribuzione definiti, ai canali saranno assegnati crediti diversi. Di seguito sono riportati alcuni esempi:

* Utilizzando **il primo contatto** e un intervallo di lookback di **sessione**, l&#39;attribuzione considera solo la terza visita. Tra e-mail e visualizzazione, e-mail è avvenuta prima, quindi e-mail ottiene 100% di credito per l’acquisto di 50 $.

* Utilizzando **il primo contatto** e un intervallo di lookback di **persona**, l&#39;attribuzione esamina tutte e tre le visite. La ricerca a pagamento è avvenuta prima, quindi ottiene il 100% di credito per l’acquisto di 50 $.

* Utilizzando **linear** e un intervallo di lookback di **sessione**, il credito è suddiviso tra e-mail e visualizzazione. Entrambi questi canali ricevono un credito di 25 $.
Utilizzando **linear** e un intervallo di lookback di **persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Ogni canale ottiene un credito di 12,50 $ per questo acquisto.

* Utilizzando **a forma di J** e un intervallo di lookback di **persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione.

   * Il 60% di credito è assegnato alla visualizzazione, per un valore di 30 $.
   * Il 20% di credito è assegnato alla ricerca a pagamento, per un valore di 10 $.
   * Il restante 20% è suddiviso tra social e e-mail, ovvero 5 $ ciascuno.

* Utilizzando **Decadimento nel tempo** e un intervallo di lookback di **persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Utilizzando la mezza durata predefinita di 7 giorni:

   * Intervallo di zero giorni tra il punto di contatto visualizzazione e la conversione. `2^(-0/7) = 1`
   * Intervallo di zero giorni tra il punto di contatto e-mail e la conversione. `2^(-0/7) = 1`
   * Intervallo di sei giorni tra il punto di contatto social e la conversione. `2^(-6/7) = 0.552`
   * Intervallo di nove giorni tra il punto di contatto ricerca a pagamento e la conversione. `2^(-9/7) = 0.41`
   * La normalizzazione di questi valori determina quanto segue:

      * Visualizzazione: 33,8%, ovvero 16,88 $
      * E-mail: 33,8% ovvero 16,88 $
      * Social: 18,6%, ovvero 9,32 $
      * Ricerca a pagamento: 13,8%, ovvero 6,92 $

Gli eventi di conversione che in genere hanno numeri interi vengono suddivisi se il credito appartiene a più di un canale. Ad esempio, se due canali contribuiscono a un ordine utilizzando un modello di attribuzione lineare, entrambi i canali ottengono 0,5 di tale ordine. Queste metriche parziali vengono sommate tra tutte le persone e quindi arrotondate al numero intero più vicino per il reporting.


>[!MORELIKETHIS]
>
>[Impostazioni del componente di attribuzione](/help/data-views/component-settings/attribution.md)
>[Metrica di partecipazione](participation-metric.md)
>

