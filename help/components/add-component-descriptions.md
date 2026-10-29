---
description: Scopri come gli amministratori possono aggiungere descrizioni ai componenti utilizzando una visualizzazione dati o il dizionario dati.
title: Aggiungere descrizioni dei componenti
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# Aggiungere descrizioni dei componenti

Le descrizioni consentono agli utenti di sapere come utilizzare i vari componenti durante la creazione di progetti in Analysis Workspace o la visualizzazione di rapporti.

Gli amministratori di Customer Journey Analytics possono aggiungere descrizioni per i componenti (dimensioni, metriche, segmenti e intervalli di date) all’interno di una visualizzazione dati o utilizzando il dizionario dati.

## Visualizzazione dati

Puoi aggiungere una descrizione a un componente aggiunto alla visualizzazione dati. Vedere [Impostazioni dei componenti](/help/data-views/component-settings/overview.md).

## Dizionario dati

Il dizionario dati in Analysis Workspace consente sia agli utenti che agli amministratori di tenere traccia dei componenti del proprio ambiente Customer Journey Analytics e di comprenderli meglio. Il dizionario dati consente agli amministratori di aggiungere descrizioni dei componenti direttamente in Analysis Workspace.

Per informazioni sulla modifica della descrizione di un componente nel dizionario dati, vedere [Modificare le voci dei componenti nel dizionario dati](/help/components/data-dictionary/edit-entries-data-dictionary.md).

Per informazioni generali sul dizionario dati, vedere la [Panoramica del dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md).

>[!MORELIKETHIS]
>
>[Impostazioni del componente Visualizzazione dati](/help/data-views/component-settings/overview.md)
>[Voci del componente del dizionario dati](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## Genera automaticamente descrizioni

{{release-limited-testing-section}}

Invece di scrivere ogni descrizione manualmente, Customer Journey Analytics può utilizzare l’intelligenza artificiale generativa per scrivere le descrizioni. È possibile generare una descrizione per un singolo componente o per più componenti contemporaneamente.

Descrizioni generate:

* Non sono lunghe più di 3 frasi.
* Termina con il testo **[!UICONTROL Generato da Adobe utilizzando AI]**, in modo che gli utenti sappiano che la descrizione è stata generata.
* Possono essere modificati dopo essere stati generati.

### Prerequisiti

Prima di poter generare le descrizioni, l’organizzazione deve accettare alcuni termini legali generativi di IA. Se l’organizzazione non ha accettato questi termini, l’opzione per generare le descrizioni non è disponibile. Seleziona l&#39;icona delle informazioni ![Informazioni](/help/assets/icons/InfoOutline.svg) accanto all&#39;opzione per scoprire come abilitare la funzione, oppure contatta l&#39;amministratore della tua organizzazione o il team dell&#39;account Adobe.

### Generazione delle descrizioni

Le descrizioni generate si basano sulla definizione del componente e su un contesto aggiuntivo relativo al modo in cui il componente viene utilizzato nella visualizzazione dati, ad esempio:

* Elementi principali di una dimensione
* Componenti utilizzati di frequente con il componente

Quando una metrica calcolata o un segmento fa riferimento a un altro segmento, la descrizione generata spiega la definizione del segmento di riferimento.

### Genera descrizioni da varie posizioni

Puoi generare descrizioni nelle seguenti aree di Customer Journey Analytics. Alcune posizioni consentono di generare descrizioni per più componenti, mentre altre no.

Seleziona una posizione per scoprire come generare le descrizioni.

| Posizione | Componenti supportati | Componente singolo | Componenti multipli |
| --- | --- | --- | --- |
| [Dizionario dati](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>Dimensioni</li><li>Metriche</li><li>Metriche calcolate</li><li>Segmenti</li><li>Intervalli di date</li></ul> | Sì | Sì |
| [Visualizzazione dati](/help/data-views/component-settings/overview.md) | <ul><li>Dimensioni</li><li>Metriche</li><li>Campi derivati</li><li>Metriche e dimensioni condivise (per ulteriori informazioni, vedi [Metriche e dimensioni condivise](#generate-descriptions-for-shared-metrics-and-dimensions).)</li></ul> | Sì | Sì |
| [Generatore di segmenti](/help/components/segments/seg-builder.md) | Segmenti | Sì | No |
| [Gestione segmenti](/help/components/segments/seg-manage.md#action-bar) | Segmenti | No | Sì |
| [Generatore di metrica calcolata](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | Metriche calcolate | Sì | No |
| [Gestione metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | Metriche calcolate | No | Sì |
| [Generatore di intervalli di date](/help/components/date-ranges/create.md#date-range-builder) | Intervalli di date | Sì | No |
| [Gestione intervalli date](/help/components/date-ranges/manage.md#action-bar) | Intervalli di date | No | Sì |

{style="table-layout:auto"}

### Generare descrizioni per metriche e dimensioni condivise

Puoi generare descrizioni per metriche e dimensioni condivise solo dall&#39;interno di una visualizzazione dati, come mostrato nella tabella in [Generare descrizioni da varie posizioni](#generate-descriptions-from-various-locations). Impossibile generare descrizioni dal [Gestione metriche e dimensioni condivise](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager).

Quando generi una descrizione per una metrica o dimensione condivisa all’interno di una visualizzazione dati, considera quanto segue:

* La descrizione si applica a tutte le visualizzazioni dati in cui il componente è condiviso e sostituisce qualsiasi descrizione esistente per quel componente in tutte le altre visualizzazioni dati e nel gestore Metriche e dimensioni condivise.

* La descrizione si basa sul contesto della visualizzazione dati in cui viene generata, ad esempio gli elementi dimensionali principali della visualizzazione dati.


