---
title: Analisi del coinvolgimento
description: Comprendi l’ampiezza e la profondità del coinvolgimento delle funzioni.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 100%

---

# [!UICONTROL Engagement] analisi {#engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_engagement_button"
>title="Coinvolgimento"
>abstract="Comprendi l’ampiezza e la profondità del coinvolgimento delle funzioni."

<!-- markdownlint-enable MD034 -->


L’analisi ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) **[!UICONTROL Engagement]** fornisce informazioni approfondite sulla frequenza di utilizzo di una funzione rispetto al numero di persone che la utilizzano. Questa analisi funziona meglio quando si confrontano più funzioni tra loro. Aiuta nelle decisioni di investimento fornendo indicazioni su quali possono essere le funzioni principali, di potenza, una tantum e discutibili.

Le funzioni che si posizionano nella parte superiore di questa visualizzazione indicano che vengono utilizzate di frequente tra gli utenti coinvolti. Le funzioni che si posizionano nella parte destra di questa visualizzazione indicano che sono ampiamente adottate tra gli utenti attivi. Il numero mediano di volte in cui una funzione viene utilizzata divide il grafico orizzontalmente. La percentuale mediana di utenti attivi divide il grafico verticalmente. Le mediane vengono calcolate in base agli eventi selezionati nella query, non a tutti i dati.

* Le funzioni nella parte superiore sinistra della matrice sono le funzioni di **potenza**. Non sono ampiamente adottate, ma sono utilizzate di frequente dagli utenti coinvolti.
* Le funzioni in alto a destra della matrice sono le funzioni ad **alto impatto**; sono ampiamente adottate e utilizzate di frequente.
* Le funzioni in basso a sinistra della matrice sono le funzioni a **basso impatto**; non sono ampiamente adottate, né utilizzate di frequente.
* Le funzioni nella parte inferiore destra della matrice sono le funzioni **una tantum**; sono ampiamente adottate, ma non utilizzate di frequente.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)


## Casi d’uso

I casi d’uso per questa analisi includono:

* **Coinvolgimento per funzione**: è possibile stabilire una correlazione diretta tra il coinvolgimento e l’adozione di una funzione specifica. Capire quali funzioni vengono utilizzate di più può aiutare a determinare su quali funzioni investire ulteriormente.
* **Scopri le funzioni sottoutilizzate**: le funzioni con un basso numero di utenti attivi ma un utilizzo elevato possono indicare una funzione di potenza, che è utile ma non viene individuata o utilizzata dalla popolazione più ampia. Valuta se migliorare la reperibilità di queste funzioni in modo che più utenti le sfruttino.
* **Migliorare le funzioni più comuni**: funzioni con un numero elevato di utenti attivi ma un basso utilizzo possono indicare che una funzione è fortemente richiesta ma sottoutilizzata. In queste situazioni è possibile ottenere ulteriori informazioni dagli utenti sui miglioramenti che renderebbero la funzione più utile.
* **Creare segmenti basati sulle funzioni**: visualizzare l’utilizzo delle funzioni in questo modo per favorire ulteriori opportunità di analisi. Crea un segmento per qualsiasi punto del grafico per immergerti ulteriormente in tale gruppo di utenti e applicare tali insegnamenti alla strategia di coinvolgimento dell’utente.
* **Test A/B di adozione della funzione**: confronta l’utilizzo di più funzioni tra gruppi di utenti diversi. Aggiungi segmenti nella barra delle query per determinare la differenza nell’utilizzo delle funzioni tra i diversi gruppi di utenti chiave.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Events]**: eventi che desideri misurare. Ogni evento rappresenta l’utilizzo di una determinata funzione e viene visualizzato come punto all’interno della matrice. Puoi includere fino a dieci eventi. La mediana viene calcolata in base agli eventi selezionati.
* **[!UICONTROL Counted as]**: lungo l’asse x è possibile misurare la percentuale media di utenti attivi giornalieri, settimanali, mensili o trimestrali. L’asse y regola automaticamente i tempi medi per utente in base alla selezione dell’asse x.
* **[!UICONTROL Segments]**: segmenti che desideri misurare. Ogni segmento selezionato raddoppia il numero di punti posizionati nel grafico e le righe nella tabella. Puoi includere fino a tre segmenti.

>[!TIP]
>
>Se più eventi rappresentano l’utilizzo di una singola funzione, puoi derivare un nuovo evento che la rappresenti nelle visualizzazioni dati.

### Impostazioni del grafico

L’analisi del [!UICONTROL Engagement] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Medians]**: determinare dove vengono visualizzate le linee mediane e come i punti posizionati si relazionano con tali mediane.
   * **[!UICONTROL Standard]**: mostrare il valore assoluto di utilizzo e coinvolgimento.
   * **[!UICONTROL Normalized]**: mostrare le modifiche relative da ogni mediana.
* **[!UICONTROL Top events overlay]**: scopri come stanno andando i tuoi eventi rispetto ai primi 20, in base all’attualità e alla rilevanza dell’azienda e dell’utente (lo stesso algoritmo applicato al selettore eventi nella barra delle query).

### Confronto temporale

{{apply-time-comparison}}

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati sulle tendenze. Questa analisi tratta [!UICONTROL Interval] in modo simile a [!UICONTROL Counted as] nella barra delle query. Gli utenti attivi su base oraria non sono supportati.
* **[!UICONTROL Date]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
