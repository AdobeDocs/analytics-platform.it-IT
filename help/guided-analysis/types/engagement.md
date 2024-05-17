---
title: Visualizzazione Coinvolgimento
description: Comprendi l’ampiezza e la profondità del coinvolgimento delle funzioni.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: a4c35466b225d44130bb55204e2fdb155fa7dee6
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 1%

---

# [!UICONTROL Engagement] visualizza

Il **[!UICONTROL Engagement]** Questa vista fornisce informazioni sulla frequenza di utilizzo di una funzione rispetto al numero di persone che la utilizzano. Questa analisi funziona meglio quando si confrontano diverse feature tra loro. Aiuta ad alimentare le decisioni di investimento comprendendo quali sono le tue caratteristiche principali, di potenza, una tantum e discutibili.

Le funzioni che tracciano la parte superiore di questa visualizzazione indicano che vengono utilizzate di frequente tra gli utenti coinvolti. Le funzioni che tracciano la parte destra di questa visualizzazione indicano che sono ampiamente adottate tra gli utenti attivi. Il numero mediano di volte in cui una feature viene utilizzata divide il grafico orizzontalmente. La percentuale mediana di utenti attivi divide il grafico verticalmente. Le mediane vengono calcolate in base agli eventi selezionati nella query, non a tutti i dati.

* Le funzioni in alto a sinistra nella matrice sono **alimentazione** caratteristiche; non sono ampiamente adottate, ma sono spesso utilizzate dagli utenti coinvolti.
* Le funzionalità in alto a destra della matrice sono **forte impatto** caratteristiche; sono ampiamente adottati e utilizzati di frequente.
* Le funzioni in basso a sinistra nella matrice sono **impatto ridotto** caratteristiche; non sono ampiamente adottate o utilizzate di frequente.
* Le funzioni in basso a destra della matrice sono **una tantum** caratteristiche; sono ampiamente adottati, ma non utilizzati di frequente.

![Schermata del coinvolgimento](../assets/feature-matrix.png)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Coinvolgimento per funzione**: puoi stabilire una correlazione diretta tra il coinvolgimento e l’adozione di una funzione specifica. Capire quali funzioni vengono utilizzate di più può aiutare a determinare quali funzioni investire ulteriormente.
* **Scopri le funzioni sottoutilizzate**: funzionalità con utenti poco attivi ma con un utilizzo elevato possono indicare una funzione di alimentazione, che è preziosa ma non scoperta o utilizzata dalla popolazione più ampia. Valuta se migliorare la reperibilità di queste funzioni in modo che più utenti le sfruttino.
* **Migliorare le funzioni più comuni**: funzionalità con utenti attivi elevati ma poco utilizzate possono indicare che una funzionalità è fortemente richiesta, ma sottoutilizzata. In queste situazioni è possibile ottenere ulteriori informazioni dagli utenti sui miglioramenti che renderebbero la funzione più utile.
* **Creare segmenti basati su funzioni**: visualizzando in questo modo l’utilizzo delle funzioni si ottengono ulteriori opportunità di analisi. Crea un segmento per qualsiasi punto del grafico per immergerti ulteriormente in tale gruppo di utenti e applicare tali insegnamenti alla tua strategia di coinvolgimento degli utenti.
* **Adozione di funzioni test A/B**: confronta l’utilizzo di più funzioni tra diversi gruppi di utenti. Aggiungi segmenti nella barra delle query per determinare la differenza nell’utilizzo delle funzioni tra i diversi gruppi di utenti chiave.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Events]**: gli eventi che desideri misurare. Ogni evento rappresenta l’utilizzo di una determinata funzione e viene visualizzato come punto all’interno della matrice. Puoi includere fino a dieci eventi. La mediana viene calcolata in base agli eventi selezionati.
* **[!UICONTROL Counted as]**: lungo l’asse x, puoi misurare la percentuale media di utenti attivi giornalieri, settimanali, mensili o trimestrali. L’asse y regola automaticamente i tempi medi per utente in base alla selezione dell’asse x.
* **[!UICONTROL Segments]**: i segmenti che desideri misurare. Ogni segmento selezionato raddoppia il numero di punti tracciati nel grafico e le righe nella tabella. Puoi includere fino a tre segmenti.

>[!TIP]
>
>Se più eventi rappresentano l’utilizzo di una singola funzione, puoi derivare un nuovo evento che rappresenta la funzione nelle Visualizzazioni dati.

## Impostazioni grafico

Il [!UICONTROL Engagement] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Medians]**: determina dove vengono visualizzate le linee mediane e come i punti tracciati si relazionano a tali mediane.
   * **[!UICONTROL Standard]**: mostra il valore assoluto di utilizzo e coinvolgimento.
   * **[!UICONTROL Normalized]**: mostra le modifiche relative da ogni mediana.
* **[!UICONTROL Top events overlay]**: scopri il comportamento degli eventi rispetto ai primi 20, in base all’attualità e alla rilevanza dell’azienda e dell’utente (lo stesso algoritmo applicato al selettore di eventi nella barra delle query).

## Confronto temporale

{{apply-time-comparison}}

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati sulle tendenze. Questo tipo di visualizzazione tratta [!UICONTROL Interval] simile a [!UICONTROL Counted as] nella barra delle query. Gli utenti attivi su base oraria non sono supportati.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
