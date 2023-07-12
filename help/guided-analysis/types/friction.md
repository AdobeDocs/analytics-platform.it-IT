---
title: Vista frizione
description: Confronta i tassi di conversione tra passaggi.
exl-id: f0ba3f00-bf1f-48db-8b6e-137460abf4f8
feature: Guided Analysis
source-git-commit: aca4a5091c65d7243f79551be7cee615ba98bb26
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# Vista frizione

{{release-limited-testing}}

Il **Attrito** visualizza fornisce una rappresentazione visiva di un percorso di utenti critico nel prodotto. L’asse orizzontale rappresenta ogni passaggio che un utente deve attraversare. L’asse verticale rappresenta la percentuale di utenti o sessioni in ogni passaggio. Tutti i passaggi devono essere eseguiti nell’ordine finale, ma possono essere eseguiti in qualsiasi momento all’interno dell’intervallo di reporting.

![Attrito](../assets/friction.png)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Analisi della conversione**: puoi analizzare le conversioni in ogni fase del funnel. Monitorando il numero di utenti che avanzano da un passaggio all’altro, puoi identificare i colli di bottiglia con tassi di conversione insoliti o indesiderati. Queste informazioni sono utili per capire dove è possibile migliorare il prodotto per ottenere risultati immediati.
* **Ottimizzazione dell’onboarding**: ottimizza il processo di onboarding del prodotto esaminando il comportamento degli utenti in relazione agli eventi chiave. Puoi identificare i passaggi con cui gli utenti hanno difficoltà o che non riescono a completare.
* **Adozione e coinvolgimento delle funzioni**: scopri come gli utenti interagiscono con funzioni specifiche del tuo prodotto. Analizzando la progressione degli utenti attraverso passaggi relativi alle funzioni, puoi valutare i tassi di adozione delle funzioni e identificare le aree in cui gli utenti potrebbero abbandonare o sottoutilizzare determinate funzioni. Puoi quindi utilizzare queste informazioni per concentrarti sui miglioramenti delle funzioni per aumentare i tassi di adozione.
* **Valutazione della campagna**: misura l’efficacia delle campagne di marketing. Puoi creare un segmento che si concentra sugli utenti che hanno toccato una determinata campagna e confrontare il loro processo di conversione con altre campagne o all’interno del tuo prodotto in generale.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **Passaggi**: i punti di contatto dell’evento di cui desideri tenere traccia. Ogni barra del grafico rappresenta un passo. Puoi includere fino a dieci passaggi.
* **Persone**: i segmenti in cui desideri confrontare il funnel. Ogni segmento selezionato suddivide ogni passaggio in più barre. Ogni colore rappresenta un segmento diverso. Puoi includere fino a tre segmenti.

## Impostazioni grafico

La vista Attrito offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **Metrica**: ambito che desideri applicare al funnel. Le opzioni includono Sessioni e Utenti. Selezionando le sessioni, per poter essere conteggiati tutti i passaggi devono avvenire all’interno della stessa sessione. Selezionando gli utenti, tutti i passaggi devono avvenire nell’intervallo di reporting selezionato per essere conteggiati.
* **Tipo di grafico**: tipo di visualizzazione che desideri utilizzare. Le opzioni includono Passaggi.
* **Conversione da**: determina il calcolo della percentuale da un passaggio all’altro. Le opzioni includono il calcolo della conversione dal primo passaggio o dal passaggio precedente.

## Applica confronto temporale

{{apply-time-comparison}}

![Confronto del tempo di attrito](../assets/friction-compare.png)

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **Interval**: granularità della data in base alla quale visualizzare i dati con tendenze. Questa impostazione non influisce sulle viste senza tendenze, ad esempio Attrito.
* **Data**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
