---
title: Che cosa sono i componenti in Customer Journey Analytics?
description: Scopri quali componenti offre Customer Journey Analytics e come puoi utilizzarli nella generazione di rapporti.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '1046'
ht-degree: 100%

---

# Panoramica dei componenti

I componenti sono funzionalità di Customer Journey Analytics che possono essere utilizzate nei rapporti o che integrano le funzioni di reporting. Puoi gestire questi componenti procedendo come segue:

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) utilizzando le tue credenziali Adobe ID.
2. Vai su [!UICONTROL Components] > [!UICONTROL Components] nel menu intestazione.

Puoi gestire i seguenti componenti:

* [**Annotazioni**](/help/components/annotations/overview.md): comunica informazioni e sfumature di dati contestuali alla tua organizzazione.
* [**Tipi di pubblico**](/help/components/audiences/audiences-overview.md): crea e pubblica i tipi di pubblico rilevati in Customer Journey Analytics (CJA) nel [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) (RTCDP) in Adobe Experience Platform per la personalizzazione e il targeting dei clienti.
* [**Filtri**](filters/filters-overview.md): creare, gestire, condividere e applicare filtri per tipi di pubblico efficaci e mirati ai rapporti. I filtri consentono di identificare sottoinsiemi di persone in base a caratteristiche o interazioni.
* [**Metriche calcolate:**](calc-metrics/calc-metr-overview.md) utilizza metriche e formule come nuovi componenti da utilizzare nella generazione rapporti.
* [**Dizionario dei dati**](/help/components/data-dictionary/data-dictionary-overview.md): consente sia agli utenti che agli amministratori di tenere traccia e comprendere meglio i componenti nell’ambiente Analytics.
* [**Intervalli di date**](date-ranges/create.md): personalizza e perfeziona gli intervalli di date che offre Analysis Workspace.
* [**Dimensioni**](/help/components/dimensions/view-dimensions.md): le dimensioni sono delle variabili che in genere contengono valori stringa. Le dimensioni comuni includono la pagina e il dominio di riferimento.
* [**Metriche**](/help/components/apply-create-metrics.md): consentono di quantificare i punti di dati in Analysis Workspace.
* [**Progetti**](/help/analysis-workspace/home.md): organizza e gestisci i progetti in Analysis Workspace.

## Componenti di Analysis Workspace

I componenti in Analysis Workspace sono metriche, dimensioni, filtri e granularità temporali da trascinare e rilasciare su un progetto. I componenti creati, come ad esempio gli intervalli di date personalizzati, vengono aggiunti a questi pannelli.

Per accedere al pannello Componenti, fai clic su **[!UICONTROL Components]** nella barra a sinistra. Puoi cambiare Pannello (pannello vuoto, [pannello a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md) o pannello [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md)), [Visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) e Componenti utilizzando le icone nella barra a sinistra o i [tasti di scelta rapida](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![Pannello Workspace con l’icona Componenti evidenziata nella barra a sinistra](assets/components.png)

Vedi [Creazione di un progetto](/help/analysis-workspace/home.md) per informazioni sull’utilizzo di Componenti all’interno di un progetto.

## Azioni dei componenti

Sono disponibili diversi metodi di gestione dei componenti (singolarmente o selezionandone più di uno). Fai clic con il pulsante destro del mouse su un componente oppure fai clic su **[!UICONTROL Actions]** in alto nell’elenco dei componenti.

>[!NOTE]
>
>Queste azioni non si applicano ai componenti Time.

| Azione del componente | Descrizione |
| --- | --- |
| Tag | Organizzare o gestire i componenti tramite l’applicazione di tag. Viene quindi visualizzato nel rispettivo Component Manager (Gestione componenti), come [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Filters], oppure [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects] |
| Preferito | Aggiungere il componente all’elenco dei preferiti. Viene quindi visualizzato nel rispettivo gestione componenti, come [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL filters]oppure [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects]. |
| Approva | Approvare il componente per renderlo canonico. Viene quindi visualizzato nel rispettivo gestione componenti, come [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Filters] oppure  [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Projects] |
| Condividi | Applicabile solo ai filtri. |
| Delete (Elimina) | Applicabile solo ai filtri. |

Guarda il video su Creazione di metriche, filtri e date:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Gestire i componenti {#actions}

Puoi gestire i componenti direttamente nella barra a sinistra.

1. Fai clic con il pulsante destro del mouse su un componente.

   Oppure

   Seleziona un componente, quindi l’icona **Azione** (tre punti in verticale) in alto nell’elenco dei componenti.

   >[!TIP]
   >
   >   È possibile selezionare più componenti tenendo premuto Maiusc oppure tenendo premuto Comando (su Mac) o Ctrl (su Windows).


   ![Elenco Azioni componenti che mostra Tag, Preferiti, Approva, Condividi ed Elimina.](assets/component-actions.png)

   | Azione componenti | Descrizione |
   |--- |--- |
   | [!UICONTROL **Tag**] | Organizzare o gestire i componenti tramite l’applicazione di tag. Per eseguire la ricerca per tag nella barra a sinistra, fai clic sul filtro o digita #. I tag fungono anche da filtri nei gestori dei componenti. |
   | [!UICONTROL **Preferito**] | Aggiungere il componente all’elenco dei preferiti. Come per i tag, puoi cercare i Preferiti nella barra a sinistra e filtrarli nei gestori dei componenti. |
   | [!UICONTROL **Approva**] | Contrassegna i componenti come approvati per segnalare agli utenti che sono approvati dall’organizzazione. Come per i tag, puoi eseguire ricerche per compomenti approvati nella barra a sinistra e filtrarli nei gestori dei componenti. |
   | [!UICONTROL **Condividi**] | Condividi i componenti con gli utenti della tua organizzazione. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio filtri o metriche calcolate. |
   | [!UICONTROL **Elimina**] | Elimina i componenti non più necessari. Questa opzione è disponibile solo per i componenti personalizzati, ad esempio filtri o metriche calcolate. |

I componenti personalizzati possono essere gestiti anche tramite i rispettivi gestori di componenti. Ad esempio, [Gestione filtri](/help/components/filters/manage-filters.md).

## Cercare, filtrare e ordinare l’elenco dei componenti

Puoi cercare, filtrare e ordinare l’elenco dei componenti nella barra a sinistra di Analysis Workspace per individuare rapidamente un particolare componente.

### Cercare nell’elenco dei componenti

1. Seleziona l’icona **Componenti** ![icona Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nella barra a sinistra.

2. Nel campo di ricerca, inizia a digitare il nome del componente che desideri utilizzare nel progetto.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimensioni** ![icona Dimensione](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Filtri** ![icona Filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sono blu, **Intervalli di date** ![icona Intervallo di date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sono viola, e **Metriche** ![icona Metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sono verdi. L’icona Adobe ![icona Adobe](assets/default-calc-metric-icon.png) indica un modello di metrica calcolata o un modello di filtro, e l’icona della calcolatrice ![icona Calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore Analytics della tua organizzazione.

3. Seleziona il componente quando viene visualizzato nell’elenco a discesa.

### Filtrare l’elenco dei componenti

1. Seleziona l’icona **Componenti** ![icona Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nella barra a sinistra.

2. Seleziona l’icona **Filtro** ![icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)).

   Oppure

   Digita il cancelletto (#) nel campo di ricerca.

3. Per filtrare l’elenco dei componenti, seleziona una delle seguenti opzioni filtro:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | [!UICONTROL **Preferiti**] | Mostra solo i componenti inclusi nell’elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Gestisci componenti](#manage-components). |
   | [!UICONTROL **Dimensioni**] | Mostra solo i componenti che sono Dimensioni. |
   | [!UICONTROL **Metriche**] | Mostra solo i componenti che sono Metriche. |
   | [!UICONTROL **Filtri**] | Mostra solo i componenti che sono Filtri. |
   | [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono Intervalli di date. |
   | [!UICONTROL **Mostra tutti**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, questo è utile per identificare i componenti che richiedono la revisione e l’approvazione. Questa opzione è disponibile solo per gli amministratori. |

4. (Facoltativo) Per affinare ulteriormente l’elenco, puoi ordinare l’elenco dei componenti come descritto in [Ordinare l’elenco dei componenti](#sort-the-component-list).

### Ordinare l’elenco dei componenti

{{release-limited-testing-section}}

1. (Facoltativo) Applica i filtri all’elenco dei componenti, come descritto in [Filtrare l’elenco dei componenti](#filter-the-component-list).

2. Seleziona l’icona **Componenti** ![icona Componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) nella barra a sinistra.

3. (Facoltativo) Seleziona l’icona **Ordina** ![icona Ordina componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), quindi seleziona una delle seguenti opzioni di filtro per ordinare l’elenco dei componenti:

   {{components-sort-options}}

## Autorizzazioni di accesso ai componenti

In Analysis Workspace, gli amministratori possono [curare](/help/analysis-workspace/curate-share/curate.md) quali componenti sono esposti agli utenti nel reporting.
