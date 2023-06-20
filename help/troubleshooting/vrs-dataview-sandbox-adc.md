---
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 63%

---
# Suite di rapporti virtuali, visualizzazioni dati, sandbox di Adobe Experience Platform e il connettore di origine di Analytics

Adobe offre diversi metodi per creare ambienti di reporting virtuali e ambienti sandbox. È utile comprendere le somiglianze e le differenze tra le seguenti funzioni e il modo in cui queste si relazionano al [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it):

* Suite di rapporti virtuali di Adobe Analytics
* Visualizzazioni dati Customer Journey Analytics
* Sandbox Adobe Experience Platform

## Suite di rapporti virtuali di Adobe Analytics (VRS)

Per ulteriori informazioni, consulta [Virtual report suites overview](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it) (Panoramica delle suite di rapporti virtuali).

Una suite di rapporti virtuali:

* può essere basata sui segmenti di Adobe Analytics;
* può essere applicata sia ai dati storici che a quelli nuovi in modo non distruttivo;
* consente di creare una o più visualizzazioni virtuali sopra una suite di rapporti di Adobe Analytics per l’utilizzo da parte di diversi team aziendali;
* può essere utilizzata per curare diversi tipi di dati per diversi utenti in Adobe Analytics e per controllarne l’accesso;
* fornisce funzionalità facoltative di [elaborazione al momento del reporting](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=it) di Adobe Analytics; in questo caso, una suite di rapporti virtuali può essere utilizzata per creare una definizione personalizzata di “visita”;
* viene applicata in fase di esecuzione del report, in modo simile alla valutazione del segmento, ovvero _dopo_ che i dati sono stati raccolti e memorizzati in Adobe Analytics;
* è richiesta per [Analisi tra dispositivi](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it) in Adobe Analytics;
* dispone dello stesso numero di variabili da utilizzare delle suite di rapporti standard di Analytics (250 eVar, 250 prop, 1000 eventi), anche se la cura delle suite di rapporti virtuali può limitare quali variabili sono presentate agli utenti;
* supporta le opzioni di calendario personalizzato.

Una suite di rapporti virtuale non:

* fornisce un mezzo per combinare le suite di rapporti;
* è disponibile in Adobe Analytics Data Warehouse;
* Disponibile come origine per i flussi di dati in Adobe Experience Platform tramite il connettore di origine di Analytics. solo le suite di rapporti complete (non virtuali) sono disponibili per l’uso con il connettore di origine di Analytics.


## Visualizzazioni dati Customer Journey Analytics

Per ulteriori informazioni, consulta [Panoramica delle visualizzazioni dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=it).

Una visualizzazione dati:

* Può essere basato su filtri di Customer Journey Analytics.
* può essere applicata sia ai dati storici che a quelli nuovi in modo non distruttivo;
* Consente di creare una o più visualizzazioni virtuali sopra una connessione di Customer Journey Analytics per l&#39;utilizzo da parte di diversi team aziendali.
* Può essere utilizzato per controllare l’accesso a e curare diversi tipi di dati per diversi utenti nel Customer Journey Analytics.
* Fornisce potenti opzioni non distruttive per trasformare e migliorare i dati che entrano nel Customer Journey Analytics tramite una connessione di Customer Journey Analytics.
* Si basa sulle funzionalità di elaborazione al momento del reporting del Customer Journey Analytics.
* consente agli utenti di creare una definizione personalizzata di “sessione”;
* viene applicata in fase di esecuzione del report, in modo simile alla valutazione del filtro, Questo è _dopo_ il connettore di origine (Adobe Analytics o altro) ha scritto dati in un set di dati nel data lake di Adobe Experience Platform, e _dopo_ i dati sono stati acquisiti nel Customer Journey Analytics tramite una connessione di Customer Journey Analytics.
* consente un numero illimitato di variabili, anche se la cura può limitare quali variabili sono presentate agli utenti;
* consente la denominazione personalizzata dei contenitori Evento, Sessione e Persona;
* supporta le opzioni di calendario personalizzato.

Una visualizzazione dati non:

* fornisce direttamente un mezzo per combinare suite di rapporti o altri set di dati. Al contrario, i set di dati vengono combinati con in una connessione di Customer Journey Analytics. I dati combinati della connessione di Customer Journey Analytics sono disponibili per l’utilizzo in tutte le visualizzazioni dati basate su tale connessione.

## Sandbox Adobe Experience Platform

Per ulteriori informazioni, consulta [Sandboxes overview](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) (Panoramica delle sandbox).

Una sandbox di Adobe Experience Platform:

* Fornisce un mezzo per suddividere una singola istanza Adobe Experience Platform in ambienti virtuali separati (sviluppo, test, fase, produzione, ecc.) utili per lo sviluppo e l’aggiornamento delle applicazioni di esperienza digitale;
* può essere considerata un contenitore che racchiude tutti i dati e le applicazioni di un determinato ambiente.

Una sandbox di Adobe Experience Platform non:

* Fornisci funzioni simili alle suite di rapporti virtuali, alle connessioni di Customer Journey Analytics o alle visualizzazioni dati.
* combina autonomamente suite di rapporti con o senza altri set di dati. Tuttavia, i set di dati all’interno di una sandbox possono essere combinati in una connessione di Customer Journey Analytics.

Ulteriori informazioni:

* I dati di sandbox diverse non possono essere combinati all’interno di un Customer Journey Analytics.
* Il connettore di origine di Analytics invia i dati della suite di rapporti _in_ una sandbox specifica. Ogni suite di rapporti può essere configurata come origine per una singola sandbox. Consulta la [documentazione relativa al connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) per ulteriori dettagli.