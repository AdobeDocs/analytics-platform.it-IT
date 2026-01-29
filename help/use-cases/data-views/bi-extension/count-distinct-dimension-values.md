---
title: Dimensioni con conteggio valori distinti
description: 'Caso di utilizzo: conteggio di valori distinti per l’estensione BI in vari strumenti di business intelligence in Customer Journey Analytics'
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 0%

---

# Contare dimensioni con valori distinti


In questo caso d’uso, vuoi ottenere il numero distinto di nomi di prodotto che sono stati segnalati durante gennaio 2023.

+++ Customer Journey Analytics

Per generare rapporti su un numero distinto di nomi di prodotto, hai impostato una metrica calcolata in Customer Journey Analytics, con **[!UICONTROL Titolo]** `Product Name (Count Distinct)` e **[!UICONTROL ID esterno]** `product_name_count_distinct`.

![Metrica calcolata per il nome prodotto Customer Journey Analytics (conteggio valori univoci)](../assets/cja-calc-metric-distinct-count-product-names.png)

Puoi quindi utilizzare tale metrica in un pannello di esempio **[!UICONTROL Conteggio valori Dimension distinti]** per il caso d&#39;uso:

![Valori conteggio valori univoci Customer Journey Analytics](../assets/cja-count-distinct-dimension-values.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Verificare di aver convalidato [una connessione, di avere la possibilità di elencare le visualizzazioni dati e di utilizzare una visualizzazione dati](connect-and-validate.md) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Desktop Power BI]

1. Per fare in modo che l&#39;intervallo di date venga applicato a tutte le visualizzazioni, trascina **[!UICONTROL daterangeday]** dal riquadro **[!UICONTROL Dati]** in **[!UICONTROL Filtri]** in questa pagina.
   1. Seleziona **[!UICONTROL daterangeday è (Tutto)]** da **[!UICONTROL Filtri su questa pagina]**.
   1. Selezionare **[!UICONTROL Filtro avanzato]** come **[!UICONTROL Tipo filtro]**.
   1. Definisci il filtro per **[!UICONTROL mostrare gli elementi quando il valore]** **[!UICONTROL è attivo o successivo]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL è precedente]** `2/1/2023`.
   1. Selezionare **[!UICONTROL Applica filtro]**.

1. Nel riquadro **[!UICONTROL Dati]**:
   1. Seleziona **[!UICONTROL datarangeday]**.
   1. Seleziona **[!UICONTROL sum cm_product_name_count_distinct]**, che è la metrica calcolata definita in Customer Journey Analytics.

1. Per modificare il grafico a barre verticale in un oggetto Table, verificare che il grafico sia selezionato e selezionare **[!UICONTROL Table]** dal riquadro **[!UICONTROL Visualizations]**.

   Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.

   ![Tabella distinta per conteggio multiplo desktop Power BI](../assets/uc7-powerbi-table.png)

1. Seleziona la visualizzazione della tabella. Dal menu di scelta rapida, selezionare **[!UICONTROL Copia]** > **[!UICONTROL Copia elemento visivo]**.
1. Incolla la visualizzazione utilizzando **[!UICONTROL ctrl-v]**. La copia esatta della visualizzazione si sovrappone a quella originale. Spostala a destra nell’area del rapporto.
1. Per modificare la visualizzazione copiata da una tabella a una scheda, seleziona **[!UICONTROL Scheda]** da **[!UICONTROL Visualizzazioni]**.

   Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.

   ![Tabella distinta per conteggio multiplo desktop Power BI](../assets/uc7-powerbi-final.png)

In alternativa, puoi utilizzare la funzionalità di conteggio dei valori univoci di Power BI.

1. Seleziona la dimensione **[!UICONTROL product_name]**.
1. Applica la funzione **[!UICONTROL Count (Distinct)]** alla dimensione **[!UICONTROL product_name]** in **[!UICONTROL Columns]**.

   ![Conteggio valori univoci Power BI](../assets/uc7-powerbi-alternative.png)



>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Foglio 1]** nella parte inferiore per passare da **[!UICONTROL Origine dati]**. Nella visualizzazione **[!UICONTROL Foglio 1]**:
   1. Trascina la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tabelle]** nel riquadro **[!UICONTROL Dati]** e rilasciala nello scaffale **[!UICONTROL Filtri]**.
   1. Nella finestra di dialogo **[!UICONTROL Campo filtro \[Daterange\]]**, seleziona **[!UICONTROL Intervallo di date]** e seleziona **[!UICONTROL Avanti >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Daterange\]]**, selezionare **[!UICONTROL Intervallo di date]**, quindi selezionare `01/01/2023` - `31/1/2023`. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Trascina **[!UICONTROL Cm Product Name Count Distinct]** In **[!UICONTROL Rows]**. Il valore cambia in **[!UICONTROL SUM(Cm Product Name Count Distinct)]**. Questo campo è la metrica calcolata definita in Customer Journey Analytics.
   1. Trascina **[!UICONTROL Daterangeday]** e rilascia accanto a **[!UICONTROL Colonne]**. Seleziona **[!UICONTROL Giorno]** e dal menu a discesa seleziona **[!UICONTROL Giorno]**.
   1. Per modificare la visualizzazione delle righe in una tabella, selezionare **[!UICONTROL Tabella testo]** da **[!UICONTROL Mostra]**.
   1. Selezionare **[!UICONTROL Scambia righe e colonne]** nella barra degli strumenti.
   1. Selezionare **[!UICONTROL Adatta larghezza]** dal menu a discesa **[!UICONTROL Adatta]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      Dimension ![Filtro Classificato Multiplo Desktop Tableau](../assets/uc7-tableau-data.png)

1. Selezionare **[!UICONTROL Duplica]** dal menu di scelta rapida della scheda **[!UICONTROL Foglio 1]** per creare un secondo foglio.
1. Selezionare **[!UICONTROL Rinomina]** dal menu di scelta rapida della scheda **[!UICONTROL Foglio 1]** per rinominare il foglio in `Data`.
1. Selezionare **[!UICONTROL Rinomina]** dal menu di scelta rapida della scheda **[!UICONTROL Foglio 1 (2)]** per rinominare il foglio in `Card`.

1. Verifica di aver selezionato la visualizzazione **[!UICONTROL Scheda]**.
1. Seleziona **[!UICONTROL GIORNO(Giorno)]** e dal menu a discesa seleziona **[!UICONTROL Mese]**. Il valore diventa **[!UICONTROL MONTH(Daterangeday)]**.
1. Seleziona **[!UICONTROL SUM(Cm Product Name Count Distinct)]** in **[!UICONTROL Indicatori]** e dal menu a discesa seleziona **[!UICONTROL Formato]**.
1. Per modificare la dimensione del carattere, nel riquadro **[!UICONTROL Formato SUM(CM Product Name Count Distinct)]**, selezionare **[!UICONTROL Carattere]** in **[!UICONTROL Predefinito]** e selezionare **[!UICONTROL 72]** per la dimensione del carattere.
1. Per allineare il numero, selezionare **[!UICONTROL Automatico]** accanto a **[!UICONTROL Allineamento]** e impostare **[!UICONTROL Orizzontale]** su Centrato.
1. Per utilizzare numeri interi, selezionare **[!UICONTROL 123.456]** accanto a **[!UICONTROL Numeri]** e selezionare **[!UICONTROL Numero (personalizzato)]**. Imposta **[!UICONTROL Cifre decimali]** su `0`.

   Il desktop Tableau dovrebbe essere simile al seguente.

   Dimension ![Filtro Classificato Multiplo Desktop Tableau](../assets/uc7-tableau-card.png)

1. Seleziona il pulsante della scheda **[!UICONTROL Nuovo dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascina e rilascia il foglio **[!UICONTROL Scheda]** dallo scaffale **[!UICONTROL Fogli]** nella visualizzazione **[!UICONTROL Dashboard 1]** che contiene *Rilascia qui i fogli*.
   1. Trascina e rilascia il foglio **[!UICONTROL Dati]** dallo scaffale **[!UICONTROL Fogli]** sotto il foglio **[!UICONTROL Scheda]** nella visualizzazione **[!UICONTROL Dashboard 1]**.

   La visualizzazione **[!UICONTROL Dashboard 1]** dovrebbe essere simile a quella riportata di seguito.

   ![Dashboard desktop Tableau 1](../assets/uc7-tableau-final.png)


In alternativa, puoi utilizzare la funzionalità di conteggio dei valori univoci di Tableau Desktop.

1. Utilizza **[!UICONTROL Nome Prodotto]** invece di **[!UICONTROL Cm Nome Prodotto Distinto]**.
1. Applica **[!UICONTROL Misura]** > **[!UICONTROL Conteggio (distinto)]** a **[!UICONTROL Nome prodotto]** in **[!UICONTROL Indicatori]**.

   ![Conteggio Tableau Distinct](../assets/uc7-tableau-alternative.png)


>[!TAB Ricerca]

1. Nell&#39;interfaccia **[!UICONTROL Esplora]** di Looker, assicurati di avere una configurazione pulita. In caso contrario, selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Rimuovi campi e filtri]**.
1. Seleziona **[!UICONTROL + Filtro]** sotto **[!UICONTROL Filtri]**.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi filtro]**:
   1. Seleziona **[!UICONTROL ‣ Visualizzazione Dati Cc]**
   1. Dall&#39;elenco dei campi, selezionare **[!UICONTROL ‣ Data intervallo]** e quindi **[!UICONTROL Data intervallo]**.
      ![Filtro ricerca](../assets/uc2-looker-filter.png)
1. Specifica Il Filtro **[!UICONTROL Cc Data Daterange Visualizzazione Dati]** Perché **[!UICONTROL È Compreso Nell&#39;Intervallo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL Fino A (Prima)]** **[!UICONTROL 2023/02/01]**.
1. Dalla sezione **[!UICONTROL ‣ Cc Data View]** nella barra a sinistra:
   1. Seleziona **[!UICONTROL Data intervallo]**, quindi **[!UICONTROL Data]**.
   1. Selezionare **[!UICONTROL Aggregate Count Distinct]** dal menu di scelta rapida **⋮ More** in **[!UICONTROL Product Name]**.
      ![Menu di scelta rapida nome prodotto ricerca](../assets/uc7-looker-count-distinct.png)
1. Seleziona **[!UICONTROL Esegui]**.
1. Selezionare **[!UICONTROL ‣ Visualizzazione]** e selezionare 6︎⃣ dalla barra degli strumenti per visualizzare una visualizzazione con valore singolo.

Dovresti visualizzare una visualizzazione e una tabella simili a quelle mostrate di seguito.

![Conteggio valori univoci](../assets/uc7-looker-result.png)


>[!TAB Blocco appunti Jupyter]

1. Immettere le istruzioni seguenti in una nuova cella.

   ```
   data = %sql SELECT COUNT(DISTINCT(product_name)) AS `Product Name` \
      FROM cc_data_view \
      WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01';
   display(data)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc7-jupyter-results.png)


>[!TAB StudioRS]

1. Immettere le istruzioni seguenti tra ` ```{r} ` e ` ``` ` in un nuovo blocco.

   ```R
   ## Count Distinct
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      summarise(product_name_count_distinct = n_distinct(product_name))
   print(df)
   ```

1. Esegui il blocco. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati studio](../assets/uc7-rstudio-results.png)


>[!ENDTABS]

+++

