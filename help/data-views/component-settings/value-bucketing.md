---
title: Impostazioni dei componenti per la divisione dei valori
description: Combinare valori numerici in una dimensione.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: c10d88c27d4a3c92e02179da4a73a6a499d2a8c2
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# Impostazioni del componente [!UICONTROL Value Bucketing] {#value-bucketing-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_value_bucketing"
>title="Bucket dei valori"
>abstract="Bucket dei valori in intervalli specifici. Questi intervalli vengono visualizzati come elementi dimensionali nei rapporti."

<!-- markdownlint-enable MD034 -->


Durante la creazione o la modifica di una visualizzazione dati, il bucket dei valori consente di combinare valori numerici in base a un intervallo. È disponibile solo per le dimensioni che utilizzano tipi di dati di schema Intero o Doppio.

![Bucketing dei valori](../assets/value-bucketing.png)

La divisione in blocchi di valori è utile quando si desidera raggruppare gli intervalli anziché trattare ogni numero univoco come un elemento di dimensione separato. Ad esempio, un bucket “Tra 5 e 10” viene visualizzato come una riga da “5 a 10” in Analysis Workspace.

Se desideri la flessibilità di generare rapporti sia su una dimensione a blocchi che su una dimensione non a blocchi, trascina due copie del componente nell’elenco delle dimensioni disponibili. Abilitare il bucket su una dimensione e disattivarla sull&#39;altra.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Bucket value] | Una casella di controllo che consente di abilitare il bucketing. |
| [!UICONTROL Less than] | Il limite superiore del primo bucket di dimensioni. |
| [!UICONTROL Including] [!UICONTROL and less than] | Limiti dei bucket successivi. |
| [!UICONTROL Greater than or equal to] | Il limite inferiore dell’ultimo bucket di dimensione. |
| [!UICONTROL Add bucket] | Consente di aggiungere un altro bucket alla creazione a blocchi di dimensioni numeriche. È possibile aggiungere fino a 20 bucket in una singola dimensione. |

{style="table-layout:auto"}
