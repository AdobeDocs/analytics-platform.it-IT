---
description: Scopri come creare una mappa visiva di qualsiasi metrica in  Analysis Workspace.
title: Mappa
translation-type: tm+mt
source-git-commit: ab1ea4c75c4c28f196c6793a819ce4dbe656d52c
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 97%

---


# Mappa

## Panoramica {#section_19F740FAF08D47B1AF1EF239A74FC75C}

La visualizzazione mappa in Analysis Workspace: 

* Consente di creare una mappa visiva di qualsiasi metrica (comprese le metriche calcolate) ed
* è utile per identificare e confrontare dati di metriche per diverse aree geografiche;
* supporta due origini di dati: latitudine/longitudine per l’utilizzo da dispositivo mobile e dimensione geografica per l’utilizzo Web;
* supporta l’esportazione PDF;
* sfrutta la visualizzazione grafica WebGL; se il driver della scheda grafica non supporta il rendering WebGL, può essere necessario aggiornare i driver.

## Creare una visualizzazione mappa {#section_61BBFA3A7BFD48DA8D305A69D9416299}

1. Dall’elenco delle visualizzazioni, trascina **[!UICONTROL Map]** (Mappa) in un pannello a forma libera:

   ![](assets/map-viz1.png)

1. Trascina in essa una metrica dall’elenco delle metriche (comprese le metriche calcolate).
1. Specifica l’origine dati desiderata. Questa finestra di dialogo compare solo se è stato abilitato il tracciamento della posizione per i dati dall’app per dispositivi mobili.

<table id="table_CD54B433464B4282A7524FB187016C47"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Lat./Long. mobile</b> </p> </td> 
   <td colname="col2"> <p>Questa opzione rappresenta i dati provenienti dall’app mobile. </p> <p>Questa opzione è disponibile solo se è stata abilitata per la suite di rapporti in <span class="ignoretag"> <span class="uicontrol"> Analytics </span> &gt; <span class="uicontrol"> Amministratore </span> &gt; <span class="uicontrol"> Suite di rapporti </span> &gt; <span class="uicontrol"> &lt;seleziona una suite di rapporti&gt; </span> &gt; <span class="uicontrol"> Modifica impostazioni </span> &gt; <span class="uicontrol"> Gestione mobile </span> &gt; <span class="uicontrol"> Abilita tracciamento posizione</span></span>. </p> <p>Impostazione predefinita (se è abilitato il tracciamento della posizione). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Dimensione geografica</b> </p> </td> 
   <td colname="col2"> <p>Questa opzione rappresenta i dati per segmentazione geografica sulla posizione del visitatore, in base al suo indirizzo IP. I dati vengono trasformati in Paese, stato/provincia e città. Tieni presente che non arriva invece al livello del codice postale. </p> <p>Questa dimensione è abilitata per quasi tutte le suite di rapporti. Se non lo è, contatta l’Assistenza clienti Adobe e richiedi che vengano abilitati i rapporti geografici. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Fai clic su **[!UICONTROL Build]** (Crea).

   La prima vista sarà quella del mondo con una mappa a bolle, simile a quella illustrata di seguito.

   ![](assets/bubble-world-view.png)

1. A questo punto puoi eseguire le seguenti operazioni: 

   * Fai uno **zoom** nella mappa per ingrandire l’area che ti interessa, facendo doppio clic o utilizzando la rotellina del mouse. La mappa viene ingrandita sul punto in cui si trova il cursore. Quando esegui lo zoom, la dimensione richiesta viene automaticamente aggiornata (Paese > stato/provincia > città), a seconda del livello di zoom.
   * **Confronta** due o più visualizzazioni mappa nello stesso progetto, affiancandole.
   * **Mostra i dati a confronto per specifici periodi (ad esempio, su base annua)**:

      * Mostra numeri negativi: ad esempio, per una metrica su base annua, la mappa può visualizzare -33% su New York.
      * Con metriche di tipo percentuale, la funzione cluster calcola le medie delle percentuali.
      * Schema di colori verde/rosso: positivo/negativo
   * **Ruota** la mappa in 2D o 3D tenendo premuto il tasto [!UICONTROL Ctrl] mentre sposti la mappa.

   * **Passa** a un’altra vista, ad esempio una mappa di calore, utilizzando le [impostazioni](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritte di seguito. La vista predefinita è la mappa a bolle.


1. **Salva** il progetto per salvare tutte le impostazioni della mappa (coordinate, zoom, rotazione).
1. Per compilare la tabella a forma libera, sotto alla visualizzazione, trascina in essa le dimensioni e metriche di posizione dalla barra a sinistra:

   ![](assets/location-dimensions.png)

## Impostazioni della visualizzazione mappa {#section_5F89C620A6AA42BC8E0955478B3A427E}

Per la mappa sono disponibili 2 set di impostazioni:

L’**icona chiave inglese** in alto a destra permette di tornare alla finestra di dialogo iniziale, dove puoi cambiare la metrica e l’origine dati:

![](assets/map-wrench.png)

L’**icona ingranaggio** presenta invece queste impostazioni:

| Impostazione | Descrizione |
|--- |--- |
| Bolle | Traccia gli eventi tramite una rappresentazione a bolle. Un grafico a bolle è un grafico con più variabili, un incrocio tra un grafico a dispersione e un grafico a superfici proporzionali. Questa è la vista predefinita. |
| Mappa di calore | Traccia gli eventi tramite una mappa di calore. Si tratta di una rappresentazione grafica in cui i singoli valori di una matrice sono rappresentati da colori. |
| Stili: Tema colore | Mostra lo schema di colori utilizzato per la mappa di calore e le bolle. Puoi scegliere tra Corallo, Rossi, Verdi e Blu. Il valore predefinito è Corallo. |
| Stili: Stile mappa | Puoi scegliere tra Base, Strade, Vivace, Chiaro, Scuro e Satellite. |
| Raggio cluster | Raggruppa i dati che si trovano entro un certo numero di pixel. Il valore predefinito è 50. |
| Valore massimo personalizzato | Permette di modificare la soglia del valore massimo per la mappa. Quando regoli questo valore, viene regolata la scala dei valori per le bolle o la mappa di calore (colore e dimensioni) rispetto al valore massimo personalizzato impostato. |
