---
title: Etichette E Criteri
description: Scopri in che modo le etichette per dati e i criteri definiti in Adobe Experience Platform influiscono sulle visualizzazioni dati e sul reporting in Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
hold: true
autotag-review: '2026-05-19T08:59:31.818Z'
TQID: 'https://experienceleague.adobe.com/SoIHLRSx90B4j8EkHWBVt3rVtt-968TN8ocWU2zuYN4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 0b6dc1d738b5f1a8aa430c990f8eb24df5d95653
workflow-type: tm+mt
source-wordcount: 770
ht-degree: 47%

---

# Etichette, criteri e azioni di marketing

Quando crei un set di dati in Experience Platform, puoi creare [etichette di utilizzo dei dati](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/reference) per alcuni o tutti gli elementi del set di dati. Puoi visualizzare queste etichette e criteri in Customer Journey Analytics.

Le etichette e le azioni di marketing seguenti sono di particolare interesse per Customer Journey Analytics:


| Etichetta | Azione di marketing | Definizione |
|---------|----------|---------|
| `C2` | [!UICONTROL Esporta a terze parti] | L’etichetta e l’azione di marketing associata indicano che i dati non possono essere esportati a terzi, se è abilitato il criterio DULE corrispondente. |
| `C3` | [!UICONTROL Combinazione con dati direttamente identificabili] | L’etichetta e la relativa azione di marketing indicano che i dati non possono essere combinati o altrimenti utilizzati con informazioni direttamente identificabili, se è abilitato il corrispondente criterio DULE. |
| `C8` | [!UICONTROL Analytics] | L’etichetta e l’azione di marketing associata indicano che i dati non possono essere utilizzati per l’analisi sui siti web o sulle app della tua organizzazione, se è abilitato il criterio DULE corrispondente. |
| `C9` | [!UICONTROL Data Science] | L’etichetta e l’azione di marketing associata indicano che i dati non possono essere utilizzati nei flussi di lavoro di data science, se è abilitato il corrispondente criterio DULE. |
| `C12` | [!UICONTROL Esportazione dati] | L’etichetta e l’azione di marketing associata indicano che i campi dello schema etichettati in questo modo non possono essere esportati o scaricati da Customer Journey Analytics (tramite reporting, esportazione, API e così via), se è abilitato il corrispondente criterio DULE. |

>[!NOTE]
>
>Le etichette di utilizzo dei dati non vengono propagate automaticamente ai set di dati uniti. Tuttavia, possono essere aggiunte manualmente.

L’etichettatura di per sé non significa che queste etichette di utilizzo dei dati siano applicate. Per questo vengono utilizzati i criteri. Puoi creare i tuoi criteri utilizzando l’[Interfaccia utente Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/policies/user-guide) o tramite l’[API di Privacy Service](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/api/overview) in Experience Platform.

In Experience Platform sono disponibili cinque criteri definiti da Adobe che possono emergere in Customer Journey Analytics e influire sulla generazione di rapporti e sull’esportazione dei dati:


| Criterio | Etichetta |
|---------|----------|
| [!UICONTROL Limita l&#39;esportazione di dati di terze parti] | `C2` |
| [!UICONTROL Limita la combinazione di dati direttamente identificabili] | `C3` |
| [!UICONTROL Limita analisi utilizzo e misurazione basata su utente] | `C8` |
| [!UICONTROL Limita data science] | `C9` |
| [!UICONTROL Limita l&#39;esportazione dei dati] | `C12` |


## Visualizzare le etichette dati nelle visualizzazioni dati di Customer Journey Analytics

Le etichette dati create da te o da altri in Experience Platform vengono visualizzate in tre aree nell’interfaccia utente della visualizzazione dati:

| Posizione | Descrizione |
| --- | --- |
| Pulsante Informazioni su un campo schema | Fare clic su questo pulsante per indicare le [!UICONTROL etichette di utilizzo dati] attualmente applicabili a un campo:<p>![](assets/data-label-left.png) |
| Barra a destra sotto [Impostazioni dei componenti](/help/data-views/component-settings/overview.md) | Tutte le [!UICONTROL etichette di utilizzo dati] sono elencate qui:<p>![](assets/data-label-right.png) |
| Aggiungi etichette dati come colonna | È possibile aggiungere [!UICONTROL Etichette di utilizzo dati] come colonna alle colonne [!UICONTROL Componenti inclusi] nelle visualizzazioni dati. Seleziona l&#39;icona del selettore colonne e seleziona **[!UICONTROL Etichette di utilizzo dati]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrare le etichette per la governance dei dati nelle visualizzazioni dati

Nell&#39;editor delle visualizzazioni dati, seleziona l&#39;icona [!UICONTROL filter] nella traccia a sinistra e filtra i componenti delle visualizzazioni dati in base a **[!UICONTROL Governance dei dati]** e al tipo di **[!UICONTROL Etichetta]**:

![](assets/filter-labels.png)

Fai clic su **[!UICONTROL Applica]** per vedere quali componenti dispongono di etichette collegate.

## Filtrare i criteri di governance dei dati nelle visualizzazioni dati

Puoi verificare se è attivato un criterio, ad esempio un criterio creato, denominato **[!UICONTROL Applica analisi]**. E se tale criterio blocca l’utilizzo di determinati elementi di visualizzazione dati di Customer Journey Analytics per l’analisi o l’esportazione di dati.

Di nuovo, seleziona l&#39;icona [!UICONTROL filtro] nella barra a sinistra e in **[!UICONTROL Governance dei dati]** seleziona **[!UICONTROL Criteri]**:

![Filtra i componenti inclusi per elenco, mostrando la selezione dell’analisi di Limita utilizzo e delle misurazione basata sull’utente](assets/filter-policies.png)

Fai clic su **[!UICONTROL Applica]** per vedere quali criteri sono abilitati.

## Effetti dei criteri abilitati sulle visualizzazioni dati

Se uno o più criteri sono attivati con C3 o C8, i componenti dello schema a cui sono applicate determinate etichette dati non possono essere aggiunti alle visualizzazioni dati.

Se uno o più criteri sono attivati con C9, tutti i componenti dello schema etichettati con C9 non saranno disponibili per l&#39;utilizzo con [server MCP di Analytics](https://developer.adobe.com/analytics-mcp/docs/).

Questi componenti sono disattivati nella barra a sinistra [!UICONTROL Elenco campi schema]:

![I componenti disattivati e il messaggio Criteri che indica l’applicazione dei criteri a questo campo limitando l’utilizzo dei dati](assets/component-greyed.png)

Inoltre, non è possibile salvare una visualizzazione dati contenente campi bloccati.

Prova ad applicare etichette di accesso e governance dei dati (tramite criteri) ai campi o ai gruppi di campi di Experience Platform, per i quali hai già definito dei componenti nella visualizzazione dati. Potrebbe essere visualizzata questa finestra di dialogo.

![Violazione](assets/violation.png)

Devi innanzitutto risolvere la violazione (ad esempio rimuovere i componenti dalla visualizzazione dati).


>[!MORELIKETHIS]
>
>[Scaricare dati sensibili](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Cosa sono le etichette per limitazioni in Report Builder?](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


