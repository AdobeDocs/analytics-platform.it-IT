---
title: Panoramica della tabella coorte
description: Scopri come approfondire i dati sul pubblico e suddividerli in gruppi correlati con l’analisi per coorte. Utilizza l’analisi per coorte in Analysis Workspace.
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
TQID: https://experienceleague.adobe.com/3WB5sKKSaLe9VvAe6rlCTUqDYsG3kiqLCN-KaEtIlDw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: addf009e-030a-4310-8534-776a3e62ed48
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 754
ht-degree: 59%

---

# Panoramica delle tabelle coorte {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Tabella coorte"
>abstract="Crea una visualizzazione per coorte per raggruppare gli utenti in base al completamento di un evento e analizzare il coinvolgimento continuo e l’abbandono nel tempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Tabella coorte"
>abstract="Raggruppa gli utenti in base al completamento di un evento, quindi analizzane il coinvolgimento continuo e l’abbandono nel tempo. Specifica impostazioni aggiuntive come granularità, tipo di analisi per coorte ed eventuale utilizzo del calcolo continuo. Puoi impostare opzioni avanzate per creare una tabella di latenza o una coorte di dimensioni personalizzata in base a una dimensione selezionata."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta la tabella coorte in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulta la [tabella coorte](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis) per la_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** versione di questo articolo._

>[!ENDSHADEBOX]


Una *coorte* è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. Una visualizzazione ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Tabella coorte]** è utile, ad esempio, quando vuoi scoprire in che modo una coorte si relaziona con un brand. Permette di individuare facilmente cambiamenti nelle tendenze e reagire di conseguenza. (Puoi trovare informazioni sull&#39;[!UICONTROL analisi per coorte] sul Web, ad esempio [analisi per coorte 101](https://it.wikipedia.org/wiki/Analisi_di_coorte).)

Dopo aver generato un rapporto sulla coorte, puoi curarne i componenti (dimensioni, metriche e segmenti specifici) e condividerlo con chiunque. Vedi [Cura e condivisione](/help/analysis-workspace/curate-share/curate.md).

Esempi di cosa è possibile fare con una [!UICONTROL tabella coorte]:

* Avvia campagne progettate per stimolare un’azione desiderata.
* Modifica il budget marketing al momento giusto nel ciclo di vita del cliente.
* Riconoscere quando interrompere una versione di prova o un’offerta per massimizzare il valore.
* Sviluppare idee per il test A/B in aree come prezzo, percorso di aggiornamento ecc.

[!UICONTROL La tabella coorte] è disponibile per tutti i clienti Customer Journey Analytics con diritti di accesso a [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analisi per coorte in Analysis Workspace](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL L&#39;analisi per coorte] non supporta metriche non segmentabili (comprese le metriche calcolate), metriche non intere (come Revenue) o Occurrences. Solo le metriche utilizzabili nei segmenti possono essere utilizzate in [!UICONTROL Analisi per coorte] e possono essere incrementate solo di 1 alla volta.

Le tabelle coorte in Customer Journey Analytics supportano metriche basate sul doppio sistema (o su qualsiasi altro sistema numerico). Ad esempio, Purchase.Value (doppio) può essere utilizzato come metrica di inclusione/ritorno. Inoltre, anche tutte le metriche passate in Adobe Experience Platform tramite il connettore di origine di Analytics sono doppie.

## Funzionalità delle tabelle coorte

Le sezioni seguenti descrivono le funzioni di analisi per coorte che consentono un controllo accurato delle coorti che stai creando.

Per informazioni più dettagliate sulla creazione di una coorte e sull&#39;esecuzione di un report di [!UICONTROL Analisi per coorte], vedere [Configurare una tabella per coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Tabella di conservazione

Una tabella coorte [!UICONTROL Mantenimento] restituisce persone: ogni cella di dati mostra il numero e la percentuale di persone nella coorte che hanno eseguito l&#39;azione in quel determinato periodo di tempo. Puoi includere fino a 3 metriche e 10 segmenti.

![Un rapporto di coorte Fidelizzazione che mostra le unità e la percentuale di persone nella coorte.](assets/retention-report.png)

### Tabella di abbandono

Una tabella coorte [!UICONTROL Churn] è l&#39;inverso di una tabella Retention e mostra le persone che non rientrano più o non sono mai rientrate nei criteri della coorte nel tempo. Puoi includere fino a 3 metriche e 10 segmenti.

![Una tabella Abbandono che mostra le unità e la percentuale di persone che non soddisfano i criteri di ritorno di una coorte.](assets/churn-report.png)

### Calcolo continuo

Puoi calcolare il livello di fidelizzazione o abbandono in base alla colonna precedenti, non alla colonna inclusi, a cui si fa riferimento come calcolo continuo.

![Un rapporto di fidelizzazione per coorte che mostra i calcoli basati su una colonna di dati precedenti.](assets/retention-report-rolling.png)

### Tabella latenza

Una tabella di latenza misura il tempo trascorso prima e dopo il verificarsi dell’evento di inclusione. La misura della latenza è un ottimo strumento di analisi pre/post. La colonna **[!UICONTROL Included]** è al centro della tabella e i periodi di tempo precedenti e successivi all&#39;evento di inclusione vengono visualizzati su entrambi i lati.

![Un rapporto di coorte che mostra il tempo trascorso prima e dopo un evento.](assets/retention-report-latency.png)

### Dimensioni coorte personalizzate

Puoi creare le coorti in base a una dimensione selezionata anziché in base al tempo, che è l’impostazione predefinita. Utilizza dimensioni quali [!UICONTROL City geo], [!UICONTROL Marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region] o qualsiasi altra dimensione per mostrare le modifiche apportate alla fidelizzazione. In base ai diversi valori di queste dimensioni.

![Un rapporto sulla coorte che mostra un rapporto personalizzato con dimensioni selezionate, non la coorte predefinita basata sul tempo.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurare una tabella coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)
>

