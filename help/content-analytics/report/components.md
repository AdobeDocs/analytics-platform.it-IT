---
title: Componenti di Content Analytics
description: Dettagli sui componenti specifici di Content Analytics, come dimensioni, metriche (calcolate) e campi derivati
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 100%

---

# Componenti di Content Analytics

Content Analytics aggiunge le seguenti categorie di componenti (dimensioni, metriche (calcolate) e campi derivati) ai componenti già disponibili in Customer Journey Analytics:

* [Metadati per esperienze](#experience-metadata)
* [Attributi per esperienze](#experience-attributes)
* [Eventi per esperienze](#experience-events)
* [Metadati per risorse](#asset-metadata)
* [Attributi delle risorse](#asset-attributes)
* [Eventi per risorse](#asset-events)
* [Metriche calcolate](#calculated-metrics)

Nelle tabelle seguenti, ![Generato dall’IA](/help/assets/icons/AI.svg) indica una coppia attributo/valore generata mediante IA/ML.

## Metadati per esperienze

| Titolo | Descrizione | Tipo |
|---|---|---|
| Canale esperienza | Canale per l’esperienza. | Dimensione |
| ID esperienza | ID univoco per l’esperienza. | Dimensione |
| URL miniatura esperienza | URL per la miniatura dell’esperienza. | Dimensione |
| Profondità orizzontale dell’esperienza in percentuale | Valore quantificabile della profondità orizzontale dell’esperienza in percentuale. | Dimensione<br/>Campo derivato |
| Profondità verticale dell’esperienza in percentuale | Valore quantificabile della profondità verticale dell’esperienza in percentuale. | Dimensione<br/>Campo derivato |

{style="table-layout:fixed"}



## Attributi per esperienze

| Titolo | Descrizione | Tipo |
|---|---|---|
| Attributi per esperienze | ![Generato dall’IA](/help/assets/icons/AI.svg) Elenco completo di tutti i nomi e i valori degli attributi dell’esperienza | Dimensione<br>Campo derivato |
| Punteggio di leggibilità dell’esperienza | ![Generato dall’IA](/help/assets/icons/AI.svg) Punteggio di leggibilità per l’esperienza | Dimensione |
| Parole chiave dell’esperienza | ![Generate dall’IA](/help/assets/icons/AI.svg) Parole chiave per l’esperienza. | Dimensione<br>Campo derivato |
| Strategie di persuasione dell’esperienza | ![Generate dall’IA](/help/assets/icons/AI.svg) Strategie di persuasione presenti nell’esperienza specificata. I valori possibili sono: Identità sociale, Prova sociale, Autorevolezza, Concretezza, Fare il primo passo, Superare la reattanza, Reciprocità, Ancoraggio e confronto, Impatto sociale, Scarsità e Antropomorfismo. | Dimensione<br/>Campo derivato |
| Narrazioni dell’esperienza | ![Generate dall’IA](/help/assets/icons/AI.svg) Narrazioni create dall’esperienza in base alla rilevanza dal punto di vista di un marketer. | Dimensione<br/>Campo derivato |
| Toni dell’esperienza | ![Generati dall’IA](/help/assets/icons/AI.svg) Toni creati dall’esperienza in base alla rilevanza dal punto di vista di un marketer | Dimensione<br/>Campo derivato |
| Emozioni marketing dell’esperienzia | ![Generate dall’IA](/help/assets/icons/AI.svg) Le emozioni suscitate nel lettore durante la lettura del testo che fa parte dell’esperienza: Urgenza, Esclusività, Incoraggiamento, Sfida, Curiosità, Risultato, Fiducia, Semplicità e Fascinazione. | Dimensione<br/>Campo derivato |
| Conteggio emoji dell’esperienza | ![Generato dall’IA](/help/assets/icons/AI.svg) Numero di emoji per l’esperienza. | Metrica |
| Conteggio hashtag dell’esperienza | ![Generato dall’IA](/help/assets/icons/AI.svg) Numero di hashtag per l’esperienza. | Metrica |
| Conteggio frasi dell’esperienza | ![Generato dall’IA](/help/assets/icons/AI.svg) Numero di frasi per l’esperienza. | Metrica |
| Proporzione parole vuote dell’esperienza | ![Generato dall’IA](/help/assets/icons/AI.svg) Numero di parole vuote per l’esperienza. | Metrica |
| Conteggio virgolette nel testo dell’esperienza | ![Generato dall’IA](/help/assets/icons/AI.svg) Numero di virgolette nel testo per l’esperienza. | Metrica |
| Conteggio parole dell’esperienza | ![Generato dall’IA](/help/assets/icons/AI.svg) Numero di parole per l’esperienza. | Metrica |
| Conteggio parole per frase dell’esperienza | ![Generato dall’IA](/help/assets/icons/AI.svg) Numero di parole per frase per l’esperienza. | Metrica |

{style="table-layout:fixed"}


## Eventi per esperienze

| Titolo | Descrizione | Tipo |
|---|---|---|
| Visualizzazioni dell’esperienza | Misurazione quantificabile del numero di visualizzazioni dell’esperienza. | Metrica |
| Clic dell’esperienza | Misurazione quantificabile del numero di clic dell’esperienza. | Metrica |

{style="table-layout:fixed"}


## Metadati per risorse

| Titolo | Descrizione | Tipo |
|---|---|---|
| ID risorsa | Identificatore univoco della risorsa. I dati binari della risorsa ne determinano l’univocità. Se i dati binari della risorsa cambiano, cambia anche il suo ID. L’ID univoco può essere l’URL, ma può anche essere un valore hash creato. | Dimensione |
| Percorso HTML della risorsa | Percorso HTML concatenato per la risorsa. | Dimensione |
| URL collegamento della risorsa | Ancoraggio pagina più vicino per la risorsa. | Dimensione |
| Larghezza visualizzazione della risorsa | Larghezza di visualizzazione della risorsa di contenuto. | Dimensione |
| Altezza visualizzazione della risorsa | Altezza di visualizzazione della risorsa di contenuto. | Dimensione |
| Posizione assoluta sinistra della risorsa | Posizione assoluta sinistra della risorsa di contenuto. | Dimensione |
| Posizione assoluta in alto della risorsa | Posizione assoluta in alto della risorsa di contenuto. | Dimensione |

{style="table-layout:fixed"}


## Attributi delle risorse

| Titolo | Descrizione | Tipo |
|---|---|---|
| Attributi delle risorse | ![Generato dall’IA](/help/assets/icons/AI.svg) Elenco completo di tutti i nomi e i valori degli attributi della risorsa. | Dimensione<br>Campo derivato |
| Orientamento della risorsa | ![Generato dall’IA](/help/assets/icons/AI.svg) Orientamento della risorsa. | Dimensione<br/>Campo derivato |
| Tono complessivo della risorsa | ![Generato dall’IA](/help/assets/icons/AI.svg) Tono complessivo della risorsa. | Dimensione<br/>Campo derivato |
| Colori di primo piano della risorsa | ![Generati dall’IA](/help/assets/icons/AI.svg) Colori di primo piano della risorsa. | Dimensione<br/>Campo derivato |
| Colori di sfondo della risorsa | ![Generati dall’IA](/help/assets/icons/AI.svg) Colori di sfondo della risorsa. | Dimensione<br/>Campo derivato |
| Tag della risorsa | ![Generati dall’IA](/help/assets/icons/AI.svg) Tag per la risorsa. | Dimensione<br/>Campo derivato |
| Scene della risorsa | ![Generate dall’IA](/help/assets/icons/AI.svg) Scene per la risorsa. | Dimensione<br/>Campo derivato |
| Oggetti della risorsa | ![Generati dall’IA](/help/assets/icons/AI.svg) Oggetti della risorsa. | Dimensione<br/>Campo derivato |
| Stili fotografici della risorsa | ![Generati dall’IA](/help/assets/icons/AI.svg) Stili fotografici della risorsa. | Dimensione<br/>Campo derivato |
| Tipo di immagine della risorsa | ![Generato dall’IA](/help/assets/icons/AI.svg) Tipo di immagine della risorsa. I valori possibili sono: photograph, sketch, painting, digital_cartoon, infographics, graphic_design, collage e software_screenshot. | Dimensione<br/>Campo derivato |
| Posizioni fotocamera della risorsa | ![Generate dall’IA](/help/assets/icons/AI.svg) Posizioni fotocamera della risorsa. | Dimensione<br/>Campo derivato |
| Prossimità fotocamera della risorsa | ![Generate dall’IA](/help/assets/icons/AI.svg) Prossimità fotocamera della risorsa. | Dimensione<br/>Campo derivato |
| Categorie di persone della risorsa | ![Generate dall’IA](/help/assets/icons/AI.svg) Categorie di persone per la risorsa. I valori possibili sono: persona, uomo, donna, gruppo sociale, folla, persone, ragazzo, ragazza e bambino. | Dimensione<br/>Campo derivato |
| Densità contenuto visivo della risorsa | ![Generata dall’IA](/help/assets/icons/AI.svg) Densità del contenuto visivo della risorsa. I valori possibili sono: bassa, media o alta. Una bassa densità di contenuto implica la presenza di una piccola quantità di informazioni per unità di area dell’immagine. | Dimensione |
| Distribuzione attenzione visiva della risorsa | ![Generata dall’IA](/help/assets/icons/AI.svg) Distribuzione dell’attenzione visiva della risorsa. I valori possibili sono: bassa, media o alta. Per “attenzione distribuita” si intende quanto l’attenzione di chi visualizza i contenuti sia divisa tra le diverse parti di un’immagine. | Dimensione<br/>Campo derivato |
| Condizione di illuminazione della risorsa | ![Generata dall’IA](/help/assets/icons/AI.svg) Condizione di illuminazione della risorsa. I valori possibili sono: ora d’oro, ora blu, mezzogiorno, cielo coperto, notte, high key, low key, luce diurna, incandescente, fluorescente, colorata e da studio. | Dimensione<br/>Campo derivato |
| Impostazioni fotocamera della risorsa | ![Generate dall’IA](/help/assets/icons/AI.svg) Impostazioni della fotocamera per la risorsa. I valori possibili sono: tempo di scatto rapido, esposizione prolungata. sfocatura bokeh, effetto movimento, effetto scostamento inclinazione, flash, grandangolo, bianco e nero, surreale, doppia esposizione, macro e modalità normale. | Dimensione<br/>Campo derivato |

{style="table-layout:fixed"}


## Eventi per risorse

| Titolo | Descrizione | Tipo |
|---|---|---|
| Visualizzazioni risorsa | Misurazione quantificabile del numero di visualizzazioni della risorsa. | Metrica |
| Clic su risorsa | Misurazione quantificabile del numero di clic sulla risorsa. | Metrica |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## Metriche calcolate

| Titolo | Descrizione | Tipo |
|---|---|---|
| Click-through rate della risorsa | Clic su risorsa per Visualizzazioni risorsa | Metrica calcolata |
| Click-through rate dell’esperienza | Clic su esperienza per Visualizzazioni esperienza | Metrica calcolata |

{style="table-layout:fixed"}

