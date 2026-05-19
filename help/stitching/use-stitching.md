---
title: Richiedi unione
description: Scopri come richiedere l’unione.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
autotag-review: '2026-05-19T09:25:02.883Z'
TQID: 'https://experienceleague.adobe.com/0A4WNJ6TQDD3QrbupAK7R2sT25Nc-ovCnLFWjIyk0tU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 422
ht-degree: 27%

---

# Richiedere l’unione delle identità


>[!IMPORTANT]
>
>L’unione delle richieste tramite Adobe non è più necessaria e questo metodo è obsoleto. [Abilitare l&#39;unione nell&#39;interfaccia utente Connessioni](use-stitching-ui.md).
>

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
