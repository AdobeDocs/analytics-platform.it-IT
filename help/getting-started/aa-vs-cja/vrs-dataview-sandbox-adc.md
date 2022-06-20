---
title: Suite di rapporti virtuali, visualizzazioni dati, Sandbox AEP e il connettore di origine di Analytics
description: Informazioni sugli ambienti di reporting virtuali e gli ambienti sandbox.
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 8%

---


# Suite di rapporti virtuali, visualizzazioni dati, Sandbox AEP e il connettore di origine di Analytics

Adobe offre diversi metodi per creare ambienti di reporting virtuali e ambienti sandbox. È utile comprendere le somiglianze e le differenze tra le seguenti funzioni e il modo in cui queste si riferiscono alle [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it):

* Suite di rapporti virtuali Adobe Analytics
* Visualizzazioni dati CJA
* Sandbox AEP

## Suite di rapporti virtuali Adobe Analytics (VRS)

Per ulteriori informazioni, consulta: [Panoramica delle suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it).

VRS:

* Può essere basato sui segmenti Adobe Analytics.
* Può essere applicato sia ai dati storici che a quelli nuovi in modo non distruttivo.
* Consente di creare una o più visualizzazioni virtuali sopra una suite di rapporti di Adobe Analytics da utilizzare per diversi team aziendali.
* Può essere utilizzato per controllare l’accesso a e curare diversi tipi di dati per diversi utenti in Adobe Analytics.
* Fornisce un [elaborazione a tempo di report](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) funzionalità di Adobe Analytics. In questo caso, una VRS può essere utilizzata per creare una definizione personalizzata per &quot;visita&quot;.
* Viene applicato in fase di esecuzione del report, in modo simile alla valutazione del segmento. Questo è _dopo_ i dati sono stati raccolti e memorizzati in Adobe Analytics.
* È richiesto per [Analisi multidispositivo](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it) in Adobe Analytics.
* Dispone dello stesso numero di variabili da utilizzare come suite di rapporti di Analytics standard (250 eVar, 250 prop, 1000 eventi), anche se la cura VRS può limitare quali variabili sono esposte agli utenti.
* Supporta le opzioni di calendario personalizzate.

Una suite di rapporti virtuale non è:

* Un mezzo per combinare le suite di rapporti.
* Disponibile in Adobe Analytics Data Warehouse.
* Disponibile come origine per i flussi di dati in AEP tramite il connettore di origine di Analytics. Solo le suite di rapporti complete (non virtuali) sono disponibili per l’uso con il connettore origine di Analytics.


## Visualizzazioni dati CJA

Per ulteriori informazioni, consulta: [Panoramica delle visualizzazioni dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=it).

Visualizzazione dati:

* Può essere basato sui filtri CJA.
* Può essere applicato sia ai dati storici che a quelli nuovi in modo non distruttivo.
* Consente di creare una o più viste virtuali sopra una connessione CJA, da utilizzare da diversi team aziendali.
* Può essere utilizzato per controllare l’accesso a e curare diversi tipi di dati per diversi utenti in CJA.
* Fornisce potenti opzioni non distruttive per trasformare e migliorare i dati in entrata in CJA tramite una connessione CJA.
* Si basa sulle funzionalità di elaborazione al momento del rapporto di CJA.
* Consente agli utenti di creare una definizione personalizzata per &quot;sessione&quot;.
* Viene applicato in fase di esecuzione del report, in modo simile a una valutazione del filtro. Questo è _dopo_ il connettore di origine (Adobe Analytics o altro) ha scritto dati in un set di dati nel lago di dati AEP, e _dopo_ i dati sono stati acquisiti in CJA tramite una connessione CJA.
* Consente un numero illimitato di variabili, anche se la cura può limitare quali variabili sono esposte agli utenti
* Consente la denominazione personalizzata dei contenitori Evento, Sessione e Persona.
* Supporta le opzioni di calendario personalizzate.

Una visualizzazione dati non:

* Fornisci direttamente un mezzo per combinare suite di rapporti o altri set di dati. Al contrario, i set di dati vengono combinati con in una connessione CJA. I dati combinati della connessione CJA sono disponibili per l’utilizzo in tutte le visualizzazioni dati basate su tale connessione.

## Sandbox AEP

Per ulteriori informazioni, consulta: [Panoramica delle sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it).

Una sandbox AEP:

* Fornisce un mezzo per suddividere una singola istanza AEP in ambienti virtuali separati (sviluppo, test, stage, produzione, ecc.) per sviluppare e sviluppare applicazioni di esperienza digitale.
* Può essere considerato un contenitore che contiene tutti i dati e le applicazioni per un determinato ambiente.

Una sandbox AEP non:

* Fornisci funzioni simili alle suite di rapporti virtuali, alle connessioni CJA o alle visualizzazioni dati.
* Di per sé combina suite di rapporti con o senza altri set di dati. Tuttavia, i set di dati all’interno di una sandbox possono essere combinati all’interno di una connessione CJA.

Tieni presente che:

* Non è possibile combinare i dati di sandbox diverse all’interno di CJA.
* Il connettore di origine di Analytics invia i dati della suite di rapporti _in_ una sandbox specifica. Ogni suite di rapporti può essere configurata come origine per una singola sandbox. Consulta la sezione [Documentazione del connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) per ulteriori dettagli.