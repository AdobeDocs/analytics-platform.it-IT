---
description: Utilizzare filtri rapidi in Analysis Workspace per il Customer Journey Analytics
title: Filtri rapidi
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 1%

---

# Filtri rapidi

I filtri rapidi consentono di esplorare rapidamente i dati all&#39;interno di un progetto Workspace, senza dover creare un filtro nel [Generatore di filtri](/help/components/filters/create-filters.md).



>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmenti rapidi in Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


Quando desideri utilizzare i filtri rapidi, tieni presente che:

* I filtri rapidi vengono creati direttamente in un progetto Workspace. Di conseguenza, un filtro rapido si applica solo al progetto Workspace in cui si crea il filtro rapido. I filtri rapidi nel progetto Workspace non sono disponibili in altri progetti e non possono essere condivisi con altri utenti.
* È possibile specificare solo tre condizioni come parte di un filtro rapido.
* I filtri rapidi non supportano contenitori nidificati o condizioni sequenziali.
* Puoi modificare i filtri rapidi all’interno di un progetto Workspace condiviso. In questo modo, altri utenti possono modificare i filtri rapidi in un progetto Workspace condiviso con loro.

## Creazione

I filtri rapidi si applicano ai pannelli. Puoi creare uno o più filtri rapidi per ogni pannello del progetto Workspace. Qualsiasi utente in Analysis Workspace può creare filtri rapidi.

Per creare un filtro rapido:

* Seleziona ![FilterAdd](/help/assets/icons/FilterAdd.svg) nella parte superiore del pannello. <br/>Modificare quindi direttamente il filtro nel [Generatore di filtri rapido](#quick-filter-builder).
* Trascina un componente dal pannello dei componenti alla zona di rilascio del filtro nell’intestazione del pannello. Una volta rilasciato, passa il cursore sul filtro e seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare il filtro nel [Generatore di filtri rapidi](#quick-filter-builder).

Quando crei un filtro rapido tramite trascinamento della selezione, tieni presente che:

* Non tutti i tipi di componenti sono supportati. Le metriche calcolate non sono supportate e sono supportate solo le dimensioni e le metriche da cui puoi creare i filtri.
* Per i componenti delle dimensioni e delle metriche, il [Generatore di filtri rapidi](#quick-filter-builder) crea automaticamente `exists` condizioni. Se ad esempio si trascina `City`, verrà creata la condizione `City exists`.
* Per i valori di dimensione, il [Generatore di filtri rapidi](#quick-filter-builder) crea automaticamente una condizione `equals`. Se ad esempio si trascina `amsterdam` dalla dimensione `City`, verrà creata la condizione `City equals amsterdam`.
* Se si trascina `unspecified` o `none`, il [Generatore di filtri rapido](#quick-filter-builder) crea automaticamente una condizione `does not exist`.

I filtri rapidi creati vengono visualizzati nella parte superiore del pannello. I filtri rapidi dispongono di una barra a sinistra sottile di colore blu chiaro. Quando un filtro rapido è in modalità di modifica mediante il [Generatore di filtri rapidi](#quick-filter-builder), lo sfondo del filtro rapido è azzurro.

I risultati dei filtri rapidi creati in un pannello vengono applicati (utilizzando la logica AND) a tutte le visualizzazioni che fanno parte del pannello.


## Gestire i

Per gestire un filtro rapido, passa il cursore del mouse su **[!UICONTROL Quick filter]** specifico.

* Seleziona ![Modifica](/help/assets/icons/Edit.svg) per aprire il [Generatore di filtri rapidi](#quick-filter-builder) e modificare il filtro rapido.
* Selezionare ![InfoOutline](/help/assets/icons/InfoOutline.svg) per aprire un popup. Nel popup vengono visualizzate informazioni sul filtro. È possibile selezionare **[!UICONTROL Make available to all projects and add to your component list]** Per aggiungere il filtro all&#39;elenco dei componenti ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** nel pannello dei componenti. Viene visualizzata una finestra di dialogo **[!UICONTROL Save quick filter]** in cui viene richiesto di specificare un nome per il filtro. Selezionare **[!UICONTROL Save]** per continuare. [!UICONTROL Quick filter] diventa **[!UICONTROL Filter]**. Non è più possibile modificare il filtro utilizzando il [Generatore di filtri rapidi](#quick-filter-builder). È invece necessario modificare il filtro come filtro normale, utilizzando il [Generatore di filtri](filter-builder.md).

## Generatore di filtri rapidi

Di seguito è riportato un esempio del generatore di filtri rapidi. Nell&#39;esempio, il generatore viene aperto per un filtro rapido denominato `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Entrambi i filtri rapidi nella parte superiore si applicano al pannello [!UICONTROL Average Order Value Dashboard] e a tutte le visualizzazioni in, ad esempio la tabella a forma libera [!UICONTROL Average Order Value Per Country].

![Generatore di filtri rapidi](assets/quick-filter-builder.png)

Il generatore di filtri rapidi è costituito dalle seguenti aree e pulsanti.

### Area intestazione

L’area dell’intestazione determina il nome, il tipo e l’ambito del filtro rapido. Inoltre, mostra un’immagine dei risultati del filtro rapido.

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Name]** | Il nome viene derivato automaticamente dalla definizione del filtro rapido. |
| **[!UICONTROL People]** <br/>![CerchioSegnoDi Spunta](/help/assets/icons/CheckmarkCircle.svg) ![Avviso](/help/assets/icons/Alert.svg) | Visualizza in anteprima i dati risultanti dal filtro rapido. Una barra e una percentuale forniscono informazioni approfondite sulla quantità di dati complessivi che fanno parte del risultato del filtro rapido. Un ![avviso](/help/assets/icons/Alert.svg) rosso segnala che il filtro rapido non restituisce dati. |
| **[!UICONTROL Include]**<br/>**[!UICONTROL Exclude]** | Seleziona dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) se desideri includere o escludere i risultati del filtro rapido dai dati nel pannello. |
| **[!UICONTROL Event]**<br/>**[!UICONTROL Session]**<br/>**[!UICONTROL Person]** | Seleziona dall&#39;elenco a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) l&#39;ambito del filtro rapido. |

### Area condizione

L’area delle condizioni specifica le condizioni (fino a un massimo di tre). Per ogni condizione puoi specificare quanto segue:

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metric]**<br/>**[!UICONTROL Date range]** | Seleziona dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) se desideri specificare una condizione per una dimensione, una metrica o un intervallo di date. |
| **[!UICONTROL *componente *]** | Il campo del componente per la condizione. È possibile [!UICONTROL *Digitare per aggiungere*] un componente, selezionare un componente dall&#39;elenco oppure trascinare un componente dal pannello dei componenti. Puoi rilasciare componenti simili solo nel campo componente della condizione. Ad esempio, potete rilasciare un componente di quota solo dal pannello dei componenti in una condizione di quota. <br/>Puoi anche trascinare e rilasciare per sostituire un componente esistente.<br/>Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per eliminare il componente dal campo del componente. |
| **[!UICONTROL *operatore *]** | Operatore del componente. Per ulteriori informazioni, vedere [Operatori](operators.md). Disponibile solo per dimensioni e metriche. |
| **[!UICONTROL *value *]** | Il valore della condizione. A seconda dell’operatore selezionato, è possibile selezionare il valore da un elenco o immetterlo. |
| ![Dimensioni incrociate75](/help/assets/icons/CrossSize75.svg) | Seleziona questa opzione per eliminare una condizione dal filtro rapido. |

### Pulsanti

| Pulsante | Descrizione |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Disponibile solo quando si definiscono più condizioni. Seleziona dall&#39;elenco a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) tra le condizioni. La selezione determina la logica booleana per il filtro rapido. Non è possibile combinare la logica quando si hanno tre condizioni. La logica booleana è **[!UICONTROL AND]** o **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Aggiunge un&#39;altra condizione al filtro rapido. Questo pulsante è disponibile solo se sono state definite una o due condizioni per il filtro rapido. |
| **[!UICONTROL Apply]** | Applica le modifiche al filtro rapido. |
| **[!UICONTROL Open builder]** | Viene richiesta una conferma con una finestra di dialogo **[!UICONTROL Are your sure?]**. Se si seleziona **[!UICONTROL OK]**, non sarà più possibile modificare il filtro nel [Generatore di filtri rapidi](#quick-filter-builder). Il filtro rapido verrà rinominato in **[!UICONTROL Filter]** e avrà una barra sinistra blu più scura.<br/>Viene aperto il [Generatore di filtri](filter-builder.md) regolare con l&#39;opzione **[!UICONTROL Make this filter available to all your projects and add it to your component list]**. <ul><li>Se si seleziona questa opzione e si seleziona **[!UICONTROL Apply]**, il filtro verrà aggiunto all&#39;elenco dei componenti ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** nel pannello dei componenti.</li><li>Se non si seleziona questa opzione e si seleziona **[!UICONTROL Apply]**, il filtro rimane un filtro solo progetto di Workspace.</li></ul> |
| **[!UICONTROL Cancel]** | Seleziona questa opzione per annullare la creazione o la modifica di un filtro rapido. |

## Filtri rapidi e Filtri

I filtri rapidi sono esattamente ciò che sono denominati. Puoi creare e modificare rapidamente i filtri rapidi in linea e vedere immediatamente gli effetti nel pannello.

I filtri presentano i seguenti vantaggi rispetto ai filtri rapidi.

* I filtri possono essere resi disponibili in tutti i tuoi progetti Workspace
* I filtri supportano una maggiore complessità utilizzando contenitori nidificati e gerarchici e sequenze (utilizzando filtri di sequenza).


