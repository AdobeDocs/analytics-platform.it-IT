---
title: Utilizzo
description: Misura il coinvolgimento degli utenti nel tempo.
exl-id: 1d103bd3-3e72-4c82-a534-c896f8433029
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Utilizzo

{{release-limited-testing}}

Il **Utilizzo** tipo di visualizzazione fornisce informazioni utili sulle prestazioni del prodotto o sul comportamento degli utenti nel tempo. L’asse orizzontale di questo rapporto è sempre una granularità temporale, mentre l’asse verticale misura gli eventi desiderati. I casi di utilizzo per questo tipo di visualizzazione includono:

* **Valutare le prestazioni del prodotto**: le tendenze ti consentono di valutare le prestazioni complessive del prodotto in un determinato periodo di tempo. Analizzando metriche quali coinvolgimento degli utenti, tassi di conversione o ricavi, puoi verificare se le prestazioni del prodotto stanno migliorando, stagnando o diminuendo.
* **Adozione di funzioni**: le tendenze ti consentono di comprendere in che modo gli utenti adottano nuove funzioni o aggiornamenti che rilasci. È possibile determinare quali feature sono popolari e quali feature richiedono miglioramenti. Queste informazioni ti consentono di prendere decisioni basate sui dati sulle funzioni per dare priorità alle tue attività di sviluppo.
* **Comportamento dell’utente**: le tendenze possono fornire informazioni sul comportamento degli utenti nel tempo. Esaminando le azioni specifiche intraprese dagli utenti, è possibile identificare i pattern in cui gli utenti potrebbero abbandonarsi. È possibile combinare informazioni provenienti da questo tipo di visualizzazione con [Attrito](friction.md) per ulteriori informazioni sul comportamento.
* **Test A/B e sperimentazione**: se esegui test A/B all’interno del prodotto, puoi utilizzare le Tendenze per determinare quali test hanno più successo nel tempo.

![Utilizzo](../assets/usage.png)

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **Eventi**: gli eventi che desideri misurare nel rapporto. Ogni evento selezionato viene rappresentato da una linea colorata o da un insieme di barre, a seconda del tipo di grafico. Alla tabella viene aggiunta una riga che rappresenta l&#39;evento con tendenze. Puoi includere fino a cinque eventi.
* **Persone**: i segmenti che desideri misurare nel rapporto. Ogni segmento selezionato raddoppia il numero di righe nel grafico e di righe nella tabella. Ogni set di eventi è rappresentato per ogni segmento. Puoi includere fino a cinque segmenti.

## Impostazioni grafico

Le tendenze offrono le seguenti impostazioni del grafico. È possibile regolare le impostazioni del grafico utilizzando il menu tra il tipo di visualizzazione e il selettore del calendario.

* **Metrica**: la metrica da misurare. Le opzioni includono Eventi, Sessioni, Utenti, Eventi per sessione ed Eventi per utente.
* **Tipo di grafico**: tipo di visualizzazione che desideri utilizzare. Le opzioni disponibili sono Linea, Barre, Barre sovrapposte e Area sovrapposta.

## Applica confronto temporale

{{apply-time-comparison}}

![Confronto tempo di utilizzo](../assets/usage-compare.png)

## Intervallo date

Imposta l’intervallo di date desiderato. Questa impostazione è composta da due componenti importanti:

* **Interval**: granularità della data in cui desideri visualizzare i dati. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **Data**: data di inizio e fine. Sono disponibili predefiniti per l’intervallo di date, oppure puoi utilizzare il selettore del calendario per impostare la data esatta desiderata.
