---
title: Analisi del coinvolgimento
description: Comprendi l’ampiezza e la profondità del coinvolgimento delle funzioni.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Analisi [!UICONTROL Engagement] {#engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_engagement_button"
>title="Coinvolgimento"
>abstract="Comprendi l’ampiezza e la profondità del coinvolgimento delle funzioni."

<!-- markdownlint-enable MD034 -->


L&#39;analisi ![EngagementGraph](/help/assets/icons/EngagementGraph.svg) **[!UICONTROL Engagement]** fornisce informazioni approfondite sulla frequenza di utilizzo di una funzionalità rispetto al numero di persone che la utilizzano. Questa analisi funziona meglio quando si confrontano diverse feature tra loro. Aiuta ad alimentare le decisioni di investimento comprendendo quali sono le tue caratteristiche principali, di potenza, una tantum e discutibili.

Le funzioni che tracciano la parte superiore di questa visualizzazione indicano che vengono utilizzate di frequente tra gli utenti coinvolti. Le funzioni che tracciano la parte destra di questa visualizzazione indicano che sono ampiamente adottate tra gli utenti attivi. Il numero mediano di volte in cui una feature viene utilizzata divide il grafico orizzontalmente. La percentuale mediana di utenti attivi divide il grafico verticalmente. Le mediane vengono calcolate in base agli eventi selezionati nella query, non a tutti i dati.

* Le funzionalità nella parte superiore sinistra della matrice sono le funzionalità di **power**. Non sono ampiamente diffuse, ma sono utilizzate di frequente dagli utenti coinvolti.
* Le funzionalità in alto a destra nella matrice sono le tue **funzionalità ad alto impatto**; sono ampiamente adottate e utilizzate di frequente.
* Le funzionalità in basso a sinistra nella matrice sono le tue **funzionalità a basso impatto**; non sono ampiamente adottate o utilizzate di frequente.
* Le funzionalità nella parte inferiore destra della matrice sono le **funzionalità occasionali**; sono ampiamente adottate, ma non utilizzate di frequente.

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)


## Casi d’uso

I casi di utilizzo per questa analisi includono:

* **Coinvolgimento per funzione**: è possibile stabilire una correlazione diretta tra il coinvolgimento e l&#39;adozione di una funzione specifica. Capire quali funzioni vengono utilizzate di più può aiutare a determinare quali funzioni investire ulteriormente.
* **Scopri le funzionalità sottoutilizzate**: le funzionalità con utenti attivi bassi ma con un utilizzo elevato possono indicare una funzionalità di alimentazione, che è preziosa ma non viene scoperta o utilizzata dalla popolazione più ampia. Valuta se migliorare la reperibilità di queste funzioni in modo che più utenti le sfruttino.
* **Miglioramento delle funzionalità più comuni**: funzionalità con utenti attivi elevati ma poco utilizzate possono indicare che una funzionalità è fortemente richiesta ma sottoutilizzata. In queste situazioni è possibile ottenere ulteriori informazioni dagli utenti sui miglioramenti che renderebbero la funzione più utile.
* **Crea segmenti basati su funzionalità**: questo tipo di visualizzazione consente di visualizzare l&#39;utilizzo delle funzionalità per richiedere ulteriori opportunità di analisi. Crea un segmento per qualsiasi punto del grafico per immergerti ulteriormente in tale gruppo di utenti e applicare tali insegnamenti alla tua strategia di coinvolgimento degli utenti.
* **Test A/B di adozione delle funzionalità**: confronta l&#39;utilizzo di più funzionalità tra gruppi di utenti diversi. Aggiungi segmenti nella barra delle query per determinare la differenza nell’utilizzo delle funzioni tra i diversi gruppi di utenti chiave.

## Interfaccia

Per una panoramica dell&#39;interfaccia di analisi guidata, vedere [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Events]**: gli eventi che si desidera misurare. Ogni evento rappresenta l’utilizzo di una determinata funzione e viene visualizzato come punto all’interno della matrice. Puoi includere fino a dieci eventi. La mediana viene calcolata in base agli eventi selezionati.
* **[!UICONTROL Counted as]**: lungo l&#39;asse x è possibile misurare la percentuale media di utenti attivi giornalieri, settimanali, mensili o trimestrali. L’asse y regola automaticamente i tempi medi per utente in base alla selezione dell’asse x.
* **[!UICONTROL Segments]**: i segmenti che si desidera misurare. Ogni segmento selezionato raddoppia il numero di punti tracciati nel grafico e le righe nella tabella. Puoi includere fino a tre segmenti.

>[!TIP]
>
>Se più eventi rappresentano l’utilizzo di una singola funzione, puoi derivare un nuovo evento che rappresenta la funzione nelle Visualizzazioni dati.

### Impostazioni grafico

L&#39;analisi [!UICONTROL Engagement] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Medians]**: Determinare dove vengono visualizzate le linee mediane e come i punti tracciati si relazionano a tali mediane.
   * **[!UICONTROL Standard]**: mostra il valore assoluto di utilizzo e coinvolgimento.
   * **[!UICONTROL Normalized]**: mostra le modifiche relative da ogni mediana.
* **[!UICONTROL Top events overlay]**: osserva come stanno andando i tuoi eventi rispetto ai primi 20, in base all&#39;attualità e alla rilevanza della società e dell&#39;utente (lo stesso algoritmo applicato al selettore di eventi nella barra delle query).

### Confronto temporale

{{apply-time-comparison}}

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati sulle tendenze. Questa analisi tratta [!UICONTROL Interval] in modo simile a [!UICONTROL Counted as] nella barra delle query. Gli utenti attivi su base oraria non sono supportati.
* **[!UICONTROL Date]**: la data di inizio e di fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.

<!--
## Example

See below for an example of the analysis.

![Enagement compare](../assets/engagement-compare.png)
-->
