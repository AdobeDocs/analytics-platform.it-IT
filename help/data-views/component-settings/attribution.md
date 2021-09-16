---
title: Impostazioni dei componenti di attribuzione
description: Consente di impostare l’attribuzione predefinita per una metrica.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---


# Impostazioni dei componenti di attribuzione

Attribution consente di impostare un modello di attribuzione predefinito per una metrica. Puoi sovrascrivere il modello di attribuzione di una data metrica mentre lavori in Analysis Workspace.

![Attribution](../assets/attribution-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Set attribution] | Abilita un modello di attribuzione predefinito quando viene utilizzata questa metrica. Questa impostazione predefinita può essere ignorata in una [!UICONTROL Freeform Table] o in una metrica calcolata. |
| [!UICONTROL Attribution model] | Consente di specificare quale modello di attribuzione [predefinito](/help/analysis-workspace/attribution/models.md) utilizzare. Predefinito su [!UICONTROL Last Touch]. Le opzioni sono: Ultimo contatto, Primo contatto, Lineare, Partecipazione, Stesso contatto, A forma di U, Curva J, J inversa, Decadimento nel tempo, Personalizzato, Algoritmico. Alcune di queste opzioni creano campi aggiuntivi da compilare, come Personalizzato o Decadimento nel tempo. È possibile creare più metriche utilizzando lo stesso campo, il che significa che è possibile avere una metrica di entrate [!UICONTROL Last touch] e una metrica di ricavi [!UICONTROL First Touch], ma basata sullo stesso campo di ricavi nello schema. |
| [!UICONTROL Lookback window] | Consente di specificare un intervallo di lookback predefinito per una metrica. Le opzioni sono: [!UICONTROL Person] (Finestra di reporting), [!UICONTROL Session], [!UICONTROL Custom]. Quando [!UICONTROL Custom] è selezionato, ti offriamo anche la possibilità di selezionare un numero qualsiasi di giorni/settimane/mesi/ecc. (fino a 90 giorni), esattamente come [!UICONTROL Attribution IQ]. Puoi avere più metriche utilizzando lo stesso campo dello schema, ma ciascuna con un intervallo di lookback separato. |
