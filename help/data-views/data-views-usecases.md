---
title: Casi d’uso per le visualizzazioni dati in Customer Journey Analytics
description: Diversi casi d’uso che illustrano la flessibilità e la potenza delle visualizzazioni dati in Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 9321831a23c1329000fd1e960c28e41d4ba18714
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 81%

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

## 7. Reporting sulla sessione nuovi e ripetuti {#new-repeat}

Puoi determinare se una sessione è effettivamente la prima sessione in assoluto per un utente, in base all’intervallo di reporting definito per questa visualizzazione dati e a un intervallo di lookback di 13 mesi. Questo reporting consente di determinare, ad esempio:

* Quale percentuale degli ordini proviene da sessioni nuove rispetto a sessioni ripetute?

* Per un dato canale di marketing, o una campagna specifica, esegui il targeting di utenti nuovi o di ritorno? In che modo queste scelte influenzano i tassi di conversione?

Tre componenti facilitano questo reporting:

* 1 dimensione: [tipo di sessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=it#optional) - Questa dimensione ha due valori: 1) [!UICONTROL New] e 2) [!UICONTROL Returning]. L&#39;elemento riga [!UICONTROL New] include tutti i comportamenti (ovvero le metriche rispetto a questa dimensione) di una sessione che è stata determinata come prima sessione definita da una persona. Tutto il resto è incluso nell&#39;elemento riga [!UICONTROL Returning] (supponendo che tutto appartenga a una sessione). Se le metriche non fanno parte di alcuna sessione, rientrano nel bucket &quot;Non applicabile&quot; per questa dimensione.

* 2 metriche: [nuove sessioni, sessioni di ritorno](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional). Una nuova sessione è definita come prima sessione definita da una persona all’interno dell’intervallo di reporting. Le sessioni di ritorno sono il numero di sessioni che non sono state le prime sessioni di una persona.

Per accedere a questi componenti:

1. Passa all’editor della visualizzazione dati.
1. Fai clic sul pulsante **[!UICONTROL Components]** > **[!UICONTROL Optional Standard components]** nella barra a sinistra.
1. Trascina questi componenti nella visualizzazione dati.

Il 95%-99% del tempo, le nuove sessioni vengono riportate con precisione. Le uniche eccezioni sono:

* Quando si è verificata una prima sessione prima dell’intervallo di lookback di 13 mesi. Questa sessione verrà ignorata.

* Quando una sessione si estende sia nell’intervallo di lookback che nell’intervallo di reporting. Supponiamo che tu esegua un rapporto dal 1° giugno al 15 giugno 2022. L’intervallo di lookback includerebbe dal 1° maggio 2021 al 31 maggio 2022. Se una sessione dovesse iniziare il 30 maggio 2022 e terminare il 1° giugno 2022, poiché la sessione è inclusa nell’intervallo di lookback, tutte le sessioni nell’intervallo di reporting saranno conteggiate come sessioni di ritorno.

## Utilizzare la funzionalità Data e ora {#date}

>[!NOTE]
>
>Questa funzionalità è attualmente in [fase di test](/help/release-notes/releases.md).

Gli schemi in Adobe Experience Platform contengono [!UICONTROL Date] e [!UICONTROL Date-Time] campi. Le visualizzazioni dati CJA ora supportano questi campi. Quando trascini questi campi in una visualizzazione dati come dimensione, puoi specificare le relative [format](/help/data-views/component-settings/format.md). Questa impostazione di formato determina la modalità di visualizzazione dei campi nel reporting. Ad esempio:

* Per il formato Data, se si seleziona **[!UICONTROL Day]** con il formato **[!UICONTROL Month, Day, Year]**, un output di esempio nel reporting potrebbe essere simile al seguente: 23 agosto 2022.

* Per il formato data-ora, se si seleziona **[!UICONTROL Minute of Day]** con il formato **[!UICONTROL Hour:Minute]**, l&#39;output potrebbe essere simile al seguente: 20:20.

### Esempi di casi di utilizzo:

* Data: Una società di viaggi sta raccogliendo la data di partenza per i viaggi come un campo nei loro dati. Vorrebbero avere una relazione che compari i [!UICONTROL Day of Week] per tutte le date di partenza raccolte per capire quale è più popolare. Vorrebbero fare lo stesso per [!UICONTROL Month of Year].

* Data e ora: Una società retail sta raccogliendo il tempo necessario per ciascuno dei suoi acquisti in-store point-of-sale (POS). In un dato mese, vorrebbero capire i periodi di acquisto più impegnativi per [!UICONTROL Hour of Day].

>[!MORELIKETHIS]
>[Data e ora nell’impostazione del componente Formato](/help/data-views/component-settings/format.md)

