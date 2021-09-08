---
title: Cos’è la persistenza della dimensione nel Customer Journey Analytics?
description: La persistenza del Dimension è una combinazione di allocazione e scadenza. Insieme, determinano in che modo o se i valori di dimensione persistono da un evento all’altro.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
source-git-commit: ab81c7fff2b7e942491fd417cfa115dd428f222d
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 6%

---

# Persistenza

La persistenza del Dimension è una combinazione di allocazione e scadenza. Insieme, determinano in che modo o se i valori di dimensione persistono da un evento all’altro. La persistenza del Dimension è configurata su una dimensione all’interno di Visualizzazioni dati ed è retroattiva e non distruttiva per i dati a cui viene applicata. La persistenza del Dimension è una trasformazione immediata dei dati applicata a una dimensione che si verifica prima che vengano eseguiti filtri o altre operazioni di analisi nel reporting.

* Per impostazione predefinita, per un valore di dimensione non è abilitata la persistenza.
* Per impostazione predefinita, quando un modello di allocazione è abilitato per una dimensione, viene utilizzata una scadenza di [!UICONTROL Session].

## Allocazione

L&#39;allocazione applica una trasformazione al valore sottostante utilizzato. I modelli di allocazione supportati includono:

* Più recente
* Originale
* Tutto

### [!UICONTROL Most recent] assegnazione

L’allocazione più recente persiste il valore più recente (per marca temporale) presente nella dimensione. Eventuali valori successivi che si verificano all’interno della stessa sessione sostituiscono il valore persistente precedente. Tieni presente che se è stato selezionato &quot;Traccia &#39;nessun valore&#39; come valore&quot; in questa dimensione, i valori vuoti vengono sostituiti con &#39;Nessun valore&#39; prima che venga applicata la persistenza. Di seguito è riportato un esempio precedente e successivo di allocazione [!UICONTROL Most recent] supponendo che per la scadenza venga utilizzato un [!UICONTROL Session] e che tutti gli eventi si verifichino all&#39;interno di un [!UICONTROL Session]:

| Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| valori del set di dati |  | C | B |  | A |
| Allocazione più recente |  | C | B | B | A |

### [!UICONTROL Original] assegnazione

L’allocazione originale persiste il valore originale (per marca temporale) presente nella dimensione per un periodo di scadenza. Di seguito è riportato un esempio precedente e successivo di allocazione [!UICONTROL Original]:

| Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| valori del set di dati |  | C | B |  | A |
| Allocazione originale |  | C | C | C | C |

### [!UICONTROL All] assegnazione

Questa allocazione delle dimensioni può essere applicata sia alle dimensioni basate su array che alle dimensioni a valore singolo. Funziona in modo simile al modello di attribuzione [!UICONTROL Participation] per le metriche. Una differenza fondamentale consiste nel fatto che le dimensioni con Allocazione completa possono essere utilizzate nelle definizioni dei filtri. Ad esempio, supponiamo di avere 5 eventi in un campo stringa, con allocazione impostata su &quot;All&quot; e scadenza impostata su 5 minuti:

| Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| valori del set di dati | A | B | C |  | A |
| post-persistenza | A | A,B | A, B, C | A, B, C | A, B, C |

## Scadenza

[!UICONTROL Expiration] consente di specificare la finestra di persistenza per una dimensione.

Esistono quattro modi per far scadere un valore di dimensione:

* Sessione (impostazione predefinita): Scade dopo una determinata sessione.
* Persona: Scade alla fine dell&#39;intervallo di reporting.
* Ora: Puoi impostare la scadenza del valore della dimensione dopo un determinato periodo di tempo (fino a 90 giorni). Questa opzione di scadenza è disponibile solo per i modelli di allocazione Originale e Più recente. Quando si utilizza una scadenza basata sul tempo, vengono considerati i valori precedenti all’inizio dell’intervallo di reporting (fino a 90 giorni).
* Metrica: Puoi specificare una qualsiasi delle metriche definite come fine di scadenza per questa dimensione (ad esempio una metrica &quot;Acquisto&quot;). Questa scadenza è disponibile solo per i modelli di allocazione Originale e Più recente.

### Qual è la differenza tra Allocazione e Attribuzione?

**Allocazione**: Considera l&#39;allocazione come una trasformazione dei dati verso la dimensione. L’allocazione avviene prima del filtro. Se crei un filtro, questo verrà escluso dalla dimensione trasformata.

**Attribuzione**: Come posso distribuire il credito di una metrica alla dimensione a cui è applicata? L’attribuzione non è una trasformazione di dati, si applica durante l’aggregazione dei dati e non influisce sui dati inclusi utilizzando un filtro.
