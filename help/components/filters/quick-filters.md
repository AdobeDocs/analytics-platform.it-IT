---
description: Utilizzare filtri rapidi in Analysis Workspace per Customer Journey Analytics
title: Filtri rapidi
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: ht
source-wordcount: '1098'
ht-degree: 100%

---

# Filtri rapidi

I filtri rapidi consentono di esplorare rapidamente i dati all’interno di un progetto Workspace, senza dover creare un filtro nel [Generatore di filtri](/help/components/filters/create-filters.md).



>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmenti rapidi in Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


Quando desideri utilizzare i filtri rapidi, tieni presente che:

* I filtri rapidi vengono creati direttamente in un progetto Workspace. Di conseguenza, un filtro rapido si applica solo al progetto Workspace in cui crei il filtro rapido. I filtri rapidi nel progetto Workspace non sono disponibili in altri progetti e non possono essere condivisi con altri utenti.
* Puoi specificare solo tre condizioni come parte di un filtro rapido.
* I filtri rapidi non supportano contenitori nidificati o condizioni sequenziali.
* Puoi modificare i filtri rapidi all’interno di un progetto Workspace condiviso. In questo modo, altri utenti possono modificare i filtri rapidi in un progetto Workspace che hai condiviso con loro.

## Creazione

I filtri rapidi si applicano ai pannelli. Puoi creare uno o più filtri rapidi per ogni pannello nel progetto Workspace. Qualsiasi utente in Analysis Workspace può creare filtri rapidi.

Per creare un filtro rapido:

* Seleziona ![FilterAdd](/help/assets/icons/FilterAdd.svg) nella parte superiore del pannello. <br/>Modifica quindi direttamente il filtro nel [Generatore di filtri rapidi](#quick-filter-builder).
* Trascina un componente dal pannello dei componenti alla zona di rilascio del filtro nell’intestazione del pannello. Una volta rilasciato, passa il cursore sul filtro e seleziona ![Edit](/help/assets/icons/Edit.svg) per modificare il filtro nel [Generatore di filtri rapidi](#quick-filter-builder).

Quando crei un filtro rapido usando il trascinamento, tieni presente che:

* Non tutti i tipi di componenti sono supportati. Le metriche calcolate non sono supportate e sono supportate solo le dimensioni e le metriche da cui puoi creare i filtri.
* Per i componenti delle dimensioni e delle metriche, il [Generatore di filtri rapidi](#quick-filter-builder) crea automaticamente una condizione `exists`. Se, ad esempio, trascini `City`, viene creata la condizione `City exists`.
* Per i valori di dimensione, il [Generatore di filtri rapidi](#quick-filter-builder) crea automaticamente una condizione `equals`. Se, ad esempio, trascini `amsterdam` dalla dimensione `City`, viene creata la condizione `City equals amsterdam`.
* Se trascini `unspecified` o `none`, il [Generatore di filtri rapidi](#quick-filter-builder) crea automaticamente una condizione `does not exist`.

I filtri rapidi creati vengono visualizzati nella parte superiore del pannello. I filtri rapidi hanno una barra sottile azzurra a sinistra. Quando un filtro rapido è in modalità di modifica utilizzando il [Generatore di filtri rapidi](#quick-filter-builder), lo sfondo del filtro rapido è azzurro.

I risultati dei filtri rapidi creati in un pannello vengono applicati (utilizzando l’operatore logico AND) a tutte le visualizzazioni che fanno parte del pannello.


## Gestire i

Per gestire un filtro rapido, passa il cursore del mouse sul **[!UICONTROL Quick filter]** specifico.

* Seleziona ![Edit](/help/assets/icons/Edit.svg) per aprire il [Generatore di filtri rapidi](#quick-filter-builder) e modifica il filtro rapido.
* Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per aprire un popup. Nel popup vengono visualizzate informazioni sul filtro. Puoi selezionare **[!UICONTROL Make available to all projects and add to your component list]** per aggiungere il filtro all’elenco dei componenti ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** nel pannello dei componenti. Viene visualizzata una finestra di dialogo **[!UICONTROL Save quick filter]** in cui viene richiesto di specificare un nome per il filtro. Seleziona **[!UICONTROL Save]** per continuare. Il [!UICONTROL Quick filter] diventa un **[!UICONTROL Filter]**. Non puoi più modificare il filtro utilizzando il [Generatore di filtri rapidi](#quick-filter-builder). Devi invece modificare il filtro come un filtro normale, utilizzando il [Generatore di filtri](filter-builder.md).

## Generatore di filtri rapidi

Di seguito è riportato un esempio del Generatore di filtri rapidi. Nell’esempio, il generatore viene aperto per un filtro rapido denominato `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Entrambi i filtri rapidi nella parte superiore si applicano al pannello [!UICONTROL Average Order Value Dashboard] e a tutte le visualizzazioni al suo interno, ad esempio alla tabella a forma libera [!UICONTROL Average Order Value Per Country].

![Generatore di filtri rapidi](assets/quick-filter-builder.png)

Il generatore di filtri rapidi è costituito dalle seguenti aree e pulsanti.

### Area intestazione

L’area dell’intestazione determina il nome, il tipo e l’ambito del filtro rapido. Inoltre, mostra un’immagine dei risultati del filtro rapido.

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Name]** | Il nome viene derivato automaticamente dalla definizione del filtro rapido. |
| **[!UICONTROL People]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alert](/help/assets/icons/Alert.svg) | Visualizza in anteprima l’immagine dei dati risultanti dal filtro rapido. Una barra e una percentuale forniscono informazioni approfondite sulla quantità di dati complessivi che fanno parte del risultato del filtro rapido. Un ![avviso](/help/assets/icons/Alert.svg) rosso segnala che il filtro rapido non restituisce dati. |
| **[!UICONTROL Include]**<br/>**[!UICONTROL Exclude]** | Seleziona dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) se desideri includere o escludere i risultati del filtro rapido dai dati nel pannello. |
| **[!UICONTROL Event]**<br/>**[!UICONTROL Session]**<br/>**[!UICONTROL Person]** | Seleziona dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) l’ambito del filtro rapido. |

### Area condizioni

L’area delle condizioni specifica le condizioni (fino a un massimo di tre). Per ogni condizione puoi specificare quanto segue:

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metric]**<br/>**[!UICONTROL Date range]** | Seleziona dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) se desideri specificare una condizione per una dimensione, una metrica o un intervallo di date. |
| **[!UICONTROL *component *]** | Il campo del componente per la condizione. Puoi [!UICONTROL *Digitare per aggiungere*] un componente, selezionare un componente dall’elenco oppure trascinarlo dal pannello dei componenti. Puoi rilasciare componenti simili solo nel campo componente della condizione. Ad esempio, puoi rilasciare un componente dimensione solo dal pannello dei componenti in una condizione di dimensione. <br/>Puoi anche trascinare un componente per sostituirne uno esistente.<br/>Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per eliminare il componente dal campo del componente. |
| **[!UICONTROL *operator *]** | Operatore del componente. Per ulteriori informazioni, consulta [Operatori](operators.md). Disponibile solo per dimensioni e metriche. |
| **[!UICONTROL *value *]** | Valore della condizione. A seconda dell’operatore selezionato, è possibile selezionare il valore da un elenco o immetterlo. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Seleziona questa opzione per eliminare una condizione dal filtro rapido. |

### Pulsanti

| Pulsante | Descrizione |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Disponibile solo quando si definiscono più condizioni. Seleziona dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) tra le due condizioni. La selezione determina la logica booleana per il filtro rapido. Non è possibile combinare la logica quando si hanno tre condizioni. La logica booleana è **[!UICONTROL AND]** o **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Aggiunge un’altra condizione al filtro rapido. Questo pulsante è disponibile solo se sono state definite una o due condizioni per il filtro rapido. |
| **[!UICONTROL Apply]** | Applica le modifiche al filtro rapido. |
| **[!UICONTROL Open builder]** | Viene richiesta una conferma con una finestra di dialogo **[!UICONTROL Are your sure?]**. Se selezioni **[!UICONTROL OK]**, non sarà più possibile modificare il filtro nel [Generatore di filtri rapidi](#quick-filter-builder). Il filtro rapido verrà rinominato in **[!UICONTROL Filter]** e avrà una sottile barra a sinistra blu più scura.<br/>Viene aperto il [Generatore di filtri](filter-builder.md) regolare con l’opzione **[!UICONTROL Make this filter available to all your projects and add it to your component list]**. <ul><li>Se selezioni questa opzione e poi **[!UICONTROL Apply]**, il filtro verrà aggiunto all’elenco dei componenti ![Filter](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filters]** nel pannello dei componenti.</li><li>Se non selezioni questa opzione ma comunque seleziona **[!UICONTROL Apply]**, il filtro rimane un filtro relativo al solo progetto di Workspace.</li></ul> |
| **[!UICONTROL Cancel]** | Seleziona questa opzione per annullare la creazione o modificare un filtro rapido. |

## Filtri rapidi e Filtri

I filtri rapidi corrispondono esattamente al loro nome. Puoi creare e modificare velocemente i filtri rapidi in linea e vedere immediatamente gli effetti nel pannello.

I filtri presentano i seguenti vantaggi rispetto ai filtri rapidi.

* I filtri possono essere resi disponibili in tutti i progetti Workspace
* I filtri supportano una maggiore complessità utilizzando contenitori nidificati e gerarchici e sequenze (utilizzando filtri di sequenza).


