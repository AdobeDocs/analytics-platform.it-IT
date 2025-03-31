---
title: Componenti di analisi dei contenuti
description: Dettagli sui componenti specifici di Content Analytics, come dimensioni, metriche (calcolate) e campi derivati
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 0731eadd403ecb428d36492b83351aa0e696b41f
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 6%

---

# Componenti di analisi dei contenuti

{{release-limited-testing}}

Analytics per contenuto aggiunge le seguenti categorie di componenti (dimensioni, metriche (calcolate) e campi derivati) ai componenti già disponibili in Customer Journey Analytics:

* [Metadati dell’esperienza](#experience-metadata)
* [Attributi esperienza](#experience-attributes)
* [Eventi esperienza](#experience-events)
* [Metadati risorsa](#asset-metadata)
* [Attributi risorsa](#asset-attributes)
* [Eventi Assets](#asset-events)
* [Metriche calcolate](#calculated-metrics)

Nelle tabelle seguenti, ![IA generata](/help/assets/icons/AI.svg) indica una coppia attributo/valore generato da IA/ML.

## Metadati dell’esperienza

| Titolo | Descrizione | Tipo |
|---|---|---|
| Canale esperienza | Canale per l’esperienza. | Dimensione |
| ID esperienza | ID univoco dell’esperienza. | Dimensione |
| URL miniatura esperienza | URL per la miniatura dell’esperienza. | Dimensione |
| Profondità percentuale orizzontale esperienza | Valore quantificabile della profondità percentuale orizzontale dell’esperienza. | Campo derivato da Dimension<br/> |
| Profondità percentuale verticale esperienza | Valore quantificabile della profondità percentuale verticale dell’esperienza. | Campo derivato da Dimension<br/> |

{style="table-layout:fixed"}



## Attributi esperienza

| Titolo | Descrizione | Tipo |
|---|---|---|
| Attributi esperienza | ![IA generata](/help/assets/icons/AI.svg) Elenco completo di tutti i nomi e i valori degli attributi esperienza | Campo derivato da Dimension<br> |
| Punteggio di leggibilità dell’esperienza | ![IA generata](/help/assets/icons/AI.svg) Punteggio di leggibilità dell&#39;esperienza | Dimensione |
| Parole chiave dell’esperienza | ![AI ha generato](/help/assets/icons/AI.svg) parole chiave per l&#39;esperienza. | Campo derivato da Dimension<br> |
| Strategie di persuasione dell’esperienza | ![IA ha generato](/help/assets/icons/AI.svg) strategie di persuasione presenti nell&#39;esperienza specificata. I valori possibili sono: Identità sociale, Prova sociale, Autorità, Concretezza, Piede nella porta, Reazione superata, Reciprocità, Ancoraggio e confronto, Impatto sociale, Scarsità e Antropomorfismo. | Campo derivato da Dimension<br/> |
| Narrative dell’esperienza | ![AI ha generato](/help/assets/icons/AI.svg) narrazioni che l&#39;esperienza sta creando in base alla rilevanza dal punto di vista di un addetto marketing. | Campo derivato da Dimension<br/> |
| Toni esperienza | ![IA ha generato](/help/assets/icons/AI.svg) toni che l&#39;esperienza sta creando in base alla rilevanza dal punto di vista di un addetto marketing | Campo derivato da Dimension<br/> |
| Emozioni di Experience Marketing | ![IA generata](/help/assets/icons/AI.svg) L&#39;emozione invocata dal lettore durante la lettura del testo utilizzato come parte dell&#39;esperienza: Urgenza, Esclusività, Incoraggiamento, Sfida, Curiosità, Risultato, Fiducia, Semplicità e Fascinazione. | Campo derivato da Dimension<br/> |
| Conteggio emoticon esperienza | ![IA ha generato](/help/assets/icons/AI.svg) numero di emoticon per l&#39;esperienza. | Metrica |
| Conteggio hashtag esperienza | ![IA ha generato](/help/assets/icons/AI.svg) numero di hashtag per l&#39;esperienza. | Metrica |
| Conteggio frasi esperienza | ![IA ha generato](/help/assets/icons/AI.svg) il numero di frasi per l&#39;esperienza. | Metrica |
| Rapporto parole arresto esperienza | ![IA ha generato](/help/assets/icons/AI.svg) numero di parole non significative per l&#39;esperienza. | Metrica |
| Conteggio delle virgolette di testo esperienza | ![IA generata](/help/assets/icons/AI.svg) Numero di virgolette di testo per l&#39;esperienza. | Metrica |
| Conteggio parole esperienza | ![IA ha generato](/help/assets/icons/AI.svg) Numero di parole per l&#39;esperienza. | Metrica |
| Conteggio parole esperienza per frase | ![IA ha generato](/help/assets/icons/AI.svg) Numero di parole per frase per l&#39;esperienza. | Metrica |

{style="table-layout:fixed"}


## Eventi esperienza

| Titolo | Descrizione | Tipo |
|---|---|---|
| Visualizzazioni esperienza | Misurazione quantificabile del numero di visualizzazioni dell’esperienza. | Metrica |
| Clic sull’esperienza | Misurazione quantificabile del numero di clic dell’esperienza. | Metrica |

{style="table-layout:fixed"}


## Metadati risorsa

| Titolo | Descrizione | Tipo |
|---|---|---|
| ID risorsa | Identificatore univoco della risorsa. Il binario della risorsa determina l’univocità. Se il binario della risorsa cambia, l’ID cambia. L’ID univoco può essere l’URL, ma può anche essere creato un hash. | Dimensione |
| Percorso Asset HTML | Percorso HTML concatenato per la risorsa. | Dimensione |
| URL collegamento risorsa | Ancoraggio pagina più vicino per la risorsa. | Dimensione |
| Larghezza visualizzazione risorsa | Larghezza di visualizzazione delle risorse di contenuto. | Dimensione |
| Altezza di visualizzazione risorsa | Altezza di visualizzazione delle risorse di contenuto. | Dimensione |
| Risorsa Assoluta a sinistra | Risorsa di contenuto a sinistra assoluta. | Dimensione |
| Assoluto risorsa superiore | La risorsa del contenuto è in cima. | Dimensione |

{style="table-layout:fixed"}


## Attributi risorsa

| Titolo | Descrizione | Tipo |
|---|---|---|
| Attributi risorsa | ![IA generata](/help/assets/icons/AI.svg) Elenco completo di tutti i nomi e i valori degli attributi delle risorse | Campo derivato da Dimension<br> |
| Orientamento risorsa | ![IA generata](/help/assets/icons/AI.svg) Orientamento della risorsa. | Campo derivato da Dimension<br/> |
| Tono generale risorsa | ![IA generata](/help/assets/icons/AI.svg) Tono generale della risorsa. | Campo derivato da Dimension<br/> |
| Colori primo piano risorse | ![IA ha generato](/help/assets/icons/AI.svg) colori di primo piano della risorsa. | Campo derivato da Dimension<br/> |
| Colori di sfondo risorsa | ![IA ha generato](/help/assets/icons/AI.svg) colori di sfondo della risorsa. | Campo derivato da Dimension<br/> |
| Tag risorsa | ![IA ha generato](/help/assets/icons/AI.svg) tag per la risorsa. | Campo derivato da Dimension<br/> |
| Scene risorse | ![AI ha generato](/help/assets/icons/AI.svg) scene per la risorsa. | Campo derivato da Dimension<br/> |
| Oggetti risorsa | ![IA ha generato](/help/assets/icons/AI.svg) oggetti della risorsa. | Campo derivato da Dimension<br/> |
| Stili fotografia risorsa | ![IA ha generato](/help/assets/icons/AI.svg) stili di fotografia della risorsa. | Campo derivato da Dimension<br/> |
| Tipo di immagine risorsa | ![IA generato](/help/assets/icons/AI.svg) Tipo di immagine della risorsa. I valori possibili sono: fotografia, schizzo, pittura, digital_cartoon, infografica, graphic_design, collage e software_screenshot. | Campo derivato da Dimension<br/> |
| Posizioni delle videocamere | ![AI generata](/help/assets/icons/AI.svg) posizioni fotocamera della risorsa. | Campo derivato da Dimension<br/> |
| Prossimità fotocamera risorsa | ![AI generata](/help/assets/icons/AI.svg) Prossimità fotocamera della risorsa. | Campo derivato da Dimension<br/> |
| Categorie di persone risorsa | ![IA ha generato](/help/assets/icons/AI.svg) categorie di persone per la risorsa. I valori possibili sono: persona, uomo, donna, gruppo sociale, folla, persone, ragazzo, ragazza e bambino. | Campo derivato da Dimension<br/> |
| Densità contenuto visivo risorsa | ![IA ha generato](/help/assets/icons/AI.svg) la densità del contenuto visivo della risorsa. I valori possibili sono: basso, medio o alto. Una bassa densità di contenuto implica una piccola quantità di informazioni per unità di area dell&#39;immagine. | Dimensione |
| Distribuzione attenzione visiva risorsa | ![IA generata](/help/assets/icons/AI.svg) Distribuzione attenzione visiva della risorsa. I valori possibili sono: basso, medio o alto. L&#39;attenzione diffusa si riferisce al grado in cui l&#39;attenzione di un osservatore è divisa tra le diverse parti di un&#39;immagine. | Campo derivato da Dimension<br/> |
| Condizione di illuminazione risorse | ![IA generata](/help/assets/icons/AI.svg) Condizione di illuminazione della risorsa. I valori possibili sono: ora dorata, ora blu, mezzogiorno, overcast, notte, chiave alta, chiave bassa, illuminazione diurna, incandescente, fluorescente, colorato e studio. | Campo derivato da Dimension<br/> |
| Impostazioni videocamera risorse | ![AI generata](/help/assets/icons/AI.svg) impostazione fotocamera della risorsa. I valori possibili sono: velocità dell&#39;otturatore elevata, esposizione prolungata. sfocatura bokeh, sfocatura movimento, sfocatura tilt-shift, flash, grandangolo, bianco e nero, surreale, doppia esposizione, macro e modalità normale. | Campo derivato da Dimension<br/> |

{style="table-layout:fixed"}


## Eventi risorsa

| Titolo | Descrizione | Tipo |
|---|---|---|
| Visualizzazioni risorse | Misurazione quantificabile del numero di visualizzazioni della risorsa. | Metrica |
| Clic su risorsa | Misurazione quantificabile del numero di clic del cespite. | Metrica |

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
| Percentuale di click-through risorsa | Clic su risorsa/Visualizzazioni risorse | Metrica calcolata |
| Percentuale di click-through esperienza | Clic su esperienza/Visualizzazioni esperienza | Metrica calcolata |

{style="table-layout:fixed"}

