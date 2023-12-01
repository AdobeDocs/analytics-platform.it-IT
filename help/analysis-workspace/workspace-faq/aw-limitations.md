---
description: Scopri le limitazioni note in Adobe Analysis Workspace e nei relativi componenti
title: Limitazioni note in Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: 412cb540af4fd7500821f42d9d89e146644997db
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 81%

---

# Limitazioni note in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando si utilizzano intervalli di date o metriche di date nelle righe di una tabella.
* La funzione Crea metrica da selezione è disabilitata quando i filtri sono utilizzati come righe di una tabella. Inoltre, la funzione Create metric from selection (Crea metrica da selezione) non deve essere applicata a colonne allineate su data.
* La formattazione condizionale per le righe di suddivisione non può utilizzare intervalli personalizzati.
* Le righe dei totali della tabella non possono includere tendenze quando si applica l’impostazione di calcolo dei totali sommando i valori delle righe (generalmente utilizzato per righe con elementi statici).

## Visualizzazioni

* Le visualizzazioni che sfruttano i filtri, come [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort] e [!UICONTROL Histogram], non possono accettare metriche calcolate come input.
* [!UICONTROL Flow]: dimensioni di entrata/uscita, ad esempio [!UICONTROL Entry page], non possono essere utilizzate in Flusso.
* [!UICONTROL Cohort]: i valori non interi non possono essere utilizzati come criteri di coorte.

## Componenti > Filtri

* Alcune metriche e dimensioni non possono essere filtrate, ad esempio [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], ecc.
* Filtri ad hoc creati in [zona di rilascio del pannello](/help/analysis-workspace/c-panels/panels.md) sono un tipo di filtro rapido. Non vengono visualizzati nella barra a sinistra di Workspace o nel Gestore dei componenti del filtro, a meno che non vengano resi pubblici. Per ulteriori informazioni, consulta [Filtri rapidi](/help/components/filters/quick-filters.md).

## Componenti > Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Vedi “Visualizzazioni” sopra.
* Le metriche calcolate non possono essere utilizzate nel pannello [!UICONTROL Attribution], poiché possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se una metrica calcolata viene creata da Workspace (anziché da [!UICONTROL Components > filters], ovvero Componenti > Segmenti). Ad esempio, [!UICONTROL IP Address].

## Componenti > Intervallo date

* Gli intervalli di date personalizzati non supportano [!UICONTROL This day last year], [!UICONTROL This day last month], ecc.


## Componenti > Impostazioni report

* Alcune delle impostazioni sulla pagina [!UICONTROL Report Settings] non sono applicabili. Analysis Workspace utilizza solo le impostazioni [!UICONTROL Language/Currency/Encoding] in basso: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] e [!UICONTROL CSV Separator Character].

