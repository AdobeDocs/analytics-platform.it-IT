---
title: Classifica più Dimension
description: Caso di utilizzo con classificazione di più dimensioni per l’estensione BI in vari strumenti di business intelligence in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 1%

---

# Classificazione di più dimensioni


In questo caso d’uso, vuoi visualizzare una tabella che suddivida i ricavi e gli acquisti di acquisto per i nomi dei prodotti all’interno delle categorie di prodotti nel corso del 2023. Inoltre, è necessario utilizzare alcune visualizzazioni per illustrare sia la distribuzione della categoria di prodotto che i contributi dei nomi dei prodotti all’interno di ogni categoria di prodotto.

+++ Customer Journey Analytics

Un esempio di pannello **[!UICONTROL Più Dimension classificati]** per il caso d&#39;uso:

![Pannello Classifica più Dimension di Customer Journey Analytics](../assets/cja-multiple-dimension-ranked.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Verificare di aver convalidato [una connessione, di avere la possibilità di elencare le visualizzazioni dati e di utilizzare una visualizzazione dati](connect-and-validate.md) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Desktop Power BI]

1. Per fare in modo che l&#39;intervallo di date venga applicato a tutte le visualizzazioni, trascina **[!UICONTROL daterangeday]** dal riquadro **[!UICONTROL Dati]** su **[!UICONTROL Filtri in questa pagina]**.
   1. Seleziona **[!UICONTROL daterangeday è (Tutto)]** da **[!UICONTROL Filtri su questa pagina]**.
   1. Seleziona **[!UICONTROL Data relativa]** come **[!UICONTROL Tipo filtro]**.
   1. Definisci il filtro per **[!UICONTROL mostrare gli elementi quando il valore]** **[!UICONTROL è negli ultimi]** `1` **[!UICONTROL anni di calendario]**.
   1. Selezionare **[!UICONTROL Applica filtro]**.

1. Nel riquadro **[!UICONTROL Dati]**:
   1. Seleziona **[!UICONTROL datarangeday]**.
   1. Seleziona **[!UICONTROL categoria_prodotto]**.
   1. Seleziona **[!UICONTROL product_name]**.
   1. Seleziona **[!UICONTROL somma ricavi_acquisto]**
   1. Seleziona **[!UICONTROL somma acquisti]**

1. Per modificare il grafico a barre verticale in un oggetto Table, verificare che la tabella sia selezionata e selezionare **[!UICONTROL Matrice]** dal riquadro **[!UICONTROL Visualizzazioni]**.
   * Trascina **[!UICONTROL product_name]** da **[!UICONTROL Columns]** e rilascia il campo sotto **[!UICONTROL product_categor]**y in **[!UICONTROL Rows]** nel riquadro **[!UICONTROL Visualization]**.

1. Per limitare il numero di prodotti visualizzati all&#39;interno della tabella, selezionare **[!UICONTROL product_name is (All)]** nel riquadro **[!UICONTROL Filters]**.

   1. Selezionare **[!UICONTROL Filtro avanzato]**.
   1. Seleziona **[!UICONTROL Tipo filtro]** **[!UICONTROL Primo N]** **[!UICONTROL Mostra elementi]** **[!UICONTROL Primi]** `15` **[!UICONTROL Per Valore]**.
   1. Trascina **[!UICONTROL acquisti]** dal riquadro **[!UICONTROL Dati]** in **[!UICONTROL Aggiungi campi dati qui]**.
   1. Selezionare **[!UICONTROL Applica filtro]**.

1. Per migliorare la leggibilità, seleziona **[!UICONTROL Visualizza]** dal menu principale, quindi seleziona **[!UICONTROL Visualizzazione pagina]** > **[!UICONTROL Dimensioni effettive]** e ridimensiona la visualizzazione della tabella.

1. Per suddividere ogni categoria nella tabella, selezionare **[!UICONTROL +]** a livello di categoria del prodotto. Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.

   ![Tabella matrice con classificazione dimensioni multiple desktop Power BI](../assets/uc6-powerbi-data.png)

1. Seleziona **[!UICONTROL Home]** dal menu principale, quindi seleziona **[!UICONTROL Nuovo elemento visivo]**. Al report viene aggiunta una nuova visualizzazione.

1. Nel riquadro **[!UICONTROL Dati]**:
   1. Seleziona **[!UICONTROL categoria_prodotto]**.
   1. Seleziona **[!UICONTROL product_name]**.
   1. Seleziona **[!UICONTROL entrate_acquisti]**.

1. Per modificare l&#39;elemento visivo, selezionare il grafico a barre e selezionare **[!UICONTROL Mappa ad albero]** dal riquadro **[!UICONTROL Visualizzazioni]**.
1. Assicurati che **[!UICONTROL product_category]** sia elencato sotto **[!UICONTROL Category]** e che **[!UICONTROL product_name]** sia elencato sotto **[!UICONTROL Details]** nel riquadro **[!UICONTROL Visualizations]**.

   Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.

   ![Mappa ad albero con classificazione dimensioni multiple Power BI Desktop](../assets/uc6-powerbi-treemap.png)

1. Seleziona **[!UICONTROL Home]** dal menu principale, quindi seleziona **[!UICONTROL Nuovo elemento visivo]**. Al report viene aggiunta una nuova visualizzazione.

1. Nel riquadro **[!UICONTROL Dati]**:
   1. Seleziona **[!UICONTROL categoria_prodotto]**.
   1. Seleziona **[!UICONTROL entrate_acquisti]**.
   1. Seleziona **[!UICONTROL acquisto]**.

1. Nel riquadro **[!UICONTROL Visualizzazioni]**:
   1. Per modificare la visualizzazione, selezionare **[!UICONTROL Grafico a linee e istogramma in pila]**.
   1. Trascina **[!UICONTROL sum_of_purchases]** dall&#39;**[!UICONTROL asse y della colonna]** all&#39;**[!UICONTROL asse y della linea]**.

1. Nel rapporto, ridistribuisci le singole visualizzazioni.

   Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.

   ![Dimensioni multiple desktop Power BI classificate finali](../assets/uc6-powerbi-final.png)


>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Foglio 1]** nella parte inferiore per passare da **[!UICONTROL Origine dati]**. Nella visualizzazione **[!UICONTROL Foglio 1]**:
   1. Trascina la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tabelle]** nel riquadro **[!UICONTROL Dati]** e rilasciala nello scaffale **[!UICONTROL Filtri]**.
   1. Nella finestra di dialogo **[!UICONTROL Campo filtri \[Daterange\]]**, seleziona **[!UICONTROL Intervallo di date]** e seleziona **[!UICONTROL Avanti >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Daterange\]]**, seleziona **[!UICONTROL Date relative]**, seleziona **[!UICONTROL Anni]** e specifica **[!UICONTROL Anno precedente]**. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      Dimension ![Filtro Classificato Multiplo Desktop Tableau](../assets/uc6-tableau-filter.png)

   1. Trascina **[!UICONTROL Categoria prodotto]** e rilascia accanto a **[!UICONTROL Colonne]**.
   1. Trascina **[!UICONTROL Ricavi acquisti]** e rilascia accanto a **[!UICONTROL Righe]**. Il valore diventa **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Trascina gli acquisti e rilascia accanto a **[!UICONTROL Righe]**. Il valore diventa **[!UICONTROL SUM(Purchases)]**.
   1. Selezionare **[!UICONTROL SOMMA(Acquisti)]** e dal menu a discesa selezionare **[!UICONTROL Asse doppio]**.
   1. Selezionare **[!UICONTROL SUM(Purchases)]** in **[!UICONTROL Marks]** e selezionare **[!UICONTROL Line]** dal menu a discesa.
   1. Seleziona **[!UICONTROL SUM(Purchase Revenue)]** in **[!UICONTROL Marks]** e seleziona **[!UICONTROL Bar]** dal menu a discesa.
   1. Selezionare **[!UICONTROL Vista intera]** dal menu **[!UICONTROL Adatta]**.
   1. Seleziona il titolo **[!UICONTROL Ricavi acquisti]** nel grafico e assicurati che i ricavi dell&#39;acquisto siano in ordine crescente.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Categoria Classificata Più Dimensioni Desktop Tableau](../assets/uc6-tableau-category.png)

1. Rinomina il **[!UICONTROL foglio 1]** corrente in `Category`.
1. Selezionare **[!UICONTROL Nuovo foglio di lavoro]** per creare un nuovo foglio e rinominarlo in `Data`.

   1. Trascina la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tabelle]** nel riquadro **[!UICONTROL Dati]** e rilasciala nello scaffale **[!UICONTROL Filtri]**.
   1. Nella finestra di dialogo **[!UICONTROL Campo filtri \[Daterange\]]**, seleziona **[!UICONTROL Intervallo di date]** e seleziona **[!UICONTROL Avanti >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Daterange\]]**, seleziona **[!UICONTROL Date relative]**, seleziona **[!UICONTROL Anni]** e specifica **[!UICONTROL Anno precedente]**. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Trascina **[!UICONTROL Ricavi acquisti]** dal riquadro **[!UICONTROL Dati]** a **[!UICONTROL Colonne]**. Il valore diventa **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Trascina **[!UICONTROL Acquisto]** dal riquadro **[!UICONTROL Dati]** a **[!UICONTROL Colonne]**, accanto a **[!UICONTROL Ricavi acquisti]**. Il valore diventa **[!UICONTROL SUM(Purchases)]**.
   1. Trascina **[!UICONTROL Categoria prodotto]** dal riquadro **[!UICONTROL Dati]** a **[!UICONTROL Righe]**.
   1. Trascina **[!UICONTROL Nome prodotto]** dal riquadro **[!UICONTROL Dati]** a **[!UICONTROL Righe]**, accanto a **[!UICONTROL Categoria prodotto]**.
   1. Per modificare le due barre orizzontali in una tabella, selezionare **[!UICONTROL Tabella testo]** da **[!UICONTROL Mostra]**.
   1. Per limitare il numero di prodotti, selezionare **[!UICONTROL Acquisti]** in **[!UICONTROL Valori di misura]**. Dal menu a discesa, selezionare **[!UICONTROL Filtro]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Purchases\]]**, seleziona **[!UICONTROL Almeno]** e immetti `7000`. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Selezionare **[!UICONTROL Adatta larghezza]** dal menu a discesa **[!UICONTROL Adatta]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dati Classificati Più Dimension Desktop Tableau](../assets/uc6-tableau-data.png)

1. Selezionare **[!UICONTROL Nuovo foglio di lavoro]** per creare un nuovo foglio e rinominarlo in **[!UICONTROL Mappa ad albero]**.
   1. Trascina la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tabelle]** nel riquadro **[!UICONTROL Dati]** e rilasciala nello scaffale **[!UICONTROL Filtri]**.
   1. Nella finestra di dialogo **[!UICONTROL Campo filtri \[Daterange\]]**, seleziona **[!UICONTROL Intervallo di date]** e seleziona **[!UICONTROL Avanti >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Daterange\]]**, seleziona **[!UICONTROL Date relative]**, seleziona **[!UICONTROL Anni]** e specifica **[!UICONTROL Anno precedente]**. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Trascina **[!UICONTROL Ricavi acquisti]** dal riquadro **[!UICONTROL Dati]** a **[!UICONTROL Righe]**. I valori diventano **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Trascina **[!UICONTROL Acquisto]** dal riquadro **[!UICONTROL Dati]** a **[!UICONTROL Righe]**, accanto a **[!UICONTROL Ricavi acquisti]**. Il valore diventa **[!UICONTROL SUM(Purchases)]**.
   1. Trascina **[!UICONTROL Categoria prodotto]** dal riquadro **[!UICONTROL Dati]** a **[!UICONTROL Colonne]**.
   1. Trascina **[!UICONTROL Nome prodotto]** dal riquadro **[!UICONTROL Dati]** a **[!UICONTROL Colonne]**.
   1. Per trasformare i due grafici a barre verticali in una mappa ad albero, selezionare **[!UICONTROL Mappa ad albero]** da **[!UICONTROL Mostra]**.
   1. Per limitare il numero di prodotti, selezionare **[!UICONTROL Acquisti]** in **[!UICONTROL Valori di misura]**. Dal menu a discesa, selezionare **[!UICONTROL Filtro]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Purchases\]]**, seleziona **[!UICONTROL Almeno]** e immetti `7000`. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Selezionare **[!UICONTROL Adatta larghezza]** dal menu a discesa **[!UICONTROL Adatta]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dati Classificati Più Dimension Desktop Tableau](../assets/uc6-tableau-treemap.png)

1. Seleziona il pulsante della scheda **[!UICONTROL Nuovo dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascinare e rilasciare il foglio **[!UICONTROL Categoria]** dallo scaffale **[!UICONTROL Fogli]** nella visualizzazione **[!UICONTROL Dashboard 1]** che contiene *Rilasciare i fogli qui*.
   1. Trascina e rilascia il foglio **[!UICONTROL Mappa ad albero]** dallo scaffale **[!UICONTROL Fogli]** sotto il foglio **[!UICONTROL Categoria]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Trascina e rilascia il foglio **[!UICONTROL Dati]** dallo scaffale **[!UICONTROL Fogli]** sotto il foglio **[!UICONTROL Mappa ad albero]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Ridimensionare ciascun foglio nella vista.

   La visualizzazione **[!UICONTROL Dashboard 1]** dovrebbe essere simile a quella riportata di seguito.

   ![Dashboard desktop Tableau 1](../assets/uc6-tableau-final.png)


>[!TAB Ricerca]

1. Nell&#39;interfaccia **[!UICONTROL Esplora]** di Looker, assicurati di avere una configurazione pulita. In caso contrario, selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Rimuovi campi e filtri]**.
1. Seleziona **[!UICONTROL + Filtro]** sotto **[!UICONTROL Filtri]**.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi filtro]**:
   1. Seleziona **[!UICONTROL ‣ Visualizzazione Dati Cc]**
   1. Dall&#39;elenco dei campi, selezionare **[!UICONTROL ‣ Data intervallo]** e quindi **[!UICONTROL Data intervallo]**.
      ![Filtro ricerca](../assets/uc2-looker-filter.png)
1. Specifica Il Filtro **[!UICONTROL Cc Data Daterange Visualizzazione Dati]** Perché **[!UICONTROL È Compreso Nell&#39;Intervallo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL Fino A (Prima)]** **[!UICONTROL 2024/01/01]**.
1. Dalla sezione **[!UICONTROL ‣ Cc Data View]** nella barra a sinistra:
   1. Seleziona **[!UICONTROL Categoria prodotto]**.
   1. Selezionare **[!UICONTROL Nome prodotto]**.
1. Dalla sezione **[!UICONTROL ‣ Campi personalizzati]** nella barra a sinistra:
   1. Selezionare **[!UICONTROL Misura personalizzata]** dal menu a discesa **[!UICONTROL + Aggiungi]**.
   1. Nella finestra di dialogo **[!UICONTROL Crea misura personalizzata]**:
      1. Seleziona **[!UICONTROL Ricavi acquisti]** dal menu a discesa **[!UICONTROL Campo da misurare]**.
      1. Selezionare **[!UICONTROL Somma]** dal menu a discesa **[!UICONTROL Tipo di misura]**.
      1. Immettere un nome di campo personalizzato per **[!UICONTROL Nome]**. Ad esempio: `Sum of Purchase Revenue`.
      1. Selezionare la scheda **[!UICONTROL Dettagli campo]**.
      1. Seleziona **[!UICONTROL Decimali]** dal menu a discesa **[!UICONTROL Formato]** e assicurati che `0` sia inserito in **[!UICONTROL Decimali]**.
         ![Campo di metrica personalizzato](../assets/uc5-looker-customfield.png)
      1. Seleziona **[!UICONTROL Salva]**.
   1. Seleziona ancora **[!UICONTROL Misura personalizzata]** dal menu a discesa **[!UICONTROL + Aggiungi]**. Nella finestra di dialogo **[!UICONTROL Crea misura personalizzata]**:
      1. Seleziona **[!UICONTROL Acquisti]** dal menu a discesa **[!UICONTROL Campo da misurare]**.
      1. Selezionare **[!UICONTROL Somma]** dal menu a discesa **[!UICONTROL Tipo di misura]**.
      1. Immettere un nome di campo personalizzato per **[!UICONTROL Nome]**. Ad esempio: `Sum of Purchases`.
      1. Selezionare la scheda **[!UICONTROL Dettagli campo]**.
      1. Seleziona **[!UICONTROL Decimali]** dal menu a discesa **[!UICONTROL Formato]** e assicurati che `0` sia inserito in **[!UICONTROL Decimali]**.
      1. Seleziona **[!UICONTROL Salva]**.
   1. Entrambi i campi vengono aggiunti automaticamente alla visualizzazione Dati.
1. Nella sezione **[!UICONTROL Filtri]**, selezionare **[!UICONTROL + Filtro]**. Nella finestra di dialogo **[!UICONTROL Aggiungi filtro]** Selezionare **[!UICONTROL ‣ campi personalizzati]**, quindi **[!UICONTROL Ricavi acquisti]**.
1. Seleziona **[!UICONTROL è >]** e immetti `800000` per limitare i risultati.
1. Seleziona **[!UICONTROL Esegui]**.
1. Selezionare **[!UICONTROL ‣ Visualizzazione]** per visualizzare la visualizzazione delle linee.
1. Seleziona **[!UICONTROL Modifica]** in **[!UICONTROL Visualizzazione]** per aggiornare la visualizzazione. Nella finestra di dialogo popup:
   1. Selezionare la scheda **[!UICONTROL Traccia]**.
   1. Scorri verso il basso e seleziona **[!UICONTROL Modifica configurazione grafico]**.
   1. Modifica il JSON in **[!UICONTROL Configurazione grafico (sostituzione)]** come nella schermata seguente, quindi seleziona **[!UICONTROL Anteprima]**.

      ![Configurazione visualizzazione looker](../assets/uc6-looker-visualization.png)

   1. Seleziona **[!UICONTROL Applica]**.
   1. Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) accanto a **[!UICONTROL Modifica]** per nascondere la finestra di dialogo a comparsa

Dovresti visualizzare una visualizzazione e una tabella simili a quelle mostrate di seguito.

![Tendenza giornaliera risultati ricerca](../assets/uc6-looker-result.png)


>[!TAB Blocco appunti Jupyter]

1. Immettere le istruzioni seguenti in una nuova cella.

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_category AS `Product Category`, product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1, 2 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby(['Product Category', 'Product Name'], as_index=False).sum()
   plt.figure(figsize=(8, 8))
   sns.scatterplot(x='Product Category', y='Product Name', size='Purchase Revenue', sizes=(10, 200), hue='Purchases', palette='husl', data=df)
   plt.show()
   display(data)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc6-jupyter-results.png)


>[!TAB StudioRS]

1. Immettere le istruzioni seguenti tra ` ```{r} ` e ` ``` ` in un nuovo blocco.

   ```R
   ## Multiple dimensions ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_category, product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. Esegui il blocco. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati studio](../assets/uc6-rstudio-results.png)


>[!ENDTABS]

+++
