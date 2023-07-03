---
title: Funnel
description: Identificare le aree di attrito in una sequenza di passaggi.
exl-id: f0ba3f00-bf1f-48db-8b6e-137460abf4f8
feature: Guided Analysis
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Funnel

{{release-limited-testing}}

Il **Funnel** [Tipo di analisi](overview.md) fornisce una rappresentazione visiva di un percorso di utenti critico nel prodotto. L’asse orizzontale rappresenta ogni evento che un utente deve toccare nell’ordine. L’asse verticale rappresenta la percentuale di utenti o sessioni che hanno toccato ogni evento. Tutti i punti di contatto devono essere eseguiti in ordine finale, ma possono verificarsi in qualsiasi momento all’interno dell’intervallo di reporting. I casi di utilizzo per questo tipo di analisi includono:

* **Analisi della conversione**: funnel consente di analizzare le conversioni in ogni fase del funnel. Monitorando il numero di utenti che avanzano da un passaggio all’altro, puoi identificare i colli di bottiglia con tassi di conversione insoliti o indesiderati. Queste informazioni sono utili per capire dove è possibile migliorare il prodotto per ottenere risultati immediati.
* **Ottimizzazione dell’onboarding**: il funnel è utile per ottimizzare il processo di onboarding del prodotto. Esaminando il comportamento degli utenti in relazione agli eventi chiave, puoi identificare i passaggi con cui gli utenti hanno difficoltà o che non riescono a completare.
* **Adozione e coinvolgimento delle funzioni**: funnel consente di comprendere come gli utenti interagiscono con funzioni specifiche del prodotto. Analizzando la progressione degli utenti attraverso passaggi relativi alle funzioni, puoi valutare i tassi di adozione delle funzioni e identificare le aree in cui gli utenti potrebbero abbandonare o sottoutilizzare determinate funzioni. Puoi quindi utilizzare queste informazioni per concentrarti su miglioramenti delle funzioni o dell’interfaccia utente per aumentare i tassi di adozione.
* **Valutazione della campagna**: il funnel può aiutare a misurare l’efficacia delle campagne di marketing. Puoi creare un segmento che si concentra sugli utenti che hanno toccato una determinata campagna e confrontare il loro processo di conversione con altre campagne o all’interno del tuo prodotto in generale.

[Schermata del funnel]

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **Passaggi**: i punti di contatto dell’evento di cui desideri tenere traccia. Ogni barra del grafico rappresenta un passo. Puoi includere fino a dieci passaggi.
* **Persone**: i segmenti in cui desideri confrontare il funnel. Ogni segmento selezionato suddivide ogni passaggio in più barre. Ogni colore rappresenta un segmento diverso. Puoi includere fino a tre segmenti.

## Tipi di visualizzazione

Funnel offre i seguenti tipi di visualizzazione. È possibile modificare il tipo di visualizzazione utilizzando il menu a discesa in alto a sinistra del grafico.

* **Attrito**: confronta i tassi di conversione tra passaggi.

## Impostazioni grafico

Funnel offre le seguenti impostazioni per i grafici. È possibile regolare le impostazioni del grafico utilizzando il menu tra il tipo di visualizzazione e il selettore del calendario.

* **Metrica**: la metrica da misurare. Le opzioni includono Sessioni e Utenti.
* **Tipo di grafico**: tipo di visualizzazione che desideri utilizzare. L&#39;unica opzione è Passaggi.
* **Conversione da**: determina il calcolo della percentuale da un passaggio all’altro. Le opzioni includono il calcolo della conversione dal primo passaggio o dal passaggio precedente.

## Intervallo date

La data di inizio e di fine. Sono disponibili predefiniti per l’intervallo di date, oppure puoi utilizzare il selettore del calendario per impostare la data esatta desiderata.
