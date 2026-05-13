---
description: Scopri le limitazioni note in Adobe Analysis Workspace e i relativi componenti
title: Limitazioni note
feature: Workspace Basics
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
TQID: https://experienceleague.adobe.com/rbguvYCSFfbmMVr5IBC1M9OD0wDIG0Z4p28Z2dOerBc
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 54%

---

# Limitazioni note

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando si utilizzano intervalli di date o metriche di date nelle righe di una tabella.
* La funzione Create metric from selection (Crea metrica da selezione) è disabilitata quando i segmenti sono utilizzati come righe di una tabella. Inoltre, la funzione Create metric from selection (Crea metrica da selezione) non deve essere applicata a colonne allineate su data.
* La formattazione condizionale per le righe di raggruppamento non può utilizzare intervalli personalizzati.
* Le righe dei totali della tabella non possono includere tendenze quando si applica l’impostazione di calcolo dei totali sommando i valori delle righe (generalmente utilizzato per righe con elementi statici).

## Visualizzazioni

* Le visualizzazioni che sfruttano i segmenti, come [!UICONTROL Abbandono], [!UICONTROL Flusso], [!UICONTROL Coorte] e [!UICONTROL Istogramma], non possono accettare metriche calcolate come input.
* [!UICONTROL Flusso]: le dimensioni di entrata/uscita, ad esempio [!UICONTROL Pagina di ingresso], non possono essere utilizzate in Flusso.
* [!UICONTROL Coorte]: i valori non interi non possono essere utilizzati come criteri di coorte.

## Segmenti

* Alcune metriche e dimensioni non possono essere segmentate, ad esempio [!UICONTROL Eventi], [!UICONTROL Persone], ecc.
* I segmenti ad hoc creati nella [zona di rilascio del pannello](/help/analysis-workspace/c-panels/panels.md) sono un tipo di segmento rapido. Non vengono visualizzati nel pannello a sinistra di Workspace o in Gestione segmenti, a meno che non vengano resi pubblici. Per ulteriori informazioni, consulta [Segmenti rapidi](/help/components/segments/seg-quick.md).

## Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Consulta [Visualizzazioni](#visualizations).
* Le metriche calcolate non possono essere utilizzate nel pannello [!UICONTROL Attribuzione], in quanto possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se una metrica calcolata viene creata da Workspace (anziché da [!UICONTROL Componenti > segmenti]). Ad esempio, [!UICONTROL Indirizzo IP].

## Intervalli di date

* Gli intervalli di date personalizzati non supportano [!UICONTROL Questo giorno lo scorso anno], [!UICONTROL Questo giorno lo scorso mese], ecc.


## Impostazioni dei rapporti

* Alcune delle impostazioni nella pagina [!UICONTROL Impostazioni report] non sono applicabili. Analysis Workspace utilizza solo le impostazioni [!UICONTROL Lingua/Valuta/Codifica] in basso: [!UICONTROL Separatore delle migliaia], [!UICONTROL Codifica report pianificata] e [!UICONTROL Carattere separatore CSV].

