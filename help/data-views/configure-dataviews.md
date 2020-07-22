---
title: Configurazione di visualizzazioni dati e attribuzione
description: Descrive come creare una visualizzazione dati in un set di dati della Platform in Customer Journey Analytics
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 98%

---


# Impostazioni del componente e di attribuzione

eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in Customer Journey Analytics. Invece, sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Tutte le impostazioni di attribuzione applicate a eVar e prop durante il processo di raccolta dati ora vengono applicate in fase di query, nota anche come elaborazione dell’ora del report.

Per una panoramica video, fai clic [qui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/attribution-settings-in-data-views.html).

Tieni presente questo aspetto prima di applicare le impostazioni di attribuzione:

* Nell’interfaccia utente della visualizzazione dati, specifica l’attribuzione predefinita. **Nota**: in una data successiva, sarà possibile ignorare queste impostazioni nei progetti Workspace. Tuttavia, al momento questa funzionalità non è disponibile.

* Le impostazioni di attribuzione in Customer Journey Analytics non sono distruttive e retroattive. In altre parole, non puoi arrecare danni irreparabili ai set di dati in Customer Journey Analytics. Anche se elimini accidentalmente qualcosa, è sempre possibile ritornare a [!UICONTROL Experience Platform] e reinserire il set di dati. Tuttavia, il ripristino del set di dati comporta costi aggiuntivi.

* Se desideri che una dimensione si comporti come una eVar tradizionale (variabile di conversione), è necessario configurarla per impostazione predefinita con l’attribuzione “Last Touch Visit” (Visita ultimo contatto).

* Se desideri che una dimensione si comporti come una prop tradizionale (variabile di traffico), è necessario configurarla per impostazione predefinita con l’attribuzione “Same Touch” (Stesso contatto).

* Se desideri che una metrica si comporti come una metrica, non devi effettuare alcuna modifica.

* Le impostazioni di attribuzione per le metriche prevalgono su quelle relative alle dimensioni.

## Specifica le impostazioni del componente e di attribuzione

Dopo aver [configurato e salvato le impostazioni di visualizzazione dati](/help/data-views/create-dataview.md) e aggiunto i componenti, puoi specificare le impostazioni di attribuzione, se lo desideri. Puoi specificare le impostazioni di attribuzione/scadenza/lookback per dimensioni e metriche. Se, ad esempio, vuoi mantenere valida l’attribuzione, dovrai probabilmente impostare un’ora di scadenza personalizzata. Ad esempio, se vuoi che la dimensione “Codice di monitoraggio”, ovvero una variabile della campagna, sia impostata sull’attribuzione “Last Touch” (Ultimo contatto) per una settimana, aggiungi una scadenza personalizzata di 1 settimana.

>[!IMPORTANT]
>È possibile scegliere di non impostare allocazione/scadenza. In tal caso, le dimensioni si comportano come prop (modello di attribuzione “Same Touch” (Stesso contatto)). Le metriche prive di impostazioni di attribuzione erediteranno le impostazioni di dimensione a cui è applicata questa metrica.

![](assets/edit-component.png)

1. Specifica le impostazioni del componente e di attribuzione relative a dimensioni e metriche. Per informazioni sulle singole impostazioni, consulta la sezione sottostante.

1. Per salvare la visualizzazione dati, fai clic su **[!UICONTROL Save]**.


### Impostazione componente

Puoi modificare il nome della metrica o della dimensione con un nome più semplice da usare. Il nome sottostante non subirà modifiche, solo il nome visualizzato.

### Modello di attribuzione

Il modello descrive la distribuzione delle conversioni negli eventi in un gruppo. Ad esempio, primo contatto o ultimo contatto. Determina il modo in cui Customer Journey Analytics assegna il credito per un evento di successo se una variabile riceve valori multipli prima dell’evento.

| Icona interfaccia utente | Modello di attribuzione | Definizione | Quando utilizzare |
| --- | --- | --- | --- |
| ![Ultimo contatto](assets/last_touch1.png) | Ultimo contatto | Attribuisce un credito del 100% al punto di contatto più di recente che si verifica prima della conversione. | Si tratta del modello di attribuzione più semplice e comune. Viene spesso utilizzato per le conversioni con un breve ciclo di considerazione. Ultimo contatto viene comunemente utilizzato dai team che gestiscono il marketing di ricerca o che analizzano le parole chiave di ricerca interne. |
| ![Primo contatto](assets/first_touch.png) | Primo contatto | Attribuisce un credito del 100% al punto di contatto visualizzato per la prima volta nell’intervallo di lookback dell’attribuzione. | Si tratta di un altro modello di attribuzione utile per l’analisi dei canali di marketing destinati a generare brand awareness o acquisizione di clienti. Viene utilizzato di frequente dai team di display/social marketing ma è ottimo anche per valutare l’efficacia dei prodotti consigliati durante la navigazione nel sito. |
| ![Stesso contatto](assets/same_touch.png) | Stesso contatto | Attribuisce un credito del 100% all’hit in cui si è verificata la conversione. Se un punto di contatto non si verifica sullo stesso hit di una conversione, viene inserito in “None”. | Si tratta di un modello utile quando si valuta l’esperienza utente o il contenuto presentato immediatamente nel momento della conversione. I team che si occupano di prodotti o design utilizzano spesso questo modello per valutare l’efficacia di una pagina in cui si verifica una conversione. |
| ![Lineare](assets/linear.png) | Lineare | Attribuisce lo stesso credito a ogni punto di contatto che porta a una conversione. | Si tratta di un modello utile per conversioni con esperienze utente o cicli di considerazione più lunghi che necessitano di un coinvolgimento del cliente più frequente. Viene spesso utilizzato dai team che misurano l’efficacia delle notifiche delle app mobili o con prodotti basati su abbonamento. |
| ![A forma di U](assets/u_shaped.png) | A forma di U | Attribuisce il 40% di credito alla prima interazione, il 40% di credito all’ultima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato un credito del 50% a entrambi. | Si tratta di un ottimo modello per individuare le interazioni che hanno avviato o chiuso una conversione, pur identificando le interazioni di supporto. L’attribuzione a forma di U è comunemente utilizzata dai team che adottano un approccio più bilanciato ma desiderano dare più valore ai canali di origine o conclusione di una conversione. |
| ![A forma di J](assets/j_shaped.png) | A forma di J | Attribuisce il 60% di credito all’ultima interazione, il 20% di credito alla prima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito all’ultima interazione e il 25% di credito alla prima. | Si tratta di un modello ideale per dare priorità a ricerche e chiusure, pur concentrandosi sulla chiusura delle interazioni. L’attribuzione a forma di J viene spesso utilizzata dai team che adottano un approccio più bilanciato e desiderano dare più valore ai canali da cui è stata conclusa una conversione. |
| ![A forma di J inversa](assets/inverse_j.png) | J inversa | Attribuisce un credito del 60% al primo punto di contatto, un credito del 20% all’ultimo punto di contatto e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito alla prima interazione e il 25% di credito all’ultima. | Si tratta di un modello ideale per dare priorità a ricerche e chiusure, pur concentrandosi sulla ricerca delle interazioni. L’attribuzione a J inversa è spesso utilizzata dai team che adottano un approccio più bilanciato e desiderano dare più valore ai canali di origine della conversione. |
| ![Personalizzato](assets/custom.png) | Personalizzato | Consente di specificare i valori da assegnare ai punti di contatto, agli ultimi punti di contatto e a eventuali punti di contatto intermedi. I valori specificati vengono normalizzati al 100% anche se la somma dei numeri personalizzati immessi è inferiore a 100. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le interazioni con due punti di contatto, il parametro intermedio viene ignorato. Il primo e l’ultimo punto di contatto vengono quindi normalizzati al 100% e il credito viene assegnato di conseguenza. | Si tratta di un modello perfetto per avere pieno controllo sul proprio modello di attribuzione e rispondere a esigenze specifiche che altri modelli di attribuzione non soddisfano. |
| ![Decadimento nel tempo](assets/time_decay.png) | Decadimento nel tempo | Segue un decadimento esponenziale con un parametro di mezza durata personalizzato, dove il valore predefinito è 7 giorni. Il valore di ciascun canale dipende dalla quantità di tempo trascorsa tra l’avvio del punto di contatto e l’eventuale conversione. La formula utilizzata per determinare il credito è `2`<sup>`(-t/halflife)`</sup>, dove `t` è il tempo tra un punto di contatto e una conversione. Tutti i punti di contatto vengono quindi normalizzati al 100%. | Si tratta di un modello ideale per i team che eseguono regolarmente campagne pubblicitarie video o che mirano su eventi basati su data prestabilita. Più una conversione si verifica dopo un evento di marketing, meno credito viene assegnato. |
| ![Partecipazione](assets/participation.png) | Partecipazione | Assegna il 100% di credito a tutti i punti di contatto unici. Il numero totale di conversioni è aumentato rispetto ad altri modelli di attribuzione. La partecipazione deduplica i canali visualizzati più volte. | Si tratta di un modello ottimo per comprendere quanto spesso i clienti sono esposti a una determinata interazione. Le società di comunicazioni utilizzano spesso questo modello per calcolare la velocità del contenuto. Le società di commercio al dettaglio usano spesso questo modello per capire quali sono le parti del sito che sono fondamentali per la conversione. |

### Scadenza

Specifica un periodo di tempo, o un evento, dopo il quale l&#39;elemento dimensione scade (non riceve più credito per gli eventi di successo). Puoi impostare la scadenza dell’attribuzione a livello di sessione, persona o in formato personalizzato.

| Impostazione | Definizione |
|---|---|
| Sessione | Precedentemente noto come livello “Visita”. Gli eventi di conversione che vanno oltre la visualizzazione pagina o la sessione non si associano alla dimensione o alla metrica. |
| Persona (intervallo di Reporting) | Precedentemente noto come livello “Visitatore”. Gli eventi di conversione non collegati a questa persona non si associano alla dimensione o alla metrica. |
| Ora personalizzata | Specifica i minuti, le ore, i giorni, i mesi o i trimestri personalizzati. Gli eventi di conversione che vanno oltre il periodo di tempo specificato non si associano alla dimensione o alla metrica. |

Per ulteriori informazioni, consulta il [documento Attribution IQ](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/panels/attribution/attribution.html).

### Intervallo di lookback

Per intervallo di lookback si intende la quantità di tempo che una conversione deve recuperare nel passato per includere i punti di contatto. I modelli di attribuzione che attribuiscono maggiore credito alle prime interazioni visualizzano differenze più importanti quando si visualizzano diversi intervalli di lookback.

* **Sessione:** considera fino l’inizio di una sessione che ha generato una conversione. Gli intervalli di lookback su visita sono stretti, dato non si estendono oltre la sessione. Gli intervalli di lookback delle sessioni rispettano la definizione di visita modificata nelle visualizzazioni dati.
* **Persona (intervallo di reporting):** esamina tutte le sessioni fino al 1° del mese dell’intervallo date corrente. Le finestre di lookback a persona sono ampie, dato che possono coinvolgere numerose sessioni. Ad esempio, se l’intervallo di date del report è dal 15 settembre al 30 settembre, l’intervallo di date del lookback a persona sarà dal 1° al 30 settembre.
