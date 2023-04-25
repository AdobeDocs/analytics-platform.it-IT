---
title: Pannello Pubblico medio per minuto
description: Come utilizzare e interpretare il pannello Pubblico medio per minuto in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: 32c507cb9de4fcd146de0e9c828c54c5f4f1a062
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 91%

---


# Pannello Pubblico medio per minuto

<!-- THIS FEATURE IS SCHEDULED FOR 2023 -->

I clienti Media Analytics possono utilizzare il pannello del pubblico medio per minuto per comprendere meglio il consumo medio dei loro contenuti. Il pubblico medio per minuto consente di confrontare la programmazione di qualsiasi lunghezza o genere. Inoltre, i clienti possono confrontare o aggiungere questo pubblico medio per minuto digitale alle metriche di minuti medi della TV lineare. Questo pannello offre maggiore flessibilità per misurare il pubblico medio per i periodi di tempo personalizzati, nonché quando la classificazione della durata è stata aggiornata dopo l’evento. La metrica del pubblico medio per minuto corrente funziona solo se la durata è disponibile al momento dell’elaborazione.

In Analysis Workspace, il pubblico medio per minuto corrisponde al tempo impiegato per visualizzare il flusso multimediale diviso per la durata del contenuto oppure per la selezione totale del periodo e della granularità selezionata.

Il pannello Pubblico medio per minuto fornisce analisi medie del pubblico in base al contenuto specifico selezionato se la durata è resa disponibile utilizzando le Classificazioni.
Il pannello Pubblico medio per minuto fornisce anche analisi per un periodo di tempo selezionato che possono essere filtrate in base al contenuto specifico, a prescindere dalla durata disponibile utilizzando le Classificazioni. Per accedere al pannello Pubblico medio per minuto passa a una suite di rapporti i cui sono abilitati i componenti Media Analytics. Fai clic sull’icona del pannello all’estrema sinistra, quindi trascina il pannello nel progetto Analysis Workspace.

<!-- For more information, see the Media Average Minute Audience introduction video:
<< replace with AMA video when available >> -->

<!-- >[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12) -->

## Input del pannello {#Input}

Puoi configurare il pannello Pubblico medio per minuto usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---------|------------|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi). È possibile modificarlo per visualizzare uno o più mesi alla volta. <br></br> Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Drag a segment here (or any other component) (Trascina qui un segmento (o qualsiasi altro componente)) | Come altri pannelli, questa impostazione filtra le selezioni in base ai segmenti creati. È un ottimo modo per esaminare piattaforme specifiche, live stream o altri segmenti multimediali comuni. |
| Calculate metric for (Calcola metrica per) | Questa impostazione consente di scegliere se visualizzare il pubblico medio per minuto di un contenuto specifico, selezionando *specific content* (contenuto specifico), o se visualizzare il pubblico medio per minuto di un periodo di tempo specifico, selezionando *custom time period* (periodo di tempo personalizzato). <br></br>Il contenuto specifico funziona solo se la durata è stata aggiornata utilizzando le classificazioni. Se la durata non è disponibile o se desideri visualizzare il pubblico medio per minuto di una serie temporale con più parti di contenuto o contenuto senza una specifica durata assegnata (come durante un live stream o un evento), seleziona un periodo di tempo personalizzato. Questa impostazione modifica il flusso di lavoro e l’output del rapporto. |

### Contenuto specifico

| Impostazione | Descrizione |
|---------|------------|
| Reporting dimensions (Dimensioni di reporting) | Quando scegli un contenuto specifico, puoi selezionare l’output del rapporto in modo da utilizzare i campi ID contenuto o nome video per mostrare il contenuto e il pubblico medio per minuto associato per il periodo di tempo selezionato. |
| Filter content by (optional) (Filtra il contenuto per (facoltativo)) | Puoi filtrare il contenuto specifico in base alla visualizzazione desiderata o alla struttura dei dati. |
| Show, season, episode (Spettacolo, stagione, episodio) | Selezionando &quot;Mostra, stagione, episodio&quot; le mostre disponibili vengono visualizzate nell&#39;elenco a discesa, che è possibile filtrare utilizzando una ricerca (o trascinando e rilasciando il nome della presentazione dalla colonna di sinistra). Puoi terminare la selezione per visualizzare tutte le stagioni dello spettacolo oppure filtrare per singole stagioni e poi per singoli episodi. Questa impostazione mostra i dati relativi a spettacoli, stagioni o episodi per il periodo di tempo selezionato. |
| Custom dimension (Dimensione personalizzata) | Se il nome dello spettacolo si trova in una dimensione personalizzata, è possibile trovarlo effettuando una ricerca nel menu a discesa della dimensione (facoltativo) o utilizzando la ricerca della colonna sinistra. L’elemento dimensionale si popola automaticamente in base a tale selezione e viene trattato come un episodio. |
| Nessuno | Puoi scegliere *Nessuno* per mostrare tutti i nomi dei video con dati di pubblico di minuti medi per la selezione scelta. |

### Impostazioni avanzate del contenuto specifico

| Impostazione | Descrizione |
|---------|------------|
| Table settings (Impostazioni di tabella) | L’impostazione predefinita mostra i valori di calcolo nella tabella, la quale mostra il numeratore e il denominatore del pubblico medio per minuto come colonne precedenti nella tabella. Deselezionando questa opzione le due colonne vengono rimosse, lasciando solo il pubblico medio per minuto accanto all’ID contenuto o nome video. |
| Time spent metric (Metrica della durata) | È possibile scegliere la durata predefinita del contenuto, che include solo la durata del contenuto, oppure scegliere di utilizzare la durata dei contenuti multimediali, che include la durata del contenuto e degli annunci insieme come calcolo del numeratore del pubblico medio per minuto. |

### Periodo di tempo personalizzato

| Impostazione | Descrizione |
|---------|------------|
| Granularity (Granularità) | La granularità predefinita è di cinque minuti, ma è possibile scegliere una qualsiasi delle granularità utilizzate come denominatore per la serie temporale all’interno della selezione complessiva del periodo temporale effettuata nella selezione del calendario. Ad esempio, selezionando dalle 12:00 alle 12:30 con una granularità di cinque minuti, verrà restituito il pubblico medio per minuto nell’intera mezz’ora, così come sei righe contenenti il pubblico medio per minuto per ogni periodo di cinque minuti. Queste righe vengono utilizzate come punti dati per il grafico delle serie temporali. |
| Filter content by (optional) (Filtra il contenuto per (facoltativo)) | Puoi filtrare il contenuto specifico in base alla visualizzazione desiderata o alla struttura dei dati. |
| Show, season, episode (Spettacolo, stagione, episodio) | Selezione *Spettacolo, stagione, episodio* visualizza le presentazioni disponibili nell’elenco a discesa, che è possibile filtrare tramite ricerca (o trascinando e rilasciando il nome della presentazione dalla colonna di sinistra). Puoi terminare la selezione per visualizzare tutte le stagioni dello spettacolo oppure filtrare per singole stagioni e poi per singoli episodi. Questa impostazione mostra i dati relativi a spettacoli, stagioni o episodi per il periodo di tempo selezionato. |
| Custom dimension (Dimensione personalizzata) | Se il nome dello spettacolo si trova in una dimensione personalizzata, è possibile trovarlo effettuando una ricerca nel menu a discesa della dimensione (facoltativo) o utilizzando la ricerca della colonna sinistra. L’elemento dimensionale si popola automaticamente in base a tale selezione e viene trattato come un episodio. |
| Nessuno | Puoi scegliere *Nessuno* per mostrare tutti i nomi dei video nel periodo di tempo scelto. |

### Impostazioni avanzate del periodo di tempo personalizzato

| Impostazione | Descrizione |
|---------|------------|
| Table settings (Impostazioni di tabella) | L’impostazione predefinita visualizza i valori di calcolo nella tabella, la quale visualizza il numeratore e il denominatore del pubblico medio per minuto come colonne precedenti nella tabella. Deselezionando questa opzione le due colonne vengono rimosse, lasciando solo il pubblico medio per minuto accanto al periodo di tempo. |


## Output del pannello del contenuto specifico

Il pannello Pubblico medio per minuto restituisce quanto segue:

* Pubblico medio per minuto totale dell’intera selezione
* Filtri e pubblico medio per minuto dei singoli video visualizzati in una tabella
* Durata del contenuto e lunghezza del video (durata), se è stata selezionata tale impostazione avanzata

Per modificare e ricreare il pannello in qualsiasi momento, fai clic sull’icona della matita (Modifica) in alto a destra.

![Vista predefinita](assets/specific-content-panel-output.png)


### Origine dati del contenuto specifico

L’unica metrica che può essere utilizzata in questo pannello è Pubblico medio per minuto.

| Metrica | Descrizione |
|--------|-------------|
| Pubblico medio per minuto | Il tempo impiegato per visualizzare il flusso multimediale diviso per la lunghezza del video (durata) fornita tramite Classificazioni. |

## Output del pannello del periodo di tempo personalizzato {#custom-time-period-output}

Il pannello Pubblico medio per minuto restituisce il pubblico medio per minuto totale dell’intera selezione, quello massimo e minimo e il grafico a linee che mostra il pubblico medio per minuto dell’intera selezione. La tabella seguente mostra i filtri e il pubblico medio per minuto delle granularità, nonché la durata del contenuto e la granularità di ogni periodo di tempo, se tale impostazione avanzata è stata selezionata.

Per modificare e ricreare il pannello in qualsiasi momento, fai clic sull’icona della matita (Modifica) in alto a destra.

![output visualizzatori simultanei](assets/custom-time-period-panel-output.png)

### Origine dati del periodo di tempo personalizzato

L’unica metrica che può essere utilizzata in questo pannello è Pubblico medio per minuto:

| Metrica | Descrizione |
|---|---|
| Pubblico medio per minuto | Il tempo impiegato per visualizzare il flusso multimediale diviso per la selezione totale o per la granularità selezionata in minuti. |



<!-- For more information about Media Average Minute Audience, visit [MA doc page]( https://url). -->
