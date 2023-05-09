---
description: Adobe fornisce varie metriche calcolate utilizzabili. In questa pagina sono elencate le metriche e gli usi previsti.
title: Metriche calcolate predefinite
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 2%

---

# Metriche calcolate predefinite

Customer Journey Analytics fornisce varie metriche calcolate per i casi d’uso più comuni. Queste metriche calcolate sono disponibili per impostazione predefinita in Analysis Workspace.

Di seguito è riportato un elenco di ciascuna metrica calcolata fornita dall’Adobe, con la relativa funzione prevista e la formula sottostante utilizzata per calcolarla:

>[!NOTE]
>
>Oltre alle metriche calcolate predefinite descritte in questa pagina, puoi aggiungere anche metriche calcolate aggiuntive a una visualizzazione dati.
>
>È possibile:
> * Aggiungi metriche calcolate predefinite per gli elementi multimediali in streaming, come descritto in [Metriche calcolate](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Crea metriche calcolate personalizzate dalle metriche esistenti, come descritto in [Metriche calcolate e metriche calcolate avanzate (derivate)](/help/components/calc-metrics/cm-adv-functions.md).



| Nome della metrica calcolata | Funzione | Formula |
|---------|----------|---------|
| Percentuale non recapitate | Il rapporto tra le visite che contenevano esattamente un hit rispetto al numero di visite in quella pagina. Questo può aiutarti a capire quali elementi dimensionali hanno il tasso di mancato recapito più alto, o a vedere un tasso di mancato recapito totale aggregato del sito nel tempo. | `[Bounces] / [Entries]` |
| Entrate/Visitatore | La quantità media di ricavi generati da ogni singolo visitatore del sito. | `[Revenue] / [Unique Visitors]` |
| Ordini / Visitatore | Numero medio di ordini o transazioni generati da ogni singolo visitatore del sito | `[Orders] / [Unique Visitors]` |
| Entrate / Visite | Importo medio dei ricavi generati da una singola visita al sito. | `[Revenue] / [Visits]` |
| Ricavi / Ordine | Importo medio dei ricavi generati da ogni transazione o ordine completato sul sito. | `[Revenue] / [Orders]` |
| Ordini / Visite | Percentuale di visite al sito che determinano una transazione completata. | `[Orders] / [Visits]` |
| Visualizzazioni pagina/Visite | Il numero medio di pagine visualizzate da un utente durante una singola visita al sito. | `[Page Views] / [Visits]` |
| Visite / Visitatore | Il numero medio di visite effettuate al sito da un visitatore univoco. | `[Visits] / [Unique Visitors]` |
| Ricarica / Pageviews | La percentuale di visualizzazioni di pagina che ha determinato il ricaricamento o l’aggiornamento della pagina. | `[Reloads] / [Page Views]` |
| Frequenza rimbalzo ponderato | Funzione | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Ordina assistenti | Il numero di volte in cui un canale o una fonte ha contribuito al percorso di un cliente per effettuare un acquisto, ma non ha portato all&#39;acquisto finale. | `[Orders (Visit Participation)] - [Orders]` |
| Tasso di uscita | La percentuale di visitatori che lasciano il sito dopo aver visualizzato una pagina specifica. | `[Exits] / [Visits]` |
| Tasso di ingresso | La percentuale di visitatori che sono entrati nel sito in una determinata pagina, rispetto al numero totale di sessioni sul sito. | `[Entries] / [Visits]` |
| Tempo medio sul sito | Il tempo medio trascorso da un visitatore sul sito prima di partire o allontanarsi. | `[Average Time Spent on Site (Seconds)]` |
| Tempo trascorso/utente (stato) | Il periodo di tempo che il visitatore medio trascorre in un determinato stato mentre si trova sul sito | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Utenti (dispositivi mobili) | Numero totale di utenti di un’app mobile | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Utenti app | Numero totale di utenti di un’app mobile | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Visualizzazioni di stato | Il numero di visualizzazioni per diversi stati o schermate dell&#39;app | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| Azioni | Numero totale di azioni eseguite nell’app | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| Clic sui collegamenti di acquisizione | Il numero di volte in cui le persone fanno clic su un collegamento progettato per indirizzare il traffico verso il sito. | `[Campaign Click-throughs]` |
| Velocity pagina | Il numero di visualizzazioni di pagina aggiuntive generate da una parte del contenuto. Questo consente di determinare quali contenuti generano ulteriore coinvolgimento. | `[Page Views] / [Visits]` |
| Tasso di conversione | La percentuale di visitatori che hanno eseguito un’azione desiderata, ad esempio un acquisto. | `[Orders] / [Visits]` |
| Lunghezza media della sessione (mobile) | La quantità media di tempo che i visitatori trascorrono sul sito durante una singola sessione. | Vuoto |
| Copertura ID Experience Cloud | La percentuale di visitatori con un ID Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Velocity contenuto | Velocità di creazione e pubblicazione dei nuovi contenuti sul sito e velocità di generazione del coinvolgimento degli utenti. | `[Page Views] / [Visits]` |
| ITP 2.1 Visitatori unici / Visitatori unici | La percentuale di visitatori unici che utilizzano un browser interessato dalle limitazioni dei cookie ITP 2.1. In altre parole, i clienti che non utilizzano un’implementazione CNAME. (Questo vale per i clienti che impostano i cookie tramite JavaScript lato client.) | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| Visitatori unici / Visitatori unici che ritornano dopo 7 giorni | La percentuale di visitatori unici che ritornano dopo un periodo di 7 o più giorni. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| Visualizzazioni pagina / Visitatore univoco | Il numero medio di pagine visualizzate per ogni visitatore univoco del sito. | `[Page Views] / [Unique Visitors]` |
| Visite / Visitatori | Il numero medio di visite che un visitatore univoco effettua al sito . | `[Visits] / [Unique Visitors]` |
| Visitatori unici stimati (ITP 2.1) | Per i visitatori ITP (utenti sui browser Safari), dividi Visitatori unici per 2 o meno. Questa metrica calcolata presuppone che tu sia impostato i cookie utilizzando JavaScript lato client (non utilizzando un&#39;implementazione CNAME). Le implementazioni che impostano i cookie utilizzando JavaScript lato client erano interessate a partire da ITP 2.1. Vedi [Prevenzione del tracciamento intelligente](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) per i dettagli. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| Visualizzazioni di pagina / Visitatori unici stimati (ITP 2.1) | Il numero medio di pagine visualizzate per Visitatori unici stimati (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
