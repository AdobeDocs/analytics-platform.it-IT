---
title: Dispositivi condivisi
description: Spiegazione di come gestire i dispositivi condivisi utilizzando l’unione e altre tecniche.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: f45a457d251767634e28984d7c75158dac6e51e8
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 3%

---

# Dispositivi condivisi

Questo articolo fornisce contesto sui dispositivi condivisi, come gestire e mitigare i dati provenienti da dispositivi condivisi utilizzando [stitching](/help/stitching/overview.md) e comprendere l&#39;esposizione dei dispositivi condivisi nei dati utilizzando Query Service.

## Che cos&#39;è un dispositivo condiviso?

Un dispositivo condiviso è un dispositivo utilizzato da più persone. Scenari comuni sono dispositivi come tablet, dispositivi utilizzati nei chioschi o attrezzature informatiche condivise dagli agenti in un call center.

Quando due persone utilizzano lo stesso dispositivo ed entrambe effettuano un acquisto autenticato, i dati dell’evento di esempio potrebbero essere simili ai seguenti:

| Evento | Marca temporale | Nome pagina | ID dispositivo | E-mail |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | Pagina Home | `1234` | |
| 2 | 2023-05-12 12:02 | Pagina prodotto | `1234` | |
| 3 | 2023-05-12 12:03 | Ordine completato | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | Pagina prodotto | `1234` | |
| 5 | 2023-05-12 12:08 | Ordine completato | `1234` | `cassidy@a.com` |

Come puoi vedere da questa tabella, una volta che l’autenticazione si verifica sugli eventi 3 e 5, inizia a formarsi un collegamento tra un ID dispositivo e un ID persona. Per comprendere l’impatto di qualsiasi attività di marketing a livello di persona, questi eventi non autenticati devono essere attribuiti alla persona giusta.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Migliorare l’analisi incentrata sulla persona

Il processo di unione risolve questo problema di attribuzione aggiungendo l’identificatore della persona selezionata (nei dati di esempio, l’e-mail) agli eventi in cui tale identificatore non esiste. L’unione sfrutta una mappatura tra gli ID dispositivo e gli ID persona per garantire che sia il traffico autenticato che quello non autenticato possano essere utilizzati nell’analisi, mantenendola incentrata sulla persona. Per ulteriori informazioni, vedere [Unione](/help/stitching/overview.md).

Con l’unione è possibile attribuire i dati dei dispositivi condivisi utilizzando l’attribuzione ultima autenticazione o suddivisione dispositivo. Tutti i tentativi di unire eventi non autenticati a un utente noto non sono deterministici.


### Attribuzione ultima autenticazione

Ultima autenticazione attribuisce tutte le attività sconosciute da un dispositivo condiviso all’ultimo utente autenticato. Il servizio Experience Platform Identity crea il grafico in base all’attribuzione dell’ultima autenticazione e, come tale, viene utilizzato nell’unione basata su grafico. Per ulteriori informazioni, vedere [Regole di collegamento del grafico delle identità](https://experienceleague.adobe.com/it/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details).

Quando nell’unione viene utilizzata l’attribuzione last-auth, gli ID uniti vengono risolti come mostrato nella tabella seguente.

| Marca temporale | Nome pagina | ID dispositivo | E-mail | ID unione |
|---|---|---|---|---|
| 2023-05-12 12:01 | Pagina Home | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Pagina prodotto | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Ordine completato | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Pagina prodotto | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Ordine completato | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Pagina Home | `1234` | | `cassidy@a.com` |


### Device-split

L’attività anonima degli attributi di suddivisione del dispositivo da un dispositivo condiviso all’utente noto più recente che ha cercato nel passato. La suddivisione del dispositivo è attualmente utilizzata nell’unione basata sui campi.

Quando nell’unione viene utilizzata l’attribuzione device-split, gli ID uniti vengono risolti come mostrato nella tabella seguente.

| Marca temporale | Nome pagina | ID dispositivo | E-mail | ID unione |
|---|---|---|---|---|
| 2023-05-12 12:01 | Pagina Home | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Pagina prodotto | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Ordine completato | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Pagina prodotto | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | Ordine completato | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Pagina Home | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`| 
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` | 
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` | 
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## Esposizione dispositivo condiviso

Considera diversi fattori per comprendere correttamente la diffusione dei dispositivi condivisi nella tua organizzazione. Inoltre, comprendere il contributo complessivo degli eventi provenienti da dispositivi condivisi può aiutarti a comprendere l’impatto sui dati generali degli eventi utilizzati per l’analisi.

Per comprendere l’esposizione del dispositivo condiviso, puoi considerare l’esecuzione delle seguenti query.

1. **Identificare i dispositivi condivisi**

   Per comprendere il numero di dispositivi condivisi, esegui una query che conta gli ID dispositivo con due o più ID persona associati. Questo aiuta a identificare i dispositivi utilizzati da più individui.

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **Attribuzione di eventi a dispositivi condivisi**

   Per i dispositivi condivisi identificati, determina quanti eventi sul totale possono essere attribuiti a questi dispositivi. Questa attribuzione fornisce informazioni sull’impatto che i dispositivi condivisi hanno sui tuoi dati e sulle implicazioni per l’analisi.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **Identifica eventi anonimi su dispositivi condivisi**

   Tra gli eventi attribuiti ai dispositivi condivisi, identifica quanti mancano di un ID persona, indicando eventi anonimi. L’algoritmo scelto (ad esempio last-auth, device-split o ECID-reset) per migliorare la qualità dei dati influisce su questi eventi anonimi.

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **Calcola l&#39;esposizione da errata classificazione degli eventi**

   Infine, valutare l’esposizione che ogni cliente potrebbe affrontare a causa di errori di classificazione degli eventi. Calcola la percentuale di eventi anonimi rispetto al totale degli eventi per ciascun dispositivo condiviso. Questo aiuta a comprendere il potenziale impatto sulla precisione dei dati dei clienti.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
