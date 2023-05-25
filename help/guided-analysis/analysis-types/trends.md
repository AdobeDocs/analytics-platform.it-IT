---
title: Tendenze
description: Trova modelli e modifiche nel coinvolgimento degli utenti nel tempo.
source-git-commit: 37699a674a190aa2f28125d5b39bb3c27ac88551
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---

# Tendenze

{{release-limited-testing}}

Il **Tendenze** [Tipo di analisi](overview.md) fornisce informazioni utili sulle prestazioni del prodotto o sul comportamento degli utenti nel tempo. L’asse orizzontale di questo rapporto è sempre una granularità temporale, mentre l’asse verticale misura gli eventi desiderati. I casi di utilizzo per questo tipo di analisi includono:

* **Valutare le prestazioni del prodotto**: le tendenze ti consentono di valutare le prestazioni complessive del prodotto in un determinato periodo di tempo. Analizzando metriche quali coinvolgimento degli utenti, tassi di conversione o ricavi, puoi verificare se le prestazioni del prodotto stanno migliorando, stagnando o diminuendo.
* **Adozione di funzioni**: le tendenze ti consentono di comprendere in che modo gli utenti adottano nuove funzioni o aggiornamenti che rilasci. È possibile determinare quali feature sono popolari e quali feature richiedono miglioramenti. Queste informazioni ti consentono di prendere decisioni basate sui dati sulle funzioni per dare priorità alle tue attività di sviluppo.
* **Comportamento dell’utente**: le tendenze possono fornire informazioni sul comportamento degli utenti nel tempo. Esaminando le azioni specifiche intraprese dagli utenti, è possibile identificare i pattern in cui gli utenti potrebbero abbandonarsi. Puoi combinare le informazioni provenienti da questo tipo di analisi con una [Funnel](funnel.md) per ulteriori informazioni sul comportamento.
* **Test A/B e sperimentazione**: se esegui test A/B all’interno del prodotto, puoi utilizzare le Tendenze per determinare quali test hanno più successo nel tempo.

[Schermata delle tendenze]

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **Eventi**: gli eventi che desideri misurare nel rapporto. Ogni evento selezionato viene rappresentato da una linea colorata o da un insieme di barre, a seconda del tipo di grafico. Alla tabella viene aggiunta una riga che rappresenta l&#39;evento con tendenze. Puoi includere fino a cinque eventi.
* **Persone**: i segmenti che desideri misurare nel rapporto. Ogni segmento selezionato raddoppia il numero di righe nel grafico e di righe nella tabella. Ogni set di eventi è rappresentato per ogni segmento. Puoi includere fino a cinque segmenti.

## Tipi di visualizzazione

Le tendenze offrono i seguenti tipi di visualizzazione. È possibile modificare il tipo di visualizzazione utilizzando il menu a discesa in alto a sinistra del grafico.

* **Utilizzo:** Misura il coinvolgimento degli utenti nel tempo.

## Impostazioni grafico

Le tendenze offrono le seguenti impostazioni del grafico. È possibile regolare le impostazioni del grafico utilizzando il menu tra il tipo di visualizzazione e il selettore del calendario.

* **Metrica**: la metrica da misurare. Le opzioni includono Eventi, Sessioni, Utenti, Eventi per sessione ed Eventi per utente.
* **Tipo di grafico**: tipo di visualizzazione che desideri utilizzare. Le opzioni disponibili sono Linea, Barre, Barre sovrapposte e Area sovrapposta.

## Applica confronto temporale

Le tendenze offrono la possibilità di confrontare il periodo di tempo corrente con un periodo di tempo precedente. Se si seleziona un&#39;opzione in questo menu, a ogni linea verrà assegnata una linea punteggiata di colore simile. Questa linea punteggiata rappresenta la stessa metrica nell’intervallo di date precedente selezionato. Impostando questa opzione si raddoppia il numero di righe nel grafico e di righe nella tabella.

Le opzioni di confronto del tempo disponibili includono il periodo precedente, 13 settimane prima, 52 settimane prima e un intervallo di date personalizzato. Se selezioni Intervallo date personalizzato, vengono visualizzate opzioni aggiuntive per consentirti di selezionare il numero e la granularità. Se selezioni Nessuno, il confronto tra date viene rimosso.

## Intervallo date

Imposta l’intervallo di date desiderato. Questa impostazione è composta da due componenti importanti:

* **Interval**: granularità della data in cui desideri visualizzare i dati. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **Data**: data di inizio e fine. Sono disponibili predefiniti per l’intervallo di date, oppure puoi utilizzare il selettore del calendario per impostare la data esatta desiderata.
