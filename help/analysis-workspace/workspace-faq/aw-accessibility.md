---
description: Funzioni di supporto per l'accessibilità in  Analysis Workspace
title: Accessibilità di Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 5%

---


# Accessibilità di Analysis Workspace

>[!NOTE]
>
>Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Scoprite il supporto per l&#39;accessibilità in [!UICONTROL Analysis Workspace], lo strumento di analisi principale per Adobe  Analytics.

Per accessibilità si intendono i prodotti utilizzabili per persone con disabilità visive, uditive, cognitive, motorie e di altro tipo. Esempi di funzioni di accessibilità per i prodotti software includono il supporto per assistenti vocali, equivalenti testuali per gli elementi grafici, scelte rapide da tastiera, la modifica dei colori dello schermo ad alto contrasto e così via.

[!UICONTROL Analysis Workspace] fornisce alcuni strumenti che ne rendono accessibile l’utilizzo, tra cui:

## Navigare [!UICONTROL Workspace] utilizzando la tastiera

Navigazione in [!UICONTROL Analysis Workspace] lavori in alto > in basso e a sinistra > a destra. I seguenti elementi di navigazione facilitano l&#39;accessibilità:

* La `F6` chiave abilita collegamenti con punti di riferimento
* La `Tab` chiave si sposta tra i singoli elementi.
* Gli indicatori di messa a fuoco vengono applicati in modo che gli utenti della tastiera vedente abbiano un&#39;indicazione chiara dell&#39;elemento dell&#39;interfaccia attualmente attivo. L&#39;indicatore è un bordo blu intorno all&#39;elemento selezionato.

   ![Indicatore di messa a fuoco](assets/focus-indicator.png)

### Navigazione tramite tastiera per interazioni con trascinamento

[!UICONTROL Analysis Workspace] è un&#39;interfaccia utente drag &amp; drop. Tuttavia, gli utenti possono aggiungere componenti utilizzando la tastiera:

1. Passa a un componente nella barra a sinistra.
1. Premere `Enter` per selezionare.
1. Utilizzare i tasti freccia per passare all&#39;area in cui si desidera rilasciare il componente.
1. Premere `Enter` per posizionare il componente.

### Scelte rapide da tastiera (tasti di scelta rapida)

[!UICONTROL Analysis Workspace] offre un set completo di scelte rapide da [tastiera](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) per un flusso di lavoro più semplice. Di seguito sono elencate alcune scorciatoie comuni per la navigazione, la creazione di analisi e la democratizzazione delle informazioni.

#### Navigazione

| Tasti di scelta rapida | Azione |
|---|---|
| Alt + Maiusc + 1 / 2 / 3 | Passare a diverse rotaie: [!UICONTROL Panels], [!UICONTROL Visualizations]oppure [!UICONTROL Components] |
| Alt + freccia sinistra/destra | Spostamento tra i pannelli |
| Alt + M | Comprimere/espandere tutti i pannelli |
| Alt+ Ctrl + M | Comprimere/espandere il pannello attivo |
| Ctrl + / | Barra di ricerca sinistra |

#### Creazione di analisi

| Tasti di scelta rapida | Azione |
|---|---|
| Alt + 1 | Nuova tabella a forma libera |
| Ctrl + Maiusc + C | Nuova metrica calcolata |
| Ctrl+Maiusc+D | Nuovo intervallo date |
| Ctrl + Maiusc + E | Nuovo segmento |
| Ctrl + Z | Annulla |
| Maiusc (nella zona di rilascio del segmento del pannello) | Creare un filtro a [discesa](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) |

#### Democratizzazione

| Tasti di scelta rapida | Azione |
|---|---|
| Ctrl + S | Salva |
| Ctrl + Maiusc + G | Cura |
| Ctrl + G | Condividi |
| Alt + Maiusc + S | Pianificazione |
| Alt + L | Ottieni collegamento al progetto |
| Ctrl + Maiusc + B | Scarica PDF |

## Supporto per assistenti vocali e lenti di ingrandimento dello schermo

Un assistente vocale legge il testo visualizzato sullo schermo del computer. Vengono inoltre lette informazioni non testuali, come etichette di pulsanti o descrizioni di immagini nell&#39;applicazione, fornite nei tag o negli attributi di accessibilità.

## Palette colori e contrasto

[!UICONTROL Analysis Workspace] si impegna per la conformità WCAG 2.1 AA, compresi i requisiti per il contrasto del colore.

Inoltre, gli utenti possono impostare la propria tavolozza di colori preferita per un progetto in **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Progetto (](/help/analysis-workspace/build-workspace-project/color-palettes.md)Progetto).

## Convalida del campo richiesta nei generatore di componenti

Durante la creazione di un componente, i campi obbligatori vengono convalidati al momento del salvataggio. Se un campo obbligatorio non supera la convalida, verrà evidenziato in rosso con un&#39;icona di errore. Viene visualizzata una descrizione scritta del problema da risolvere.

Quando un componente viene convalidato completamente, premendo `Save` il tasto viene chiuso il generatore.

![Convalida errore](assets/error-validation.png)

## Supporto delle funzioni di accessibilità del sistema operativo

 Analysis Workspace supporta funzioni integrate di accessibilità di MS Windows e macOS quali modalità ad alto contrasto, tasti fissi e tasti lenti/tasti filtro. Fornisce inoltre informazioni sull&#39;interfaccia utente del sistema operativo per consentire l&#39;interazione con le tecnologie di assistenza, compresi gli assistenti vocali come VoiceOver per macOS e NVDA su Windows.