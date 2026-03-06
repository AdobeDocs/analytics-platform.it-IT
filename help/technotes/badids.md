---
title: ID Customer Journey Analytics non validi
description: Comprendere gli ID non validi (BAVID) in Customer Journey Analytics. Scopri come identificare gli ID non validi nei dati, perché influiscono sulla generazione di rapporti e come indagare e risolvere l’esposizione agli ID non validi nelle connessioni.
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 0%

---


# ID non validi

Questo articolo fornisce informazioni contestuali sugli ID non validi e su come rilevarne la presenza o il rischio di occorrenza nei dati utilizzando Query Service.


>[!INFO]
>
>Nell&#39;interfaccia di Customer Journey Analytics gli ID non validi vengono indicati anche come BAVID (provenienti da [BAVID di Analytics](https://experienceleague.adobe.com/it/docs/experience-cloud-kcs/kbarticles/ka-16444)).
>

## Definizione

In Customer Journey Analytics, come parte di tutti i dati definiti in una connessione, un Bad ID è un identificatore:

* con un valore ID specifico che ha origine
   * da un campo ID persona (set di dati non uniti), **o**
   * da un campo ID persistente o ID persona (set di dati abilitati per l’unione),

  **e**
* si trova su più di un milione (1.000.000) eventi nei dati di connessione (conteggiati per tutti i set di dati all’interno della connessione), entro un mese.

Quando un valore ID è contrassegnato come ID errato, tutti gli eventi futuri che contengono tale valore ID vengono eliminati dai dati della connessione e non vengono visualizzati nel reporting.

### Esempio

Un esempio di uno scenario con ID non validi è che nel campo ID persona siano presenti valori personalizzati o segnaposto (ad esempio, `undefined`per il traffico anonimo). Per un set di dati abilitato all’unione, questa situazione può avere un impatto ancora maggiore sui dati di reporting, in quanto la qualità dell’unione ne risente molto probabilmente. Per risolvere questo problema, potrebbe essere necessario cancellare e riabilitare la configurazione dell’unione, inclusa l’eliminazione dei dati storici dei set di dati nella connessione.


## Metriche

L&#39;interfaccia di connessione di Customer Journey Analytics offre **[!UICONTROL informazioni sulle metriche ID non validi]** in diverse posizioni nell&#39;interfaccia.

* Puoi visualizzare **[!UICONTROL ID non validi]** (o **[!UICONTROL BAVID]**) come possibili motivi per ignorare i record nella finestra di dialogo **[!UICONTROL Controlla dettagli ignorati]**. Utilizza **[!UICONTROL Controlla dettagli]** (se disponibile) sotto **[!UICONTROL Record ignorati]** nella [schermata di dettaglio di una connessione](/help/connections/create-connection.md).
* Per un set di dati abilitato per l&#39;unione, l&#39;[**[!UICONTROL anteprima del set di dati]**](/help/stitching/use-stitching-ui.md#bad-ids) mostra **[!UICONTROL ID non validi]** come parte delle **[!UICONTROL metriche di unione]**. Questa metrica può aiutarti a identificare possibili casi di ID non validi. Tuttavia, tieni presente che questa metrica viene calcolata in base a un set limitato di dati.

Consulta [Esposizione di ID non validi](#bad-ids-exposure) per identificare la presenza di ID non validi per un set di dati che intendi utilizzare all&#39;interno di una connessione (indipendentemente dal fatto che sia abilitata o meno l&#39;unione).


## Esposizione

Per analizzare l’esposizione di ID non validi per un determinato campo di set di dati, è consigliabile eseguire la seguente query in Experience Platform Query Service. Controlla i primi valori ID restituiti per vedere se ci sono candidati per ID non validi. Tieni presente che la [definizione ID non valido](#definition) prende in considerazione tutti i set di dati all&#39;interno della connessione.


### Identificare (rischiare di) ID non validi all’interno di un campo

Puoi utilizzare Experience Platform Query per gestire al fine di identificare il potenziale rischio di ID non validi all’interno di un campo.

La query seguente restituisce i primi 20 valori ID da un campo. In ordine decrescente in base al numero di eventi totali. E dove ogni valore viene rilevato entro un determinato intervallo (ad esempio entro gli ultimi 30 giorni).

Eseguire questa query per un campo ID persona specifico da analizzare. Per un set di dati che deve essere unito, puoi anche eseguire la query per un campo ID persistente.

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

Nella query, sostituisci `INSERT FIELD HERE` a seconda del tipo di campo esaminato per gli ID non validi:

* `full.field.path.from.XDM.schema` (per i campi stringa definiti nello schema XDM)
* `identityMap['namespace_value'][0].id` (per i campi definiti con `namespace_value` in `identityMap`)

Controlla i risultati per vedere se ci sono valori ID problematici. Come valori personalizzati o segnaposto, o valori con occorrenza elevata che arriva o potrebbe avvicinarsi a 1 milione in un mese a livello di dati della connessione.
Anche se l’implementazione è ancora in fase di sviluppo, è necessario valutare il rischio di presenza di ID non validi una volta che la configurazione è stabile e pronta per la produzione.
