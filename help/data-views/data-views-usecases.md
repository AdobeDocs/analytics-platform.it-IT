---
title: Casi d’uso per le visualizzazioni dati in Customer Journey Analytics
description: Diversi casi d’uso che illustrano la flessibilità e la potenza delle visualizzazioni dati in Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 80f31a77df68dca91c1f9f5a0d521b0ea7d450ce
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 100%

---

# Casi d’uso per le visualizzazioni dati

Questi casi d’uso mostrano la flessibilità e la potenza delle visualizzazioni dati in Customer Journey Analytics.

## 1. Creare una metrica da un campo schema di tipo stringa {#string}

Ad esempio, quando crei una visualizzazione dati, puoi creare una metrica [!UICONTROL Orders] da una campo schema [!UICONTROL pageTitle] di tipo stringa. Ecco come si fa:

1. Nella scheda Components (Componenti), trascina [!UICONTROL pageTitle] nella sezione [!UICONTROL Metrics] in [!UICONTROL Included Components].
   ![](assets/use-case1a.png)
1. Evidenzia la metrica appena trascinata e rinominala in [!UICONTROL Component Settings], a destra:
   ![](assets/orders.png)
1. Apri la finestra di dialogo [!UICONTROL Include/Exclude Values] a destra e specifica quanto segue:
   ![](assets/orders2.png)

   Il termine “confirmation” (conferma) indica che si tratta di un ordine. Dopo aver esaminato tutti i titoli delle pagine che rispondono a tali criteri, viene conteggiato “1” per ogni istanza. Il risultato è una nuova metrica (non una metrica calcolata). Una metrica con valori inclusi o esclusi può essere utilizzata ovunque sia possibile utilizzare qualsiasi altra metrica. Funziona con Attribution IQ, con i filtri e ovunque sia possibile utilizzare le metriche standard.
1. Puoi anche specificare un modello di attribuzione per questa metrica, ad esempio [!UICONTROL Last Touch], con [!UICONTROL Lookback window] impostato su [!UICONTROL Session].
Inoltre, puoi crearne un’altra metrica [!UICONTROL Orders] dallo stesso campo e specificare un altro modello di attribuzione (ad esempio [!UICONTROL First Touch]) e un altro valore di [!UICONTROL Lookback window] (ad esempio [!UICONTROL 30 days]).

Oppure, potresti voler utilizzare l’ID visitatore, una dimensione, come metrica per determinare quanti ID visitatore ha la tua azienda.

## 2. Utilizzare numeri interi come dimensioni {#integers}

In precedenza, i numeri interi venivano trattati automaticamente come metriche in CJA. Ora i valori numerici (compresi gli eventi personalizzati da Adobe Analytics) possono essere trattati come dimensioni. Ecco un esempio:

1. Trascina il numero intero [!UICONTROL call_length_min] nella sezione [!UICONTROL Dimensions] in [!UICONTROL Included Components]:

   ![](assets/integers.png)

1. Ora puoi aggiungere [!UICONTROL Value Bucketing] per presentare questa dimensione sotto forma di bucket nei rapporti. (Senza bucket, ogni istanza della dimensione si presenta come una voce distinta nei rapporti di Workspace.)

   ![](assets/bucketing.png)

## 3. Utilizzare le dimensioni numeriche come “metriche” nei diagrammi di flusso {#numeric}

Puoi utilizzare una dimensione numerica per inserire “metriche” nella visualizzazione [!UICONTROL  Flow].

1. Nella scheda [Components](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=it#configure-component-settings) (Componenti) delle visualizzazioni dati, trascina il campo schema [!UICONTROL Marketing Channels] nell’area [!UICONTROL Metrics] in [!UICONTROL Included components].
2. Nei rapporti di Workspace, questo flusso mostra come [!UICONTROL Marketing Channels] scorre in [!UICONTROL Orders]:

![](assets/flow.png)

## 4. Applicare filtri agli eventi secondari {#sub-event}

Questa funzionalità è specifica per i campi basati su array. La funzionalità di inclusione/esclusione consente di filtrare a livello di evento secondario; i filtri (segmenti) generati nel generatore di filtri consentono invece di filtrare solo a livello di evento. Pertanto, puoi filtrare gli eventi secondari mediante inclusione/esclusione nelle visualizzazioni dati, e quindi fare riferimento a tale nuova metrica o dimensione in un filtro a livello di evento.

Ad esempio, utilizza la funzionalità di inclusione/esclusione nelle visualizzazioni dati per concentrarti solo sui prodotti che hanno generato vendite per più di 50 dollari. Se un ordine include l’acquisto di un prodotto da 50 dollari e un prodotto da 25 dollari, non verrà rimosso l’intero ordine ma solo l’acquisto del prodotto da 25 dollari.

1. Nella scheda [Components](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings) (Componenti) delle visualizzazioni dati, trascina il campo schema [!UICONTROL Revenue] nell’area [!UICONTROL Metrics] in [!UICONTROL Included components].
1. Seleziona la metrica e configura quanto segue a destra:
a. Per [!UICONTROL Format], seleziona [!UICONTROL Currency].
b. Per [!UICONTROL Currency], seleziona USD.
c. Per [!UICONTROL Include/Exclude Values], seleziona la casella di controllo accanto a [!UICONTROL Set include/exclude values].
d. Per [!UICONTROL Match], seleziona [!UICONTROL If all criteria are met].
e. Per [!UICONTROL Criteria], seleziona [!UICONTROL is greater than or equal].
f. Specifica il valore “50”.

Con queste nuove impostazioni verranno visualizzati solo i ricavi di alto valore, escludendo tutto ciò che è inferiore a 50 dollari.

## 5. Utilizzare l’impostazione [!UICONTROL No Value Options] {#no-value}

La tua azienda può aver dedicato del tempo a insegnare agli utenti ad aspettarsi “Unspecified” (Non specificato) nei rapporti. Il valore predefinito nelle visualizzazioni dati è “No Value” (Nessun valore). Ora nell’interfaccia utente delle visualizzazioni dati puoi [cambiare “No Value” in “Unspecified”](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=it#configure-no-value-options-settings). 

Oppure, nel caso della dimensione per la registrazione a un programma di iscrizione, puoi cambiare “No Value” in “Non registrato al programma di iscrizione”.

## 6. Creare più metriche con impostazioni [!UICONTROL Attribution] diverse {#attribution}

Con la funzione [!UICONTROL Duplicate] in alto a destra, crea alcune metriche Ricavi con impostazioni di attribuzione diverse, come [!UICONTROL First Touch], [!UICONTROL Last Touch] e [!UICONTROL Algorithmic].

Non dimenticare di rinominare ogni metrica in base alle differenze, ad esempio “Ricavi algoritmici”:

![](assets/algo-revenue.png)

Per informazioni sulle altre impostazioni di visualizzazione dati, vedi [Creare le visualizzazioni dati](/help/data-views/create-dataview.md).
Per una panoramica concettuale delle visualizzazioni dati, vedi [Panoramica delle visualizzazioni dati](/help/data-views/data-views.md).

## 7. Nuovo reporting sulle sessioni {#new-repeat}

Puoi determinare se una sessione è effettivamente la prima sessione in assoluto per un utente, in base all’intervallo di reporting definito per questa visualizzazione dati e a un intervallo di lookback di 13 mesi. Questo reporting consente di determinare, ad esempio:

* Quale percentuale degli ordini proviene da sessioni nuove?

* Il targeting di un canale di marketing o di una campagna interessa nuovi utenti? In che modo questa scelta influisce sui tassi di conversione?

Una metrica facilita questo reporting:

<!--* 1 dimension: [Session type](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional) - This dimension has two values: 1) [!UICONTROL New] and 2) [!UICONTROL Returning]. The [!UICONTROL New] line item includes all of the behavior (i.e. metrics against this dimension) from a session that has been determined to be a person's defined first session. Everything else is included in the [!UICONTROL Returning] line item (assuming everything belongs to a session). Where metrics are not part of any session, they fall into the 'Not applicable' bucket for this dimension.-->

* [Nuove sessioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=it#optional). Per “nuova sessione” si intende la prima sessione definita per una persona all’interno dell’intervallo di reporting.

   <!--* [Return sessions](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional) Return sessions is the number of sessions that were not a person's first-ever session.-->

Per accedere a questo componente:

1. Passa all’editor della visualizzazione dati.
1. Fai clic sul pulsante **[!UICONTROL Components]** > **[!UICONTROL Optional Standard components]** nella barra a sinistra.
1. Trascina questi componenti nella vista dati.

Il 95%-99% del tempo, le nuove sessioni saranno segnalate con precisione. Le uniche eccezioni sono:

* Quando si è verificata una prima sessione prima dell’intervallo di lookback di 13 mesi. Questa sessione verrà ignorata.

* Quando una sessione si estende sia nell’intervallo di lookback che nell’intervallo di reporting. Supponiamo che tu esegua un rapporto dal 1° giugno al 15 giugno 2022. L’intervallo di lookback includerebbe il periodo dal 1° maggio 2021 al 31 maggio 2022. Se una sessione dovesse iniziare il 30 maggio 2022 e terminare il 1° giugno 2022, poiché la sessione è inclusa nell’intervallo di lookback, tutte le sessioni nell’intervallo di reporting vengono conteggiate come sessioni di ritorno.

<!--## Use the Date and Date-Time functionality {#date}

Schemas in Adobe Experience Platform contain [!UICONTROL Date] and [!UICONTROL Date-Time] fields. CJA data views now support these fields. When you drag these fields into a data view as a dimension, you can specify their [format](/help/data-views/component-settings/format.md). This format setting determines how the fields are displayed in reporting. For example:

* For the Date format, if you select **[!UICONTROL Day]** with the format **[!UICONTROL Month, Day, Year]**, an example output in reporting might look like: August 23, 2022.

* For the Date-Time format, if you select **[!UICONTROL Minute of Day]** with the format **[!UICONTROL Hour:Minute]**, your output might look like: 20:20.

### Example use cases:

* Date: A travel company is collecting the departure date for trips as a field in their data. They would like to have a report which compares the [!UICONTROL Day of Week] for all departure dates collected to understand which is most popular. They would like to do the same for [!UICONTROL Month of Year].

* Date-Time: A retail company is collecting the time for each of their in-store point-of-sale (POS) purchases. Over a given month, they would like to understand the busiest shopping periods by [!UICONTROL Hour of Day].

>[!MORELIKETHIS]
>[Date and Date-Time in the Format component setting](/help/data-views/component-settings/format.md)-->

