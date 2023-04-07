---
description: Elenco delle limitazioni note in Adobe Analysis Workspace e dei relativi componenti
title: Limitazioni note in Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: c21eb39e0af36ad54fd675c147e2f50b6b00711a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---

# Limitazioni note in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando si utilizzano intervalli di date o metriche di date nelle righe di una tabella.
* La funzione Crea metrica da selezione è disabilitata quando i filtri sono utilizzati come righe di una tabella. Inoltre, la funzione Create metric from selection (Crea metrica da selezione) non deve essere applicata a colonne allineate su data.
* La formattazione condizionale per le righe di suddivisione non può utilizzare intervalli personalizzati.
* Le righe dei totali della tabella non possono includere tendenze quando si applica l’impostazione di calcolo dei totali sommando i valori delle righe (generalmente utilizzato per righe con elementi statici).
* [!UICONTROL Contribution Analysis] può essere eseguita con granularità [!UICONTROL daily] _esclusivamente_. Non può essere eseguita con dati [!UICONTROL hourly], [!UICONTROL weekly], ecc.

## Visualizzazioni

* Le visualizzazioni che sfruttano i filtri, come [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort] e [!UICONTROL Histogram], non possono accettare metriche calcolate come input.
* [!UICONTROL Flow]: dimensioni di entrata/uscita, ad esempio [!UICONTROL Entry page], non possono essere utilizzate in Flusso.
* [!UICONTROL Cohort]: i valori non interi non possono essere utilizzati come criteri di coorte.

## Componenti > Filtri

* Alcune metriche e dimensioni non possono essere filtrate, ad esempio [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], ecc.
* I filtri ad hoc creati nell’[area di rilascio del pannello](/help/analysis-workspace/c-panels/panels.md) non vengono visualizzati nella barra a sinistra di Workspace o nel gestore dei componenti del filtro, a meno che non vengano resi pubblici. Per rendere pubblico un filtro occorre modificarlo e selezionare **[!UICONTROL Make this filter public]**.

## Componenti > Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Vedi “Visualizzazioni” sopra.
* Le metriche calcolate non possono essere utilizzate nel pannello [!UICONTROL Attribution], poiché possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se una metrica calcolata viene creata da Workspace (anziché da [!UICONTROL Components > filters], ovvero Componenti > Segmenti). Ad esempio, [!UICONTROL IP Address].

## Componenti > Intervallo date

* Gli intervalli di date personalizzati non supportano [!UICONTROL This day last year], [!UICONTROL This day last month], ecc.


## Componenti > Impostazioni report

* Alcune delle impostazioni sulla pagina [!UICONTROL Report Settings] non sono applicabili. Analysis Workspace utilizza solo le impostazioni [!UICONTROL Language/Currency/Encoding] in basso: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] e [!UICONTROL CSV Separator Character].

