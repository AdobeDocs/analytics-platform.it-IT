---
title: Che cosa sono i componenti in Customer Journey Analytics?
description: Scopri quali componenti offre Customer Journey Analytics e come puoi utilizzarli nella generazione di rapporti.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 33%

---

# Panoramica dei componenti

I componenti sono funzioni di Customer Journey Analytics che possono essere utilizzate nelle visualizzazioni (come le tabelle a forma libera) o che integrano le funzioni di reporting.

Per gestire i componenti dall&#39;interfaccia principale del Customer Journey Analytics:

1. Seleziona **[!UICONTROL Components]** dalla barra superiore.
1. Selezionare **[!UICONTROL Components]** per visualizzare una panoramica dei componenti che è possibile gestire oppure selezionare direttamente il componente che si desidera gestire dal menu.

Puoi gestire i seguenti componenti:

* [Filtri](filters/filters-overview.md): creare, gestire, condividere e applicare filtri per tipi di pubblico efficaci e mirati ai rapporti. I filtri consentono di identificare sottoinsiemi di persone in base a caratteristiche o interazioni.
* [Metriche calcolate:](calc-metrics/calc-metr-overview.md) utilizza metriche e formule come nuovi componenti da utilizzare nella generazione rapporti.
* [Intervalli di date](date-ranges/create.md): personalizza e perfeziona gli intervalli di date che offre Analysis Workspace.
* [Annotazioni](/help/components/annotations/overview.md): comunica informazioni e sfumature di dati contestuali alla tua organizzazione.
* [Avvisi intelligenti](/help/components/c-intelligent-alerts/intelligent-alerts.md): consenti di ricevere notifiche in base alle percentuali modificate o a punti dati specifici.
* [Progetti pianificati](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): gestisci i progetti pianificati.
* [Preferenze](/help/analysis-workspace/user-preferences.md): gestisci le preferenze per Analysis Workspace.
* [Tipi di pubblico](/help/components/audiences/audiences-overview.md): crea e pubblica tipi di pubblico dal Customer Journey Analytics in [Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home), ad Experience Platform per il targeting e la personalizzazione.
* [Esportazioni](/help/components/exports/manage-export-locations.md): gestisci l&#39;account e i percorsi di esportazione.


## Componenti di Analysis Workspace

I componenti in Analysis Workspace sono metriche, dimensioni, filtri e intervalli di date da trascinare su pannelli e visualizzazioni nel progetto Workspace. I componenti personalizzati creati vengono aggiunti a questi pannelli, ad esempio una metrica calcolata o un intervallo di date personalizzato.

Per accedere al pannello Componenti, seleziona ![Cura](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** nel pannello del pulsante.

![Pannello Workspace con l’icona Componenti evidenziata nella barra a sinistra](assets/components.png)

Per informazioni sull&#39;utilizzo dei componenti in un progetto, vedere [Creare un progetto](/help/analysis-workspace/home.md).


+++ Visualizza un video che mostra le possibilità dei componenti:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

+++

## Gestire i componenti {#actions}

È possibile creare rapidamente un nuovo componente utilizzando il menu **[!UICONTROL Components]** in Analysis Workspace. Per ulteriori dettagli, consulta il [menu Analysis Workspace](/help/analysis-workspace/home.md#menu).

Puoi gestire i componenti (singolarmente o selezionandone più di uno).

1. Seleziona uno o più componenti.

1. Dal menu di scelta rapida o dal pulsante ![AltreVerticali](/help/assets/icons/MoreVertical.svg) azioni del componente (nella parte superiore di Componenti), selezionare una delle azioni seguenti.


   >[!TIP]
   >
   >È possibile selezionare più componenti tenendo premuto **[!UICONTROL Shift]** o tenendo premuto **[!UICONTROL Command]** (su macOS) o **[!UICONTROL Ctrl]** (su Windows).


   ![Elenco Azioni componenti che mostra Tag, Preferiti, Approvazione, Condivisione ed Eliminazione.](assets/component-menu.gif){width=100%}

   | Azione del componente | Descrizione |
   |--- |--- |
   | ![Etichetta](/help/assets/icons/Label.svg) [!UICONTROL **Tag**] | Organizzare o gestire i componenti tramite l’applicazione di tag. Puoi quindi eseguire ricerche per tag nel pannello a sinistra selezionando il filtro ![Filtro](/help/assets/icons/Filter.svg) o digitando `#`. I tag fungono anche da filtri nei gestori dei componenti. |
   | ![Stella](/help/assets/icons/Star.svg) [!UICONTROL **Preferito**] | Aggiungere il componente all’elenco dei preferiti. Come per i tag, puoi cercare i Preferiti nel pannello a sinistra e filtrarli nei gestori dei componenti. |
   | ![ContornoStella](/help/assets/icons/StarOutline.svg) **[!UICONTROL Un-favorite]** | Rimuovi il componente dall’elenco dei preferiti. |
   | ![Segno di spunta](/help/assets/icons/Checkmark.svg) [!UICONTROL **Approva**] | Contrassegna i componenti come approvati per segnalare agli utenti che sono approvati dall’organizzazione. Come per i tag, nel pannello a sinistra puoi cercare e filtrare per Approvato. Un ![segno di spunta](/help/assets/icons/Checkmark.svg) identifica i componenti approvati. |
   | ![Condividi](/help/assets/icons/ShareAlt.svg) [!UICONTROL **Condividi**] | Condividi i componenti con gli utenti della tua organizzazione. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio filtri o metriche calcolate. |
   | ![Elimina](/help/assets/icons/Delete.svg) [!UICONTROL **Elimina**] | Elimina i componenti non più necessari. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio filtri o metriche calcolate. |

I componenti personalizzati possono essere gestiti anche tramite i rispettivi gestori di componenti. Ad esempio, vedi [Gestire i filtri](/help/components/filters/manage-filters.md).

## Gestire l’elenco dei componenti

Per individuare un particolare componente, puoi cercare, filtrare e ordinare l’elenco dei componenti nel pannello a sinistra di Analysis Workspace.

### Ricerca

1. Seleziona **Componenti** ![Icona Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nel pannello a sinistra.

2. Nel campo di ricerca, inizia a digitare il nome del componente che desideri visualizzare nel progetto.

   Un colore e un’icona identificano il tipo di componente. **Dimension** ![Icona Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Filtri** ![Icona filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) è blu, **Intervalli di date** ![Icona intervallo di date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) è viola e **Metriche** ![Icona metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) è verde.<br/>L&#39;icona Adobe ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) indica un modello di metrica calcolata o un modello di filtro. L&#39;icona del calcolatore ![icona del calcolatore](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore dell&#39;organizzazione.

3. Seleziona il componente dall’elenco a discesa.

### Filtro

1. Seleziona l&#39;icona **Componenti** ![Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nel pannello a sinistra.

2. Seleziona **Filtro** ![Icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) oppure immetti `#` nel campo di ricerca.

3. Per filtrare l’elenco dei componenti, seleziona una delle seguenti opzioni filtro:

   | Icona | Opzione filtro | Descrizione |
   |---------|---|----------|
   | ![Segno di spunta](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Approved]** | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | ![Stella](/help/assets/icons/Star.svg) | **[!UICONTROL Favorites]** | Mostra solo i componenti inclusi nell’elenco dei Preferiti. <br/>Per informazioni sull&#39;aggiunta di componenti all&#39;elenco dei preferiti, vedere [Gestione componenti](#manage-components). |
   | ![Dimensioni](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensions]** | Mostra solo i componenti che sono Dimensioni. |
   | ![Evento](/help/assets/icons/Event.svg) | **[!UICONTROL Metrics]** | Mostra solo i componenti che sono Metriche. |
   | ![Segmentazione](/help/assets/icons/Segmentation.svg) | **[!UICONTROL Filters]** | Mostra solo i componenti che sono Filtri. |
   | ![Calendario](/help/assets/icons/Calendar.svg) | **[!UICONTROL Date ranges]** | Mostra solo i componenti che sono intervalli di date. |
   | ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL *Nome tag *]** | Mostra solo i componenti con i tag selezionati specifici. Per Adobe Template è disponibile un tag dedicato, ovvero le [metriche calcolate predefinite](/help/components/calc-metrics/default-calcmetrics.md) di Adobe. |

   Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) in un filtro per rimuovere il filtro.

4. Facoltativamente, è possibile ordinare l&#39;elenco dei componenti come descritto in [Ordinare l&#39;elenco dei componenti](#sort-the-component-list).

### Ordina

<!-- {{release-limited-testing-section}}-->

1. (Facoltativo) Applica i filtri all’elenco dei componenti, come descritto in [Filtrare l’elenco dei componenti](#filter-the-component-list).

2. Seleziona **Componenti** ![Icona Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nel pannello a sinistra.

3. Seleziona **Ordina** ![Ordina icona componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), quindi seleziona una delle seguenti opzioni di filtro per ordinare l&#39;elenco dei componenti.

Sono disponibili le seguenti opzioni di ordinamento:

{{components-sort-options}}

## Autorizzazioni di accesso

In Analysis Workspace, gli amministratori possono [curare](/help/analysis-workspace/curate-share/curate.md) quali componenti sono esposti agli utenti nel reporting.
