---
title: Impostazioni dei componenti per la divisione dei valori
description: Combinare valori numerici in una dimensione.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:00.872Z'
TQID: 'https://experienceleague.adobe.com/LHEk3h9utGW73kSo2-SgY5NgKi11uktKR0ucPxw9IcY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 92%

---

# Impostazioni del componente [!UICONTROL Bucketing dei valori] {#value-bucketing-component-settings}

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
| [!UICONTROL Valore bucket] | Una casella di controllo che consente di abilitare il bucketing. |
| [!UICONTROL Minore di] | Il limite superiore del primo bucket di dimensioni. |
| [!UICONTROL Incluso] [!UICONTROL e meno di] | Limiti dei bucket successivi. |
| [!UICONTROL Maggiore o uguale a] | Il limite inferiore dell’ultimo bucket di dimensione. |
| [!UICONTROL Aggiungi bucket] | Consente di aggiungere un altro bucket alla creazione a blocchi di dimensioni numeriche. È possibile aggiungere fino a 20 bucket in una singola dimensione. |

{style="table-layout:auto"}
