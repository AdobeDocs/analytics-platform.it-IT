---
title: Configurazione di visualizzazioni dati e attribuzione
description: Descrive come creare una visualizzazione dati in un dataset della piattaforma in Analisi del percorso cliente
translation-type: tm+mt
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Impostazioni dei componenti e di attribuzione

eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in Customer Journey Analytics. Sono disponibili elementi dello schema illimitati (dimensioni, metriche, campi elenco). Tutte le impostazioni di attribuzione applicate a eVar e prop durante il processo di raccolta dati ora vengono applicate in fase di query, nota anche come elaborazione report-time.

Fate clic [qui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/attribution-settings-in-data-views.html) per una panoramica video.

Tenete presente questo aspetto prima di applicare le impostazioni di attribuzione:

* Nell’interfaccia utente della visualizzazione dati, specificate l’attribuzione predefinita. **Nota**: In una data successiva, sarà possibile ignorare queste impostazioni nei progetti Workspace. Tuttavia, al momento questa funzionalità non è disponibile.

* Le impostazioni di attribuzione in Customer Journey Analytics non sono distruttive e retroattive. In altre parole, non puoi arrecare danni irreparabili ai set di dati in Analisi del percorso cliente. Anche se si elimina accidentalmente qualcosa, è sempre possibile tornare indietro [!UICONTROL Experience Platform] e riportare il dataset. Tenete presente, tuttavia, che il ripristino del set di dati comporta costi aggiuntivi.

* Se desiderate che una dimensione &quot;si comporti&quot; come una eVar tradizionale (variabile di conversione), è necessario configurarla con l&#39;attribuzione &quot;Ultima visita di contatto&quot; per impostazione predefinita.

* Se desiderate che una dimensione &quot;si comporti&quot; come una proprietà tradizionale (variabile di traffico), è necessario configurarla con l’attribuzione &quot;Simile tocco&quot; per impostazione predefinita.

* Se desideri che una metrica &quot;si comporti&quot; come una metrica predefinita, non devi cambiare nulla.

* Le impostazioni di attribuzione per le metriche prevalgono sulle impostazioni di attribuzione per le dimensioni.

## Specificare le impostazioni di componente e attribuzione

Dopo aver [impostato e salvato le impostazioni](/help/data-views/create-dataview.md) di visualizzazione dei dati e aggiunto i componenti, potete specificare le impostazioni di attribuzione, se lo desiderate. Puoi specificare le impostazioni di attribuzione/scadenza/lookback per dimensioni e metriche. Se, ad esempio, si desidera che l&#39;attribuzione rimanga valida, è probabile che si desideri impostare un&#39;ora di scadenza personalizzata. Ad esempio, se desiderate che la dimensione &quot;Codice di tracciamento&quot; (una variabile della campagna) impostata su &quot;Ultima interazione&quot; rimanga invariata per una settimana, aggiungete una scadenza personalizzata di 1 settimana.

>[!IMPORTANT]
>È possibile scegliere di non impostare allocazione/scadenza. In tal caso, le dimensioni si comportano come proprietà (modello di attribuzione &quot;Same Touch&quot;). Metriche senza impostazioni di attribuzione impostate erediteranno le impostazioni per la dimensione a cui questa metrica è applicata.

![](assets/edit-component.png)

1. Specifica le impostazioni di componenti e attribuzione per dimensioni e metriche. Consultate di seguito per informazioni sulle singole impostazioni.

1. Fare clic **[!UICONTROL Save]** per salvare la visualizzazione dati.


### Impostazione componente

Puoi cambiare il nome della metrica o della dimensione in qualcosa di più semplice da usare. Il nome sottostante non cambia, ma solo il nome visualizzato.

### Modello di attribuzione

Il modello descrive la distribuzione delle conversioni agli eventi di un gruppo. Ad esempio, primo contatto o ultimo contatto. Determina il modo in cui l&#39;analisi del percorso cliente assegna il credito per un evento di successo se una variabile riceve più valori prima dell&#39;evento.

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

Specifica un periodo di tempo, o un evento, dopo il quale il valore della dimensione scade (non riceve più credito per gli eventi di successo). Puoi impostare la scadenza dell’attribuzione a livello di sessione, persona o personalizzato.

| Impostazione | Definizione |
|---|---|
| Sessione | Precedentemente noto come livello &#39;Visita&#39;. Gli eventi di conversione oltre la visualizzazione pagina o la sessione non si associano alla dimensione o alla metrica. |
| Persona (finestra Rapporti) | Precedentemente noto come livello &#39;Visitatore&#39;. Gli eventi di conversione non associati a questa persona non si associano alla dimensione o alla metrica. |
| Ora personalizzata | Specificate i minuti, le ore, i giorni, i mesi o i trimestri personalizzati. Gli eventi di conversione oltre il periodo di tempo specificato non vengono associati alla dimensione o alla metrica. |

Per ulteriori informazioni, consulta la [sezione](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html)Attribuzione IQ.

### Finestra di ricerca

Per intervallo di lookback si intende la quantità di tempo che una conversione deve recuperare nel passato per includere i punti di contatto. I modelli di attribuzione che attribuiscono maggiore credito alle prime interazioni visualizzano differenze più importanti quando si visualizzano diversi intervalli di lookback.

* **Sessione:** Controlla di nuovo fino all&#39;inizio di una sessione in cui si è verificata una conversione. Le finestre di lookback delle visite sono strette, in quanto non guardano oltre la sessione. Le finestre di lookback delle sessioni rispettano la definizione di visita modificata nelle viste dati.
* **Persona (finestra di rapporto):** Controlla tutte le sessioni fino al primo mese del mese dell&#39;intervallo di date corrente. Le finestre di lookback delle persone sono ampie, in quanto possono estendere molte sessioni. Ad esempio, se l&#39;intervallo di date del rapporto è compreso tra il 15 e il 30 settembre, l&#39;intervallo di date del lookback della persona include tra il 1 e il 30 settembre.
