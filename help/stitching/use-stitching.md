---
title: Richiedi unione
description: Scopri come richiedere l’unione.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# Richiedere l’unione delle identità


>[!IMPORTANT]
>
>L’unione delle richieste tramite Adobe non è più necessaria e questo metodo è obsoleto. [Abilitare l&#39;unione nell&#39;interfaccia utente Connessioni](use-stitching-ui.md).
>

Quando l&#39;organizzazione soddisfa [prerequisiti](overview.md#prerequisites) generici, comprende [limitazioni](overview.md#limitations) comuni e i prerequisiti e le limitazioni specifici per il metodo di unione ([basati sui campi](fbs.md) e [basati sui grafi](gbs.md)), puoi seguire questi passaggi per richiedere e iniziare a utilizzare l&#39;unione in Customer Journey Analytics.

## Seleziona opzioni

Il pacchetto Customer Journey Analytics a cui hai diritto determina i metodi di unione disponibili, le opzioni per la durata della retrocompilazione iniziale, l’intervallo di lookback, la frequenza di ripetizione e il numero massimo di set di dati consentiti per l’unione. Per ulteriori dettagli, consulta la [descrizione del prodotto Customer Journey Analytics](https://helpx.adobe.com/it/legal/product-descriptions/customer-journey-analytics.html). Decidi le opzioni disponibili prima di richiedere assistenza.

| | Customer Journey Analytics<br/>Seleziona | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Metodi di unione disponibili | Unione delle identità basata sui campi | Unione basata sui campi<br/>Unione basata sui grafici | Unione basata sui campi<br>Unione basata sui grafici</li> |
| Durata retrocompilazione unione una tantum | 13 mesi | 13 mesi | 25 mesi |
| Intervallo di lookback e frequenza di ripetizione | 1 giorno, ogni giorno<br/>fino a 7 giorni, settimanalmente | 1 giorno, ogni giorno<br/>fino a 14 giorni, settimanalmente | 1 giorno, ogni giorno<br/>fino a 30 giorni, settimanalmente |
| Numero massimo di set di dati consentiti per l’unione | 5 | 15 | 50 |

## Richiedi supporto

1. Contatta l’Assistenza clienti di Adobe con le seguenti informazioni:

   - Richiesta per abilitare l’unione.
   - ID del set di dati per il set di dati da reimpostare.
   - Il nome della colonna (percorso identità e spazio dei nomi) dell’ID persistente per il set di dati desiderato (l’identificatore visualizzato su ogni riga).
   - Se il set di dati supporta `identityMap`:
      - Per l’unione basata sui campi, specifica lo spazio dei nomi per gli ID persistente e persona.
      - Per l’unione basata su grafo, specifica lo spazio dei nomi per l’ID persistente e lo spazio dei nomi delle identità da utilizzare per eseguire query sul grafo delle identità.
   - Se il set di dati non supporta `identityMap`:
      - Per l’unione basata sui campi, il nome della colonna dell’ID persona per il set di dati desiderato (l’identificatore della persona, che funge anche da collegamento tra i set di dati nel contesto di una connessione).
      - Per l’unione basata su grafico, lo spazio dei nomi delle identità che desideri utilizzare per eseguire query sul grafo delle identità.
   - Preferenza di intervallo di lookback e frequenza di ripetizione. Consulta il tuo pacchetto Customer Journey Analytics per le [opzioni](#options) disponibili.
   - Nome della sandbox.


2. L’Assistenza clienti Adobe collabora con i tecnici Adobe per abilitare l’unione dopo aver ricevuto la richiesta. Una volta abilitato, in Adobe Experience Platform viene visualizzato un set di dati reimpostato contenente una colonna ID unita. L’Assistenza clienti Adobe può fornire l’ID del nuovo set di dati.
3. Quando è attivato per la prima volta, Adobe fornisce la retrocompilazione dei dati uniti. Visualizza il tuo pacchetto Customer Journey Analytics per l&#39;[opzione](#options) disponibile.

4. Se desideri utilizzare il set di dati uniti in un&#39;analisi cross-channel, devi aggiungere il set di dati uniti a una [connessione](../connections/overview.md) in Customer Journey Analytics. Quindi aggiungi tutti gli altri set di dati necessari per l’analisi cross-channel e seleziona l’ID persona corretto per ciascun set di dati.

5. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) in base alla connessione.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una volta configurata la visualizzazione dati, puoi eseguire l’analisi dei rapporti di Customer Journey Analytics tra canali e dispositivi.

## Limitazioni

- Applica eventuali modifiche apportate allo schema del set di dati evento di origine anche al nuovo schema del set di dati con unione delle identità.

- Se rimuovi il set di dati di origine, il set di dati con unione delle identità non può più essere elaborato e viene rimosso dal sistema.

- Le etichette di utilizzo dei dati non vengono propagate automaticamente allo schema del set di dati con unione delle identità. Se hai applicato delle etichette di utilizzo dei dati allo schema del set di dati di origine, devi applicarle manualmente anche allo schema del set di dati con unione delle identità. Per ulteriori informazioni, consulta [Gestione delle etichette di utilizzo dei dati in Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/data-governance/labels/overview).
