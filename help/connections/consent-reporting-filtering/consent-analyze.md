---
title: Analizzare i dati dei criteri di consenso in Customer Journey Analytics
description: Scopri come utilizzare dimensioni, metriche e modelli dei criteri di consenso per creare rapporti sull’iscrizione ai criteri di consenso dei visitatori in Analysis Workspace.
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hide: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 7bb16378fc8813ca126cb786c5d36bf9daa0fe7d
workflow-type: tm+mt
source-wordcount: 388
ht-degree: 2%

---

# Analizzare i dati dei criteri di consenso

Puoi acquisire i dati dei criteri di consenso dai set di dati del profilo di Experience Platform in una connessione Customer Journey Analytics.

Dopo aver [creato una configurazione di reporting e filtro del consenso](/help/connections/consent-reporting-filtering/consent-configure.md) e abilitato il reporting, i dati dei criteri di consenso diventano disponibili come nuovi componenti nelle visualizzazioni dati nella connessione configurata. Puoi utilizzare questi componenti ovunque in Analysis Workspace, se hai accesso a una visualizzazione dati in cui esistono.

## Componenti dei criteri di consenso

Il reporting sul consenso aggiunge i seguenti componenti alle visualizzazioni dati. Questi componenti vengono letti dal campo `consentPoliciesIDMap` nel set di dati profilo e i nomi e le descrizioni dei criteri provengono dal set di dati di ricerca dei criteri di consenso.

### Dimensioni

| Dimensione | Descrizione |
|---------|----------|
| **[!UICONTROL ID criterio di consenso]** | Identificatore di un criterio di consenso corrispondente a un visitatore. |
| **[!UICONTROL Nome criterio]** | Il nome descrittivo del criterio di consenso, dal set di dati di ricerca del criterio di consenso. |
| **[!UICONTROL Descrizione criterio]** | Descrizione del criterio di consenso, dal set di dati di ricerca del criterio di consenso. |

### Metriche

| Metrica | Descrizione |
|---------|----------|
| **[!UICONTROL Visitatori con consenso]** | Il numero di visitatori che corrispondono a un criterio di consenso. |
| **[!UICONTROL Eventi con consenso]** | Il numero di eventi associati ai visitatori che corrispondono a un criterio di consenso. |
| **[!UICONTROL Criteri di consenso univoci]** | Il numero di criteri di consenso distinti rappresentati nell’intervallo di reporting. |

### Campo derivato

Un campo derivato fa riferimento al campo `consentPoliciesIDMap` per estrarre gli ID dei criteri di consenso. Puoi utilizzare questo campo derivato come base per dimensioni aggiuntive basate sul consenso. Per ulteriori informazioni sui campi derivati, vedere [Campi derivati](/help/data-views/derived-fields/derived-fields.md).

## Utilizzare i componenti dei criteri di consenso in Analysis Workspace

Per generare rapporti sull’iscrizione ai criteri di consenso:

1. In Analysis Workspace, apri un progetto che utilizza una visualizzazione dati configurata per la generazione di rapporti sul consenso.

1. Dal pannello dei componenti, trascina una dimensione del criterio di consenso, ad esempio **[!UICONTROL Nome criterio]**, in una tabella a forma libera.

1. Aggiungi una metrica di consenso, ad esempio **[!UICONTROL Visitatori con consenso]**, alla tabella.

1. Suddividi i risultati per qualsiasi altra dimensione, ad esempio Pagina o Canale, per capire come si comportano i visitatori consenzienti.

## Utilizzare il modello di analisi dei criteri di consenso

Quando una visualizzazione dati è configurata per la generazione di rapporti sul consenso, Customer Journey Analytics rende automaticamente disponibile in Analysis Workspace un modello di analisi dei criteri di consenso. Questo modello fornisce un punto di partenza per la generazione di rapporti sull’iscrizione ai criteri di consenso dei visitatori.

Per informazioni su come accedere ai modelli, vedere [Accedere ed eseguire un modello](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template).
