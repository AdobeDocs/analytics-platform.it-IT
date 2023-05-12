---
title: Ottimizzare le prestazioni di CJA
description: Best practice su come ottimizzare le prestazioni di CJA
solution: Customer Journey Analytics
role: Admin
hide: true
hide-from-toc: true
source-git-commit: a546c52d2a686c38f7a9a23e0c541568c2918495
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 94%

---


# Ottimizzare le prestazioni di CJA

>[!NOTE]
>
>Per l’ottimizzazione dei fattori di prestazioni di Workspace, consulta [Ottimizzare [!UICONTROL Analysis Workspace] prestazioni](/help/analysis-workspace/workspace-faq/optimizing-performance.md).

Questi fattori influenzano le prestazioni complessive di CJA:

| Fattore | Definizione | Influenzato da | Ottimizzazione |
| --- | --- | --- | --- |
| Complessità del filtro | Filtri complessi possono avere un impatto significativo sulle prestazioni del progetto. | I fattori che aggiungono complessità a un filtro (in ordine decrescente di impatto) includono: <ul><li>Operatori di “contains”, “contains any of”, “matches”, “starts with” o “ends with” </li><li>Il filtro sequenziale avviene specialmente quando si utilizzano restrizioni delle dimensioni (entro/dopo) </li><li>Numero di elementi di dimensione univoca, compresa nelle dimensioni utilizzate nel filtro, (ad es. Pagina = “A” quando la Pagina ha 10 elementi univoci sarà più veloce della Pagina = “A” quando la Pagina ha 100.000 elementi univoci) </li><li>Numero di diverse dimensioni utilizzate (ad es. Pagina = “Home” e Pagina = “Search results” sarà più veloce di eVar 1 = “red” ed eVar 2 = “blue”)</li><li>Molti operatori OR (invece di AND)</li><li>Contenitori nidificati di vario ambito (ad es., “Hit” all’interno di “Visita” all’interno di “Visitatore”)</li></ul> | Mentre alcuni dei fattori di complessità non possono essere evitati, cerca di individuare le opportunità di riduzione della complessità dei filtri. In generale, più si può essere specifici con i propri criteri di filtro, meglio è. Ad esempio:<ul><li>Con i contenitori, l’utilizzo di un singolo contenitore nella parte superiore del segmento sarà più veloce di una serie di contenitori nidificati.</li><li>Con l’utilizzo degli operatori, “equals” sarà più veloce di “contains” e “equals any of” sarà più veloce di “contains any of”.</li><li>Con molti criteri, gli operatori AND saranno più veloci di una serie di operatori OR.</li></ul> Inoltre, prova a ridurre numerose istruzioni OR in un’unica istruzione “equals any of”. <br> |
| Complessità della visualizzazione (filtri, metriche, filtri) | Il tipo di visualizzazione (ad es. abbandono o tabella a forma libera) aggiunta a un progetto di per sé non influenza molto le prestazioni del progetto. È la complessità della visualizzazione che influenzerà il tempo di elaborazione. | Fattori che aggiungono complessità a una visualizzazione includono:<ul><li>Intervallo dei dati richiesti</li><li>Numero di filtri applicati; ovvero filtri utilizzati come righe di una tabella a forma libera</li><li>Utilizzo di filtri complessi</li><li>Righe o colonne [statiche di elementi](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) in tabelle a forma libera</li><li>Filtri applicati a righe in tabelle a forma libera</li><li>Numero di metriche incluse, in particolare metriche calcolate che utilizzano filtri</li></ul> | Se noti che i tuoi progetti non si caricano rapidamente tanto quanto vorresti, prova a sostituire alcuni filtri con eVar e filtri, ove possibile.<br><br>Se utilizzi sempre filtri e metriche calcolate per punti dati importanti per la tua azienda, puoi migliorare la tua implementazione per acquisire questi punti dati in modo più diretto. L’utilizzo di un gestore di tag come Adobe Experience Platform Launch e delle regole di elaborazione di Adobe può rendere le modifiche di implementazione veloci e facili da applicare. |
| Capacità del centro dati | Capacità di generazione dei rapporti condivisa da te e altri clienti all’interno di un data center di Adobe. | È influenzata dal numero di query simultanee effettuate dalla tua organizzazione e da altre organizzazioni all’interno del centro dati. | La tua organizzazione ha diritto a una determinata capacità e, se il carico del sistema è leggero, Adobe ti allocherà una maggiore capacità, oltre il limite determinato. |



