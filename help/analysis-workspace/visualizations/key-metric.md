---
description: Utilizza la visualizzazione di riepilogo delle metriche chiave per confrontare le prestazioni delle metriche in due timeline.
title: Riepilogo delle metriche chiave
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 24c2ab4a49b87b11046317a40882dde72a2a49c1
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 84%

---

# Riepilogo delle metriche chiave

La visualizzazione [!UICONTROL Key metric summary] ti consente di vedere come si presenta una metrica importante in un singolo arco temporale. Consente inoltre di confrontare le prestazioni delle metriche in due archi temporali. Fornisce i vantaggi di più visualizzazioni combinate in un’unica visualizzazione:

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

1. Configura la visualizzazione selezionando una metrica, un intervallo di date principale, un intervallo di date di confronto e un filtro (se desiderato):

   ![Configurazione della metrica chiave che mostra le opzioni per metrica, intervallo di date principale, intervallo di date di confronto e segmento.](assets/key-metric-config.png)

   | Impostazione di configurazione | Definizione |
   | --- | --- |
   | **[!UICONTROL Metric]** | Seleziona la metrica da esaminare. Sono supportate tutte le metriche. |
   | **[!UICONTROL Primary date range]** | L’intervallo di date corrente per la tabella a forma libera. |
   | **[!UICONTROL Comparison date range]** | L’intervallo di date a cui si desidera confrontare l’intervallo di date principale. |
   | **[!UICONTROL Filter (optional)]** | Qualsiasi filtro a cui sei interessato in modo specifico per questo riepilogo. |

   {style="table-layout:auto"}

1. Fai clic su **[!UICONTROL Build]** (Usa modello di attribuzione non predefinito).

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

## Visualizza l’output

![Output metrico chiave che mostra i grafici metrica, variazione di riepilogo, numero di riepilogo e linea.](assets/key-metric-output.png)

Nota:

* Il grafico a linee **[!UICONTROL Previous period]** (sempre visualizzato in grigio) corrisponde al **[!UICONTROL Comparison date range]** nel passaggio di configurazione.

* Se durante la configurazione non viene specificato un intervallo di date di confronto o se questo è nascosto nelle impostazioni di visualizzazione, viene visualizzato solo il grafico a linee per l’intervallo di date principale. La modifica di riepilogo sarà nascosta.

* Da qui, puoi passare il cursore del mouse sui grafici a linee per vedere le statistiche dei singoli giorni:

![Statistiche sulle visite](assets/key-metric-output2.png)

## Impostazioni di visualizzazione

Il riepilogo delle metriche chiave offre diverse impostazioni flessibili per consentire una migliore generazione di rapporti e comunicazioni di metriche importanti. È possibile accedere alle impostazioni tramite l’icona a forma di ingranaggio nell’angolo in alto a destra della visualizzazione.

![Impostazioni di riepilogo delle metriche chiave che mostrano le opzioni Tipo di visualizzazione Riepilogo, Generale e Visualizzazione.](assets/key-metric-settings.png)

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

   ![Icone di modifica della visualizzazione](assets/edit-icon.png)

   Ora ritorni alla visualizzazione di configurazione originale.

1. Modifica la metrica, l’intervallo di date primario, l’intervallo di date del confronto o il filtro come preferisci.
