---
description: Elenco delle limitazioni note in Adobe Analysis Workspace e dei relativi componenti
title: Limitazioni note in Analysis Workspace
translation-type: tm+mt
source-git-commit: 7f6afbb7c0376791c286021d9ffe4ac670ed7bd7
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 85%

---


# Limitazioni note in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando si utilizzano intervalli di date o metriche di date nelle righe di una tabella.
* La funzione Create metric from selection (Crea metrica da selezione) è disabilitata quando i segmenti sono utilizzati come righe di una tabella. Inoltre, la funzione Create metric from selection (Crea metrica da selezione) non deve essere applicata a colonne allineate su data.
* La formattazione condizionale per le righe di suddivisione non può utilizzare intervalli personalizzati.
* Le righe dei totali della tabella non possono includere tendenze quando si applica l’impostazione di calcolo dei totali sommando i valori delle righe (generalmente utilizzato per righe con elementi statici).
* [!UICONTROL Contribution Analysis] può essere eseguita con granularità [!UICONTROL daily] _esclusivamente_. Non può essere eseguita con dati [!UICONTROL hourly], [!UICONTROL weekly], ecc.

## Visualizzazioni

* Le visualizzazioni che sfruttano la segmentazione, come [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort] e [!UICONTROL Histogram], non possono accettare metriche calcolate come input.
* [!UICONTROL Flow]: dimensioni di entrata/uscita, ad esempio [!UICONTROL Entry page], non possono essere utilizzate in Flusso.
* [!UICONTROL Cohort]: i valori non interi non possono essere utilizzati come criteri di coorte.

## Pannelli

* Confronto segmenti: il segmento [!UICONTROL Everyone Else] non viene creato se viene utilizzato un modello di segmento nella zona di rilascio iniziale.

## Componenti > Filtri

* Alcune metriche e dimensioni non possono essere filtrate, come [!UICONTROL Occurrences], [!UICONTROL Unique Visitors] e così via.
* I filtri ad hoc creati nel [pannello dropzone](/help/analysis-workspace/c-panels/panels.md) non vengono visualizzati nella barra a sinistra di Workspace o nel gestore dei componenti Filtro, a meno che non vengano resi pubblici. A tale scopo, è possibile modificare il filtro e selezionare **[!UICONTROL Make this filter public]**.

## Componenti > Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Vedi “Visualizzazioni” sopra.
* Le metriche calcolate non possono essere utilizzate nel pannello [!UICONTROL Attribution], poiché possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se una metrica calcolata viene creata da Workspace (anziché da [!UICONTROL Components > Segments], ovvero Componenti > Segmenti). Ad esempio, [!UICONTROL IP Address].

## Componenti > Intervallo date

* Gli intervalli di date personalizzati non supportano [!UICONTROL This day last year], [!UICONTROL This day last month], ecc.


## Componenti > Impostazioni report

* Alcune delle impostazioni sulla pagina [!UICONTROL Report Settings] non sono applicabili. Analysis Workspace utilizza solo le impostazioni [!UICONTROL Language/Currency/Encoding] in basso: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] e [!UICONTROL CSV Separator Character].

## Attribution IQ

* Un sottoinsieme di metriche non è supportato in [!UICONTROL Attribution IQ]. Per un elenco completo, vedi le [domande frequenti relative ad Attribution IQ](../attribution/faq.md).
