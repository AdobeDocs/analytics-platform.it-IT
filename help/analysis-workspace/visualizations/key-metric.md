---
description: Utilizza la visualizzazione di riepilogo delle metriche chiave per confrontare le prestazioni delle metriche in due timeline.
title: Riepilogo delle metriche chiave
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 55b312552d32070875714a77e1177bf0da5f9d87
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 36%

---

# Riepilogo delle metriche chiave {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Riepilogo delle metriche chiave"
>abstract="Crea una visualizzazione che combina grafici a linee, a variazione di riepilogo e a numero di riepilogo. Utilizza questa visualizzazione per confrontare la tendenza delle metriche importanti tra due periodi di tempo."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta la visualizzazione del riepilogo delle metriche chiave in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consulta [Riepilogo delle metriche chiave](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/key-metric) per_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** versione di questo articolo._

>[!ENDSHADEBOX]


La visualizzazione ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]** ti consente di vedere come si presenta una metrica importante in un singolo arco temporale. Consente inoltre di confrontare le prestazioni delle metriche in due archi temporali. Fornisce i vantaggi di più visualizzazioni combinate in un’unica visualizzazione:

* La visualizzazione **[!UICONTROL Line]** mostra la tendenza della metrica per gli intervalli di date principali e di confronto

* **[!UICONTROL Summary percent change]** mostra l&#39;aumento o la diminuzione della metrica tra gli intervalli di date principali e di confronto

* Valore totale corrente ([!UICONTROL **numero di riepilogo**]) per la metrica

## Casi d’uso

Questa visualizzazione tratta diversi casi d’uso comuni, tra cui:

* Un analista che cerca di capire l’aspetto della creazione di opportunità questo mese rispetto allo stesso arco temporale dello scorso anno.

* Un addetto al marketing che esplora in che modo la generazione di lead per uno specifico tipo di lead è cambiata da questo mese all’ultimo mese.

* Un dirigente che vuole capire come sono cambiate le prenotazioni da questo trimestre all’ultimo trimestre.

## Utilizzo

1. Aggiungi una visualizzazione ![Metriche chiave](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]**. Vedi [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Configura la visualizzazione selezionando un **[!UICONTROL Metric]**, un **[!UICONTROL Primary date range]**, un **[!UICONTROL Comparison date range]** (facoltativo) e un **[!UICONTROL Filter]** (facoltativo):

   ![Configurazione delle metriche chiave che mostra le opzioni per metrica, intervallo di date primario, intervallo di date di confronto e segmento.](assets/key-metrics-config.png)

   | Opzione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Metric]** | Seleziona la metrica da esaminare. Sono supportate tutte le metriche. |
   | **[!UICONTROL Primary date range]** | L’intervallo di date corrente per la tabella a forma libera.<p>Scegli uno degli intervalli di date disponibili nella visualizzazione dati.</p> <p>Scegli [!UICONTROL **Intervallo date pannello**] se desideri utilizzare lo stesso intervallo di date utilizzato nel pannello in cui si trova la visualizzazione.</p> |
   | **[!UICONTROL Comparison date range]** | L’intervallo di date che desideri confrontare con l’intervallo di date principale. |
   | **[!UICONTROL Filter (optional)]** | Qualsiasi filtro a cui sei interessato per questo riepilogo. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >Quando il campo [!UICONTROL **Intervallo date primario**] è impostato su [!UICONTROL **Intervallo date pannello**], **[!UICONTROL Comparison date range]** può essere aggiornato automaticamente, a seconda che l&#39;opzione **[!UICONTROL Comparison date range]** scelta sia relativa all&#39;intervallo date primario o fissa.
   >
   >* **Relativo:** Se il campo **[!UICONTROL Comparison date range]** è impostato su un&#39;opzione relativa all&#39;intervallo di date primario (ad esempio [!UICONTROL **Giorno precedente**], [!UICONTROL **Stesso giorno della settimana scorsa**], [!UICONTROL **Stesso giorno 4 settimane prima**] e così via), eventuali aggiornamenti al campo [!UICONTROL **Intervallo di date primario**] fanno sì che **[!UICONTROL Comparison date range]** venga aggiornato automaticamente al periodo immediatamente successivo all&#39;intervallo di date del pannello.
   >* **Fisso:** se il campo [!UICONTROL **Intervallo date di confronto**] è impostato su un intervallo di date fisso (ad esempio **3 febbraio 2023**), le modifiche apportate al campo [!UICONTROL **Intervallo date principale**] o all&#39;intervallo date del pannello non hanno alcun effetto sull&#39;[!UICONTROL **Intervallo date di confronto**]. Tuttavia, eventuali aggiornamenti all&#39;intervallo di date del pannello causano l&#39;aggiornamento automatico dell&#39;[!UICONTROL **Intervallo di date principale**].

1. Seleziona **[!UICONTROL Build]**.

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

L’output del riepilogo delle metriche chiave è simile al seguente:

![Output delle metriche chiave che mostra i grafici metrica, modifica di riepilogo, numero di riepilogo e linea.](assets/key-metrics.png)

Quando visualizzi l’output, tieni presente quanto segue:

* Il grafico a linee **[!UICONTROL Previous period]** (sempre visualizzato in grigio) corrisponde a **[!UICONTROL Comparison date range]** nel passaggio di configurazione.

* Se durante la configurazione non viene specificato un intervallo di date di confronto o se questo è nascosto nelle impostazioni di visualizzazione, viene visualizzato solo il grafico a linee per l’intervallo di date principale. La modifica di riepilogo è nascosta.

* Da qui, puoi passare il cursore del mouse sui grafici a linee per vedere le statistiche dei singoli giorni:


## Configurare

Dopo aver creato la visualizzazione, puoi modificare la configurazione originale.

1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Configure visualization]** nella parte superiore della visualizzazione.

   Viene visualizzata di nuovo la finestra di dialogo di configurazione originale.

1. Modifica le impostazioni come preferisci. Selezionare **[!UICONTROL Reset]** per ripristinare le impostazioni correnti. Seleziona **[!UICONTROL Build]** per ricreare la visualizzazione.

## Impostazioni

Come parte delle impostazioni di visualizzazione, sono disponibili impostazioni specifiche di riepilogo delle metriche chiave.

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Emphasize percent change]** | Visualizzare la modifica di riepilogo in grassetto prominente al centro della visualizzazione |
| **[!UICONTROL Emphasize number value]** | Visualizzare il numero di riepilogo in grassetto prominente al centro della visualizzazione |
| **[!UICONTROL Legend visible]** | Mostrare o nascondere la legenda nella parte inferiore della visualizzazione |
| **[!UICONTROL Show annotations]** | Mostrare o nascondere le annotazioni aggiunte da un amministratore |
| **[!UICONTROL Hide title]** | Nasconde il titolo della visualizzazione. |
| **[!UICONTROL Percentages]** | Visualizza la visualizzazione in percentuale anziché in numero. |
| **[!UICONTROL Show trendlines]** | Mostra le linee di tendenza nella visualizzazione. |
| **[!UICONTROL Show max and min on trendlines]** | Mostrare o nascondere valori minimi e massimi nei grafici a linee principali e a linee di confronto |
| **[!UICONTROL Show comparison percentage and trendline]** | Mostra o nascondi i dati di confronto. Quando sono nascosti, gli oggetti grafico a linee di confronto e di riepilogo delle modifiche sono nascosti. |
| **[!UICONTROL Show total number]** | Mostrare o nascondere il numero di riepilogo |
| **[!UICONTROL Show raw difference]** | Mostra o nascondi la differenza non elaborata tra il valore totale della metrica nell’intervallo di date principale e l’intervallo di date secondario. |
| **[!UICONTROL Abbreviate value]** | Selezionare **[!UICONTROL Abbreviate value]** per abbreviare in modo intelligente il valore numerico. Se questa opzione è selezionata, immettere un numero per definire la quantità di abbreviazione. Esempio:<br/><table><tr><td>**Valore originale**</td><td>**Abbreviazione**</td><td>**Risultato**</td></tr><tr><td>12.011.141,25 $</td><td>Non selezionato</td><td align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su 1</td><td align="right">$ 12 milioni</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su 2</td><td align="right">$ 12,0 milioni</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su 2</td><td align="right">$ 12,011 milioni</td></tr><tr><td>12.011.141,25 $</td><td>Seleziona, imposta su 3</td><td align="right">$ 12,011 milioni</td></tr></table> |

## Visualizzazione Modifica

Dopo aver creato la visualizzazione, puoi comunque modificare la configurazione originale.

1. Fai clic sull’icona a forma di matita nell’angolo in alto a destra della visualizzazione (accanto all’icona a forma di ingranaggio delle impostazioni).

   ![Icona modifica visualizzazione](assets/edit-icon.png)

   Ora ritorni alla visualizzazione di configurazione originale.

1. Modifica la metrica, l’intervallo di date primario, l’intervallo di date del confronto o il filtro come preferisci.

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida visualizzazione](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
