---
title: Visualizzazione utilizzo
description: Misura il coinvolgimento degli utenti nel tempo.
exl-id: 1d103bd3-3e72-4c82-a534-c896f8433029
feature: Guided Analysis
source-git-commit: 9f176bc6bc12291dcdab80af50c32df7d8edf220
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# [!UICONTROL Usage] view

Il **[!UICONTROL Usage]** fornisce informazioni utili sulle prestazioni del prodotto o sul comportamento degli utenti nel tempo. L’asse orizzontale di questo rapporto è un intervallo di tempo, mentre l’asse verticale misura gli eventi desiderati.

![Utilizzo](../assets/usage.png)

## Consulta [!UICONTROL Usage] visualizza in azione

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Valutare le prestazioni del prodotto**: le tendenze ti consentono di valutare le prestazioni complessive del prodotto in un determinato periodo di tempo. Analizzando metriche quali coinvolgimento degli utenti, tassi di adozione o di conversione, puoi verificare se le prestazioni del prodotto stanno migliorando, stagnando o diminuendo.
* **Adozione di funzioni**: le tendenze ti consentono di comprendere in che modo gli utenti adottano nuove funzioni o aggiornamenti che rilasci. È possibile determinare quali feature sono popolari e quali feature richiedono miglioramenti. Queste informazioni ti consentono di prendere decisioni basate sui dati sulle funzioni per dare priorità alle tue attività di sviluppo.
* **Comportamento dell’utente**: le tendenze possono fornire informazioni sul comportamento degli utenti nel tempo. Esaminando le azioni specifiche intraprese dagli utenti, è possibile identificare i pattern in cui gli utenti potrebbero abbandonarsi. Puoi combinare le informazioni provenienti da questa visualizzazione con [Attrito](friction.md) per ulteriori informazioni sul comportamento.
* **Test A/B e sperimentazione**: se esegui test A/B all’interno del prodotto, puoi utilizzare le Tendenze per determinare quali test hanno più successo nel tempo.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Events]**: gli eventi che desideri misurare. Ogni evento selezionato viene rappresentato come una linea colorata o un set di barre, a seconda del tipo di grafico. Alla tabella viene aggiunta una riga che rappresenta l&#39;evento con tendenze. Puoi includere fino a cinque eventi.
* **[!UICONTROL People]**: i segmenti che desideri misurare. Ogni segmento selezionato raddoppia il numero di righe nel grafico e di righe nella tabella. Puoi includere fino a cinque segmenti.

## Impostazioni grafico

Il [!UICONTROL Usage] visualizza offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Metric]**: la metrica da misurare. Le opzioni includono Eventi, Sessioni, Utenti, Eventi per sessione ed Eventi per utente.
* **[!UICONTROL Chart type]**: tipo di visualizzazione che desideri utilizzare. Le opzioni disponibili sono Linea, Barre, Barre sovrapposte e Area sovrapposta.

## Applica confronto temporale

{{apply-time-comparison}}

![Confronto tempo di utilizzo](../assets/usage-compare.png)

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Le opzioni valide includono Orario, Giornaliero, Settimanale, Mensile e Trimestrale. Lo stesso intervallo di date può avere intervalli diversi che influiscono sul numero di coordinate nel grafico e sul numero di colonne nella tabella. Ad esempio, la visualizzazione di un’analisi con granularità giornaliera della durata di tre giorni mostrerebbe solo tre punti di dati, mentre un’analisi con granularità oraria della durata di tre giorni mostrerebbe 72 punti di dati.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
