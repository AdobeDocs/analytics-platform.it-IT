---
description: Esempi durante la configurazione di una visualizzazione area di lavoro Percorso
title: Esempi di area di lavoro percorso
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: 057c9f4a0e8fb163bfb23cea1870f949ad4ae1c0
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# Risoluzione dei problemi di area di lavoro del percorso

{{release-limited-testing}}

La visualizzazione area di lavoro Percorso consente di analizzare e ottenere informazioni approfondite sui percorsi forniti a utenti e clienti.

Per ulteriori informazioni sull&#39;area di lavoro Percorso, vedere [Panoramica sull&#39;area di lavoro Percorso](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) e [Configurare una visualizzazione dell&#39;area di lavoro Percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


## Compatibilità tra la metrica contenitore e la metrica principale

Puoi configurare il contenitore dell’area di lavoro del Percorso come Persona (che utilizza la metrica Persone) o Sessione (che utilizza la metrica Sessioni).

Quando scegli una metrica principale o secondaria, accertati di scegliere una metrica compatibile con la metrica contenitore attualmente selezionata. La maggior parte delle metriche è compatibile con le metriche contenitore disponibili. Tuttavia, è necessario evitare alcune combinazioni di metriche contenitore e metriche primarie o secondarie.

Ad esempio, se utilizzi Persona come contenitore con Sessione come metrica principale o secondaria


| Contenitore | Metrica primaria o secondaria | Risultato |
|---------|----------|---------|
| Persone | Sessione | Questa combinazione può causare risultati non desiderati. Nello specifico, il risultato di questa combinazione può essere |
| A2 | B2 | C2 |
| A3 | B3 | C3 |


## Percentuali che superano il 100%

Le seguenti configurazioni possono causare nodi che mostrano percentuali superiori al 100%:

* Quando il campo **[!UICONTROL Percentage value]** è impostato su **[!UICONTROL Percent of total]** e viene selezionata una metrica primaria che restituisce meno dati per il nodo iniziale rispetto ai nodi successivi.

  Ad esempio, se Ricavi è selezionato come metrica principale e non viene realizzato alcun ricavo sulla metrica principale, su qualsiasi nodo in cui i ricavi vengono realizzati verrà visualizzato un valore superiore al 100%.


## Percorso non a forma di imbuto

Nell’area di lavoro del Percorso, i nodi che si trovano in una fase successiva del percorso possono mostrare un conteggio percentuale o numerico più elevato rispetto ai nodi che si trovano in una fase precedente del percorso.

In altre parole, a differenza delle visualizzazioni Abbandono, che sono sempre a forma di imbuto (con la partecipazione che diminuisce con ogni passaggio), le visualizzazioni dell’area di lavoro del Percorso possono avere una partecipazione più elevata ai passaggi successivi del percorso.

Si consideri un percorso con le seguenti caratteristiche:

* Il percorso contiene 3 nodi: Nodo A —> Nodo B —> Nodo C

* Campo **[!UICONTROL Percentage value]** impostato su **[!UICONTROL Percent of total]**

* **[!UICONTROL Person]** è impostato come contenitore

* **[!UICONTROL Event]** è impostato come metrica principale

In questo scenario, supponiamo che un visitatore abbia visitato il nodo A, il nodo B e quindi il nodo C. Ognuna di queste visite conta come un singolo evento su ciascun nodo, perché sono state visitate nell’ordine definito dal percorso.

In una visita successiva al sito, il visitatore visita solo il nodo C, dando luogo a un evento aggiuntivo sul nodo C.

In questo caso, i nodi A e B mostrerebbero ciascuno 1 evento e 100%, mentre il nodo C mostrerebbe 2 eventi e 200%.

D’altra parte, se Session fosse impostato come contenitore, i nodi A, B e C mostrerebbero ciascuno 1 evento e 100%, perché la visita successiva al sito in cui il visitatore ha visitato solo il nodo C non avrebbe soddisfatto i requisiti percorsi, perché i nodi A e B non sono stati visitati prima della visita del nodo C.
