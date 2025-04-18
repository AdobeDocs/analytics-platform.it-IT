---
title: Impostazioni dei componenti di persistenza
description: Determina in che modo o se i valori delle dimensioni persistono da un evento all’altro.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 77%

---


# Impostazioni del componente [!UICONTROL Persistence] {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_persistence"
>title="Persistenza"
>abstract="Configura il modello di allocazione predefinito applicato a una dimensione. L’allocazione si applica prima dei segmenti nel reporting. Per ulteriori informazioni, consulta [impostazioni di allocazione](/help/data-views/component-settings/persistence.md#allocation-settings), [impostazioni di scadenza](/help/data-views/component-settings/persistence.md#expiration-settings), [dimensione vincolante](/help/data-views/component-settings/persistence.md#binding-dimension) e [metriche vincolanti](/help/data-views/component-settings/persistence.md#binding-metric)."

<!-- markdownlint-enable MD034 -->



[!UICONTROL Persistence] è la capacità di un dato valore di dimensione di attribuire a una metrica oltre l&#39;evento su cui è impostato. Utilizza una combinazione di allocazione e scadenza.

![Finestra Visualizzazioni dati che evidenzia le opzioni di persistenza](../assets/persistence.png)

* **Allocazione** consente di determinare quale valore mantenere quando più elementi dimensionali possono persistere alla volta in una singola colonna.

  >[!NOTE]
  >
  >Se in un report è impostato un [modello di attribuzione non predefinito](/help/data-views/component-settings/attribution.md) per una metrica, il modello di attribuzione ignora l’allocazione impostata sulla dimensione per lo stesso report.
  >
  >Tuttavia, quando si esegue un’[esportazione di tabelle complete](/help/analysis-workspace/export/export-cloud.md) che include più dimensioni, l’attribuzione mantiene i modelli di allocazione applicati a ogni dimensione.

* **Scadenza** consente di determinare per quanto tempo un elemento dimensione persiste oltre l’evento su cui è impostato.

[!UICONTROL Persistence] è disponibile solo sulle dimensioni ed è retroattivo per i dati a cui viene applicato. Si tratta di una trasformazione immediata dei dati che avviene prima dell’applicazione di segmentazioni o di altre operazioni di analisi.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Set persistence] | Abilita la persistenza per la dimensione. Se la persistenza non è abilitata, la dimensione si riferisce solo alle metriche esistenti nello stesso evento. Questa impostazione è disattivata per impostazione predefinita. |
| [!UICONTROL Allocation] | Consente di specificare il modello di allocazione utilizzato su una dimensione per la persistenza. Le opzioni sono:<ul><li>**[!UICONTROL Most recent]**: i valori nella dimensione persistono finché non vengono sovrascritti dai valori successivi</li><li> **[!UICONTROL Original]**: il primo valore per questa dimensione persiste e non viene sovrascritto dai valori successivi</li><li>**[!UICONTROL All]**: tutti i valori per questa dimensione persistono contemporaneamente</li><li>**[!UICONTROL First known]**: viene utilizzato il primo valore per questa dimensione che verrà applicato a tutti gli eventi prima e dopo.</li><li>**[!UICONTROL Last known]**: viene utilizzato l&#39;ultimo valore per questa dimensione, che verrà applicato a tutti gli eventi precedenti e successivi.</li></ul> |
| [!UICONTROL Expiration] | Consente di specificare la finestra di persistenza per una dimensione. Le opzioni sono: <ul><li>**[!UICONTROL Session]** (predefinito)</li><li>**[!UICONTROL Person]**</li><li>**[!UICONTROL Custom Time]**</li><li>**[!UICONTROL Metric]**</li></ul>. Potrebbe essere necessario poter scadere la dimensione su un acquisto (ad esempio termini di ricerca interni o altri casi d’uso di merchandising). Il tempo massimo di scadenza che puoi impostare è di 90 giorni. Se selezioni un&#39;allocazione di [!UICONTROL All], solo [!UICONTROL Session] o [!UICONTROL Person] è disponibile la scadenza. |

{style="table-layout:auto"}

## [!UICONTROL Allocation] del profilo

Dettagli sulle impostazioni di allocazione disponibili.

* **[!UICONTROL Most Recent]**: persiste il valore più recente (per marca temporale) presente nella dimensione. Eventuali valori successivi che si verificano all’interno del periodo di scadenza della dimensione sostituiscono il valore persistente precedente. Se su questa dimensione è abilitato “Treat &#39;No Value&#39; as a value” in [Nessuna opzione di valore](no-value-options.md), i valori vuoti sovrascrivono quelli persistenti in precedenza. Ad esempio, considera la seguente tabella con [!UICONTROL Most recent] assegnazione e [!UICONTROL Session] scadenza:

  | Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valori del set di dati |  | C | B |  | A |
  | Allocazione più recente |  | C | B | B | A |

* **[!UICONTROL Original]**: Persiste il valore originale per marca temporale presente nella dimensione per la durata del periodo di scadenza. Se questa dimensione ha un valore, non viene sovrascritta quando viene visualizzato un valore diverso in un evento successivo. Ad esempio, considera la seguente tabella con [!UICONTROL Original] assegnazione e [!UICONTROL Session] scadenza:

  | Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valori del set di dati |  | C | B |  | A |
  | Allocazione originale |  | C | C | C | C |

* **[!UICONTROL All]**: Agisce in modo simile al [!UICONTROL Participation] modello di attribuzione per le metriche. Persiste tutti i valori equamente in modo che ciascuno ottenga il pieno credito per la metrica nel reporting. Ad esempio, considera la seguente tabella con [!UICONTROL All] assegnazione e [!UICONTROL Session] scadenza:

  | Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valori del set di dati | A | B | C |  | A |
  | Tutte le allocazioni | A | A,B | A, B, C | A, B, C | A, B, C |

* **[!UICONTROL First Known]** e **[!UICONTROL Last Known]**: (19 gennaio 2022 ) questi due modelli di allocazione soddisfano i casi d’uso per le dimensioni “entrata” e “uscita”. Considerano il primo o l’ultimo valore osservato relativo a una dimensione all’interno di un ambito di persistenza specificato (sessione, persona o periodo di tempo personalizzato con lookback) e lo applicano a tutti gli eventi all’interno dell’ambito specificato. Esempio:

  | Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
  | --- | --- | --- | --- | --- | --- |
  | Marca temporale (min) | 1 | 2 | 3 | 6 | 7 |
  | Valori originali |  | C | B |  | A |
  | First known (Primo noto) | C | C | C | C | C |
  | Last known (Ultimo noto) | A | A | A | A | A |


## [!UICONTROL Expiration] del profilo

Dettagli sulle impostazioni di scadenza disponibili.

* **Sessione**: scade dopo una determinata sessione. Finestra di scadenza predefinita.
* **Finestra di reporting per persona**: scade alla fine dell&#39;intervallo di reporting.
* **Finestra di reporting account globale** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}: scade alla fine dell&#39;intervallo di reporting.
* **Finestra di reporting account** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}: scade alla fine dell&#39;intervallo di reporting.
* **Finestra di reporting opportunità** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}: scade alla fine dell&#39;intervallo di reporting.
* **Finestra di reporting per gruppi di acquisto** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}: scade alla fine dell&#39;intervallo di reporting.
* **Orario personalizzato**: scade dopo un determinato periodo di tempo (fino a 90 giorni). Questa opzione di scadenza è disponibile solo per i modelli di allocazione Originale e Più recente. Quando si utilizza una scadenza basata sul tempo, vengono considerati i valori precedenti all’inizio dell’intervallo di reporting (fino a 90 giorni).
* **Metrica**: quando questa metrica viene visualizzata in un evento, scade immediatamente il valore persistente nella dimensione. Puoi utilizzare qualsiasi metrica come termine scadenza per questa dimensione. Questa opzione di scadenza è disponibile solo per le impostazioni di allocazione Originale e Più recente.


## [!UICONTROL Binding Dimension]

Un elenco a discesa che consente di associare la persistenza di un valore di dimensione ai valori di dimensione in un’altra dimensione. Le opzioni valide includono altre dimensioni presenti nella visualizzazione dati.

Per esempi su come utilizzare in modo efficace le dimensioni di binding, consulta [Utilizzo di dimensioni e metriche di binding in Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md).


>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensioni di binding](https://video.tv.adobe.com/v/342694/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


## [!UICONTROL Binding Metric]

Un elenco a discesa che consente di scegliere una metrica che agisce come un trigger di binding. Le opzioni valide includono le metriche presenti nella visualizzazione dati.

Questa impostazione viene visualizzata solo quando la dimensione di binding è inferiore nell’array dell’oggetto rispetto al componente. Quando la metrica di binding è presente in un evento, i valori di dimensione vengono copiati dalla dimensione a livello di evento fino al livello di schema inferiore della dimensione di binding.

Per ulteriori informazioni su come utilizzare in modo efficace le metriche di binding, consulta il secondo esempio in [Utilizzo di dimensioni e metriche di binding in Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md).
