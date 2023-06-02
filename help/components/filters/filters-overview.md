---
title: Panoramica sui filtri
description: Scopri i filtri utilizzati e come creare un filtro semplice.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: 4e2d4d8c4f8145ae691114d57d663af96240b5f5
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 34%

---


# Panoramica sui filtri {#overview}

Customer Journey Analytics ti consente di generare, gestire e condividere filtri potenti e precisi del pubblico e di applicarli ai rapporti. I filtri ti consentono di identificare sottoinsiemi di persone in base a caratteristiche o interazioni con siti web. I filtri sono progettati come approfondimenti codificati del pubblico che puoi generare in base alle tue esigenze specifiche e quindi verificare, modificare e condividere con altri membri del gruppo.

I filtri possono essere basati su

- attributi (tipo di browser, dispositivo, numero di visite, paese, genere),
- interazioni (campagne, ricerca di parole chiave, motore di ricerca),
- uscite ed entrate (persone provenienti da Facebook,
- una pagina di destinazione definita, dominio di riferimento),
- variabili personalizzate (campo modulo, categorie definite, ID cliente),
- e altri criteri.

Puoi generare e salvare filtri nel Generatore di filtri o generarli da una visualizzazione Fallout (in Workspace). Inoltre, i filtri possono essere utilizzati insieme come filtri sovrapposti.

Gli strumenti per filtri includono il [Generatore di filtri](/help/components/filters/filter-builder.md), per creare filtri ed eseguire un test preliminare, e il [Gestore filtri](/help/components/filters/manage-filters.md) per raccogliere i filtri, assegnare loro tag, approvarli, impostarne la protezione e condividerli all’interno dell’organizzazione.

Il numero massimo di filtri che è possibile creare per l’organizzazione IMS è 50.000.

## Tipi di filtro {#types}

Per informazioni sui tipi di filtri disponibili e su come crearli, consulta [Creare filtri](/help/components/filters/create-filters.md).

## Filtri sequenziali {#sequential}

I filtri sequenziali ti consentono di identificare le persone in base alla navigazione e alla visualizzazione di pagine nel sito, fornendo un filtro di azioni e interazioni definite. I filtri sequenziali consentono di identificare cosa piace a una persona e cosa evita. Quando si creano filtri sequenziali, l’operatore THEN viene utilizzato per definire e ordinare la navigazione delle persone.

Ecco un esempio:

<!--![](assets/sequential_fil.png)-->

| Sessione uno | Sessione due | Sessione tre |
| --- | --- | --- |
| La persona è andata alla pagina di destinazione principale A, ha escluso la pagina della campagna B e ha quindi visualizzato la pagina di prodotto C. | La persona è andata nuovamente alla pagina di destinazione principale A, ha escluso la pagina della campagna B, ha visitato nuovamente la pagina di prodotto C e quindi una nuova pagina D. | La persona è entrata e ha seguito lo stesso percorso della prima e seconda visita, quindi ha escluso la pagina F per passare direttamente a una pagina di prodotto mirata G. |

## Contenitori di filtri {#containers}

I filtri si basano su una gerarchia a livello di persona, sessione ed evento che utilizza un modello di contenitore nidificato. I contenitori nidificati ti consentono di definire gli attributi e le azioni delle persone in base alle regole tra e all’interno dei contenitori.


<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Persona</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Sessione</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Evento</td>
</tr>
</table>

>[!NOTE]
>Il contenitore Persona era precedentemente noto come contenitore Visitatore. Il contenitore Sessione era denominato contenitore Visita e il contenitore Evento era il contenitore Hit.

Un filtro imposta le condizioni per filtrare una persona in base agli attributi o alle interazioni della persona con il sito. Per impostare le condizioni in un filtro, imposta le regole per filtrare le persone in base alle caratteristiche della persona e/o alle caratteristiche di navigazione. Per suddividere ulteriormente i dati di una persona, puoi filtrare in base a visite e/o hit di visualizzazione pagina specifici per ogni persona. Il Generatore di filtri fornisce un’architettura semplice per generare questi sottoinsiemi e applicare le regole come contenitori Persona, Sessione o Evento nidificati e gerarchici.

L’architettura dei contenitori utilizzata nel Generatore filtri definisce Persona come il contenitore più esterno, contenente i dati generali specifici della persona per visite e visualizzazioni di pagina. Un contenitore Sessione nidificato consente di impostare regole per suddividere i dati della persona in base alle sessioni, mentre un contenitore Evento nidificato consente di suddividere le informazioni della persona in base alle singole visualizzazioni di pagina. Ogni contenitore consente di generare rapporti sulla cronologia di una persona e sulle sue interazioni suddivise per sessioni o di suddividere singoli eventi.

### Contenitore Persona {#person}

Il contenitore Persona include ogni visita e visualizzazione di pagina per le persone entro un intervallo di tempo specificato. Un filtro a livello di Persona restituisce la pagina che soddisfa la condizione più tutte le altre pagine visualizzate dalla persona (e vincolate solo da intervalli di date definiti). Poiché è il contenitore definito in modo più ampio, i rapporti generati a livello del contenitore Persona restituiscono le visualizzazioni di pagina per tutte le visite e consentono di generare un’analisi per più visite. Pertanto, il contenitore Persona è il più suscettibile a modifiche in base a intervalli di date definiti.
I contenitori Persona possono includere valori basati sulla cronologia generale di una persona:

- Giorni precedenti al primo acquisto
- Pagina di ingresso originale
- Domini di riferimento originali

### Contenitore Sessione {#session}

Il contenitore Sessione consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica. Il contenitore Sessione è il contenitore più comunemente utilizzato perché acquisisce i comportamenti per l’intera sessione di visita una volta soddisfatta la regola. Il contenitore Sessione consente inoltre di definire quali sessioni includere o escludere nella creazione e applicazione di un filtro. Può aiutarti a rispondere alle seguenti domande:

- Quante sessioni sono interattive con le origini dati Web e Call Center?
- Quali pagine hanno contribuito alla conversione in una vendita?

I contenitori Sessione includono valori basati sull’occorrenza per sessione:

- Tipo di sessione
- Pagina di ingresso
- Frequenza di ritorno
- Metriche di partecipazione
- Metriche allocate linearmente

### Contenitore Evento {#event}

Il contenitore Evento definisce gli eventi di pagina da includere o escludere da un filtro. È il contenitore più ristretto disponibile per identificare clic specifici e visualizzazioni di pagina in cui è vera una condizione. Il contenitore Evento consente di visualizzare un singolo codice di tracciamento o di isolare il comportamento all’interno di una particolare sezione del sito. Puoi inoltre identificare un valore specifico quando si verifica un’azione, ad esempio il canale di marketing al momento di un ordine.

I contenitori Evento includono raggruppamenti di singole pagine basati su valori:

- Prodotti
- Proprietà elenco
- Dimensioni elenco
- Dimensioni del merchandising (nel contesto degli eventi)

## Modello di filtro preconfigurato {#template}

La versione tradizionale di Analytics include numerosi filtri modelli di filtri e metriche calcolate pronti all’uso. Molti non sono applicabili in CJA, oppure devono essere rinominati o ricreati. Altri dipendono da una soluzione per variabili in base al contesto in CJA.

| Nome filtro | Descrizione |
| --- | --- |
| Tutti i dati | Tutti i dati è un filtro obbligatorio che viene aggiunto in modo dinamico ai rapporti quando una metrica viene aggiunta alla riga di una tabella a forma libera. |
