---
title: Analisi della frequenza
description: Misura il coinvolgimento in base alla frequenza d’uso.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
TQID: https://experienceleague.adobe.com/q-egeF94DZ-kxHpVBJX7A-Th0N30t7ji-V2EoXMe1P4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 671
ht-degree: 78%

---

# Analisi della [!UICONTROL frequenza] {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_frequency_button"
>title="Frequenza"
>abstract="Visualizza la distribuzione delle attività degli utenti ripetuti per eventi specifici."

<!-- markdownlint-enable MD034 -->

L&#39;analisi ![Frequenza](/help/assets/icons/Histogram.svg) **[!UICONTROL Frequenza]** raggruppa i dati dell&#39;evento in base alla frequenza con cui si verificano gli eventi nel prodotto. L’asse verticale di questa analisi contiene bucket che rappresentano la frequenza dell’evento. L’asse orizzontale misura il numero di utenti o sessioni per ciascun bucket.

>[!VIDEO](https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/guided-analysis/frequency)

## Casi d’uso

I casi d’uso per questa analisi includono:

* **Coinvolgimento**: tieni traccia del livello di coinvolgimento degli utenti con qualsiasi evento del prodotto. Puoi fare clic su una parte qualsiasi del grafico a barre per salvarlo come segmento. I segmenti per bucket di coinvolgimento ridotti possono aiutarti a determinare il motivo per cui gli utenti non interagiscono con l’evento alla frequenza desiderata. I segmenti per bucket di coinvolgimento elevati possono aiutarti a capire perché gli utenti interagiscono spesso con l’evento. Da lì, puoi incoraggiare altri utenti ad adottare un comportamento simile.
* **Fedeltà del cliente**: imposta l’evento su Ordini e la metrica su Utenti. Questa analisi consente di raggruppare gli utenti in base al numero di volte in cui hanno effettuato un acquisto sul sito entro l’intervallo di date specificato.
* **Ottimizzazione del supporto**: visualizza il numero di chiamate al supporto o casi aperti per utente per ottenere informazioni approfondite su quali utenti riscontrano il maggior numero di problemi. Puoi quindi creare un segmento con focus sulla loro esperienza per aiutarli a identificare e risolvere i loro problemi.
* **Servizi in abbonamento**: gli utenti con un coinvolgimento basso hanno maggiori probabilità di abbandono. Comprendere il comportamento degli utenti altamente coinvolti può aiutare a incoraggiare un comportamento simile negli utenti meno coinvolti, rendendoli meno propensi ad annullare l’abbonamento.

## Interfaccia

Per una panoramica dell’interfaccia dell’analisi guidata, consulta [Interfaccia](../overview.md#interface). Le seguenti impostazioni sono specifiche per questa analisi:

### Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL Visualizzazione]**: passa da questa analisi a [Tendenze](trends.md).
* **[!UICONTROL Eventi]**: gli eventi che desideri misurare. Ogni evento selezionato viene rappresentato da un grafico separato. Alla tabella viene aggiunta una riga che rappresenta l’evento con tendenze. Puoi includere fino a cinque eventi.
* **[!UICONTROL Conteggiato come]**: metodo di conteggio che desideri applicare agli eventi selezionati. Le opzioni includono [!UICONTROL Utenti], [!UICONTROL Sessioni], [!UICONTROL Percentuale di utenti] e [!UICONTROL Percentuale di sessioni]. Il denominatore per le metriche basate sulle percentuali in questa analisi è rappresentato dagli utenti o dalle sessioni che hanno eseguito gli eventi selezionati, non tutti gli utenti attivi del prodotto.
* **[!UICONTROL Segmenti]**: i segmenti che desideri misurare. Ogni segmento selezionato raddoppia il numero di barre posizionate nel grafico e le righe nella tabella. Puoi includere fino a cinque segmenti.

### Impostazioni del grafico

L&#39;analisi [!UICONTROL Frequency] offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Tipo di grafico]**: tipo di visualizzazione che si desidera utilizzare. Le opzioni includono [!UICONTROL Barra orizzontale] e [!UICONTROL Barra sovrapposta].

### Impostazioni del bucket

Determina il modo in cui l’evento viene classificato in gruppi (bucket). Nella vista della tabella con tendenze, gli utenti vengono inseriti nei bucket in base alla frequenza di utilizzo in totale e in ogni intervallo, il che significa che 1 utente può essere contato in bucket diversi in intervalli diversi.

* **[!UICONTROL Bucket automatici]**: identifica automaticamente la dimensione ottimale del bucket in base alla distribuzione dei dati.
* **[!UICONTROL Bucket personalizzati]**: personalizzare il raggruppamento dei dati in bucket.
   * [!UICONTROL Da]: primo bucket. La frequenza inferiore a questo valore è esclusa dalla generazione dei rapporti.
   * [!UICONTROL A]: la frequenza maggiore di questo valore è raggruppata nell&#39;ultimo bucket.
   * [!UICONTROL Dimensione]: intervallo di bucket.

### Confronto temporale

{{apply-time-comparison}}

### Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è costituita da due componenti:

* **[!UICONTROL Intervallo]**: granularità della data in base alla quale visualizzare i dati con tendenze. Il grafico e la tabella mostrano i dati aggregati per impostazione predefinita, con l’opzione di espandere la tabella a una vista delle tendenze. Nella vista delle tendenze, gli utenti vengono inseriti nei bucket in base alla frequenza di utilizzo in totale e in ogni intervallo, il che significa che 1 utente può essere contato in bucket diversi in intervalli diversi.
* **[!UICONTROL Data]**: la data di inizio e di fine. Per comodità, sono disponibili intervalli di date continui predefiniti e intervalli personalizzati salvati in precedenza; in alternativa, puoi utilizzare il selettore del calendario per scegliere un intervallo di date fisso.


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
