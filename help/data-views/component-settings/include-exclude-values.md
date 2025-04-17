---
title: Includi impostazioni del componente Valori di esclusione
description: Includi o escludi in modo condizionale un elemento dimensione a seconda del relativo valore.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 93%

---

# Includi impostazioni del componente Valori di esclusione {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_includeexcludevalues"
>title="Includere valori di esclusione"
>abstract="Filtra una metrica per contare solo i valori che corrispondono a criteri specifici."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_includeexcludevalues"
>title="Includere valori di esclusione"
>abstract="Restringi una dimensione per includere solo i valori che corrispondono a criteri specifici. Le inclusioni e le esclusioni si verificano prima dell’allocazione e dei filtri nei rapporti. Determina se la logica di filtro specificata distingue tra maiuscole e minuscole."

<!-- markdownlint-enable MD034 -->

Includi valori di esclusione consente di creare regole che dipendono dal valore di un elemento dimensione. I valori che non soddisfano i criteri impostati vengono trattati in Analysis Workspace come se non fossero mai esistiti, anche se i dati esistono ancora nel set di dati sottostante.

![Finestra Visualizzazioni dati che evidenzia i valori di inclusione/esclusione](../assets/include-exclude.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Set include/exclude values] | Casella di controllo che consente di abilitare le condizioni in cui i dati vengono inclusi in una vista dati. |
| [!UICONTROL Case sensitive] | Visibile sui tipi di dati di schema Stringa. L&#39;impostazione predefinita è attivata. Questa impostazione si applica solo alla logica [!UICONTROL Include/Exclude Values], non al valore risultante. Ti consente di specificare se la regola fa distinzione tra maiuscole e minuscole. |
| [!UICONTROL Match] | Consente di specificare quali valori si desidera considerare per il reporting prima dell’attribuzione e dei filtri (ad esempio, utilizza solo valori contenenti la frase “error”). Puoi specificare **[!UICONTROL If all criteria are met]** o **[!UICONTROL If any criteria are met]**. Separa ogni valore con una virgola. |
| [!UICONTROL Criteria] | Consente di specificare la logica di corrispondenza da applicare a una regola di filtro specifica.<ul><li>**Stringa**: [!UICONTROL Contains the phrase], [!UICONTROL Contains any term], [!UICONTROL Contains all terms], [!UICONTROL Does not contain any term], [!UICONTROL Does not contain the phrase], [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with]</li><li>**Doppio/Intero**: [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Is greater than], [!UICONTROL Is less than], [!UICONTROL Is greater than or equal to], [!UICONTROL Is less than or equal to]</li><li>**Data**: [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Is later than], [!UICONTROL Is before], [!UICONTROL Occurs within]</li></ul> |
| [!UICONTROL Match operand] | Consente di specificare l’operando di corrispondenza a cui deve essere applicato l’operatore di corrispondenza.<ul><li>**Stringa**: Campo di testo</li><li>**Doppio/Intero**: Campo di testo con frecce verso l’alto o il basso per i valori numerici</li><li>**Data**: Selettore di granularità del giorno (calendario)</li><li>**Data e ora**: Selettore di granularità data e ora</li></ul> |
| [!UICONTROL Add rule] | Consente di specificare un operatore di corrispondenza e un operando aggiuntivi. |

{style="table-layout:auto"}
