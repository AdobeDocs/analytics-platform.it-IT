---
keywords: Analysis Workspace
title: Panoramica di Analysis Workspace
description: Scopri Analysis Workspace, lo strumento di analisi principale per Adobe Analytics. Utilizza progetti, pannelli, tabelle, visualizzazioni e altri componenti per dare vita ai dati e per curare e condividere le analisi.
feature: Workspace Basics
exl-id: 9075518e-54fe-49a6-9601-aa9468187b8f
solution: Customer Journey Analytics
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1490'
ht-degree: 86%

---

# Panoramica di Analysis Workspace {#analysis-workspace-overview}

Analysis Workspace consente di realizzare rapidamente le analisi per raccogliere informazioni e quindi condividerle con altri utenti. Utilizzando l’interfaccia di trascinamento del browser, puoi creare analisi, aggiungere visualizzazioni per mettere in risalto i dati, curare un set di dati, condividere e pianificare [progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md) con chiunque desideri.

>[!BEGINSHADEBOX]

Per un video demo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panoramica di Analysis Workspace](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]

## Interfaccia

L’immagine seguente e la tabella associata illustrano gli elementi principali dell’interfaccia utente di Analysis Workspace:

![Finestra di Analysis Workspace che evidenzia le varie sezioni dell’interfaccia](assets/analysis-workspace-overview.png)

| Posizione | Nome e funzione |
|:---------:|----------|
| A | Contiene il nome del progetto, una struttura di menu per accedere alle funzionalità, un pulsante ![Indietro](/help/assets/icons/ChevronLeft.svg) per tornare all&#39;elenco dei progetti e un pulsante **[!UICONTROL Condividi]** per [condividere il progetto Workspace](/help/analysis-workspace/curate-share/share-projects.md). <br/>Seleziona il nome del progetto (ad esempio: Nuovo progetto) in qualsiasi momento per modificare il nome. <br/>Seleziona ![Unfavor](/help/assets/icons/StarOutline.svg) per contrassegnare il progetto come progetto preferito ![Favor](/help/assets/icons/Star.svg). |
| B | **Pannello pulsanti:** contiene i pulsanti per accedere alle [funzionalità](#features) chiave di Analysis Workspace:<ul><li>![PaginaWeb](/help/assets/icons/WebPage.svg) [[!UICONTROL Pannelli]](/help/analysis-workspace/c-panels/panels.md)</li><li>![Analisi guidata](/help/assets/icons/GuidedAnalysis.svg) [[!UICONTROL Analisi guidata]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL Visualizzazioni]](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![Cura](/help/assets/icons/Curate.svg) [[!UICONTROL Componenti]](/help/components/overview.md)</li><li>![VisualizzaElenco](/help/assets/icons/ViewList.svg) [[!UICONTROL Sommario]](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![Segnalibro](/help/assets/icons/Bookmark.svg) [[!UICONTROL Dizionario dati]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **Pannello a sinistra:** quest’area contiene pannelli singoli, visualizzazioni, componenti o elenchi. Il contenuto dipende dal pulsante selezionato nel pannello pulsante. |
| D | **Area di lavoro:** area principale in cui trascini il contenuto dal pannello a sinistra per creare il progetto. Il progetto viene aggiornato dinamicamente quando aggiungi pannelli, visualizzazioni ai pannelli e componenti alle visualizzazioni. Puoi creare più pannelli e, all’interno di ogni pannello, creare più visualizzazioni.<br/>Ogni pannello si basa su una visualizzazione dati selezionata. La visualizzazione dati selezionata determina i componenti disponibili, come metriche e dimensioni. Per ulteriori informazioni, consulta [Pannelli: dati di riepilogo](/help/analysis-workspace/c-panels/panels.md#data-view). |

## Funzioni

Le funzioni chiave di Analysis Workspace sono disponibili tramite il pannello pulsante:

| Icona | Funzione | Descrizione |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL Pannelli]** | I [pannelli](/help/analysis-workspace/c-panels/panels.md) servono per organizzare l’analisi all’interno di un progetto e possono contenere diverse tabelle e visualizzazioni. Molti dei pannelli forniti in Analysis Workspace generano un intero set di analisi basate su alcuni input dell’utente. |
| ![Analisi guidata](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL Analisi guidata]** | L’[Analisi guidata](../guided-analysis/overview.md) ti consente di gestire autonomamente dati e informazioni di alta qualità sul percorso cliente tramite flussi di lavoro guidati. Puoi creare un’analisi da includere nel progetto Workspace o includere un’analisi esistente salvata in precedenza. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL Visualizzazioni]** | [Visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), ad esempio un grafico a barre o a linee che può essere utilizzato per mettere visivamente in risalto i dati. Nel pannello a sinistra, seleziona l&#39;icona centrale **[!UICONTROL Visualizzazioni]** per visualizzare l&#39;elenco completo delle visualizzazioni disponibili. |
| ![Cura](/help/assets/icons/Curate.svg) | **[!UICONTROL Componenti]** | I [Componenti](/help/components/overview.md) includono i seguenti elementi:<ul><li>![Dimensioni](/help/assets/icons/Dimensions.svg) [Dimensioni](/help/components/dimensions/overview.md)</li><li>![Evento](/help/assets/icons/Event.svg) [Metriche](/help/components/apply-create-metrics.md)</li><li>![Segmentazione](/help/assets/icons/Segmentation.svg) [Segmenti](/help/components/segments/seg-overview.md)</li><li>![Calendario](/help/assets/icons/Calendar.svg) [Intervalli di date](/help/components/date-ranges/overview.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL Sommario]** | Il sommario organizza tutti i pannelli e le visualizzazioni inclusi nel progetto in un elenco comprimibile, che consente di accedere rapidamente a un pannello specifico o a una visualizzazione specifica. |
| ![Segnalibro](/help/assets/icons/Bookmark.svg) | **Dizionario dati** | Il [Dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md) aiuta sia agli utenti che agli amministratori a tenere traccia e comprendere meglio i componenti nell’ambiente Analytics. |


## Menu

La maggior parte delle funzionalità di Analysis Workspace è disponibile tramite trascinamento e menu di scelta rapida all’interno di pannelli, visualizzazioni e componenti.

La funzionalità è anche disponibile tramite il menu di Workspace e i tasti di scelta rapida. I tasti di scelta rapida variano a seconda del sistema operativo su cui è in esecuzione il browser. Per una panoramica, consulta le seguenti tabelle.

Sulla tastiera possono essere utilizzati i seguenti simboli:

- **⇧** per **[!UICONTROL *Maiusc *]**.
- **⌘** per **[!UICONTROL *Comando *]**(comando).
- **⌃** per **[!UICONTROL *Ctrl *]**(controllo).
- **⌥** per **[!UICONTROL *Opzione *]**(opzione).
- **⎇** per **[!UICONTROL *Alt *]**(alternativo).

Per una panoramica dei menu disponibili, consulta le seguenti tabelle.

| **[!UICONTROL Progetto]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Crea progetto]** | **[!UICONTROL *Maiusc+Comando+p *]** | **[!UICONTROL *Maiusc+Ctrl+p *]** | Crea un nuovo progetto. |
| **[!UICONTROL Creare una scorecard per dispositivi mobili]** | | | [Crea una scorecard per dispositivi mobili](/help/mobile-app/create-scorecard.md). |
| **[!UICONTROL Apri...]** | **[!UICONTROL *Comando+o *]** | **[!UICONTROL *Ctrl+o *]** | [Apri un progetto esistente](/help/analysis-workspace/build-workspace-project/save-projects.md#open-another-project). |
| **[!UICONTROL Apri versione precedente...]** | **[!UICONTROL *Opzione+Comando+o *]** | **[!UICONTROL *Alt+Ctrl+o *]** | [Apri le versioni precedenti del progetto](/help/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version). |
| **[!UICONTROL Salva]** | **[!UICONTROL *Comando+s *]** | **[!UICONTROL *Ctrl+s *]** | [Salva il progetto](/help/analysis-workspace/build-workspace-project/save-projects.md#save-projects). |
| **[!UICONTROL Salva con note...]** | **[!UICONTROL *Opzione+Comando+s *]** | **[!UICONTROL *Alt+Ctrl+s *]** | [Aggiungi note alla versione del progetto salvata](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Salva con nome...]** | **[!UICONTROL *Maiusc+Comando+s *]** | **[!UICONTROL *Maiusc+Ctrl+s *]** | [Salva il progetto utilizzando un nome e dettagli diversi](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Aggiorna progetto]** | **[!UICONTROL *Opzione+r *]** | **[!UICONTROL *Alt+r *]** | Aggiorna il progetto. |
| **[!UICONTROL Scarica CSV]** | **[!UICONTROL *Maiusc+Comando+v *]** | **[!UICONTROL *Maiusc+Ctrl+v *]** | Esporta il proggetto come file CSV. |
| **[!UICONTROL Scarica PDF]** | **[!UICONTROL *Maiusc+Comando+b *]** | **[!UICONTROL *Maiusc+Ctrl+b *]** | Scarica il progetto come documento PDF. |
| **[!UICONTROL Informazioni e impostazioni progetto]** | | | Definisci le impostazioni per i progetti, ad esempio nome, tag, palette di colori e altro ancora. |
| **[!UICONTROL Impostazioni utente]** | | | [Configura le preferenze per l’utilizzo di Analysis Workspace](/help/analysis-workspace/user-preferences.md). |


| **[!UICONTROL Modifica]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Annulla]** | **[!UICONTROL *Comando+z *]** | **[!UICONTROL *Ctrl+z *]** | Annulla l’azione precedente. |
| **[!UICONTROL Ripristina]** | **[!UICONTROL *Comando+Maiusc+z *]** | **[!UICONTROL *Ctrl+Maiusc+z *]** | Ripristina l’azione precedente. |
| **[!UICONTROL Cancella tutto]** | **[!UICONTROL *Opzione+w *]** | **[!UICONTROL *Alt+w *]** | Cancella tutti i pannelli nel progetto corrente. |

| **[!UICONTROL Inserisci]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Pannello vuoto]** | **[!UICONTROL *Opzione+b *]** | **[!UICONTROL *Alt+b *]** | Inserisci un [pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md). |
| **[!UICONTROL Visualizzatori simultanei di contenuti multimediali]** | **[!UICONTROL *Opzione+h *]** | **[!UICONTROL *Alt-h *]** | Inserisci un pannello [Visualizzatori simultanei contenuti multimediali](/help/analysis-workspace/c-panels/media-concurrent-viewers.md). |
| **[!UICONTROL Tempo trascorso su contenuti multimediali]** | **[!UICONTROL *Opzione+i *]** | **[!UICONTROL *Alt+i *]** | Inserisci un pannello [Tempo trascorso su contenuti multimediali](/help/analysis-workspace/c-panels/media-playback-time-spent.md). |
| **[!UICONTROL Pubblico medio per minuto del file multimediale]** | **[!UICONTROL *Opzione+m *]** | **[!UICONTROL *Alt+m *]** | Inserisci un pannello per [Pubblico medio per minuto del file multimediale](/help/analysis-workspace/c-panels/average-minute-audience-panel.md). |
| **[!UICONTROL Attribuzione]** | **[!UICONTROL *Opzione+e *]** | **[!UICONTROL *Alt+e *]** | Inserisci un pannello [Attribuzione](/help/analysis-workspace/c-panels/attribution.md). |
| **[!UICONTROL A forma libera]** | **[!UICONTROL *Opzione+a *]** | **[!UICONTROL *Alt+a *]** | Inserisci un pannello [A forma libera](/help/analysis-workspace/c-panels/freeform-panel.md). |
| **[!UICONTROL Quick Insights]** | **[!UICONTROL *Opzione+j *]** | **[!UICONTROL *Alt+j *]** | Inserisci un pannello [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md). |
| **[!UICONTROL Sperimentazione]** | **[!UICONTROL *Opzione+x *]** | **[!UICONTROL *Alt+x *]** | Inserisci un pannello [Sperimentazione](/help/analysis-workspace/c-panels/experimentation.md). |
| **[!UICONTROL Tabella a forma libera]** | **[!UICONTROL *Opzione+1 *]** | **[!UICONTROL *Alt+1 *]** | Inserisci una visualizzazione [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). |
| **[!UICONTROL Linee]** | **[!UICONTROL *Opzione+2 *]** | **[!UICONTROL *Alt+2 *]** | Inserisci una visualizzazione [A linee](/help/analysis-workspace/visualizations/line.md). |
| **[!UICONTROL Barre]** | **[!UICONTROL *Opzione+3 *]** | **[!UICONTROL *Alt+3 *]** | Inserisci una visualizzazione [A barre](/help/analysis-workspace/visualizations/bar.md). |
| **[!UICONTROL Combinato]** | **[!UICONTROL *Opzione+4 *]** | **[!UICONTROL *Alt+4 *]** | Inserisci una visualizzazione [Combinato](/help/analysis-workspace/visualizations/combo-charts.md). |


| **[!UICONTROL Componenti]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Crea segmento...]** | **[!UICONTROL *Maiusc+Comando+e *]** | **[!UICONTROL *Maiusc+Ctrl+e *]** | Crea un nuovo [segmento](/help/components/segments/seg-create.md). |
| **[!UICONTROL Crea metrica...]** | **[!UICONTROL *Maiusc+Comando+c *]** | **[!UICONTROL *Maiusc+Ctrl+c *]** | Crea una nuova [metrica calcolata](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Crea intervallo di date...]** | **[!UICONTROL *Maiusc+Comando+d *]** | **[!UICONTROL *Maiusc+Ctrl+d *]** | Crea un nuovo [intervallo di date](/help/components/date-ranges/overview.md). |
| **[!UICONTROL Crea annotazione...]** | **[!UICONTROL *Maiusc+Comando+o *]** | **[!UICONTROL *Maiusc+Ctrl+o *]** | Crea una nuova [annotazione](/help/components/annotations/overview.md). |
| **[!UICONTROL Crea pubblico...]** | **[!UICONTROL *Maiusc+Comando+u *]** | **[!UICONTROL *Maiusc+Ctrl+u *]** | Crea un nuovo [pubblico](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Aggiorna componenti]** | **[!UICONTROL *Opzione+Maiusc+r *]** | **[!UICONTROL *Alt+Maiusc+r *]** | Aggiorna i componenti nel progetto. |

| **[!UICONTROL Condividi]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Condividi con utenti Workspace]** | **[!UICONTROL *Comando+h *]** | **[!UICONTROL *Ctrl+h *]** | [Condividi il progetto con altri utenti di Workspace](/help/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization). |
| **[!UICONTROL Condividi con chiunque]** | **[!UICONTROL *Opzione+l *]** | **[!UICONTROL *Alt+l *]** | [Condividi una versione di sola lettura del progetto con un altro utente](/help/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project). |
| **[!UICONTROL Invia file]** | **[!UICONTROL opt+s]** | **[!UICONTROL *Alt+s *]** | [Invia il progetto come file CSV o PDF ad altri destinatari](/help/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Pianifica esportazione file]** | **[!UICONTROL *Maiusc+Opzione+s *]** | **[!UICONTROL *Maiusc+Alt+s *]** | [Invia il progetto secondo una pianificazione come file CSV o PDF ad altri destinatari](/help/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Cura dati progetto]** | **[!UICONTROL *Maiusc+Comando+g *]** | **[!UICONTROL *Maiusc+Ctrl+g *]** | [Cura i dati del progetto](/help/analysis-workspace/curate-share/curate.md). |

| Aiuto | Descrizione |
|---|---|
| **[!UICONTROL Videos]** | Apri il canale YouTube di Customer Journey Analytics in una nuova scheda del browser. |
| **[!UICONTROL Documentazione della Guida]** | Apri la documentazione (quella che stai leggendo in questo momento) in una nuova scheda del browser. |
| **[!UICONTROL Forum della Guida]** | Apri il forum delle community Experience League per Adobe Analytics in una nuova scheda del browser. |
| **[!UICONTROL Tasti di scelta rapida]** | Mostra una panoramica dei tasti di scelta rapida che è possibile utilizzare in Workspace. |
| **[!UICONTROL Abilita debugger]** | Abilita il debugger. Il progetto verrà ricaricato. |
| **[!UICONTROL Disabilita debugger]** | Disabilita il debugger. Il progetto verrà ricaricato. |
| **[!UICONTROL Prestazioni]** | Visualizza una finestra di dialogo che mostra le metriche sulle **[!UICONTROL prestazioni Analysis Workspace]**. Utilizza **[!UICONTROL Scarica come CSV]** per scaricare un file CSV delle metriche delle prestazioni. |
| **[!UICONTROL Informazioni su Workspace]** | Mostra una finestra di dialogo **[!UICONTROL Informazioni su Analysis Workspace]** con informazioni sulla versione, i livelli di accesso alle funzionalità e i flag di funzionalità attivi. |

## Origini dati

Sincronizza le visualizzazioni per controllare quale tabella dati oppure origine dati corrisponde a una visualizzazione. Per ulteriori informazioni, consulta come [gestire le origini dati](/help/analysis-workspace/visualizations/t-sync-visualization.md).

## Utilizzare Analysis Workspace


Per iniziare a utilizzare Analysis Workspace:

1. Accedi ad [Adobe Experience Cloud](https://experience.adobe.com).
1. Seleziona **[!UICONTROL Customer Journey Analytics]** dal commutatore di app ![App](/help/assets/icons/Apps.svg) in alto a destra nell&#39;interfaccia.
1. Per impostazione predefinita, viene visualizzata la pagina **[!UICONTROL Progetti]** di Analysis Workspace. Se è stato selezionato per un progetto specifico o hai lavorato sul progetto di recente, questo viene mostrato per impostazione predefinita.

### Creare un progetto

Un’analisi in Analysis Workspace è definita come [progetto](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

Puoi creare un progetto in Analysis Workspace come descritto in [Creare progetti](/help/analysis-workspace/build-workspace-project/create-projects.md).

I progetti possono essere organizzati in cartelle e sottocartelle, come descritto in [Cartelle in Analysis Workspace](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Salvare e condividere un progetto

Quando crei un’analisi in Analysis Workspace, il lavoro viene [salvato automaticamente](/help/analysis-workspace/build-workspace-project/save-projects.md).

Una volta che il progetto è stato completato e sta raccogliendo informazioni approfondite fruibili, altri potrebbero volerlo utilizzare. Puoi condividere il progetto con utenti e gruppi dell’organizzazione o anche con persone esterne a questa. Per informazioni sulla condivisione di un progetto, consulta [Condividere progetti](/help/analysis-workspace/curate-share/share-projects.md).

## Risorse aggiuntive {#resources}

- La pagina di destinazione [Apprendimento](/help/getting-started/landing.md#learning) in Customer Journey Analytics. Questa pagina è un ottimo modo per acquisire familiarità con Analysis Workspace. In particolare la parte Apprendimento delle nozioni di base di Workspace. Questo modello spiega la terminologia e i passaggi comuni per la realizzazione della prima analisi in Workspace
- Adobe offre centinaia di [tutorial di formazione video per Analytics](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/overview).
- Per aggiornamenti sulle nuove funzioni, consulta [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/it/docs/release-notes/experience-cloud/current).

