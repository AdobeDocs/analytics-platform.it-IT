---
title: Dispositivi condivisi
description: Spiegazione di come gestire i dispositivi condivisi utilizzando l’unione e altre tecniche.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hide-from-toc: true
role: Admin
source-git-commit: f17d2ebdf9a45ebb3a4e923a34c4b9b3d629f038
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 4%

---

# Dispositivi condivisi

Questo articolo fornisce contesto sui dispositivi condivisi, come gestire e mitigare i dati provenienti da dispositivi condivisi utilizzando l’unione e comprendere l’esposizione dei dispositivi condivisi nei dati utilizzando Query Service.

## Che cos&#39;è un dispositivo condiviso?

Un dispositivo condiviso è un dispositivo utilizzato da più persone. Scenari comuni sono dispositivi come tablet, dispositivi utilizzati nei chioschi o attrezzature informatiche condivise dagli agenti in un call center.

Quando due persone utilizzano lo stesso dispositivo ed entrambe effettuano un acquisto, i dati dell’evento di esempio potrebbero essere simili ai seguenti:

| Marca temporale | Nome pagina | ID dispositivo | E-mail |
|---|---|---|---|
| 2023-05-12 12:01 | Pagina Home | 1234 | |
| 2023-05-12 12:02 | Pagina prodotto | 1234 | |
| 2023-05-12 12:03 | Ordine completato | 1234 | <ryan@a.com> |
| 2023-05-12 12:07 | Pagina prodotto | 1234 | |
| 2023-05-12 12:08 | Ordine completato | 1234 | <cassidy@a.com> |

Gli eventi di successo dell’ordine (acquisto) assegnano i dati con precisione all’e-mail corretta. Il modo in cui questa assegnazione influisce sull&#39;analisi dipende dal modo in cui questa viene eseguita:

- Approccio incentrato sul dispositivo: analisi eseguita utilizzando l’ID dispositivo. Con questo approccio, i dati autenticati e non autenticati vengono inclusi nell’analisi. Tuttavia, questo approccio non consente un’analisi più basata sulle persone.
- Approccio incentrato sulla persona: analisi eseguita utilizzando l’indirizzo e-mail o un altro identificatore della persona. Con questo approccio, nell’analisi vengono inclusi solo gli eventi autenticati. Questo approccio non offre un quadro completo del percorso di clienti, inclusa l&#39;acquisizione

## Migliorare l’analisi incentrata sulla persona

Per migliorare l’analisi incentrata sulla persona dei dispositivi condivisi, puoi utilizzare le unioni o implementare la funzionalità di ripristino ECID. Entrambi gli approcci sono discussi più dettagliatamente nelle sezioni seguenti.

### Unione

Il processo di unione risolve il problema dell’approccio incentrato sulla persona. L’unione aggiunge l’identificatore della persona selezionata (nei dati di esempio, l’e-mail) agli eventi in cui tale identificatore non esiste. L’unione sfrutta una mappatura tra gli ID dispositivo e gli ID persona per garantire che sia il traffico autenticato che quello non autenticato possano essere utilizzati nell’analisi, mantenendola incentrata sulla persona. Per ulteriori informazioni, vedere [Unione](/help/stitching/overview.md).

Con l’unione è possibile attribuire i dati dei dispositivi condivisi utilizzando l’attribuzione ultima autenticazione o suddivisione dispositivo. Tuttavia, le modifiche di implementazione tramite il ripristino ECID possono riguardare anche i dispositivi condivisi.


#### Attribuzione ultima autenticazione

Ultima autenticazione attribuisce tutte le attività sconosciute da un dispositivo condiviso all’ultimo utente autenticato. In Audience Manager viene utilizzato Last-auth, l’approccio preferito per i casi di utilizzo di Real-Time Customer Data Profile. Il servizio Experience Platform Identity crea il grafico in base all’attribuzione dell’ultima autenticazione e, come tale, viene utilizzato nell’unione basata su grafico. Per ulteriori informazioni, vedere [Panoramica delle regole di collegamento del grafico delle identità](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview).

Quando si utilizza l’attribuzione last-auth nell’unione, gli ID uniti vengono risolti come mostrato nella tabella seguente.

| Marca temporale | Nome pagina | ID dispositivo | E-mail | ID unione |
|---|---|---|---|---|
| 2023-05-12 12:01 | Pagina Home | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:02 | Pagina prodotto | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:03 | Ordine completato | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 12:07 | Pagina prodotto | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:08 | Ordine completato | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Pagina Home | 1234 | | <cassidy@a.com> |


#### Device-split

L’attività anonima degli attributi di suddivisione del dispositivo da un dispositivo condiviso all’utente nelle immediate vicinanze dell’attività anonima. La suddivisione del dispositivo è attualmente utilizzata nell’unione basata sui campi. La suddivisione dei dispositivi è l’approccio preferito per i casi di utilizzo analitici, in quanto attribuisce il merito per l’attività non autenticata e autenticata alla persona nota più vicina. La suddivisione del dispositivo è attualmente utilizzata nell’unione basata sui campi.

Quando si utilizza l’attribuzione device-split nell’unione, gli ID uniti vengono risolti come mostrato nella tabella seguente.

| Marca temporale | Nome pagina | ID dispositivo | E-mail | ID unione |
|---|---|---|---|---|
| 2023-05-12 12:01 | Pagina Home | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | Pagina prodotto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | Ordine completato | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | Pagina prodotto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:08 | Ordine completato | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Pagina Home | 1234 | | <cassidy@a.com> |


### Reimpostazione ECID

Come suggerisce il nome, il ripristino ECID implementa una funzionalità che ripristina l’ECID su un trigger predeterminato, nella maggior parte dei casi un evento di accesso o disconnessione. Con questa implementazione, un singolo dispositivo ottiene un nuovo ECID ogni volta che il trigger predeterminato si attiva. In sostanza, questo ripristino costringe il dispositivo a diventare un *nuovo dispositivo* più e più volte dal punto di vista dei dati. Il ripristino ECID consente inoltre di evitare che i dispositivi condivisi vengano visualizzati nei dati. Non sono necessari algoritmi aggiuntivi, ma è tua responsabilità implementare il segnale di ripristino ECID come parte dell’implementazione della raccolta dati di Adobe.


Quando si utilizza il ripristino ECID, gli ID uniti vengono risolti come mostrato nella tabella seguente.

| Marca temporale | Nome pagina | ID dispositivo | E-mail | ID unione |
|---|---|---|---|---|
| 2023-05-12 12:01 | Pagina Home | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | Pagina prodotto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | Ordine completato | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | Pagina prodotto | 5678 | | <cassidy@a.com> |
| 2023-05-12 12:08 | Ordine completato | 5678 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Pagina Home | 5678 | | <cassidy@a.com> |

## Esposizione dispositivo condiviso

Considera diversi fattori per comprendere correttamente la diffusione dei dispositivi condivisi nella tua organizzazione. Inoltre, comprendere il contributo complessivo degli eventi provenienti da dispositivi condivisi può aiutarti a comprendere l’impatto sui dati generali degli eventi utilizzati per l’analisi.

Per comprendere l’esposizione del dispositivo condiviso, puoi considerare l’esecuzione delle seguenti query.

1. Comprendere il numero di dispositivi condivisi. Puoi utilizzare una query che conta gli ID dispositivo a cui sono associati due o più ID persona. Un esempio di query potrebbe essere simile al seguente:

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


2. Per i dispositivi condivisi, risultanti dalla prima query, è necessario comprendere quanti eventi del totale degli eventi possono essere attribuiti a tali dispositivi condivisi. Questa attribuzione offre un’idea migliore dell’impatto dei dispositivi condivisi sui dati e dell’impatto durante l’analisi. Un esempio di query potrebbe essere simile al seguente:

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

3. Per gli eventi attribuiti ai dispositivi condivisi (il risultato della seconda query), è necessario comprendere quanti di questi eventi NON hanno un ID persona. In caso contrario, quanti eventi del dispositivo condiviso sono eventi anonimi. In ultima analisi, l’algoritmo (last-auth, device-split, ECID-reset) scelto per migliorare la qualità dei dati influisce su questi eventi anonimi del dispositivo condiviso. Un esempio di query potrebbe essere simile al seguente:

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

4. Infine, è importante comprendere l&#39;esposizione che ogni cliente potrebbe avere a causa di errori di classificazione degli eventi. Per ottenere questa esposizione, devi calcolare, per ogni dispositivo condiviso, la percentuale di eventi anonimi relativi al numero totale di eventi. Un esempio di query potrebbe essere simile al seguente:

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


