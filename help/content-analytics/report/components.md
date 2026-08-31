---
title: Componenti Content Analytics
description: Scopri i dettagli dei componenti Content Analytics specifici, come dimensioni, metriche (calcolate) e campi derivati
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
TQID: https://experienceleague.adobe.com/grwbNht938ivCsnzlFBzP8Ga8h1udmQLcZngxY6s0-4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 3e9a9042bfe707971c4e37d319a23ab9bdc80075
workflow-type: tm+mt
source-wordcount: 1869
ht-degree: 55%

---


# Componenti di Content Analytics

Content Analytics aggiunge le seguenti categorie di componenti (dimensioni, metriche (calcolate) e campi derivati) ai componenti già disponibili in Customer Journey Analytics:

* [Metadati per esperienze](#experience-metadata)
* [Attributi per esperienze](#experience-attributes)
* [Eventi per esperienze](#experience-events)
* [Metadati per risorse](#asset-metadata)
* [Attributi delle risorse](#asset-attributes)
* [Eventi per risorse](#asset-events)
* [Paid Media](#paid-media)
* [Metriche calcolate](#calculated-metrics)

Nelle tabelle seguenti, ![Generato dall’IA](/help/assets/icons/AI.svg) indica una coppia attributo/valore generata mediante IA/ML.

## Metadati per esperienze

| Titolo | Descrizione | Tipo |
|---|---|---|
| ID SOURCE | Per Content Analytics, il valore è `ContentAnalytics`. | Dimensione |
| Canale | Canale per l’esperienza. Valore `Web`, `Mobile` o `Paid Media`. | Dimensione |
| ID esperienza contenuti | ID univoco per l’esperienza. <br>Per **web**: URL della pagina Web. <br/>Per **web granulare**: hash calcolato sul lato client in base al payload del contenuto (testi, immagini, ctas) con prefisso `web-`. <br/>Per **mobile**: hash calcolato sul lato client in base al payload del contenuto (testi, immagini, ctas) con prefisso `mobile-`. | Dimensione |
| Content Experience Source | Per **web**: l&#39;URL della pagina Web.<br/>Per **mobile**: il nome dello schermo, trasmesso tramite Experience Platform Mobile SDK. | Dimensione |
| Canale esperienza (obsoleto) | Canale per l’esperienza. Valore `Web` o `Mobile`. | Dimensione |
| Funzionalità aggiuntive | Qualsiasi altro dato aggiuntivo di cui desideri tenere traccia. Come ID o posizionamento esterno. | Dimensione |
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
| Origine risorsa | | Dimensione |
| Percorso HTML della risorsa | Percorso HTML concatenato per la risorsa. | Dimensione |
| URL collegamento della risorsa | Ancoraggio pagina più vicino per la risorsa. | Dimensione |
| Larghezza visualizzazione della risorsa | Larghezza di visualizzazione della risorsa di contenuto. | Dimensione |
| Altezza visualizzazione della risorsa | Altezza di visualizzazione della risorsa di contenuto. | Dimensione |
| Posizione assoluta sinistra della risorsa | Posizione assoluta sinistra della risorsa di contenuto. | Dimensione |
| Posizione assoluta in alto della risorsa | Posizione assoluta in alto della risorsa di contenuto. | Dimensione |
| Funzionalità aggiuntive risorse | Qualsiasi altro dato aggiuntivo di cui desideri tenere traccia. Come ID o posizionamento esterno. | Dimensione |

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

## Paid Media

Questi componenti vengono aggiunti a una visualizzazione dati quando il canale **File multimediali a pagamento** è abilitato tramite un [connettore di origine di file multimediali a pagamento di Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/sources/home) (ad esempio, Meta Ads o Google Ads). Ti consentono di creare rapporti sulle entità multimediali a pagamento, sulla creatività e di spendere insieme ai contenuti web e mobili.

Gli **attributi di risorse** e **attributi di esperienza** generati dall&#39;intelligenza artificiale sopra descritti sono disponibili anche per i creativi di contenuti multimediali a pagamento: la stessa funzionalità viene eseguita sui canali Web, Mobile e Paid Media.

### Dimensioni per file multimediali a pagamento

| Titolo | Descrizione | Tipo |
|---|---|---|
| Ad network | La piattaforma pubblicitaria da cui sono stati acquisiti i dati multimediali a pagamento. | Dimensione |
| Nome account | Nome dell’account dell’annuncio. | Dimensione |
| Nome della campagna | Nome della campagna multimediale a pagamento. | Dimensione |
| Nome gruppo di annunci | Nome del gruppo di annunci (set di annunci Meta / gruppo di annunci Google). | Dimensione |
| Nome annuncio | Nome del singolo annuncio. | Dimensione |
| Nome esperienza | Nome dell’esperienza annuncio (composizione creativa). | Dimensione |
| Nome della risorsa | Nome della risorsa creativa. | Dimensione |
| Stato della campagna | Stato della campagna. | Dimensione |
| Stato del gruppo di annunci | Stato del gruppo di annunci. | Dimensione |
| Stato annuncio | Stato dell’annuncio. | Dimensione |
| Stato server | Stato dettagliato del servizio che indica se l’entità sta effettuando la consegna. | Dimensione |
| Valuta conto | Valuta del conto dell’annuncio. | Dimensione |
| Fuso orario dell’account | Fuso orario dell’account dell’annuncio. | Dimensione |
| Tipo di account | Tipo dell’account dell’annuncio. | Dimensione |
| Nome azienda account | Nome aziendale associato all’account dell’annuncio. | Dimensione |
| Tipo di campagna | Tipo di canale principale della campagna. | Dimensione |
| Obiettivo campagna | Obiettivo della campagna. | Dimensione |
| Strategia di offerta della campagna | Strategia di offerta per la campagna. | Dimensione |
| Tipo di budget campagna | Tipo di allocazione di budget per la campagna. | Dimensione |
| Budget giornaliero campagna | Importo budget giornaliero, nella valuta del conto pubblicitario. | Dimensione |
| Budget del ciclo di vita della campagna | Importo budget ciclo di vita, nella valuta del conto pubblicitario. | Dimensione |
| Ora di inizio della campagna | Quando è iniziata la campagna. | Dimensione |
| Ora di fine campagna | Quando la campagna è terminata. | Dimensione |
| Tipo di gruppo di annunci | Tipo del gruppo di annunci. | Dimensione |
| Strategia di offerta del gruppo di annunci | Strategia di offerta per il gruppo di annunci. | Dimensione |
| Obiettivo di ottimizzazione del gruppo di annunci | Obiettivo di ottimizzazione per il gruppo di annunci. | Dimensione |
| Ora di inizio del gruppo di annunci | Quando il gruppo di annunci è iniziato. | Dimensione |
| Ora di fine del gruppo di annunci | Al termine del gruppo di annunci. | Dimensione |
| Tipo di annuncio | Tipo/formato dell’annuncio. | Dimensione |
| Stato revisione annuncio | Stato di revisione/approvazione dell’annuncio. | Dimensione |
| Tipo di annuncio Creative | Tipo di creatività utilizzato dall’annuncio. | Dimensione |
| Titolo annuncio | Titolo della creatività dell’annuncio. | Dimensione |
| Ad Call to action | Call-to-action della creatività dell’annuncio. | Dimensione |
| URL di destinazione dell’annuncio | URL di destinazione dell’annuncio. | Dimensione |
| URL di visualizzazione annuncio | Visualizza l’URL visualizzato nell’annuncio. | Dimensione |
| Tipo di esperienza | Tipo/formato dell’esperienza dell’annuncio. | Dimensione |
| URL della pagina di destinazione dell’esperienza | URL della pagina di destinazione per l’esperienza. | Dimensione |
| Experience Call to action | Call-to-action dell’esperienza. | Dimensione |
| Tipo di risorsa | Tipo di risorsa creativa (ad esempio immagine o video). | Dimensione |
| Larghezza risorsa | Larghezza della risorsa, in pixel. | Dimensione |
| Altezza risorsa | Altezza della risorsa, in pixel. | Dimensione |
| Proporzioni risorse | Proporzioni della risorsa. | Dimensione |
| Orientamento della risorsa | Orientamento della risorsa. | Dimensione |
| Tipo di dispositivo | Suddivisione per tipo di dispositivo per le metriche riportate. | Dimensione |
| Posizionamento | Suddivisione del posizionamento per le metriche riportate. | Dimensione |
| Piattaforma | Suddivisione della piattaforma per le metriche riportate. | Dimensione |
| Paese | Suddivisione per paese delle metriche riportate. | Dimensione |
| Area geografica | Raggruppamento per regione per le metriche riportate. | Dimensione |

{style="table-layout:fixed"}

### Metriche per media a pagamento

| Titolo | Descrizione | Tipo |
|---|---|---|
| Impression | Numero di volte in cui l’annuncio è stato visualizzato. | Metrica |
| Clic | Numero di clic sull’annuncio. | Metrica |
| Spesa | Importo speso, nella valuta del conto dell’annuncio. | Metrica |
| Conversioni | Numero totale di conversioni. | Metrica |
| Valore di conversione | Valore totale delle conversioni. | Metrica |
| Raggiungi | Numero di persone univoche che hanno visto l’annuncio. | Metrica |
| Coinvolgimenti | Numero di impegni con l’annuncio. | Metrica |
| Visualizzazioni video | Numero di visualizzazioni video. | Metrica |
| Completamenti video | Numero di video guardati fino al completamento. | Metrica |
| Riproduzioni video | Numero di riproduzioni video. | Metrica |
| Acquisti | Numero di conversioni di acquisto. | Metrica |
| Aggiungi al carrello | Numero di conversioni da aggiungere al carrello. | Metrica |
| Lead | Numero di conversioni di lead. | Metrica |
| Registrazioni | Numero di conversioni di registrazione. | Metrica |
| Download | Numero di conversioni da scaricare. | Metrica |
| Abbonamenti | Numero di conversioni di abbonamento. | Metrica |
| Visualizzazioni pagina di destinazione | Numero di visualizzazioni della pagina di destinazione. | Metrica |
| Conversioni post-clic | Conversioni attribuite a un clic. | Metrica |
| Conversioni post-visualizzazione | Conversioni attribuite a una visualizzazione. | Metrica |
| Valore ordine totale | Valore totale degli ordini. | Metrica |
| Clic sui collegamenti | Numero di clic sul collegamento. | Metrica |
| Clic in uscita | Numero di clic in uscita. | Metrica |
| Installazioni app | Numero di installazioni dell’app. | Metrica |
| Invii lead | Numero di invii di moduli lead. | Metrica |

{style="table-layout:fixed"}

### Metriche calcolate per elementi multimediali a pagamento

| Titolo | Descrizione | Tipo |
|---|---|---|
| Percentuale di click-through | Clic divisi per impression. | Metrica calcolata |
| Costo per clic | Spesa divisa per clic. | Metrica calcolata |
| Costo per Mille | Costo per mille impression. | Metrica calcolata |
| Costo per conversione | Spesa divisa per le conversioni. | Metrica calcolata |
| Ritorno sulla spesa pubblicitaria | Valore di conversione diviso per la spesa. | Metrica calcolata |
| Frequenza | Impression divise per portata. | Metrica calcolata |
| Tasso di coinvolgimento | Coinvolgimenti divisi per impression. | Metrica calcolata |
| Percentuale di completamento video | Completamenti video divisi per riproduzioni video. | Metrica calcolata |
| Tasso di conversione | Conversioni divise per clic. | Metrica calcolata |
| Valore medio ordine | Il valore totale dell&#39;ordine diviso per gli acquisti. | Metrica calcolata |

{style="table-layout:fixed"}


## Metriche calcolate

| Titolo | Descrizione | Tipo |
|---|---|---|
| Click-through rate della risorsa | Clic su risorsa per Visualizzazioni risorsa | Metrica calcolata |
| Percentuale di click-through esperienza | Clic su esperienza per Visualizzazioni esperienza | Metrica calcolata |

{style="table-layout:fixed"}

