---
title: Vista frizione
description: Confronta i tassi di conversione tra passaggi.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: 63dd68d31a9f2b907419fa660904f1dfdacaa0b8
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 2%

---

# [!UICONTROL Friction] visualizza

Il **[!UICONTROL Friction]** visualizza fornisce una rappresentazione visiva di un percorso di utenti critico nel prodotto. L’asse orizzontale rappresenta ogni passaggio che un utente deve attraversare. L’asse verticale rappresenta la percentuale di utenti o sessioni in ogni passaggio. Tutti i passaggi devono essere eseguiti nell’ordine finale, ma possono essere eseguiti in qualsiasi momento all’interno dell’intervallo di reporting.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on)

## Casi d’uso

I casi di utilizzo per questo tipo di visualizzazione includono:

* **Analisi della conversione**: puoi analizzare le conversioni in ogni fase del funnel, ad esempio un checkout retail, la registrazione dell’account, il flusso di abbonamento o altri percorsi critici per la tua esperienza di prodotto. Monitorando il numero di utenti che avanzano da un passaggio all’altro, puoi identificare i colli di bottiglia con tassi di conversione insoliti o indesiderati. Queste informazioni sono utili per capire dove è possibile migliorare il percorso di prodotti per ottenere risultati immediati.
* **Analisi della sperimentazione**: puoi confrontare i tassi di conversione tra un funnel con passaggi o passaggi opzionali in cui viene eseguito un esperimento A/B. Queste informazioni possono aiutarti a determinare quale variante del funnel porta al tasso di conversione più alto, in modo da poter incoraggiare più utenti lungo quel percorso.
* **Ottimizzazione dell’onboarding**: ottimizza il processo di onboarding del prodotto esaminando il comportamento degli utenti in relazione agli eventi chiave. Puoi identificare i passaggi con cui gli utenti hanno difficoltà o che non riescono a completare.
* **Adozione e coinvolgimento delle funzioni**: scopri come gli utenti interagiscono con funzioni specifiche del tuo prodotto. L’analisi della progressione degli utenti attraverso i passaggi relativi alle funzioni consente di visualizzare i tassi di adozione e identificare le aree in cui gli utenti potrebbero sottoutilizzare determinate funzioni. Puoi quindi utilizzare queste informazioni per concentrarti sui miglioramenti delle funzioni per aumentare i tassi di adozione.
* **Efficacia del canale di marketing**: misura l’efficacia dei canali di marketing. Puoi creare un segmento che si concentra sugli utenti che hanno interagito con diversi canali di marketing (ad esempio ricerca a pagamento, visualizzazione, ricerca naturale o diretta), quindi confrontare i loro percorsi per vedere quale canale porta ai migliori risultati di prodotto.

## Barra delle query

La barra delle query consente di configurare i seguenti componenti:

* **[!UICONTROL View]**: passa da questo tipo di visualizzazione a [Tendenze di conversione](conversion-trends.md).
* **[!UICONTROL Steps]**: i punti di contatto dell’evento di cui desideri tenere traccia. Ogni barra del grafico rappresenta un passo. Puoi includere fino a dieci passaggi.
   * [!UICONTROL Compare]: ogni passaggio fornisce un’opzione per confrontare più eventi in un singolo passaggio funnel, creando un &quot;funnel fork&quot;. Questa funzione consente di confrontare l&#39;attrito di due percorsi uno accanto all&#39;altro senza creare due analisi separate. È utile quando sono presenti opzioni di passaggio o quando un esperimento A/B viene eseguito all’interno dell’imbuto.
* **[!UICONTROL Counted as]**: ambito che desideri applicare al funnel. Le opzioni includono [!UICONTROL Sessions] e [!UICONTROL Users].
   * [!UICONTROL Sessions]: per essere conteggiati, tutti i passaggi devono avvenire nella stessa sessione.
   * [!UICONTROL Users]: per essere conteggiati, tutti i passaggi devono avvenire nell’intervallo di reporting selezionato.
* **[!UICONTROL Segments]**: i segmenti in cui desideri confrontare il funnel. Ogni segmento selezionato suddivide ogni passaggio in più barre. Ogni colore rappresenta un segmento diverso. Puoi includere fino a tre segmenti.

## Impostazioni grafico

La vista Attrito offre le seguenti impostazioni del grafico, che possono essere regolate nel menu sopra il grafico:

* **[!UICONTROL Chart type]**: tipo di visualizzazione che desideri utilizzare. Le opzioni includono [!UICONTROL Steps].
* **[!UICONTROL Conversion from]**: determina il calcolo della percentuale da un passaggio all’altro. Le opzioni includono il calcolo della conversione dal [!UICONTROL First step] o [!UICONTROL Previous step].

## Confronto temporale

{{apply-time-comparison}}

![Confronto del tempo di attrito](../assets/friction-compare.png){style="border:1px solid gray"}

## Intervallo date

L’intervallo di date desiderato per l’analisi. Questa impostazione è composta da due componenti:

* **[!UICONTROL Interval]**: granularità della data in base alla quale visualizzare i dati con tendenze. Questa impostazione non influisce sulle viste senza tendenze, ad esempio Attrito.
* **[!UICONTROL Date]**: data di inizio e fine. Sono disponibili predefiniti per intervalli di date continui e intervalli personalizzati salvati in precedenza, oppure puoi utilizzare il selettore calendario per scegliere un intervallo di date fisso.
