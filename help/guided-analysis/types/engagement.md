---
title: Visualizzazione Coinvolgimento
description: Comprendi l’ampiezza e l’ampiezza del coinvolgimento delle funzioni.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 1%

---

# [!UICONTROL Engagement] visualizza

Il **[!UICONTROL Engagement]** Questa vista fornisce informazioni sulla frequenza di utilizzo di una funzione rispetto al numero di persone che la utilizzano. Questa analisi funziona meglio quando si confrontano diverse feature tra loro.

Le funzioni che tracciano la parte superiore di questa visualizzazione indicano che viene visitata frequentemente tra gli individui che la utilizzano. Le feature tracciate verso destra di questa visualizzazione indicano che la percentuale maggiore di utenti che interagisce con la feature è rappresentata da. Il numero mediano di volte in cui una feature viene utilizzata divide il grafico orizzontalmente. La percentuale mediana di utenti attivi giornalieri divide il grafico verticalmente.

* Le funzioni in alto a sinistra nella matrice indicano che una funzione non è ampiamente adottata. Tuttavia, tra gli individui che lo usano, lo usano frequentemente.
* Le funzioni in alto a destra nella matrice indicano che una funzione è ampiamente adottata e spesso utilizzata.
* Le funzioni in basso a destra nella matrice indicano che una funzione è ampiamente adottata, ma non utilizzata di frequente.
* Le funzioni in basso a sinistra nella matrice indicano che una funzione non è ampiamente adottata, né viene utilizzata di frequente.

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Coinvolgimento per funzione**: puoi stabilire una correlazione diretta tra il coinvolgimento e l’adozione di una funzione specifica. Capire quali feature vengono utilizzate maggiormente può aiutare a determinare quali feature dare priorità all&#39;ottimizzazione.
* **Scopri le funzioni sottoutilizzate**: caratteristiche con utenti attivi giornalieri bassi, ma un utilizzo elevato può indicare una funzione nascosta ma preziosa. Esamina l’esposizione di questi tipi di funzioni a più utenti.
* **Migliorare le funzioni più comuni**: funzionalità con utenti attivi elevati ma poco utilizzate possono indicare che una funzionalità è fortemente richiesta, ma sottoutilizzata. Valuta l’opportunità di investire nel miglioramento di queste funzioni in modo che vengano utilizzate più spesso.
* **Creare segmenti basati su funzioni**: l’analisi della frequenza di utilizzo di una funzione rispetto al numero di utenti che la adottano può aiutare a determinare i tipi di utenti che adottano una determinata funzione. Puoi creare segmenti in base agli utenti che utilizzano una funzione in modo occasionale o in base agli utenti che utilizzano frequentemente tale funzione.
* **Adozione di funzioni test A/B**: confronta l’utilizzo di più funzioni utilizzando i segmenti. Aggiungi i segmenti di ciascuna coorte nella barra delle query per determinare facilmente la differenza nell’utilizzo delle funzioni.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Events]**: gli eventi che desideri misurare. Questi eventi rappresentano in genere l’utilizzo di una determinata funzione. Ogni selezione è rappresentata come un punto all&#39;interno della matrice. Puoi includere fino a dieci eventi.
* **[!UICONTROL Counted as]**: determina i dettagli del conteggio degli utenti sull’asse x. Puoi misurare la percentuale media di utenti attivi giornalieri, settimanali, mensili o trimestrali. L’asse y regola automaticamente i tempi medi per utente in base alla selezione dell’asse x.
* **[!UICONTROL Segments]**: i segmenti che desideri misurare. Ogni segmento selezionato raddoppia il numero di punti tracciati nel grafico e le righe nella tabella. Puoi includere fino a tre segmenti.

## Impostazioni grafico

Il [!UICONTROL Engagement] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Medians]**: determina dove vengono visualizzate le linee mediane e come i punti tracciati si relazionano a tali mediane.
   * **[!UICONTROL Standard]**: mostra il valore assoluto di utilizzo e coinvolgimento.
   * **[!UICONTROL Normalized]**: mostra le modifiche relative da ogni mediana.
* **[!UICONTROL Top events overlay]**: osserva come stanno andando gli eventi rispetto agli eventi più comuni.

## Confronto temporale

{{apply-time-comparison}}

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati sulle tendenze. Questo tipo di visualizzazione tratta [!UICONTROL Interval] simile a [!UICONTROL Counted as] nella barra delle query. Gli utenti attivi su base oraria non sono supportati.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
