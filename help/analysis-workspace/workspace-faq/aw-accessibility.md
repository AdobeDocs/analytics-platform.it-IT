---
description: Funzioni di supporto per l’accessibilità in Analysis Workspace
title: Accessibilità di Analysis Workspace
translation-type: tm+mt
source-git-commit: e004a2a8ec24113ae8b62a9d30c10fe0eb763460
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 82%

---


# Accessibilità di Analysis Workspace

Scopri il supporto per l’accessibilità in [!UICONTROL Analysis Workspace], lo strumento di analisi principale per Adobe Analytics.

Per accessibilità si intendono i prodotti utilizzabili da persone con disabilità visive, uditive, cognitive, motorie e di altro tipo. Esempi di funzioni di accessibilità per i prodotti software includono il supporto per assistenti vocali, equivalenti testuali per gli elementi grafici, scelte rapide da tastiera, modifica dei colori dello schermo su alto contrasto e così via.

[!UICONTROL Analysis Workspace] fornisce alcuni strumenti che ne rendono accessibile l’utilizzo, tra cui:

## Navigare in [!UICONTROL Workspace] utilizzando la tastiera

La navigazione in [!UICONTROL Analysis Workspace] avviene dall’alto verso il basso e da sinistra a destra. I seguenti elementi di navigazione facilitano l’accessibilità:

* Il tasto `Tab` abilita scelte rapide per punti di riferimento, spostandosi tra le sezioni più grandi di Workspace. Nella barra a sinistra, `Tab` consente anche di passare da un&#39;opzione trascinabile all&#39;altra.
* Lo spostamento `left/right arrows` tra i singoli elementi dopo che `Tab` l&#39;ha evidenziato.
* Il `F6` si sposta sul primo pannello del progetto e tra le visualizzazioni all&#39;interno di tale pannello. Quindi si sposta nel pannello successivo del progetto e si ripete.
* Gli indicatori di focus vengono applicati in modo che gli utenti vedenti che utilizzano la tastiera abbiano un’indicazione chiara dell’elemento dell’interfaccia attualmente attivo. L’indicatore è un bordo blu intorno all’elemento selezionato.

   ![Indicatore di focus](assets/focus-indicator.png)

### Navigazione da tastiera per la barra dei menu

1. Tab finché non viene raggiunta la barra dei menu.
1. Utilizzate i tasti freccia sinistra/destra per passare al menu desiderato.
1. Premere `Enter` per selezionare il menu e visualizzarne le opzioni.
1. Utilizzate i tasti freccia su/giù per passare all&#39;opzione di menu desiderata.
1. Premere `Enter` per selezionare l&#39;opzione.

### Navigazione tramite tastiera per interazioni con trascinamento

[!UICONTROL Analysis Workspace] è un’interfaccia utente di tipo trascina e rilascia. Tuttavia, gli utenti possono in alternativa aggiungere componenti utilizzando la tastiera:

1. Passa a un componente nella barra a sinistra.
1. Premi `Enter` per selezionare.
1. Utilizza i tasti freccia per passare all’area in cui desideri rilasciare il componente.
1. Premi `Enter` per posizionare il componente.

### Scelte rapide da tastiera

[!UICONTROL Analysis Workspace] offre un set completo di [scelte rapide da tastiera](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=it-IT) per un flusso di lavoro più semplice. Di seguito sono elencate alcune scorciatoie comuni per la navigazione, la creazione di analisi e la democratizzazione delle informazioni.

#### Navigazione

| Tasti di scelta rapida | Azione |
|---|---|
| Alt+Maiusc+1 / 2 / 3 | Passa a barre diverse: [!UICONTROL Panels], [!UICONTROL Visualizations] oppure [!UICONTROL Components] |
| Alt+freccia sinistra/destra | Naviga tra i pannelli |
| Alt+M | Comprimi/espandi tutti i pannelli |
| Alt+Ctrl+M | Comprimi/espandi pannello attivo |
| Ctrl+/ | Barra sinistra di ricerca |

#### Creazione di analisi

| Tasti di scelta rapida | Azione |
|---|---|
| Alt+1 | Nuova tabella a forma libera |
| Ctrl+Maiusc+C | Nuova metrica calcolata |
| Ctrl+Maiusc+D | Nuovo intervallo date |
| Ctrl+Maiusc+E | Nuovo segmento |
| Ctrl+Z | Annulla |
| Pressione prolungata di Maiusc (nella zona di rilascio del segmento del pannello) | Crea un [filtro a discesa](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=it-IT) |

#### Democratizzazione

| Tasti di scelta rapida | Azione |
|---|---|
| Ctrl+S | Salva |
| Ctrl+Maiusc+G | Cura |
| Ctrl+G | Condividi |
| Alt+Maiusc+S | Pianificazione |
| Alt+L | Ottieni collegamento al progetto |
| Ctrl+Maiusc+B | Scarica PDF |

## Supporto per assistenti vocali e lenti di ingrandimento dello schermo

Un assistente vocale legge il testo visualizzato sullo schermo del computer. Vengono inoltre lette informazioni non testuali, come etichette di pulsanti o descrizioni delle immagini nell’applicazione fornite nei tag o negli attributi di accessibilità.

## Palette di colori e contrasto

[!UICONTROL Analysis Workspace] si impegna per essere conforme a WCAG 2.1 AA, compresi i requisiti per il contrasto del colore.

Inoltre, gli utenti possono impostare la propria palette di colori preferita per un progetto in **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=it-IT).

## Convalida dei campi obbligatori nei generatori di componenti

Quando si crea un componente, i campi obbligatori vengono convalidati al momento del salvataggio. Se un campo obbligatorio non supera la convalida, viene evidenziato in rosso con un’icona di errore. Viene visualizzata una descrizione scritta del problema da risolvere.

Quando un componente viene convalidato completamente, premendo `Save` viene chiuso il generatore.

![Convalida non superata](assets/error-validation.png)

## Supporto per le funzioni di accessibilità del sistema operativo

Analysis Workspace supporta funzioni integrate di accessibilità di MS Windows e macOS come modalità ad alto contrasto, tasti permanenti e tempo di pressione/filtro tasti. Fornisce inoltre informazioni sull’interfaccia utente del sistema operativo per consentire l’interazione con le tecnologie di assistenza, compresi gli assistenti vocali come VoiceOver per macOS e NVDA su Windows.
