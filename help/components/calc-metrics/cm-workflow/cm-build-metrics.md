---
description: Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare Dimension, metriche, filtri e funzioni per creare metriche personalizzate basate sulla logica gerarchica dei contenitori, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare semplici metriche calcolate o metriche calcolate avanzate complesse.
title: Creare metriche
source-git-commit: e50636784e406da84c986645ac380d68d9622bc6
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 10%

---

# Creare metriche

Il Generatore di metriche calcolate fornisce un’area di lavoro per trascinare Dimension, metriche, filtri e funzioni per creare metriche personalizzate basate sulla logica gerarchica dei contenitori, sulle regole e sugli operatori. Questo strumento di sviluppo integrato consente di generare e salvare semplici metriche calcolate o metriche calcolate avanzate complesse.

Esistono diversi modi per accedere al Generatore di metriche calcolate:

* In Analysis Workspace, apri un progetto e fai clic su  **[!UICONTROL + New]** > **[!UICONTROL Create Metric]** .
* In [!DNL Analytics], vai a **[!UICONTROL Components]** > **[!UICONTROL Calculated Metrics]**.

* Fai clic su **[!UICONTROL + Add]** nella parte superiore del [Gestore della metrica calcolata](/help/components/calc-metrics/cm-workflow/cm-manager.md)oppure

* Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, apri un rapporto e fai clic sull’icona Metriche  ![](assets/metrics_icon.png) per visualizzare la barra Metriche , fai clic su **[!UICONTROL Add]**.

![](assets/cm_builder_ui.png)

## Componenti dell’interfaccia utente {#section_9382AEEBA4244DD6A9F6C1DD3F6D076B}

<table id="table_60A82936321047D1A335331BF83B0972"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Titolo </span> </td> 
   <td colname="col3"> <p>La denominazione della metrica è obbligatoria. Non è possibile salvare la metrica a meno che non sia denominata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Descrizione </span> </td> 
   <td colname="col3"> <p>Dategli una descrizione facile da usare per mostrare ciò che viene utilizzato e per distinguerlo da quelli simili. </p> <p>La descrizione viene visualizzata anche all’interno di un rapporto. È meglio NON inserire la formula nella descrizione, ma descrivere per cosa questa metrica dovrebbe e non deve essere utilizzata. La formula viene generata durante la creazione della metrica, sotto l’intestazione Riepilogo . Di conseguenza, non è necessario aggiungere la formula alla descrizione.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Formato </span> </td> 
   <td colname="col3"> <p>Le scelte includono Decimale, Tempo, Percentuale e Valuta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Luoghi decimali </span> </td> 
   <td colname="col3"> <p>Mostra il numero di posizioni decimali da visualizzare nel rapporto. Il numero massimo di posizioni decimali è 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Mostra tendenza verso l'alto come.. </span> </td> 
   <td colname="col3"> <p>Questa impostazione di polarità della metrica indica se Analytics deve considerare una tendenza al rialzo nella metrica buona (verde) o cattiva (rossa). Di conseguenza, il grafico del rapporto sarà visualizzato in verde o rosso quando cresce. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Tag </span> </td> 
   <td colname="col3"> <p>L’assegnazione tag è un buon modo per organizzare le metriche. Tutti gli utenti possono creare tag e applicare uno o più tag a una metrica. Tuttavia, puoi visualizzare solo i tag dei segmenti di tua proprietà o che sono stati condivisi con te. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili: 
     <ul id="ul_9A6CE5F179424687A39F2D5C1A953258"> 
      <li id="li_A8815F2D8D284874AD701A7B103D82A3">Tag basati sui <b>nomi dei team</b>, ad esempio Social Marketing e Mobile Marketing. </li> 
      <li id="li_A51A4515A541488E9D90296A955E9F4F">Tag del <b>progetto</b> (tag di analisi), ad esempio Analisi per pagina di ingresso. </li> 
      <li id="li_B4605470A7094026AC168420B64BBCC3">Tag di <b>categorie</b>: maschile, geografia. </li> 
      <li id="li_B6EAB0F2A96C41209C4EC97B9E64390B">Tag del <b>flusso di lavoro</b>: Da approvare, Curato per (una specifica unità aziendale) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Riepilogo </span> </td> 
   <td colname="col3"> <p>La <span class="uicontrol"> Riepilogo </span> La formula viene aggiornata ogni volta che apporti una modifica alla definizione della metrica. Questa formula viene visualizzata anche nella barra delle metriche a sinistra quando passi il cursore su una metrica e fai clic sul pulsante <img placement="inline"  src="assets/i_icon.png" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icona. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Definizione </span> </td> 
   <td colname="col3"> <p>È qui che trascina metriche/metriche calcolate, segmenti e/o funzioni per creare la metrica calcolata. </p> <p> 
     <ul id="ul_B13401A266354DC594C6176025DB61CB"> 
      <li id="li_01776C32C7C5440AA1F847096CBED92B">Se trascini una metrica calcolata, la definizione della metrica viene automaticamente espansa. </li> 
      <li id="li_A483D352522E4572AB43042473053359">È possibile nidificare le definizioni con i contenitori. Tuttavia, a differenza dei contenitori di segmenti, questi contenitori funzionano come un'espressione matematica e determinano l'ordine delle operazioni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Operatore </span> </td> 
   <td colname="col3"> <p>Diviso da ( <img placement="inline"  src="assets/divided_icon.png" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) è l’operatore predefinito, oltre agli operatori +, - e x. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Anteprima </span> </td> 
   <td colname="col3"> <p>Fornisce una lettura rapida di eventuali errori. L’anteprima copre gli ultimi 90 giorni. Questo è un modo per verificare inizialmente se hai selezionato i componenti giusti per la metrica. Un risultato imprevisto implica la necessità di dare un'occhiata alla definizione della metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Add </span> </td> 
   <td colname="col3"> <p>Per tutti i tipi di metriche calcolate, puoi aggiungere contenitori e numeri statici alla definizione. Per le metriche calcolate avanzate, puoi anche aggiungere segmenti e funzioni. </p> <p> 
     <ul id="ul_607C1B303F334062BC620317667DE490"> 
      <li id="li_53462789B8AF4F1AA9B45565D37CF22B">I contenitori funzionano come un'espressione matematica e determinano l'ordine delle operazioni. Pertanto, qualsiasi elemento in un contenitore viene elaborato prima dell’operazione successiva. </li> 
      <li id="li_401A9E0D8B3B468990289DBF66A06F63">Quando si trascina un segmento su un contenitore, vengono segmentati tutti gli elementi presenti in tale contenitore. (Solo metriche calcolate avanzate) </li> 
      <li id="li_F191B200D7A944F9ADC0573A9A82A6DA">Puoi impilare più segmenti in un contenitore. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Icona ingranaggio ( <span class="uicontrol"> Tipo di metrica </span>, <span class="uicontrol"> Attribuzione </span>) </td> 
   <td colname="col3"> <p>Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare la <a href="/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md"  > tipo di metrica e modelli di attribuzione </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> + Nuovo </span> </td> 
   <td colname="col3"> <p>Consente di creare un nuovo componente, ad esempio un nuovo filtro (che ti porta al <a href="/help/components/filters/create-filters.md"  > Generatore di filtri </a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Componenti di ricerca </p> </td> 
   <td colname="col3"> <p>Questa barra di ricerca consente di cercare dimensioni, metriche, segmenti (solo metriche calcolate avanzate) e funzioni (solo metriche calcolate avanzate). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco dei Dimension </p> </td> 
   <td colname="col3"> <p>Anziché uscire dal Generatore di metriche calcolate per creare un segmento semplice (nel Generatore di segmenti), ad esempio "Pagina = Home page", puoi trascinare in Pagina e selezionare Home page direttamente dal Generatore di metriche calcolate. </p> <p>Questo semplifica il flusso di lavoro per la creazione di metriche calcolate segmentate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco delle metriche </p> </td> 
   <td colname="col3"> <p>Le metriche sono suddivise in 3 categorie: </p> 
    <ul id="ul_7BF50F4964EF45858FBA1634FBFA45CF"> 
     <li id="li_90F2312927A6499CA1CE04F8FFC912CF">Metriche standard ( <img placement="inline"  src="assets/met_icon.png" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li> 
     <li id="li_A3F59083E79B4AC780D6F8CEDFFD20C9">Metriche calcolate ( <img placement="inline"  src="assets/calc_met_icon.png" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li> 
     <li id="li_8735E76637ED4C3F983731A66E04C93E">Modelli di metriche ( <img placement="inline"  src="assets/cm_template_icon.png" width="25px" id="image_D236601511CC4DD3828F223431E27E88" />) - in fondo all'elenco. </li> 
    </ul> <p>Quando passi il puntatore del mouse su una metrica, puoi vedere l’icona Informazioni a destra: <img placement="inline"  src="assets/info.png" width="150px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Fai clic su questa icona per ottenere le seguenti informazioni: </p> 
    <ul id="ul_DF35DDB9FBFA40C8A93FA0F2286A0BBE"> 
     <li id="li_4215AA9BF93F4C8B941002A7A4D2F50B">La formula di calcolo. </li> 
     <li id="li_6A8E39EB6DCE4377B0B594B6D4FC0294">Una tendenza di anteprima della metrica. </li> 
     <li id="li_44C1595E4BE64ED69D1DB3BB6655ED55">Icona di modifica (matita) in alto a destra per passare al generatore di metriche calcolate, dove è possibile modificare la metrica calcolata. </li> 
    </ul> <p><img placement="break" align="center"  src="assets/info2.png" width="200px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco dei filtri </p> </td> 
   <td colname="col3"> <p>(Solo metriche calcolate avanzate) In qualità di Amministratore, questo elenco mostra tutti i filtri creati nella società di accesso. Se non sei un utente amministratore, questo elenco mostra i filtri che possiedi e quelli condivisi con te. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Elenco delle funzioni </p> </td> 
   <td colname="col3"> <p>(Solo metriche calcolate avanzate) Le funzioni sono suddivise in due elenchi: <a href="/help/components/calc-metrics/cm-functions.md"  > Base </a> (utilizzato più spesso) e <a href="/help/components/calc-metrics/cm-adv-functions.md"  > Avanzate </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Selettore della visualizzazione dati </p> </td> 
   <td colname="col3"> <p>Consente di passare a una visualizzazione dati diversa. </p> </td> 
  </tr> 
 </tbody> 
</table>
