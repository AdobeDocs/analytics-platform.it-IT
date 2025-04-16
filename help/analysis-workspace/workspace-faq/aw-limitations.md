---
description: Scopri le limitazioni note in Adobe Analysis Workspace e i relativi componenti
title: Limitazioni note in Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 86%

---

# Limitazioni note in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando si utilizzano intervalli di date o metriche di date nelle righe di una tabella.
* La funzione Crea metrica da selezione è disabilitata quando i filtri sono utilizzati come righe di una tabella. Inoltre, la funzione Create metric from selection (Crea metrica da selezione) non deve essere applicata a colonne allineate su data.
* La formattazione condizionale per le righe di suddivisione non può utilizzare intervalli personalizzati.
* Le righe dei totali della tabella non possono includere tendenze quando si applica l’impostazione di calcolo dei totali sommando i valori delle righe (generalmente utilizzato per righe con elementi statici).

## Visualizzazioni

* Le visualizzazioni che sfruttano segmenti quali [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort] e [!UICONTROL Histogram] non possono accettare metriche calcolate come input.
* [!UICONTROL Flow]: dimensioni di entrata/uscita, ad esempio [!UICONTROL Entry page], non possono essere utilizzate in Flusso.
* [!UICONTROL Cohort]: i valori non interi non possono essere utilizzati come criteri di coorte.

## Filtri

* Alcune metriche e dimensioni non possono essere segmentate, ad esempio [!UICONTROL Events], [!UICONTROL Persons] e così via.
* I segmenti ad hoc creati nella zona di rilascio [pannello](/help/analysis-workspace/c-panels/panels.md) sono un tipo di segmento rapido. Non vengono visualizzati nel pannello a sinistra di Workspace o nel gestore dei componenti Filtro a meno che non vengano resi pubblici. Per ulteriori informazioni, consultare [Segmenti rapidi](/help/components/filters/quick-filters.md).

## Metriche calcolate 

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Consulta [Visualizzazioni](#visualizations).
* Le metriche calcolate non possono essere utilizzate nel pannello [!UICONTROL Attribution], poiché possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se una metrica calcolata viene creata da Workspace (anziché da [!UICONTROL Components > segments], ovvero Componenti > Segmenti). Ad esempio, [!UICONTROL IP Address].

## Intervalli di date

* Gli intervalli di date personalizzati non supportano [!UICONTROL This day last year], [!UICONTROL This day last month], ecc.


## Impostazioni dei rapporti

* Alcune delle impostazioni sulla pagina [!UICONTROL Report Settings] non sono applicabili. Analysis Workspace utilizza solo le impostazioni [!UICONTROL Language/Currency/Encoding] in basso: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] e [!UICONTROL CSV Separator Character].

