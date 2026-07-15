---
title: Analisi degli eventi secondari
description: Scopri come l’analisi dei sub-eventi consente di filtrare singoli prodotti o altri contenitori all’interno di un evento in Customer Percorsi Analytics, eliminando il bleed di attribuzione nei rapporti sui prodotti.
feature: Segmentation
hide: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 9%

---

# Analisi dei sottoeventi

{{release-limited-testing}}

L’analisi dei sottoeventi consente di analizzare i dati dell’evento a un livello più granulare rispetto al livello dell’evento. Invece di filtrare sull’intero evento, puoi segmentare singoli contenitori all’interno di eventi. Ad esempio:

- Segmentazione per una categoria di prodotti specifica senza includere tutti gli altri prodotti acquistati nello stesso ordine
- Segmentare una categoria di risorse specifica nei dati di analisi dei contenuti?
- Segmentazione su un canale multimediale specifico all’interno dei dati di analisi multimediale.


In Customer Journey Analytics, all’interno di una visualizzazione dati puoi definire i contenitori per i quali desideri utilizzare l’analisi degli eventi secondari. Senza analisi di eventi secondari, la segmentazione su un attributo di elemento contenitore restituisce tutti gli eventi, le sessioni, le persone, gli account (globali) [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, i gruppi di acquisto [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, le opportunità [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} o altri [contenitori](/help/data-views/create-dataview.md#containers-1) definiti. Il risultato è un’attribuzione errata e metriche di ricavi gonfiate. L’analisi sub-evento esamina il filtro in singole righe del contenitore all’interno di un evento e risolve questi problemi.

Nell’analisi dei sottoeventi, la logica di esclusione si comporta in modo diverso rispetto all’esclusione standard a livello di evento rispetto al contenitore. Quando si escludono gli attributi di elementi all&#39;interno del contenitore, il segmento restituisce eventi che **contengono elementi** all&#39;interno del contenitore ma non corrispondono ai criteri di esclusione. Il segmento non restituisce alcun evento senza elementi.


## Esempio

Si desidera misurare i ricavi solo dalla categoria abiti professionali. Senza analisi dei sub-eventi, l&#39;applicazione di un segmento per le cause professionali include i ricavi di ogni prodotto su qualsiasi ordine (evento) che contiene almeno un prodotto con la categoria delle cause professionali. Con l’analisi dei sub-eventi, puoi definire l’ambito del filtro a livello di prodotto e restituire solo i ricavi per i prodotti della categoria tute professionali.

Desideri inoltre misurare i ricavi online da tutte le altre categorie ad eccezione della categoria tute professionali.

>[!BEGINTABS]

>[!TAB Analisi degli eventi]

Nel generatore di segmentazione o come parte di un **[!UICONTROL segmento rapido]**, si specifica di **[!UICONTROL includere]** il **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** nel contenitore **[!UICONTROL Events]**.

![Pannello che mostra la segmentazione a livello di evento per le tute professionali della categoria di prodotti](./assets/product-category-segmentation-events.png)

Di conseguenza, vengono considerati tutti gli ordini contenenti almeno una **[!UICONTROL suite professionali]** **[!UICONTROL categoria_prodotto]** e i ricavi da altri prodotti inclusi in tali ordini sono inclusi nella metrica **[!UICONTROL Ricavi]**.Quando si crea un report sulle categorie, vengono segnalati tutti gli altri valori per **[!UICONTROL product_category]** che facevano parte di un ordine che includeva un prodotto con le **[!UICONTROL tute professionali]** **[!UICONTROL product_category]**.

>[!TAB Analisi sub-evento]

Nel generatore di segmentazione o come parte di un **[!UICONTROL segmento rapido]**, si specifica di **[!UICONTROL includere]** il **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** nel contenitore **[!UICONTROL Products]**.

![Pannello che mostra la segmentazione a livello di evento secondario per le tute professionali della categoria di prodotti](./assets/product-category-segmentation-subevents.png)

Di conseguenza, vengono considerati tutti gli ordini contenenti almeno una **[!UICONTROL Vestibilità professionali]** **[!UICONTROL categoria_prodotto]** e solo i ricavi dei prodotti appartenenti alla **[!UICONTROL Vestibilità professionali]** **[!UICONTROL categoria_prodotto]** sono inclusi per la metrica **[!UICONTROL Ricavi]**.Quando si crea un report sulle categorie, viene segnalato solo il **[!UICONTROL Abiti professionali]** **[!UICONTROL Rproduct_category]**.

>[!TAB Analisi sub-evento (esclusione)]

Nel generatore di segmentazione o come parte di un **[!UICONTROL segmento rapido]**, si specifica di **[!UICONTROL escludere]** il **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]** nel contenitore **[!UICONTROL Products]**.

![Pannello che mostra la segmentazione a livello di hit secondario per escludere la categoria di prodotti Men](./assets/product-category-segmentation-subevents-exclude.png)

Per escludere a livello di prodotto, sono inclusi gli eventi che contengono almeno un prodotto, quindi l’esclusione a livello di evento secondario viene applicata all’interno di tale ambito. Questa esclusione è diversa dall’esclusione a livello di evento, che esclude l’intero evento.

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
