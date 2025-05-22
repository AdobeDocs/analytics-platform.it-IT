---
title: Che cosa sono i componenti in Customer Journey Analytics?
description: Scopri quali componenti offre Customer Journey Analytics e come puoi utilizzarli nella generazione di rapporti.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 95%

---

# Panoramica dei componenti

I componenti sono funzioni di Customer Journey Analytics che possono essere utilizzate nelle visualizzazioni (come Tabella a forma libera) o per integrare le funzioni di reporting.

Per gestire i componenti dall’interfaccia principale di Customer Journey Analytics:

1. Seleziona **[!UICONTROL Components]** nella barra superiore.
1. Seleziona **[!UICONTROL Components]** per visualizzare una panoramica dei componenti che puoi gestire oppure seleziona direttamente il componente che desideri gestire dal menu.

Puoi gestire i seguenti componenti:

* [Segmenti](filters/filters-overview.md): crea, gestisci, condividi e applica segmenti di pubblico potenti e incentrati sui tuoi rapporti. I segmenti ti consentono di identificare sottoinsiemi di persone in base a caratteristiche o interazioni.
* [Metriche calcolate:](calc-metrics/calc-metr-overview.md) utilizza metriche e formule come nuovi componenti da utilizzare nella generazione rapporti.
* [Intervalli di date](date-ranges/create.md): personalizza e perfeziona gli intervalli di date che offre Analysis Workspace.
* [Annotazioni](/help/components/annotations/overview.md): comunica alla tua organizzazione informazioni e dettagli contestuali sui dati.
* [Avvisi intelligenti](/help/components/c-intelligent-alerts/intelligent-alerts.md): consentono di ricevere notifiche in base a percentuali di cambiamento o a punti dati specifici.
* [Progetti pianificati](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): gestisci i progetti pianificati.
* [Preferenze](/help/analysis-workspace/user-preferences.md): gestisci le preferenze di Analysis Workspace.
* [Tipi di pubblico](/help/components/audiences/audiences-overview.md): crea e pubblica i tipi di pubblico da Customer Journey Analytics a [Real-Time Customer Data Platform](https://experienceleague.adobe.com/it/docs/experience-platform/profile/home) in Experience Platform per la personalizzazione e il targeting.
* [Esportazioni](/help/components/exports/manage-export-locations.md): gestisci l’account e le posizioni di esportazione.


## Componenti di Analysis Workspace

I componenti in Analysis Workspace costituiscono metriche, dimensioni, segmenti e intervalli di date che puoi trascinare su pannelli e visualizzazioni nel progetto Workspace. I componenti creati, come ad esempio una metrica calcolata, vengono aggiunti a questi pannelli o a un intervallo di date personalizzato.

Per accedere al pannello Componenti, seleziona ![Cura](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** nel pannello del pulsante.

![Pannello Workspace con l’icona Componenti evidenziata nella barra a sinistra](assets/components.png)

Consulta [Creare un progetto](/help/analysis-workspace/home.md) per informazioni su come utilizzare i componenti all’interno di un progetto.


## Gestire i componenti {#actions}

È possibile creare rapidamente un nuovo componente utilizzando il menu **[!UICONTROL Components]** in Analysis Workspace. Per ulteriori dettagli, consulta il [menu Analysis Workspace](/help/analysis-workspace/home.md#menu).

Puoi gestire i componenti (singolarmente o selezionandone più di uno).

1. Seleziona uno o più componenti.

1. Dal menu di scelta rapida o dal pulsante ![MoreVertical](/help/assets/icons/MoreVertical.svg) Azioni componente (nella parte superiore di Componenti), seleziona una delle azioni seguenti.


   >[!TIP]
   >
   >Per selezionare più componenti, tieni premuto **[!UICONTROL Shift]** oppure **[!UICONTROL Command]** (su macOS) o **[!UICONTROL Ctrl]** (su Windows).


   ![Elenco Azioni componenti che mostra Tag, Preferiti, Approva, Condividi ed Elimina.](assets/component-menu.gif){width=100%}

   | Azione componenti | Descrizione |
   |--- |--- |
   | ![Etichetta](/help/assets/icons/Label.svg) [!UICONTROL **Tag**] | Organizzare o gestire i componenti tramite l’applicazione di tag. Puoi eseguire la ricerca nel pannello a sinistra facendo clic sul filtro ![Filtra](/help/assets/icons/Filter.svg) o digitando `#`. I tag fungono anche da filtri nei gestori dei componenti. |
   | ![Stella](/help/assets/icons/Star.svg) [!UICONTROL **Preferiti**] | Aggiunge il componente all’elenco dei preferiti. Come per i tag, puoi cercare i Preferiti nel pannello a sinistra e filtrarli nei gestori dei componenti. |
   | ![StarOutline](/help/assets/icons/StarOutline.svg) **[!UICONTROL Un-favorite]** | Rimuovi il componente dall’elenco dei preferiti. |
   | ![Segno di spunta](/help/assets/icons/Checkmark.svg) [!UICONTROL **Approva**] | Contrassegna i componenti come approvati per segnalare agli utenti che sono approvati dall’organizzazione. Come per i tag, puoi cercare e filtrare per Approvato nel pannello a sinistra. Un ![Segno di spunta](/help/assets/icons/Checkmark.svg) identifica i componenti approvati. |
   | ![Condividi](/help/assets/icons/ShareAlt.svg) [!UICONTROL **Condividi**] | Condividi i componenti con gli utenti della tua organizzazione. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio segmenti o metriche calcolate. |
   | ![Elimina](/help/assets/icons/Delete.svg) [!UICONTROL **Elimina**] | Elimina i componenti non più necessari. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio segmenti o metriche calcolate. |

I componenti personalizzati possono essere gestiti anche tramite i rispettivi gestori di componenti. Ad esempio, consulta [Gestire i segmenti](/help/components/filters/manage-filters.md).

## Gestione dell’elenco dei componenti

Puoi cercare, filtrare e ordinare l’elenco dei componenti nel pannello a sinistra di Analysis Workspace per individuare un particolare componente.

### Ricerca

1. Seleziona **Componenti** ![icona Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nel pannello a sinistra.

2. Nel campo di ricerca, inizia a digitare il nome del componente da visualizzare nel progetto.

   Un colore e un’icona identificano il tipo di componente. **Le dimensioni** ![icona di Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Segmenti** ![icona segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) è blu, **Intervalli di date** ![icona intervallo di date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) è viola e **Metriche** ![icona metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) è verde.<br/>L’icona Adobe ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) indica un modello di metrica calcolata o un modello di segmento. L’icona della calcolatrice ![icona calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore dell’organizzazione.

3. Seleziona il componente dal menu a discesa.

### Filtro

1. Seleziona l’icona **Componenti** ![icona Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nel pannello a sinistra.

2. Seleziona **Filtro** ![Icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) oppure immetti `#` nel campo di ricerca.

3. Per filtrare l’elenco dei componenti, seleziona una delle seguenti opzioni filtro:

   | Icona | Opzione filtro | Descrizione |
   |---------|---|----------|
   | ![Segno di spunta](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Approved]** | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | ![Stella](/help/assets/icons/Star.svg) | **[!UICONTROL Favorites]** | Mostra solo i componenti inclusi nell’elenco dei Preferiti. <br/>Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Gestire i componenti](#manage-components). |
   | ![Dimensioni](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensions]** | Mostra solo i componenti che sono Dimensioni. |
   | ![Evento](/help/assets/icons/Event.svg) | **[!UICONTROL Metrics]** | Mostra solo i componenti che sono Metriche. |
   | ![Segmentazione](/help/assets/icons/Segmentation.svg) | **[!UICONTROL Segments]** | Mostra solo i componenti che sono segmenti. |
   | ![Calendario](/help/assets/icons/Calendar.svg) | **[!UICONTROL Date ranges]** | Mostra solo i componenti che sono Intervalli di date. |
   | ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL *Nome tag *]** | Mostra solo i componenti con i tag selezionati specifici. È disponibile un tag dedicato Adobe Template, per le [metriche calcolate predefinite](/help/components/calc-metrics/default-calcmetrics.md) fornite da Adobe. |

   Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) in un filtro per rimuovere il filtro.

4. Facoltativamente, è possibile ordinare l’elenco dei componenti come descritto in [Ordinare l’elenco dei componenti](#sort-the-component-list).

### Ordina

<!-- {{release-limited-testing-section}}-->

1. (Facoltativo) Applica i filtri all’elenco dei componenti, come descritto in [Filtrare l’elenco dei componenti](#filter-the-component-list).

2. Seleziona **Componenti** ![icona Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nel pannello a sinistra.

3. Seleziona **Ordina** ![icona Ordina componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), quindi seleziona una delle seguenti opzioni filtro per ordinare l’elenco dei componenti.

Sono disponibili le seguenti opzioni di ordinamento:

{{components-sort-options}}

## Autorizzazioni di accesso

In Analysis Workspace, gli amministratori possono [curare](/help/analysis-workspace/curate-share/curate.md) i progetti, per fornire agli utenti una selezione di componenti accessibili per le attività di reporting.
