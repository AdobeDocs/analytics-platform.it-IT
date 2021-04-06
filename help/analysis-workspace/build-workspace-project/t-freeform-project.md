---
description: Crea un progetto e aggiungi componenti (dimensioni, metriche, filtri, intervalli di date) al pannello a forma libera.
keywords: Analysis Workspace
title: Creare un progetto Workspace
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 84%

---


# Creare un progetto Workspace

Crea un progetto e aggiungi componenti (dimensioni, metriche, filtri, intervalli di date) al pannello a forma libera.

Questo articolo presenta gli elementi dell’interfaccia di Analysis Workspace e mostra come creare un progetto.

## Creazione di un progetto

1. Specifica le autorizzazioni per l’utente per creare e curare progetti.

   Prima di creare o curare un progetto di Analysis Workspace, gli amministratori devono aggiungere gli utenti a un gruppo su cui sia abilitata l’autorizzazione **[!UICONTROL Create / Curate Projects in Analysis Workspace]** oppure al gruppo di utenti **[!UICONTROL All Report Access]**. ( **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > [Gruppi](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=it-IT)).

1. In [!DNL Experience Cloud], fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**.

   ![](assets/analysis_workspace_menu.png)

   In alternativa, inserisci una barra (/) per aprire la barra di ricerca del rapporto, quindi digita *`workspace`*.

   ![](assets/analysis-app-search.png)

1. Fai clic su **[!UICONTROL Create New Project]**.

   Puoi scegliere di creare un progetto in base a

* Un progetto vuoto (impostazione predefinita). Per le istruzioni del caso, leggi di seguito.
* Un modello personalizzato. Questi modelli vengono creati da utenti provvisti di diritti di amministratore.

   ![](assets/start_modal.png)

1. Per creare un nuovo progetto da un progetto vuoto, fai clic su **[!UICONTROL Blank Project]**.

   * Quindi fai clic su **[!UICONTROL Create]**, oppure
   * Fai clic su **[!UICONTROL Enter]**.

   Viene visualizzato un progetto vuoto con un pannello a forma libera e una visualizzazione della tabella di dati.

   ![](assets/fa_project_new.png)

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > Componenti</a> </td> 
   <td colname="col2"> <p>Dimension, metriche, filtri e intervalli di date che puoi trascinare nei progetti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Visualizzazioni</a> </td> 
   <td colname="col2"> <p>Elementi da trascinare nel pannello o nelle aree di progetto dell’interfaccia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md"  >Pannello a forma libera</a> </td> 
   <td colname="col2"> <p>Area di lavoro con la quale interagisci in Analysis Workspace. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salva il progetto. Assegna un nome al progetto, fornisci una descrizione (facoltativa, ma utile) e assegna i tag desiderati al progetto (facoltativo), quindi fai clic su **[!UICONTROL Save Project]**.

   ![](assets/save_project.png)

1. Ora puoi fare clic con il pulsante destro del mouse e copiare una visualizzazione o un pannello, quindi incollare (inserire) l’elemento copiato in un’altra posizione all’interno del progetto o in un progetto diverso.

   Puoi utilizzare questa funzionalità per creare “blocchi costitutivi” (visualizzazioni/pannelli predefiniti) che possono essere copiati in altri progetti da avviare più rapidamente, con dati specifici della tua attività.

   >[!NOTE]
   >
   >Dopo l’operazione di copia o salvataggio con nome, gli intra-link sono relativi al progetto a cui sono collegati, non a quello originale dal quale sono stati copiati.

## Aggiungere componenti e visualizzazioni {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. Crea il progetto trascinando *`components`* (Componenti) e *`visualizations`* (Visualizzazioni) nel progetto.

   **Componenti**

   La barra degli strumenti Componenti visualizza le dimensioni, le metriche, i filtri e gli intervalli di date ricercabili utilizzati più frequentemente.

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensioni (arancione) </td> 
   <td colname="col2"> <p>Sono componenti a livello di progetto </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Ai nomi delle dimensioni vengono aggiunti i numeri relativi a proprietà, variabili ed eventi (prop#, eVar#, event#) ed è possibile eseguire delle ricerche in base a tali numeri. Esempio: “Internal Campaign” compare nella barra a sinistra come “Internal Campaign (evar2)”. </p> <p> Tieni presente che i numeri di proprietà, variabili ed eventi non sono riportati nella tabella (per evitare titoli troppo lunghi). </p> <p>Alcune dimensioni predefinite vengono ordinate in modo prestabilito quando vengono trascinate in una tabella a forma libera o visualizzate nella barra a sinistra. Ad esempio, se la dimensione “Ora del giorno” viene rilasciata in una tabella o visualizzata nella barra a sinistra, verrà ordinata dalle 00:00 alle 23:00. L’opzione di ordinamento per qualsiasi colonna di metrica rimane valida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metriche (verde) </td> 
   <td colname="col2"> <p>Sono componenti a livello di progetto. </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> Occorrenze</span> è la metrica predefinita selezionata per la tabella di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtri (blu) </td> 
   <td colname="col2"> <p>È trascinabile solo a livello di pannello, ma è possibile creare filtri in linea nella tabella di dati. </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>Per ulteriori informazioni, consulta <a href="/help/analysis-workspace/components/t-freeform-project-segment.md"  > Filtri </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalli di date e granularità temporali (viola) </td> 
   <td colname="col2"> <p>Sono trascinabili solo a livello di pannello. In fase di configurazione di un intervallo di date, puoi creare un progetto direttamente dal calendario. </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[Visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

Il pannello [!UICONTROL Visualizations] fornisce grafici, grafici a torta, tabelle di dati, tabelle di [coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), diagrammi di Venn e così via nel formato standard di Analytics. Puoi trascinare diverse visualizzazioni all’interno del progetto.

![Risultato passaggio](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. Passaggio

## Usa il menu di scelta rapida per personalizzare i dati {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

Il menu di scelta rapida consente di effettuare le seguenti azioni in base alla cella su cui fai clic con il pulsante destro, all’interno di una tabella.

![Risultato passaggio](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Azione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Aggiunta di una colonna di periodi temporali</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Confronto tra periodi temporali</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copia negli Appunti </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elimina selezionati </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > Crea avviso da selezione</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > Suddividi</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">Dimensioni </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">Metriche </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">Filtri </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">Tempo </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > Creazione di visualizzazioni</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/curate-share/download-send.md"  > Scarica come CSV</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/home.md"  > Selezione di tendenze</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analysis-workspace/components/t-freeform-project-segment.md"  > Crea filtro da selezione</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzare solo le righe selezionate </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizza tutte le righe </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Vedi [Interazioni con la tastiera e con il mouse in Analysis Workspace](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) per ulteriori informazioni su come copiare e selezionare le righe.
