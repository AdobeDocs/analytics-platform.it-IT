---
title: Domande frequenti su Attribution
description: Risposte alle domande più frequenti sull’attribuzione.
translation-type: tm+mt
source-git-commit: e4bef70f72019bdceb09938dffe2fd266ff4248d
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 93%

---


# Domande frequenti su Attribution

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

**Qual è l’elemento di riga “None” quando si utilizza l’attribuzione?**

“None” è un elemento catch-all che rappresenta tutte le conversioni avvenute senza punti di contatto all’interno dell’intervallo di lookback. Prova a includere un intervallo di tempo più lungo nel periodo definito per la generazione del rapporto.

**Perché talvolta visualizzo date al di fuori del periodo definito per la generazione del rapporto quando utilizzo modelli di attribuzione?**

Queste date aggiuntive sono dovute all’intervallo di lookback inerente al rapporto sui visitatori. Per ulteriori informazioni, vedi [Dati visualizzati all’esterno del periodo definito per la generazione del rapporto](https://helpx.adobe.com/it/analytics/kb/data-appearing-outside-reporting-window.html) nel portale di aiuto di Analytics. Adobe prevede di escludere queste righe aggiuntive in una delle prossime versioni.

**Quando dovrei usare un lookback di attribuzione basato su visita o visitatore?**

La scelta del lookback di attribuzione dipende dal caso di utilizzo. Se le conversioni in genere richiedono più tempo di una singola visita, si consiglia di effettuare un lookback su visitatore. Inoltre, la creazione di una suite di rapporti virtuale con una definizione di visita più lunga rappresenta una soluzione potenziale.

**Come si confrontano proprietà e eVar quando si utilizza l’attribuzione?**

L’attribuzione viene ricalcolata in fase di esecuzione dei report, quindi non c’è differenza tra proprietà e eVar (o qualsiasi altra dimensione) per la modellazione dell’attribuzione. Le proprietà possono persistere utilizzando qualsiasi intervallo di lookback o modello di attribuzione e le impostazioni di allocazione/scadenza eVar vengono ignorate.

**Quali sono le dimensioni e metriche non supportate?**

Il pannello di attribuzione supporta tutte le dimensioni. Le metriche non supportate includono:

* Visitatori unici
* Visite
* Occorrenze
* Visualizzazioni pagina
* Metriche A4T
* Metriche Tempo trascorso
* Rimbalzi
* Percentuale non recapitate
* Voci
* Uscite
* Pagine non trovate
* Ricerche
* Visite a pagina singola
* Accesso singolo

**Come funziona l’attribuzione con i filtri?**

L’attribuzione viene sempre eseguita prima dei filtri e la segmentazione viene eseguita prima dell’applicazione di qualsiasi altro filtro di rapporto.
