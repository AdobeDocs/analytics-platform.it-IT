---
description: Scopri come generare presentazioni in formato pptx dai rapporti di Workspace.
keywords: Analysis Workspace
title: Generare presentazioni dai report di Workspace
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 3%

---

# Narrazione dei dati: generare presentazioni di diapositive dai rapporti di Workspace {#generate-powerpoint}

Puoi generare automaticamente presentazioni .pptx dai progetti Analysis Workspace. Durante la generazione delle presentazioni, Customer Journey Analytics identifica automaticamente le informazioni chiave e le converte in diapositive pronte per le parti interessate.

Questa funzionalità riduce il tempo e l’impegno necessari per far emergere i risultati dei progetti Workspace e consente di creare rapidamente narrazioni manageriali e comunicare l’impatto aziendale.

## Generare una presentazione .pptx basata su un progetto Workspace

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Pannelli e visualizzazioni inclusi"
>abstract="Scegli i pannelli e le visualizzazioni da includere nella presentazione. Puoi includere fino a 50 visualizzazioni."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Componenti evidenziati"
>abstract="Scegli fino a 5 metriche e 5 dimensioni dalle visualizzazioni che desideri enfatizzare nella presentazione. Le metriche scelte sono visualizzate in corsivo, le dimensioni in grassetto e gli elementi dimensionali in contrasto."

<!-- markdownlint-enable MD034 -->

1. Passare al progetto Workspace contenente i dati che si desidera utilizzare come base per la presentazione.

1. Seleziona **[!UICONTROL Generate slides]** nell&#39;angolo superiore destro della pagina.

1. Specifica le seguenti informazioni:

   | Opzione | Descrizione |
   |---------|----------|
   | **[!UICONTROL Cover title]** | Specificare un titolo per la presentazione. Questo titolo viene visualizzato nella diapositiva titolo della presentazione. |
   | **[!UICONTROL Include presenter name]** | Specifica il nome del relatore. Questo nome viene visualizzato nella diapositiva del titolo della presentazione, sotto il titolo della copertina. |
   | **[!UICONTROL Panels and visualizations to include]** | Scegli i pannelli e la visualizzazione da includere nella presentazione. Puoi includere fino a 50 visualizzazioni.<p>Sono supportati la maggior parte dei pannelli e delle visualizzazioni. Per informazioni sui pannelli e la visualizzazione non supportati, vedere [Elementi e funzionalità del progetto non supportati](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Panel and visualization descriptions]** | |
   | **[!UICONTROL Annotations]** | |
   | **[!UICONTROL Emphasize components]** | Scegli fino a 5 metriche e 5 dimensioni dalle visualizzazioni che desideri enfatizzare nella presentazione.<p>Quando non viene applicata alcuna enfasi, i componenti vengono visualizzati nelle presentazioni nel modo seguente:<ul><li>**Metriche e dimensioni:** corsivo</li><li>**Elementi Dimension:** virgolette</li></ul></p><p>Quando si applica l’enfasi, i componenti vengono visualizzati nelle presentazioni come segue:</p><ul><li>**Metriche e dimensioni:** corsivo e grassetto</li><li>**Elementi Dimension:** grassetto quando la dimensione corrispondente viene enfatizzata<p>Un colore viene applicato anche all’elemento dimensione quando questo viene evidenziato nel grafico.</p></li></ul> |

(Condizionale) Seleziona **[!UICONTROL Default theme]** se vuoi che le diapositive vengano generate con il tema predefinito.

1. Seleziona se utilizzare un tema predefinito o caricare un modello personalizzato:

   * **[!UICONTROL Default theme]**:

   * **[!UICONTROL Upload template]**:





## Modificare diapositive da una presentazione generata in precedenza


## Scaricare una presentazione .pptx generata

## Elementi e funzionalità del progetto non supportati {#unsupported}

I seguenti elementi e funzioni di Analysis Workspace utilizzati in un progetto non sono supportati durante la generazione delle diapositive:

* Pannello Attribuzione

  Questo pannello viene visualizzato in grigio quando vengono visualizzate le opzioni di configurazione.

  Tutti gli altri pannelli possono essere inclusi nelle diapositive generate da un progetto Workspace.

* Alcune visualizzazioni

  La maggior parte delle visualizzazioni può essere inclusa nelle diapositive generate da un progetto Workspace. Tuttavia, le seguenti visualizzazioni non possono essere incluse e vengono visualizzate in grigio quando vengono visualizzate le opzioni di configurazione:

   * Tabella coorte

   * Area di lavoro del percorso

   * Bullet

   * Combinato

   * A dispersione

   * Mappa ad albero

* Raggruppamenti

* Analisi guidate


