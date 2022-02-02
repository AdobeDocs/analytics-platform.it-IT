---
description: Elenco delle limitazioni note in Adobe Analysis Workspace e dei relativi componenti
title: Limitazioni note in Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 75%

---

# Limitazioni note in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando si utilizzano intervalli di date o metriche di date nelle righe di una tabella.
* La funzione Crea metrica da selezione è disabilitata quando i filtri vengono utilizzati come righe di una tabella. Inoltre, la funzione Create metric from selection (Crea metrica da selezione) non deve essere applicata a colonne allineate su data.
* La formattazione condizionale per le righe di suddivisione non può utilizzare intervalli personalizzati.
* Le righe dei totali della tabella non possono includere tendenze quando si applica l’impostazione di calcolo dei totali sommando i valori delle righe (generalmente utilizzato per righe con elementi statici).
* [!UICONTROL Contribution Analysis] può essere eseguita con granularità [!UICONTROL daily] _esclusivamente_. Non può essere eseguita con dati [!UICONTROL hourly], [!UICONTROL weekly], ecc.

## Visualizzazioni

* Visualizzazioni che sfruttano i filtri, come [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort]e [!UICONTROL Histogram], non può accettare metriche calcolate come input.
* [!UICONTROL Flow]: dimensioni di entrata/uscita, ad esempio [!UICONTROL Entry page], non possono essere utilizzate in Flusso.
* [!UICONTROL Cohort]: i valori non interi non possono essere utilizzati come criteri di coorte.

## Componenti > Filtri

* Alcune metriche e dimensioni non possono essere filtrate, ad esempio [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], ecc.
* Filtri ad hoc creati nel [zona di rilascio del pannello](/help/analysis-workspace/c-panels/panels.md) non vengono visualizzati nella barra a sinistra di Workspace o nel Gestore componenti filtro, a meno che non siano resi pubblici. Per eseguire questa operazione, modifica il filtro e seleziona **[!UICONTROL Make this filter public]**.

## Componenti > Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Vedi “Visualizzazioni” sopra.
* Le metriche calcolate non possono essere utilizzate nel pannello [!UICONTROL Attribution], poiché possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se una metrica calcolata viene creata da Workspace (anziché da [!UICONTROL Components > filters], ovvero Componenti > Segmenti). Ad esempio, [!UICONTROL IP Address].

## Componenti > Intervallo date

* Gli intervalli di date personalizzati non supportano [!UICONTROL This day last year], [!UICONTROL This day last month], ecc.


## Componenti > Impostazioni report

* Alcune delle impostazioni sulla pagina [!UICONTROL Report Settings] non sono applicabili. Analysis Workspace utilizza solo le impostazioni [!UICONTROL Language/Currency/Encoding] in basso: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] e [!UICONTROL CSV Separator Character].

## Attribution IQ

* Un sottoinsieme di metriche non è supportato in [!UICONTROL Attribution IQ]. Per un elenco completo, vedi le [domande frequenti relative ad Attribution IQ](../attribution/faq.md).
