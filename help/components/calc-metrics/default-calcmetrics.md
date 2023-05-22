---
description: Adobe fornisce varie metriche calcolate che puoi utilizzare. In questa pagina sono elencate tali metriche e i loro utilizzi previsti.
title: Metriche calcolate predefinite
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 2%

---

# Metriche calcolate predefinite

Customer Journey Analytics fornisce varie metriche calcolate per coprire i casi d’uso più comuni. Queste metriche calcolate sono disponibili per impostazione predefinita in Analysis Workspace.

Di seguito è riportato un elenco di ogni metrica calcolata fornita da Adobe, con la relativa funzione prevista e la formula sottostante utilizzata per calcolarla:

>[!NOTE]
>
>Oltre alle metriche calcolate predefinite descritte in questa pagina, è possibile aggiungere ulteriori metriche calcolate a una visualizzazione dati.
>
>È possibile:
> * Aggiungere metriche calcolate predefinite per Streaming Media, come descritto in [Metriche calcolate](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Creare metriche calcolate personalizzate dalle metriche esistenti, come descritto in [Metriche calcolate e metriche calcolate avanzate (derivate)](/help/components/calc-metrics/cm-adv-functions.md).



| Nome metrica calcolata | Funzione | Formula |
|---------|----------|---------|
| Percentuale non recapitate | Il rapporto tra le visite che contenevano esattamente un evento e il numero di visite su quella pagina. Questo può aiutarti a capire quali elementi dimensionali hanno il tasso di mancato recapito più alto o a vedere un tasso di mancato recapito totale aggregato del tuo sito nel tempo. | `[Bounces] / [Entries]` |
| Ricavi / Visitatore | L’importo medio dei ricavi generati da ogni singolo visitatore del sito. | `[Revenue] / [Unique Visitors]` |
| Ordini / Visitatore | Numero medio di ordini o transazioni generati da ogni singolo visitatore del sito | `[Orders] / [Unique Visitors]` |
| Ricavi/visite | L’importo medio dei ricavi generati da una singola visita al sito. | `[Revenue] / [Visits]` |
| Ricavi/Ordine | L&#39;importo medio dei ricavi generati da ogni transazione o ordine completato sul sito. | `[Revenue] / [Orders]` |
| Ordini/Visite | Percentuale di visite al sito che risultano in una transazione completata. | `[Orders] / [Visits]` |
| Visualizzazioni pagina/Visite | Il numero medio di pagine visualizzate da un utente durante una singola visita al sito. | `[Page Views] / [Visits]` |
| Visite/Visitatore | Il numero medio di visite effettuate da un visitatore univoco al sito. | `[Visits] / [Unique Visitors]` |
| Ricarica/Visualizzazioni pagina | Percentuale di visualizzazioni di pagina che hanno portato a un ricaricamento o aggiornamento della pagina. | `[Reloads] / [Page Views]` |
| Percentuale rimbalzo ponderato | Funzione | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Ordina assistenze | Il numero di volte in cui un canale o un’origine ha contribuito al percorso di un cliente per effettuare un acquisto, ma non ha prodotto l’acquisto finale. | `[Orders (Visit Participation)] - [Orders]` |
| Frequenza di uscita | La percentuale di visitatori che abbandonano il sito dopo aver visualizzato una pagina particolare. | `[Exits] / [Visits]` |
| Tasso di ingresso | La percentuale di visitatori che sono entrati nel sito in una determinata pagina rispetto al numero totale di sessioni sul sito. | `[Entries] / [Visits]` |
| Tempo medio sul sito | Il tempo medio trascorso da un visitatore sul sito prima di partire o di allontanarsi. | `[Average Time Spent on Site (Seconds)]` |
| Tempo trascorso/utente (stato) | Il periodo di tempo che il visitatore medio trascorre in un particolare stato mentre è sul sito | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Utenti (dispositivi mobili) | Numero totale di utenti di un’app mobile | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Utenti dell’app | Numero totale di utenti di un’app mobile | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Visualizzazioni stato | Numero di visualizzazioni ai diversi stati o schermate dell’app | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| Azioni | Numero totale di azioni eseguite nell&#39;app | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| Clic sui collegamenti di acquisizione | Il numero di volte in cui le persone fanno clic su un collegamento progettato per indirizzare il traffico verso il sito. | `[Campaign Click-throughs]` |
| Velocità pagina | Il numero di visualizzazioni di pagina aggiuntive generate da un contenuto. Questo può aiutarti a determinare quali contenuti favoriscono un coinvolgimento aggiuntivo. | `[Page Views] / [Visits]` |
| Tasso di conversione | Percentuale di visitatori che hanno intrapreso un’azione desiderata, ad esempio un acquisto. | `[Orders] / [Visits]` |
| Lunghezza media sessione (mobile) | La quantità media di tempo che i visitatori trascorrono sul sito durante una singola sessione. | Vuoto |
| Copertura ID Experience Cloud | La percentuale di visitatori che hanno un ID Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Velocity contenuto | La velocità con cui i nuovi contenuti vengono creati e pubblicati sul sito e la velocità con cui generano coinvolgimento degli utenti. | `[Page Views] / [Visits]` |
| ITP 2.1 Visitatori univoci / Visitatori univoci | La percentuale di visitatori univoci che utilizzano un browser soggetta alle limitazioni dei cookie ITP 2.1. In altre parole, i clienti che non utilizzano un’implementazione CNAME. Questo vale per i clienti che impostano i cookie tramite JavaScript lato client. | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| Visitatori univoci/Visitatori univoci che ritornano dopo 7 giorni | La percentuale di visitatori univoci che ritornano dopo un periodo di 7 o più giorni. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| Visualizzazioni pagina/Visitatore univoco | Il numero medio di pagine visualizzate per ogni visitatore univoco del sito. | `[Page Views] / [Unique Visitors]` |
| Visite / Visitatori | Il numero medio di visite effettuate da un visitatore univoco al sito. | `[Visits] / [Unique Visitors]` |
| Visitatori univoci stimati (ITP 2.1) | Per i visitatori ITP (utenti nei browser Safari), dividi Visitatori univoci per 2 o meno. Questa metrica calcolata presuppone che tu abbia impostato i cookie utilizzando JavaScript lato client (non utilizzando un’implementazione CNAME). Le implementazioni che impostavano i cookie utilizzando JavaScript lato client erano interessate a partire da ITP 2.1. Consulta [Prevenzione intelligente del tracciamento](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) per i dettagli. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| Visualizzazioni di pagina/Visitatori univoci stimati (ITP 2.1) | Il numero medio di pagine visualizzate per Visitatori univoci stimati (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
