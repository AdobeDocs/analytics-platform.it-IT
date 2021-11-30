---
title: Impostazioni dei componenti di attribuzione
description: Consente di impostare l’attribuzione predefinita per una metrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---

# Impostazioni dei componenti di attribuzione

Attribution consente di impostare un modello di attribuzione predefinito per una metrica. Puoi sovrascrivere il modello di attribuzione di una data metrica mentre lavori in Analysis Workspace.

![Attribution](../assets/attribution-settings.png)

| Impostazione | Caso di utilizzo/descrizione |
| --- | --- |
| [!UICONTROL Set attribution] | Abilita un modello di attribuzione predefinito quando viene utilizzata questa metrica. Questo valore predefinito può essere ignorato in un [!UICONTROL Freeform Table] o in una metrica calcolata. |
| [!UICONTROL Attribution model] | Consente di specificare il valore predefinito [modello di attribuzione](/help/analysis-workspace/attribution/models.md) da utilizzare. Predefinito su [!UICONTROL Last Touch]. Le opzioni sono: Ultimo contatto, Primo contatto, Lineare, Partecipazione, Stesso contatto, A forma di U, Curva J, J inversa, Decadimento nel tempo, Personalizzato, Algoritmico. Alcune di queste opzioni creano campi aggiuntivi da compilare, come Personalizzato o Decadimento nel tempo. Puoi creare più metriche utilizzando lo stesso campo, il che significa che puoi averne una [!UICONTROL Last touch] metrica ricavi e una [!UICONTROL First Touch] metrica Ricavo, ma basata sullo stesso campo Ricavo nello schema. |
| [!UICONTROL Lookback window] | Consente di specificare un intervallo di lookback predefinito per una metrica. Le opzioni sono: [!UICONTROL Person] (Finestra di reporting), [!UICONTROL Session], [!UICONTROL Custom]. Quando [!UICONTROL Custom] è selezionato, ti offriamo anche la possibilità di selezionare un numero qualsiasi di giorni/settimane/mesi/ecc. (fino a 90 giorni), proprio come [!UICONTROL Attribution IQ]. Puoi avere più metriche utilizzando lo stesso campo dello schema, ma ciascuna con un intervallo di lookback separato. |
