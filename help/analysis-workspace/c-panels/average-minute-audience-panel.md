---
title: Pannello Pubblico medio per minuto
description: Come utilizzare e interpretare il pannello Pubblico medio in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: a9ba9def94a2f156f6d2d8e59c0155a492c3978c
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 23%

---


# Pannello Pubblico medio per minuto

I clienti Media Analytics possono utilizzare il pannello del pubblico medio per minuto per comprendere meglio il consumo medio dei loro contenuti. Il pubblico medio per minuto consente di confrontare la programmazione di qualsiasi lunghezza o genere. Inoltre, i clienti possono confrontare o aggiungere questo pubblico medio per minuto digitale alle metriche di minuti medi della TV lineare. Questo pannello offre maggiore flessibilità per misurare il pubblico medio per i periodi di tempo personalizzati, nonché quando la classificazione della durata è stata aggiornata dopo l’evento. La metrica del pubblico medio per minuto corrente funziona solo se la durata è disponibile al momento dell’elaborazione.

In Analysis Workspace, il pubblico medio per minuto corrisponde al tempo impiegato per visualizzare il flusso multimediale diviso per la durata del contenuto oppure per la selezione totale del periodo e della granularità selezionata.

Il pannello Pubblico medio per minuto fornisce analisi medie del pubblico in base al contenuto specifico selezionato se la durata è resa disponibile utilizzando le Classificazioni.
Il pannello Pubblico medio per minuto fornisce anche analisi per un periodo di tempo selezionato che possono essere filtrate in base al contenuto specifico, a prescindere dalla durata disponibile utilizzando le Classificazioni. Per accedere al pannello Pubblico medio per minuto passa a una suite di rapporti i cui sono abilitati i componenti Media Analytics. Fai clic sull’icona del pannello all’estrema sinistra, quindi trascina il pannello nel progetto Analysis Workspace.

<!-- For more information, see the Media Average Minute Audience introduction video:
<< replace with AMA video when available >> -->

<!-- >[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12) -->

## Input del pannello {#Input}

Puoi configurare il pannello Pubblico medio per minuto utilizzando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---------|------------|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi). È possibile modificarlo per visualizzare uno o più mesi alla volta. <br></br> Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Trascina qui un segmento (o altri componenti) | Come altri pannelli, questa impostazione filtra le selezioni in base ai segmenti creati. Questo è un ottimo modo per guardare piattaforme specifiche, flussi live o altri segmenti multimediali comuni. |
| Calcola metrica per | Questa impostazione consente di scegliere se visualizzare il pubblico medio di minuti per un contenuto specifico, selezionando *contenuto specifico* o se desideri visualizzare il pubblico medio dei minuti per un periodo di tempo specifico, selezionando *periodo di tempo personalizzato*. <br></br>Il contenuto specifico funziona solo se la durata è stata aggiornata utilizzando le classificazioni. Se la durata non è disponibile o se desideri visualizzare il pubblico medio dei minuti per una serie temporale con più parti di contenuto o contenuto senza una specifica durata assegnata (come durante un flusso live o un evento), seleziona un periodo di tempo personalizzato. Questa impostazione modifica il flusso di lavoro e l’output del rapporto. |

### Contenuto specifico

| Impostazione | Descrizione |
|---------|------------|
| Dimensioni di reporting | Quando scegli un contenuto specifico, puoi selezionare l’output del rapporto in modo da utilizzare i campi nome video o ID contenuto per mostrare il contenuto e il pubblico medio di minuti associato per il periodo di tempo selezionato. |
| Filtrare il contenuto per (facoltativo) | Puoi filtrare il contenuto specifico in base alla visualizzazione desiderata o alla struttura dei dati. |
| Spettacolo, stagione, episodio | Selezionando &quot;Mostra, stagione, episodio&quot;, le mostre disponibili vengono visualizzate nel menu a discesa, che è possibile filtrare utilizzando una ricerca (oppure trascinando e rilasciando il nome della presentazione dalla colonna di sinistra). È possibile terminare la selezione per visualizzare tutte le stagioni del programma, oppure filtrare per singole stagioni e poi per singoli episodi. Questa impostazione mostra i dati relativi a mostre, stagioni o episodi per il periodo di tempo selezionato. |
| Dimensione personalizzata | Se il nome della visualizzazione si trova sotto una dimensione personalizzata, è possibile trovarlo ricercando nel menu a discesa della dimensione (facoltativo) o utilizzando la ricerca a sinistra della colonna. L’elemento dimensionale si popola automaticamente in base a tale selezione e viene trattato come un episodio. |
| Nessuno | Puoi scegliere *Nessuno* per mostrare tutti i nomi dei video con dati di pubblico di minuti medi per la selezione scelta. |

### Impostazioni avanzate per contenuti specifici

| Impostazione | Descrizione |
|---------|------------|
| Impostazioni tabella | L’impostazione predefinita mostra i valori di calcolo nella tabella, che mostra il numeratore e il denominatore del pubblico medio dei minuti come le colonne precedenti nella tabella. Deselezionando questa opzione, le due colonne vengono rimosse, lasciando solo il pubblico medio al minuto accanto al nome del video o all’ID contenuto. |
| Tempo trascorso della metrica | È possibile scegliere il tempo contenuto predefinito trascorso, che include solo il tempo contenuto, oppure scegliere di utilizzare il tempo trascorso per i contenuti multimediali, che include il contenuto e il tempo pubblicitario insieme come calcolo del numeratore per il pubblico medio di minuti. |

### Periodo di tempo personalizzato

| Impostazione | Descrizione |
|---------|------------|
| Granularity (Granularità) | La granularità predefinita è di 5 minuti, ma è possibile scegliere una qualsiasi delle granularità utilizzate come denominatore per la serie temporale nell’ambito della selezione del periodo temporale complessivo effettuata nella selezione del calendario. Ad esempio, selezionando dalle 12:00 alle 12:30 con una granularità di 5 minuti, il pubblico medio dei minuti verrà restituito nell’intera mezz’ora, così come in sei righe con il pubblico medio dei minuti per ogni periodo di 5 minuti. Queste righe vengono utilizzate come punti dati per il grafico a serie temporali. |
| Filtrare il contenuto per (facoltativo) | Puoi filtrare il contenuto specifico in base alla visualizzazione desiderata o alla struttura dei dati. |
| Spettacolo, stagione, episodio | Selezione *Spettacolo, stagione, episodio* visualizza le presentazioni disponibili nel menu a discesa, che puoi filtrare tramite ricerca (oppure trascinando e rilasciando il nome della visualizzazione dalla colonna a sinistra). È possibile terminare la selezione per visualizzare tutte le stagioni del programma, oppure filtrare per singole stagioni e poi per singoli episodi. Questa impostazione mostra i dati relativi a mostre, stagioni o episodi per il periodo di tempo selezionato. |
| Dimensione personalizzata | Se il nome della visualizzazione si trova sotto una dimensione personalizzata, è possibile trovarlo ricercando nel menu a discesa della dimensione (facoltativo) o utilizzando la ricerca a sinistra della colonna. L’elemento dimensionale si popola automaticamente in base a tale selezione e viene trattato come un episodio. |
| Nessuno | Puoi scegliere *Nessuno* per mostrare tutti i nomi dei video nel periodo di tempo scelto. |

### Impostazioni avanzate del periodo di tempo personalizzato

| Impostazione | Descrizione |
|---------|------------|
| Impostazioni tabella | L’impostazione predefinita visualizza i valori di calcolo nella tabella, che visualizza il numeratore e il denominatore del pubblico medio dei minuti come colonne precedenti nella tabella. Deselezionando questa opzione, le due colonne vengono rimosse lasciando solo il pubblico medio al minuto accanto al periodo di tempo. |


## Output del pannello dei contenuti specifico

Il pannello Pubblico medio in minuti restituisce quanto segue:

* Pubblico medio totale per l’intera selezione
* Filtri e pubblico medio dei minuti per i singoli video visualizzati in una tabella
* Tempo di contenuto trascorso e lunghezza del video (durata) se è stata selezionata tale impostazione avanzata

Per modificare e ricreare il pannello in qualsiasi momento, fai clic sulla matita di modifica in alto a destra.

![Vista predefinita](assets/specific-content-panel-output.png)


### Origine dati contenuto specifica

L’unica metrica che può essere utilizzata in questo pannello è Pubblico medio per minuto.

| Metrica | Descrizione |
|--------|-------------|
| Pubblico medio per minuto | Il tempo impiegato per visualizzare lo streaming multimediale diviso per la lunghezza (durata) del video fornita tramite Classificazioni. |

## Output del pannello del periodo di tempo personalizzato {#custom-time-period-output}

Il pannello Pubblico medio in minuti restituisce il pubblico medio totale per l’intera selezione, il pubblico medio massimo e minimo del minuto e il grafico della serie di linee che mostra il pubblico medio dei minuti per l’intera selezione. La tabella seguente mostra i filtri e il pubblico medio dei minuti per le granularità, nonché il tempo di contenuto trascorso e la granularità per ogni periodo di tempo, se tale impostazione avanzata è stata selezionata.

Per modificare e ricreare il pannello in qualsiasi momento, fai clic sulla matita di modifica in alto a destra.

![output visualizzatori simultanei](assets/custom-time-period-panel-output.png)

### Origine dati del periodo di tempo personalizzato

L’unica metrica che può essere utilizzata in questo pannello è Pubblico medio per minuto:

| Metrica | Descrizione |
|---|---|
| Pubblico medio per minuto | Tempo impiegato per visualizzare il flusso multimediale diviso per la selezione totale o per la granularità selezionata in minuti. |



<!-- For more information about Media Average Minute Audience, visit [MA doc page]( https://url). -->
