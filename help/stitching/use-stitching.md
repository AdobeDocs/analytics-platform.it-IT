---
title: Utilizzare l’unione
description: Come utilizzare l’unione
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 5e25cb4d974ab85cca3aa2bb777675e12f63038b
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 9%

---

# Utilizzare l’unione

Una volta che l&#39;organizzazione soddisfa tutti i [prerequisiti](#prerequisites) e comprende le [limitazioni](#limitations) comuni e le limitazioni specifiche del metodo di unione ([basate sui campi](#limitations-1) e [basate sui grafi](#limitations-2)), puoi seguire questi passaggi per iniziare a utilizzare l&#39;unione in Customer Journey Analytics.

## Seleziona opzioni

Il pacchetto di Customer Journey Analytics a cui hai diritto determina i metodi di unione disponibili, le opzioni per la durata della retrocompilazione iniziale, l’intervallo di lookback, la frequenza di ripetizione e il numero massimo di set di dati consentiti per l’unione. Per ulteriori dettagli, consulta la [descrizione del prodotto del Customer Journey Analytics](https://helpx.adobe.com/it/legal/product-descriptions/customer-journey-analytics.html). Decidi le opzioni disponibili prima di richiedere assistenza.

| | Customer Journey Analytics<br/>Seleziona | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Metodi di unione disponibili | <li>Unione basata sui campi</li> | <li>Unione basata sui campi</li><li>Unione basata su grafo</li> | <li>Unione basata sui campi</li><li>Unione basata su grafo</li> |
| Durata retrocompilazione unione una tantum | 13 mesi | 13 mesi | 25 mesi |
| Intervallo di lookback e frequenza di ripetizione | <li>1 giorno, ogni giorno</li><li>fino a 7 giorni, settimanalmente</li> | <li>1 giorno, ogni giorno</li><li>fino a 14 giorni, settimanalmente</li> | <li>1 giorno, ogni giorno</li><li>fino a 30 giorni, settimanalmente</li> |
| Numero massimo di set di dati consentiti per l’unione | 5 | 10 | 50 |

## Richiedi supporto

1. Contatta l’Assistenza clienti di Adobe con le seguenti informazioni:

   - Richiesta per abilitare l’unione.
   - ID del set di dati per il set di dati da reimpostare.
   - Il nome della colonna (percorso identità e spazio dei nomi) dell’ID persistente per il set di dati desiderato (l’identificatore visualizzato su ogni riga).
   - Per l’unione basata sui campi, il nome della colonna dell’ID transitorio per il set di dati desiderato (l’identificatore della persona, che funge anche da collegamento tra i set di dati nel contesto di una connessione). Per l’unione basata su grafico, lo spazio dei nomi delle identità da utilizzare per eseguire query sul grafo delle identità.
   - Preferenza di intervallo di lookback e frequenza di ripetizione. Visualizza il pacchetto di Customer Journey Analytics per le [opzioni](#options) disponibili.
   - Nome della sandbox.


2. L’Assistenza clienti Adobe collabora con il team di progettazione Adobe per abilitare l’unione dopo la ricezione della richiesta. Una volta abilitato, in Adobe Experience Platform viene visualizzato un nuovo set di dati reimpostato contenente una nuova colonna ID unita. L’Assistenza clienti di Adobe può fornire l’ID del nuovo set di dati.

3. Quando è attivato per la prima volta, Adobe fornisce la retrocompilazione dei dati uniti. Visualizza il pacchetto di Customer Journey Analytics per l&#39;[opzione](#options) disponibile.

4. Se desideri utilizzare il nuovo set di dati uniti in un&#39;analisi cross-channel, devi aggiungere il nuovo set di dati uniti a una [connessione](../connections/overview.md) nel Customer Journey Analytics. Quindi aggiungi tutti gli altri set di dati necessari per l’analisi cross-channel e seleziona l’ID persona corretto per ciascun set di dati.

5. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) in base alla connessione.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una volta configurata la visualizzazione dati, puoi eseguire l’analisi dei rapporti di Customer Journey Analytics su canali e dispositivi diversi.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


