---
description: Scopri come utilizzare il pannello Elemento successivo o precedente che mostra gli elementi successivi o precedenti per una dimensione specifica.
title: Pannello Elemento Successivo O Precedente
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 66%

---

# Pannello elemento successivo o precedente {#next-or-previous-item-panel}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Elemento successivo o precedente"
>abstract="Crea un pannello per comprendere le dimensioni da cui in precedenza provenivano le persone o la dimensione dove andranno successivamente."

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Elemento successivo o precedente"
>abstract="Analizza gli elementi più comuni da cui provengono o a cui passeranno i visitatori. Specifica la dimensione, l’elemento dimensione, la direzione e il contenitore da utilizzare per la visualizzazione."


>[!BEGINSHADEBOX]

_Questo articolo descrive il pannello elemento successivo o precedente in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Consulta il [Pannello elemento successivo o precedente](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/panels/next-previous) per la versione_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** di questo articolo._

>[!ENDSHADEBOX]

Il pannello **[!UICONTROL Elemento successivo o precedente]** contiene diverse tabelle e visualizzazioni per identificare l&#39;elemento dimensione successivo o precedente per una dimensione specifica. Ad esempio, potresti voler scoprire a quali pagine la clientela accede più spesso dopo aver visitato la pagina Home.

## Utilizzo {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="Contenitore"
>abstract="Seleziona il contenitore per determinare l’ambito della richiesta."

Per utilizzare un pannello **[!UICONTROL Elemento successivo o precedente]**:

1. Crea un pannello **[!UICONTROL Elemento successivo o precedente]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

### Input del pannello

Puoi configurare il pannello [!UICONTROL Elemento successivo o precedente] utilizzando le seguenti impostazioni di input:

![Pannello elemento successivo o precedente](assets/next-or-previous-item.png)

| Input | Descrizione |
| --- | --- |
| **[!UICONTROL Dimensione]** | Seleziona la dimensione per la quale desideri scoprire gli elementi successivi o precedenti. |
| **[!UICONTROL Elemento Dimension]** | Seleziona l’elemento dimensionale specifico al centro della richiesta successiva/precedente. |
| **[!UICONTROL Direzione]** | Specifica se stai cercando l&#39;elemento di dimensione [!UICONTROL Next] o [!UICONTROL Previous]. |
| **[!UICONTROL Contenitore]** | Seleziona il contenitore **[!UICONTROL Account globale]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Gruppo acquisti]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Opportunità]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Sessione]** o **[!UICONTROL Persona]** per determinare l&#39;ambito della richiesta di informazioni. |

{style="table-layout:auto"}

Seleziona **[!UICONTROL Build]** per generare il pannello.

### Output del pannello

Il pannello [!UICONTROL Elemento successivo o precedente] restituisce un set completo di dati e visualizzazioni per consentirti di comprendere meglio le occorrenze che seguono o precedono specifici elementi dimensionali.


![Output del pannello successivo/precedente](assets/next-or-previous-item-output.png)


| Visualizzazione | Descrizione |
| --- | --- |
| **[!UICONTROL Barre orizzontali]** | Elenca gli elementi successivi (o precedenti) in base all’elemento dimensionale selezionato. Passando il puntatore su una singola barra viene evidenziato l’elemento corrispondente nella tabella a forma libera. |
| **[!UICONTROL Numero di riepilogo]** | Numero di riepilogo di alto livello di tutte le occorrenze degli elementi dimensionali successivi o precedenti per il mese corrente (finora). |
| **[!UICONTROL Tabella a forma libera]** | Elenca gli elementi successivi (o precedenti) in base all’elemento dimensionale selezionato, in formato tabella. Ad esempio, quali sono le pagine più popolari (per occorrenze) a cui gli utenti accedono dopo (o prima) della pagina Home o dell’area di lavoro. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Creare un pannello](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
