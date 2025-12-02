---
description: Scopri come utilizzare i segmenti rapidi in Analysis Workspace.
title: Segmenti rapidi
feature: Workspace Basics, Filters, Segments
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 17%

---

# Segmenti rapidi

I segmenti rapidi consentono di esplorare rapidamente i dati all&#39;interno di un progetto Workspace, senza dover creare un segmento nel [Generatore di segmenti](/help/components/segments/seg-create.md).



>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmenti rapidi in Analysis Workspace](https://video.tv.adobe.com/v/345338/?captions=ita&quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


Quando desideri utilizzare i segmenti rapidi, tieni presente che:

* I segmenti rapidi vengono creati direttamente in un progetto Workspace. Di conseguenza, un segmento rapido si applica solo al progetto Workspace in cui è stato creato. I segmenti rapidi nel progetto Workspace non sono disponibili in altri progetti e non possono essere condivisi con altri utenti.
* È possibile specificare solo tre condizioni come parte di un segmento rapido.
* I segmenti rapidi non supportano contenitori nidificati o condizioni sequenziali.
* Puoi modificare i segmenti rapidi all’interno di un progetto Workspace condiviso. In questo modo, altri utenti possono modificare i segmenti rapidi in un progetto Workspace condiviso con questi utenti.

## Creazione

I segmenti rapidi si applicano ai pannelli. Puoi creare uno o più segmenti rapidi per ogni pannello del progetto Workspace. Qualsiasi utente in Analysis Workspace può creare segmenti rapidi.

Per creare un segmento rapido:

* Seleziona ![SegmentAdd](/help/assets/icons/FilterAdd.svg) nella parte superiore del pannello. <br/>Quindi, modifica direttamente il segmento nel [Generatore di segmenti rapido](#quick-segment-builder).
* Trascina un componente dal pannello dei componenti alla zona di rilascio del segmento nell’intestazione del pannello. Una volta rilasciato, passa il cursore sul segmento e seleziona ![Modifica](/help/assets/icons/Edit.svg) per modificare il segmento nel [Generatore di segmenti rapidi](#quick-segment-builder).

Quando crei un segmento rapido tramite trascinamento, tieni presente che:

* Non tutti i tipi di componenti sono supportati. Le metriche calcolate non sono supportate e sono supportate solo le dimensioni e le metriche da cui puoi creare i segmenti.
* Per i componenti delle dimensioni e delle metriche, [Generatore di segmenti rapido](#quick-segment-builder) crea automaticamente `exists` condizioni. Ad esempio, se trascini **[!UICONTROL Città]**, viene creata la condizione **[!UICONTROL Città]** **[!UICONTROL esiste]**.
* Per i valori di dimensione, il [Generatore di segmenti rapido](#quick-segment-builder) crea automaticamente una condizione **[!UICONTROL uguale a]**. Ad esempio, se trascini **[!UICONTROL Amsterdam]** dall&#39;elenco delle dimensioni **[!UICONTROL Città]**, verrà creata la condizione **[!UICONTROL Città]** **[!UICONTROL è uguale a]** `Amsterdam`.
* Se trascini **[!UICONTROL non specificato]** o **[!UICONTROL nessuno]**, il [Generatore di segmenti rapidi](#quick-segment-builder) crea automaticamente una condizione **[!UICONTROL non esiste]**.

I segmenti rapidi creati vengono visualizzati nella parte superiore del pannello. I segmenti rapidi hanno una barra a sinistra sottile di colore blu chiaro. Quando un segmento rapido è in modalità di modifica mediante il [Generatore di segmenti rapidi](#quick-segment-builder), lo sfondo del segmento rapido è di colore blu chiaro.

I risultati dei segmenti rapidi creati in un pannello vengono applicati (utilizzando la logica AND) a tutte le visualizzazioni che fanno parte del pannello.


## Gestire i

Per gestire un segmento rapido, passa il cursore del mouse su **[!UICONTROL Segmento rapido]** specifico.

* Seleziona ![Modifica](/help/assets/icons/Edit.svg) per aprire il [Generatore di segmenti rapidi](#quick-segment-builder) e modificare i segmenti rapidi.
* Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per aprire un popup. Nel pop-up vengono visualizzate informazioni sul segmento. Puoi selezionare **[!UICONTROL Rendi disponibile per tutti i progetti e aggiungerlo all&#39;elenco dei componenti]** Per aggiungere il segmento all&#39;elenco dei componenti ![Segmento](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmenti]** nel pannello dei componenti. Viene visualizzata una finestra di dialogo **[!UICONTROL Salva segmento rapido]** in cui viene richiesto di specificare un nome per il segmento. Seleziona **[!UICONTROL Salva]** per continuare. Il [!UICONTROL segmento rapido] si trasforma in **[!UICONTROL segmento]**. Non è più possibile modificare il segmento utilizzando [Generatore di segmenti rapidi](#quick-segment-builder). È invece necessario modificare il segmento come segmento regolare, utilizzando il [Generatore di segmenti](seg-builder.md).

## Generatore di segmenti rapidi

Consulta di seguito un esempio del Generatore di segmenti rapidi. Nell&#39;esempio, il generatore viene aperto per un segmento rapido denominato `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Entrambi i segmenti rapidi nella parte superiore si applicano al pannello **[!UICONTROL Dashboard del valore medio dell&#39;ordine]** e a tutte le visualizzazioni all&#39;interno di, ad esempio la tabella a forma libera [!UICONTROL Valore medio dell&#39;ordine per paese].

![Generatore di segmenti rapidi](assets/quick-filter-builder.png)

Il generatore di segmenti rapidi è costituito dalle seguenti aree e pulsanti.

### Area intestazione

L’area dell’intestazione determina il nome, il tipo e l’ambito del segmento rapido. Inoltre, mostra un’immagine per i risultati del segmento rapido.

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Nome]** | Il nome viene derivato automaticamente dalla definizione del segmento rapido. |
| **[!UICONTROL Persone]** <br/>![CerchioSegno di spunta](/help/assets/icons/CheckmarkCircle.svg) ![Avviso](/help/assets/icons/Alert.svg) | Visualizzazione in anteprima dei dati risultanti dal segmento rapido. Una barra e una percentuale forniscono ad insight la quantità di dati complessivi che fa parte del risultato del segmento rapido. Un ![avviso](/help/assets/icons/AlertRed.svg) segnala che il segmento rapido non restituisce dati. |
| **[!UICONTROL Includi]**<br/>**[!UICONTROL Escludi]** | Seleziona dall&#39;elenco a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) se desideri includere o escludere i risultati del segmento rapido dai dati nel pannello. |
| **[!UICONTROL Evento]**<br/>**[!UICONTROL Sessione]**<br/>**[!UICONTROL Persona]** | Dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg), seleziona l&#39;ambito del segmento rapido. |

### Area condizioni

L’area delle condizioni specifica le condizioni (fino a un massimo di tre). Per ogni condizione puoi specificare quanto segue:

| Elemento | Descrizione |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Metrica]**<br/>**[!UICONTROL Intervallo date]** | Dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg), seleziona se desideri specificare una condizione per una dimensione, una metrica o un intervallo di date. |
| **[!UICONTROL *component *]** | Il campo del componente per la condizione. Puoi [!UICONTROL *Digitare per aggiungere*] un componente, selezionare un componente dall’elenco oppure trascinarlo dal pannello dei componenti. Puoi rilasciare componenti simili solo nel campo componente della condizione. Ad esempio, puoi rilasciare un componente dimensione solo dal pannello dei componenti in una condizione di dimensione. <br/>Puoi anche trascinare un componente per sostituirne uno esistente.<br/>Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per eliminare il componente dal campo del componente. |
| **[!UICONTROL *operator *]** | Operatore del componente. Per ulteriori informazioni, consulta [Operatori](seg-operators.md). Disponibile solo per dimensioni e metriche. |
| **[!UICONTROL *value *]** | Valore della condizione. A seconda dell’operatore selezionato, è possibile selezionare il valore da un elenco o immetterlo. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Seleziona questa opzione per eliminare una condizione dal segmento rapido. |

### Pulsanti

| Pulsante | Descrizione |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Disponibile solo quando si definiscono più condizioni. Selezionare dal menu a discesa ![ChevronDown](/help/assets/icons/ChevronDown.svg) tra le condizioni. La selezione determina la logica booleana per il segmento rapido. Non è possibile combinare la logica quando si hanno tre condizioni. La logica booleana è **[!UICONTROL AND]** o **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Aggiunge un’altra condizione al segmento rapido. Questo pulsante è disponibile solo quando sono state definite una o due condizioni per il segmento rapido. |
| **[!UICONTROL Applica]** | Applica le modifiche al segmento rapido. |
| **[!UICONTROL Apri generatore]** | Viene richiesta una conferma con **[!UICONTROL Continuare?Finestra di dialogo]**. Se si seleziona **[!UICONTROL OK]**, non sarà più possibile modificare il segmento nel [Generatore di segmenti rapidi](#quick-segment-builder). Il segmento rapido verrà rinominato in **[!UICONTROL Segmento]** e ora presenta una barra sinistra blu più scura.<br/>Viene aperto il [Generatore di segmenti](seg-builder.md) regolare con l&#39;opzione di **[!UICONTROL Rendere questo segmento disponibile per tutti i progetti e aggiungerlo all&#39;elenco dei componenti]**. <ul><li>Se si seleziona questa opzione e si seleziona **[!UICONTROL Applica]**, il segmento verrà aggiunto all&#39;elenco dei componenti ![Segmento](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmento]** nel pannello dei componenti.</li><li>Se non si seleziona questa opzione e si seleziona **[!UICONTROL Applica]**, il segmento rimane un segmento solo progetto di Workspace.</li></ul> |
| **[!UICONTROL Annulla]** | Seleziona per annullare la creazione o la modifica di un segmento rapido. |

## Segmenti rapidi e segmenti

I segmenti rapidi sono esattamente ciò che sono denominati. Puoi creare e modificare rapidamente i segmenti rapidi in linea e vedere immediatamente gli effetti nel pannello.

I segmenti presentano i seguenti vantaggi rispetto ai segmenti rapidi.

* I segmenti possono essere resi disponibili in tutti i tuoi progetti Workspace
* I segmenti supportano una maggiore complessità utilizzando [contenitori](seg-builder.md#containers) nidificati e gerarchici e sequenze (utilizzando [segmenti sequenziali](seg-sequential-build.md)).


