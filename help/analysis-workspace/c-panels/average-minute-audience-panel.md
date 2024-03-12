---
title: Pannello Pubblico medio per minuto
description: Come utilizzare e interpretare il pannello Pubblico medio per minuto in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: a6dd3495b51edcb823431ccb87b283665ccd765d
workflow-type: tm+mt
source-wordcount: '1656'
ht-degree: 31%

---


# Pannello del pubblico medio per minuto del file multimediale

>[!NOTE]
>
>Il pannello Pubblico medio per minuto di Media è disponibile solo per i clienti che hanno acquistato il componente aggiuntivo Media Analytics per il Customer Journey Analytics.
>
>Per acquistare Media Analytics, contatta il tuo rappresentante commerciale Adobe o il team dell’account Adobe.

In Analysis Workspace, il pubblico medio per minuto corrisponde al tempo impiegato per visualizzare il flusso multimediale diviso per la durata del contenuto oppure per la selezione totale del periodo e della granularità selezionata.

Il pannello Pubblico medio per minuto consente di comprendere meglio il consumo medio dei contenuti confrontando programmi di qualsiasi durata o genere. Ad esempio, puoi comprendere il consumo medio quando confronti una sitcom di 30 minuti con un evento sportivo di 3 ore.

Inoltre, puoi utilizzare il pannello Pubblico medio per minuto del file multimediale per confrontare o aggiungere questo pubblico medio per minuto digitale alle metriche medie per minuto della TV lineare.

Il pannello Pubblico medio per minuto fornisce i seguenti vantaggi rispetto alla metrica Pubblico medio per minuto:

* Supporta periodi di tempo personalizzati

* Consente di aggiornare la classificazione della durata dopo l’elaborazione delle viste (se non era presente o se deve essere corretta)

  Se lo hai fatto quando utilizzi la metrica, questa non esisterà (se la classificazione non era presente) o non sarà aggiornata (se la classificazione era presente ma non corretta).

## Accedere al pannello Pubblico medio per minuto del file multimediale

1. In Analysis Workspace, vai a una suite di rapporti i cui componenti Media Analytics sono abilitati.

1. Nella barra di navigazione a sinistra, seleziona la **Pannelli** icona.

   ![Icona Pannelli nella navigazione a sinistra](assets/panels-icon.png)

1. Trascina [!UICONTROL **Pubblico medio per minuto del file multimediale**] nell’area di lavoro in Analysis Workspace.

1. Per configurare il pannello, continua con [Input del pannello](#panel-inputs).

## Input del pannello {#Input}

Utilizza le impostazioni di input descritte in questa sezione per configurare il pannello Pubblico medio per minuto del file multimediale.

1. Inizia a creare un pannello del pubblico medio per minuto, come descritto in [Accedere al pannello Pubblico medio per minuto del file multimediale](#access-the-media-average-minute-audience-panel).

1. Configura le seguenti impostazioni di input:

   | Impostazione | Descrizione |
   |---------|------------|
   | **Intervallo date pannello** | L’intervallo di date predefinito del pannello è [!UICONTROL **Questo mese**]. È possibile modificarlo per visualizzare uno o più mesi alla volta. <br></br> Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
   | [!UICONTROL **Rilascia qui un segmento (o qualsiasi altro componente)**] | Come altri pannelli, questa impostazione filtra le selezioni in base ai segmenti creati. È un ottimo modo per esaminare piattaforme specifiche, live stream o altri segmenti multimediali comuni. |
   | [!UICONTROL **Calcola metrica per**] | Scegli se visualizzare il pubblico medio per minuto di un contenuto specifico o se visualizzare il pubblico medio per minuto di un periodo di tempo personalizzato:<ul><li>**Contenuto specifico:** Questa opzione è disponibile solo se la durata è stata aggiornata utilizzando le classificazioni. Se la durata non è disponibile o se desideri visualizzare il pubblico medio per minuto di una serie temporale con più parti di contenuto o contenuto senza una specifica durata assegnata (come durante un live stream o un evento), seleziona [!UICONTROL **Periodo di tempo personalizzato**]. Le durate possono essere impostate utilizzando le classificazioni prima o dopo il tempo di elaborazione.</li><li>**Periodo personalizzato:** Questo è disponibile indipendentemente dal fatto che le durate siano rese disponibili utilizzando le Classificazioni.</li></ul> <p>Questa impostazione modifica il flusso di lavoro e l’output del rapporto.</p> |

1. Continua con [Contenuto specifico](#specific-content) o [Periodo di tempo personalizzato](#custom-time-period), a seconda dell’opzione scelta in [!UICONTROL **Calcola metrica per**] menu a discesa.

### Contenuto specifico

1. Se hai selezionato [!UICONTROL **Contenuto specifico**] nel [!UICONTROL **Calcola metrica per**] menu a discesa quando [configurazione degli input del pannello](#panel-inputs), specifica le seguenti opzioni di configurazione:

   | Impostazione | Descrizione |
   |---------|------------|
   | [!UICONTROL **Dimensione di reporting**] | Quando scegli un contenuto specifico, puoi selezionare l’output del rapporto in modo da utilizzare i campi ID contenuto o nome video per mostrare il contenuto e il pubblico medio per minuto associato per il periodo di tempo selezionato. |
   | [!UICONTROL **Filtra contenuto per (facoltativo)**] | Scegli come filtrare il contenuto specifico, a seconda della visualizzazione desiderata o della struttura dei dati. <ul>[!UICONTROL **Spettacolo, stagione, episodio**]: mostra gli spettacoli disponibili nel menu a discesa, che puoi filtrare utilizzando una ricerca (oppure trascinando e rilasciando il nome dello spettacolo dalla colonna sinistra). Puoi terminare la selezione per visualizzare tutte le stagioni dello spettacolo oppure filtrare per singole stagioni e poi per singoli episodi. Questa impostazione mostra i dati relativi a spettacoli, stagioni o episodi per il periodo di tempo selezionato.</li><li>[!UICONTROL **Dimensione personalizzata**]: se il nome dello spettacolo si trova in una dimensione personalizzata, puoi trovarlo eseguendo una ricerca nel menu a discesa della dimensione (facoltativo) o utilizzando la ricerca nella colonna sinistra. L’elemento dimensionale si popola automaticamente in base a tale selezione e viene trattato come un episodio.</li><li>[!UICONTROL **Nessuno**]: mostra tutti i nomi dei video con dati del pubblico medio per minuto per la selezione scelta. Questa opzione è selezionata per impostazione predefinita.</li></ul> |

1. Continua con [Impostazioni avanzate del contenuto specifico](#specific-content-advanced-settings) per configurare le impostazioni avanzate.

### Impostazioni avanzate del contenuto specifico

1. Con [!UICONTROL **Contenuto specifico**] selezionato in [!UICONTROL **Calcola metrica per**] menu a discesa, seleziona [!UICONTROL **Mostra impostazioni avanzate**], quindi specifica le seguenti opzioni di configurazione:

   | Impostazione | Descrizione |
   |---------|------------|
   | Table settings (Impostazioni di tabella) | L’impostazione predefinita mostra i valori di calcolo nella tabella, la quale mostra il numeratore e il denominatore del pubblico medio per minuto come colonne precedenti nella tabella. Deselezionando questa opzione le due colonne vengono rimosse, lasciando solo il pubblico medio per minuto accanto all’ID contenuto o nome video. |
   | Time spent metric (Metrica della durata) | È possibile scegliere la durata predefinita del contenuto, che include solo la durata del contenuto, oppure scegliere di utilizzare la durata dei contenuti multimediali, che include la durata del contenuto e degli annunci insieme come calcolo del numeratore del pubblico medio per minuto. |

1. Seleziona [!UICONTROL **Genera**] per terminare la creazione del pannello Pubblico medio per minuto.

1. Continua con [Output del pannello](#panel-output) per informazioni su come utilizzare il pannello Pubblico medio per minuto del file multimediale.

### Periodo di tempo personalizzato

1. Se hai selezionato [!UICONTROL **Periodo di tempo personalizzato**] nel [!UICONTROL **Calcola metrica per**] menu a discesa quando [configurazione degli input del pannello](#panel-inputs), specifica le seguenti opzioni di configurazione:

   | Impostazione | Descrizione |
   |---------|------------|
   | Granularity (Granularità) | La granularità predefinita è [!UICONTROL **5 minuti**], ma puoi scegliere una qualsiasi delle granularità utilizzate come denominatore per le serie temporali all’interno della selezione complessiva del periodo temporale effettuata nella selezione del calendario. Ad esempio, selezionando dalle 12:00 alle 12:30 con una granularità di 5 minuti, viene restituito il pubblico medio per minuto nell’intera mezz’ora, nonché sei righe contenenti il pubblico medio per minuto per ogni periodo di 5 minuti. Queste righe vengono utilizzate come punti dati per il grafico delle serie temporali. |
   | [!UICONTROL **Filtra contenuto per (facoltativo)**] | Scegli come filtrare il contenuto specifico, a seconda della visualizzazione desiderata o della struttura dei dati. <ul>[!UICONTROL **Spettacolo, stagione, episodio**]: mostra gli spettacoli disponibili nel menu a discesa, che puoi filtrare utilizzando una ricerca (oppure trascinando e rilasciando il nome dello spettacolo dalla colonna sinistra). Puoi terminare la selezione per visualizzare tutte le stagioni dello spettacolo oppure filtrare per singole stagioni e poi per singoli episodi. Questa impostazione mostra i dati relativi a spettacoli, stagioni o episodi per il periodo di tempo selezionato.</li><li>[!UICONTROL **Dimensione personalizzata**]: se il nome dello spettacolo si trova in una dimensione personalizzata, puoi trovarlo eseguendo una ricerca nel menu a discesa della dimensione (facoltativo) o utilizzando la ricerca nella colonna sinistra. L’elemento dimensionale si popola automaticamente in base a tale selezione e viene trattato come un episodio.</li><li>[!UICONTROL **Nessuno**]: mostra tutti i nomi dei video con dati del pubblico medio per minuto per la selezione scelta. Questa opzione è selezionata per impostazione predefinita.</li></ul> |

1. Continua con [Impostazioni avanzate del periodo di tempo personalizzato](#custom-time-period-advanced-settings) per configurare le impostazioni avanzate.

### Impostazioni avanzate del periodo di tempo personalizzato

1. Con [!UICONTROL **Periodo di tempo personalizzato**] selezionato in [!UICONTROL **Calcola metrica per**] menu a discesa, seleziona [!UICONTROL **Mostra impostazioni avanzate**], quindi specifica la seguente opzione di configurazione:

   | Impostazione | Descrizione |
   |---------|------------|
   | Table settings (Impostazioni di tabella) | L’impostazione predefinita visualizza i valori di calcolo nella tabella, la quale visualizza il numeratore e il denominatore del pubblico medio per minuto come colonne precedenti nella tabella. Deselezionando questa opzione le due colonne vengono rimosse, lasciando solo il pubblico medio per minuto accanto al periodo di tempo. |

1. Seleziona [!UICONTROL **Genera**] per terminare la creazione del pannello Pubblico medio per minuto.

1. Continua con [Output del pannello](#panel-output) per informazioni su come utilizzare il pannello Pubblico medio per minuto del file multimediale.

## Output del pannello

L’output del pannello varia a seconda che sia stato scelto o meno [!UICONTROL **Contenuto specifico**] o [!UICONTROL **Periodo di tempo personalizzato**] nel [!UICONTROL **Calcola metrica per**] menu a discesa quando [configurazione degli input del pannello](#panel-inputs).

### Contenuto specifico

Il pannello Pubblico medio per minuto restituisce quanto segue:

* Pubblico medio per minuto totale dell’intera selezione
* Filtri e pubblico medio per minuto dei singoli video visualizzati in una tabella
* Durata del contenuto e lunghezza del video (durata), se è stata selezionata tale impostazione avanzata

Per modificare e ricreare il pannello in qualsiasi momento, seleziona l’icona Modifica (matita) in alto a destra.

![Vista predefinita](assets/specific-content-panel-output.png)

### Origine dati del contenuto specifico

Il pannello Pubblico medio per minuto utilizza solo la metrica Pubblico medio per minuto per raccogliere i dati. Raggruppamenti o altre metriche non possono essere utilizzati nel pannello.

| Metrica | Descrizione |
|--------|-------------|
| Pubblico medio per minuto | Il tempo impiegato per visualizzare il flusso multimediale diviso per la lunghezza del video (durata) fornita tramite Classificazioni. |

### Periodo di tempo personalizzato {#custom-time-period-output}

Il pannello Pubblico medio per minuto restituisce quanto segue:

* Il pubblico medio per minuto totale dell’intera selezione

* Pubblico medio per minuto massimo e minimo

* Grafico a linee che mostra il pubblico medio per minuto dell’intera selezione.

* Una tabella che mostra i filtri e il pubblico medio per minuto delle granularità, nonché la durata del contenuto e la granularità di ogni periodo di tempo

  Questa tabella viene visualizzata solo se l’opzione in Impostazioni avanzate è denominata [!UICONTROL **Mostra valori di calcolo nella tabella**] è selezionato.

Per modificare e ricreare il pannello in qualsiasi momento, seleziona l’icona Modifica (matita) in alto a destra.

![output visualizzatori simultanei](assets/custom-time-period-panel-output.png)

### Origine dati del periodo di tempo personalizzato

Il pannello Pubblico medio per minuto utilizza solo la metrica Pubblico medio per minuto per raccogliere i dati. Raggruppamenti o altre metriche non possono essere utilizzati nel pannello.

| Metrica | Descrizione |
|---|---|
| Pubblico medio per minuto | Il tempo impiegato per visualizzare il flusso multimediale diviso per la selezione totale o per la granularità selezionata in minuti. |
