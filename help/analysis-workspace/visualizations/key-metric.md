---
description: Utilizza la visualizzazione di riepilogo delle metriche chiave per confrontare le prestazioni delle metriche in due timeline.
title: Riepilogo delle metriche chiave
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: fa86c113de8cf533e7b68df1aad7ac02aa60f7e8
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 100%

---

# Riepilogo delle metriche chiave

La visualizzazione [!UICONTROL Key metric summary] ti consente di vedere come si presenta una metrica importante in un singolo arco temporale. Consente inoltre di confrontare le prestazioni delle metriche in due intervalli di tempo. Fornisce i vantaggi di più visualizzazioni combinate in un’unica visualizzazione:

* **[!UICONTROL Line]** visualizzazioni che mostrano la tendenza della metrica per gli intervalli di date principali e di confronto

* **[!UICONTROL Summary percent change]** che mostra l’aumento o la diminuzione della metrica tra gli intervalli di date principali e di confronto

* Valore totale corrente ([!UICONTROL **numero di riepilogo**]) per la metrica

## Casi d’uso

Questa visualizzazione tratta diversi casi d’uso comuni, tra cui:

* Un analista che cerca di capire l’aspetto della creazione di opportunità questo mese rispetto allo stesso arco temporale dello scorso anno.

* Un addetto al marketing che esplora in che modo la generazione di lead per uno specifico tipo di lead è cambiata da questo mese all’ultimo mese.

* Un dirigente che vuole capire come sono cambiate le prenotazioni da questo trimestre all’ultimo trimestre.

## Configurare il riepilogo delle metriche chiave

1. Trascina visualizzazione **[!UICONTROL Key metric summary]** dal menu **[!UICONTROL Visualizations]** nella barra a sinistra in un pannello.

1. Configura la visualizzazione selezionando una metrica, un intervallo di date principale, un intervallo di date di confronto e un segmento (se desiderato):

   ![](assets/key-metric-config.png)

   | Impostazione di configurazione | Definizione |
   | --- | --- |
   | **[!UICONTROL Metric]** | Seleziona la metrica da esaminare. Sono supportate tutte le metriche. |
   | **[!UICONTROL Primary date range]** | L’intervallo di date corrente per la tabella a forma libera. |
   | **[!UICONTROL Comparison date range]** | L’intervallo di date a cui si desidera confrontare l’intervallo di date principale. |
   | **[!UICONTROL Segment (optional)]** | Qualsiasi segmento a cui sei interessato in modo specifico per questo riepilogo. |

   {style=&quot;table-layout:auto&quot;}

1. Fai clic su **[!UICONTROL Build]**.

## Visualizza l’output

![](assets/key-metric-output.png)

Nota:

* Il grafico a linee **[!UICONTROL Previous period]** (sempre visualizzato in grigio) corrisponde al **[!UICONTROL Comparison date range]** nel passaggio di configurazione.

* Se durante la configurazione non viene specificato un intervallo di date di confronto o se questo è nascosto nelle impostazioni di visualizzazione, viene visualizzato solo il grafico a linee per l’intervallo di date principale. La modifica di riepilogo sarà nascosta.

* Da qui, puoi passare il cursore del mouse sui grafici a linee per vedere le statistiche dei singoli giorni:

![](assets/key-metric-output2.png)

## Impostazioni di visualizzazione

Il riepilogo delle metriche chiave offre diverse impostazioni flessibili per consentire una migliore generazione di rapporti e comunicazioni di metriche importanti. È possibile accedere alle impostazioni tramite l’icona a forma di ingranaggio nell’angolo in alto a destra della visualizzazione.

![](assets/key-metric-settings.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Emphasize percent change]** | Visualizzare la modifica di riepilogo in grassetto prominente al centro della visualizzazione |
| **[!UICONTROL Emphasize number value]** | Visualizzare il numero di riepilogo in grassetto prominente al centro della visualizzazione |
| **[!UICONTROL Legend visible]** | Mostrare o nascondere la legenda nella parte inferiore della visualizzazione |
| **[!UICONTROL Show annotations]** | Mostrare o nascondere le annotazioni aggiunte da un amministratore |
| **[!UICONTROL Show sparklines]** | Mostra o nascondi i grafici a linee nella parte inferiore del grafico. Quando è nascosta, la legenda non fa più riferimento visivamente alle linee |
| **[!UICONTROL Show min and max on sparklines]** | Mostrare o nascondere valori minimi e massimi nei grafici a linee principali e a linee di confronto |
| **[!UICONTROL Show comparison]** | Mostra o nascondi i dati di confronto. Se nascosti, gli oggetti grafico a linee di confronto e di riepilogo delle modifiche saranno nascosti dalla visualizzazione. |
| **[!UICONTROL Show total number]** | Mostrare o nascondere il numero di riepilogo |
| **[!UICONTROL Show raw difference]** | Mostra o nascondi la differenza non elaborata tra il valore totale della metrica nell’intervallo di date principale e l’intervallo di date secondario. |
| **[!UICONTROL Abbreviate value]** | Abbrevia i valori numerici per semplificare le informazioni comunicate (ad esempio 20.000 -> 20K) |

## Visualizzazione Modifica

Dopo aver creato la visualizzazione, puoi comunque modificare la configurazione originale.

1. Fai clic sull’icona a forma di matita nell’angolo in alto a destra della visualizzazione (accanto all’icona a forma di ingranaggio delle impostazioni).

   ![](assets/edit-icon.png)

   Ora ritorni alla visualizzazione di configurazione originale.

1. Modifica la metrica, l’intervallo di date primario, l’intervallo di date del confronto o il segmento come preferisci.
