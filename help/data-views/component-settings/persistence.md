---
title: Impostazioni dei componenti di persistenza
description: Determina in che modo o se i valori delle dimensioni persistono da un evento all’altro.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 459249c74bf4dadf84c2adf96498f2eea21be1ee
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 8%

---


# [!UICONTROL Persistence] Impostazioni del componente

[!UICONTROL Persistence] è la capacità di un dato valore di dimensione di riferirsi a una metrica oltre l’evento su cui è impostato. Utilizza una combinazione di allocazione e scadenza.

* **Allocazione** consente di determinare quale valore viene mantenuto quando più elementi dimensionali possono persistere alla volta in una singola colonna.
* **Scadenza** consente di determinare per quanto tempo un elemento dimensione persiste oltre l’evento su cui è impostato.

[!UICONTROL Persistence] è disponibile solo sulle dimensioni ed è retroattivo ai dati a cui viene applicato. Si tratta di una trasformazione immediata dei dati che avviene prima dell’applicazione di filtri o di altre operazioni di analisi.

![Persistenza](../assets/persistence.png)

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Set persistence] | Abilita la persistenza per la dimensione. Se la persistenza non è abilitata, la dimensione si riferisce solo alle metriche esistenti nello stesso evento. Questa impostazione è disattivata per impostazione predefinita. |
| [!UICONTROL Allocation] | Consente di specificare il modello di allocazione utilizzato su una dimensione per la persistenza. Le opzioni sono: [!UICONTROL Most recent], [!UICONTROL Original], [!UICONTROL Instance], [!UICONTROL All]. A partire dal 28 ottobre 2021, un intervallo di lookback fino a 90 giorni verrà aggiunto al [!UICONTROL Allocation] impostazione. |
| [!UICONTROL Expiration] | Consente di specificare la finestra di persistenza per una dimensione. Le opzioni sono: [!UICONTROL Session] (predefinito), [!UICONTROL Person], [!UICONTROL Custom Time], [!UICONTROL Metric]. Potrebbe essere necessario poter scadere la dimensione su un acquisto (ad esempio termini di ricerca interni o altri casi d’uso di merchandising). Il tempo massimo di scadenza che puoi impostare è di 90 giorni. Se selezioni un&#39;allocazione di [!UICONTROL All], solo [!UICONTROL Session] o [!UICONTROL Person] è disponibile la scadenza. |

## [!UICONTROL Allocation] del profilo

Dettagli sulle impostazioni di allocazione disponibili.

* **[!UICONTROL Most Recent]**: persiste il valore più recente (per marca temporale) presente nella dimensione. Eventuali valori successivi che si verificano all’interno del periodo di scadenza della dimensione sostituiscono il valore persistente precedente. Se su questa dimensione è abilitato &quot;Treat &#39;No Value&#39; as a value&quot; in [Nessuna opzione di valore](no-value-options.md), i valori vuoti sovrascrivono quelli persistenti in precedenza. Ad esempio, considera la seguente tabella con [!UICONTROL Most recent] assegnazione e [!UICONTROL Session] scadenza:

   | Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valori del set di dati |  | C | B |  | A |
   | Allocazione più recente |  | C | B | B | A |

* **[!UICONTROL Original]**: Persiste il valore originale per marca temporale presente nella dimensione per la durata del periodo di scadenza. Se questa dimensione ha un valore, non viene sovrascritta quando viene visualizzato un valore diverso in un evento successivo. Ad esempio, considera la seguente tabella con [!UICONTROL Original] assegnazione e [!UICONTROL Session] scadenza:

   | Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valori del set di dati |  | C | B |  | A |
   | Allocazione originale |  | C | C | C | C |

* **[!UICONTROL All]**: Agisce in modo simile al [!UICONTROL Participation] modello di attribuzione per le metriche. Persiste tutti i valori equamente in modo che ciascuno ottenga il pieno credito per la metrica nel reporting. Ad esempio, considera la seguente tabella con [!UICONTROL All] assegnazione e [!UICONTROL Session] scadenza:

   | Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valori del set di dati | A | B | C |  | A |
   | Tutte le allocazioni | A | A,B | A, B, C | A, B, C | A, B, C |

* **[!UICONTROL First Known]** e **[!UICONTROL Last Known]**: (19 gennaio 2022 ) Questi due modelli di allocazione soddisfano i casi d’uso per le dimensioni &quot;entrata&quot; e &quot;uscita&quot;. Ottengono il primo o l’ultimo valore osservato per una dimensione all’interno di un ambito di persistenza specificato (sessione, persona o periodo di tempo personalizzato con lookback) e lo applicano a tutti gli eventi all’interno dell’ambito specificato. Esempio:

   | Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
   | --- | --- | --- | --- | --- | --- |
   | Timestamp (min) | 1 | 2 | 3 | 6 | 7 |
   | Valori originali |  | C | B |  | A |
   | Primo noto | C | C | C | C | C |
   | Ultimo noto | A | A | A | A | A |

## [!UICONTROL Expiration] del profilo

Dettagli sulle impostazioni di scadenza disponibili.

* **Sessione**: Scade dopo una determinata sessione. Finestra di scadenza predefinita.
* **Persona**: Scade alla fine dell&#39;intervallo di reporting.
* **Ora personalizzata**: Scade dopo un determinato periodo di tempo (fino a 90 giorni). Questa opzione di scadenza è disponibile solo per i modelli di allocazione Originale e Più recente. Quando si utilizza una scadenza basata sul tempo, vengono considerati i valori precedenti all’inizio dell’intervallo di reporting (fino a 90 giorni).
* **Metrica**: Quando questa metrica viene visualizzata in un hit, scade immediatamente il valore persistente nella dimensione. Puoi utilizzare qualsiasi metrica come fine di scadenza per questa dimensione. Questa opzione di scadenza è disponibile solo per le impostazioni di allocazione Originale e Più recente.

## [!UICONTROL Binding Dimension]

Elenco a discesa che consente di associare la persistenza di un valore di dimensione ai valori di dimensione in un’altra dimensione. Le opzioni a discesa valide includono altre dimensioni incluse nella visualizzazione dati.

Vedi [Utilizzo di dimensioni e metriche di binding in CJA](../../use-cases/binding-dimensions-metrics.md) esempi su come utilizzare in modo efficace le dimensioni di binding.

## [!UICONTROL Binding Metric]

Elenco a discesa che consente di scegliere una metrica che agisce come attivatore di binding. Le opzioni a discesa valide includono le metriche incluse nella visualizzazione dati.

Questa impostazione viene visualizzata solo quando il Dimension di binding è inferiore nella matrice dell’oggetto rispetto al componente. Quando la metrica di binding è presente in un evento, i valori di dimensione vengono copiati dalla dimensione a livello di evento fino al livello di schema inferiore della dimensione di binding.

Vedi il secondo esempio sotto [Utilizzo di dimensioni e metriche di binding in CJA](../../use-cases/binding-dimensions-metrics.md) per ulteriori informazioni su come utilizzare in modo efficace le metriche di binding.
