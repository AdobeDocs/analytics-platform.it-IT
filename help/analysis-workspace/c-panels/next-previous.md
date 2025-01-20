---
description: Pannello che mostra gli elementi dimensionali precedenti o successivi per una dimensione specifica.
title: Pannello elemento successivo o precedente
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: 55b312552d32070875714a77e1177bf0da5f9d87
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 38%

---

# Pannello elemento successivo o precedente {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Elemento successivo o precedente"
>abstract="Crea un pannello per comprendere le dimensioni da cui in precedenza provenivano le persone o la dimensione dove andranno successivamente."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Elemento successivo o precedente"
>abstract="Analizza i luoghi più comuni da cui in precedenza venivano i visitatori o dove andranno successivamente.<br/><br/>**Dimensione**: seleziona una dimensione. Ad esempio **Pagina**.<br/>**Elemento dimensionale**: seleziona un elemento dimensionale specifico. Ad esempio, **Homepage**.<br/>**Direzione**: seleziona **Avanti** per visualizzare gli elementi dimensione immediatamente successivi all’elemento dimensionale selezionato. Seleziona **Precedente** per visualizzare gli elementi dimensionali che conducono all’elemento dimensionale selezionato.<br/>**Contenitore**: seleziona **Sessione** per visualizzare gli elementi dimensione precedente/successiva nella stessa sessione oppure **Persona** per visualizzare l’elemento dimensione precedente/successivo per la stessa persona."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Questo articolo documenta il pannello Elemento successivo o precedente in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Consulta [Pannello elemento successivo o precedente](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) per_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** versione di questo articolo._

>[!ENDSHADEBOX]

Il pannello **[!UICONTROL Next or previous item]** contiene diverse tabelle e visualizzazioni per identificare l&#39;elemento dimensione successivo o precedente per una dimensione specifica. Ad esempio, puoi scoprire a quali pagine i clienti accedono più spesso dopo aver visitato la home page.

## Utilizzo

Per usare un pannello **[!UICONTROL Next or previous item]**:

1. Crea un pannello **[!UICONTROL Next or previous item]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

### Input del pannello

È possibile configurare il pannello [!UICONTROL Next or previous item] utilizzando le seguenti impostazioni di input:

![Pannello elemento successivo o precedente](assets/next-or-previous-item.png)

| Input | Descrizione |
| --- | --- |
| **[!UICONTROL Dimension]** | Seleziona la dimensione per la quale desideri esplorare gli elementi successivi o precedenti. |
| **[!UICONTROL Dimension item]** | Seleziona l’elemento dimensione specifico al centro dell’interrogazione successiva/precedente. |
| **[!UICONTROL Direction]** | Specificare se si sta cercando l&#39;elemento di dimensione [!UICONTROL Next] o [!UICONTROL Previous]. |
| **[!UICONTROL Container]** | Selezionare il contenitore [!UICONTROL Session] o [!UICONTROL Person] (impostazione predefinita) per determinare l&#39;ambito della richiesta di informazioni. |

{style="table-layout:auto"}

Seleziona **[!UICONTROL Build]** per creare il pannello.

### Output del pannello

Il pannello [!UICONTROL Next or previous item] restituisce un set completo di dati e visualizzazioni per consentirti di comprendere meglio le occorrenze che seguono o precedono specifici elementi dimensionali.


![Output pannello precedente/successivo](assets/next-or-previous-item-output.png)


| Visualizzazione | Descrizione |
| --- | --- |
| **[!UICONTROL Horizontal bar]** | Elenca gli elementi successivi (o precedenti) in base all’elemento dimensione selezionato. Passando il puntatore del mouse su una singola barra viene evidenziato l’elemento corrispondente nella tabella a forma libera. |
| **[!UICONTROL Summary number]** | Numero di riepilogo di alto livello di tutte le occorrenze successive o precedenti degli elementi dimensione per il mese corrente (finora). |
| **[!UICONTROL Freeform table]** | Elenca gli elementi successivi (o precedenti) in base all’elemento dimensione selezionato, in formato tabella. Ad esempio, si trattava delle pagine più popolari (per occorrenze) a cui gli utenti accedevano dopo (o prima) la pagina Home o l’area di lavoro. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Creare un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
