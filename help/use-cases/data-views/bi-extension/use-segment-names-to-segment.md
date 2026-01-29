---
title: Utilizzare I Nomi Dei Segmenti Per Segmentare
description: Utilizzare i nomi dei segmenti per segmentare il caso d’uso per l’estensione BI in vari strumenti di business intelligence in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 1%

---

# Utilizzare i nomi dei segmenti per segmentare

In questo caso d’uso, vuoi utilizzare un segmento esistente per la categoria di prodotti della pesca, che hai definito in Customer Journey Analytics. Per segmentare e creare rapporti sui nomi dei prodotti e sulle occorrenze (eventi) durante gennaio 2023.

+++ Customer Journey Analytics

Esamina il segmento che desideri utilizzare in Customer Journey Analytics.

![Customer Journey Analytics Utilizza Nomi Filtro Per Filtrare](../assets/cja-fishing-products.png)

È quindi possibile utilizzare tale segmento in un esempio **[!UICONTROL Utilizzo dei nomi dei segmenti nel pannello Segmento]** per il caso d&#39;uso:

![Valori conteggio valori univoci Customer Journey Analytics](../assets/cja-using-filter-names-to-filter.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Verificare di aver convalidato [una connessione, di avere la possibilità di elencare le visualizzazioni dati e di utilizzare una visualizzazione dati](connect-and-validate.md) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Desktop Power BI]

1. Nel riquadro **[!UICONTROL Dati]**:
   1. Seleziona **[!UICONTROL daterange]**.
   1. Selezionare **[!UICONTROL filterName]**.
   1. Seleziona **[!UICONTROL product_name]**.
   1. Seleziona **[!UICONTROL somma occorrenze]**.

Visualizzazione con **[!UICONTROL Errore durante il recupero dei dati per questo oggetto visivo]**.

1. Nel riquadro **[!UICONTROL Filtri]**:

   1. Seleziona **[!UICONTROL filterName is (All)]** from **[!UICONTROL Filters on this visual]**.
   1. Selezionare **[!UICONTROL Filtro base]** come **[!UICONTROL Tipo filtro]**.
   1. Sotto il campo **[!UICONTROL Ricerca]**, selezionare **[!UICONTROL Prodotti per la pesca]**, che è il nome del filtro esistente definito in Customer Journey Analytics.
   1. Seleziona **[!UICONTROL l&#39;intervallo di dati è (Tutto)]** da **[!UICONTROL Filtri per questo elemento visivo]**.
   1. Selezionare **[!UICONTROL Filtro avanzato]** come **[!UICONTROL Tipo filtro]**.
   1. Definisci il filtro per **[!UICONTROL mostrare gli elementi quando il valore]** **[!UICONTROL è attivo o successivo]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL è precedente]** `2/1/2023`.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL filterName]** da **[!UICONTROL Columns]**.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL daterange]** da **[!UICONTROL Colonne]**.

   La tabella viene aggiornata con il filtro **[!UICONTROL filterName]** applicato. Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.

   ![Desktop Power BI Con Nomi Di Intervalli Di Date Per Filtrare](../assets/uc9-powerbi-final.png)


>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Foglio 1]** nella parte inferiore per passare da **[!UICONTROL Origine dati]**. Nella visualizzazione **[!UICONTROL Foglio 1]**:
   1. Trascina la voce **[!UICONTROL Nome filtro]** dall&#39;elenco **[!UICONTROL Tabelle]** nello scaffale **[!UICONTROL Filtri]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Nome filtro\]]** verifica che **[!UICONTROL Seleziona dall&#39;elenco]** sia selezionato e seleziona **[!UICONTROL Prodotti della pesca]** dall&#39;elenco. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Trascina la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tabelle]** nello scaffale **[!UICONTROL Filtri]**.
   1. Nella finestra di dialogo **[!UICONTROL Campo filtro \[Daterange\]]**, seleziona **[!UICONTROL Intervallo di date]** e seleziona **[!UICONTROL Avanti >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Daterang\]]**, selezionare **[!UICONTROL Intervallo di date]**, quindi selezionare `01/01/2023` - `01/02/2023`. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Trascina **[!UICONTROL Nome prodotto]** dall&#39;elenco **[!UICONTROL Tabelle]** a **[!UICONTROL Righe]**.
   1. Trascina **[!UICONTROL Occorrenze]** dall&#39;elenco **[!UICONTROL Tabelle]** e rilascia la voce nel campo accanto a **[!UICONTROL Colonne]**. Il valore diventa **[!UICONTROL SUM(Occurrences)]**.
   1. Seleziona **[!UICONTROL Tabella di testo]** da **[!UICONTROL Mostra]**.
   1. Selezionare **[!UICONTROL Adatta larghezza]** dal menu a discesa **[!UICONTROL Adatta]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      Dimension ![Filtro Classificato Multiplo Desktop Tableau](../assets/uc9-tableau-final.png)

>[!TAB Ricerca]

1. Nell&#39;interfaccia **[!UICONTROL Esplora]** di Looker, assicurati di avere una configurazione pulita. In caso contrario, selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Rimuovi campi e filtri]**.
1. Seleziona **[!UICONTROL + Filtro]** sotto **[!UICONTROL Filtri]**.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi filtro]**:
   1. Seleziona **[!UICONTROL ‣ Visualizzazione Dati Cc]**
   1. Dall&#39;elenco dei campi, selezionare **[!UICONTROL ‣ Data intervallo]** e quindi **[!UICONTROL Data intervallo]**.
      ![Filtro ricerca](../assets/uc2-looker-filter.png)
1. Specifica Il Filtro **[!UICONTROL Cc Data Daterange Visualizzazione Dati]** Perché **[!UICONTROL È Compreso Nell&#39;Intervallo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL Fino A (Prima)]** **[!UICONTROL 2023/02/01]**.
1. Seleziona **[!UICONTROL + Filtro]** sotto **[!UICONTROL Filtri]** per aggiungere un altro filtro.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi filtro]**:
   1. Seleziona **[!UICONTROL ‣ Visualizzazione Dati Cc]**
   1. Dall&#39;elenco dei campi selezionare **[!UICONTROL ‣ Nome filtro]**.
1. Assicurarsi che **[!UICONTROL sia]** la selezione per il filtro.
1. Seleziona **[!UICONTROL Prodotti della pesca]** dall&#39;elenco dei valori possibili.
1. Dalla sezione **[!UICONTROL ‣ Cc Data View]** nella barra a sinistra:
   1. Selezionare **[!UICONTROL Nome prodotto]**.
   1. Seleziona **[!UICONTROL Conteggio]** sotto **[!UICONTROL MISURE]** nella barra a sinistra (in basso).
1. Seleziona **[!UICONTROL Esegui]**.
1. Selezionare **[!UICONTROL ‣ Visualizzazione]**.

Dovresti visualizzare una visualizzazione e una tabella simili a quelle mostrate di seguito.

![Conteggio valori univoci](../assets/uc9-looker-result.png)



>[!TAB Blocco appunti Jupyter]

1. Immettere le istruzioni seguenti in una nuova cella.

   ```python
   data = %sql SELECT filterName FROM cc_data_view;
   style = {'description_width': 'initial'}
   filter_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Filter Name:',
      style=style
   )
   display(filter_name)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc9-jupyter-input.png)

1. Seleziona **[!UICONTROL Prodotti della pesca]** dal menu a discesa.

1. Immettere le istruzioni seguenti in una nuova cella.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
                  AND filterName = '{filter_name.value}' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc9-jupyter-results.png)


>[!TAB StudioRS]

1. Immettere le istruzioni seguenti tra ` ```{r} ` e ` ``` ` in un nuovo blocco. Assicurati di utilizzare il nome del filtro appropriato. Ad esempio: `Fishing Products`.

   ```R
   ## Dimension filtered by name
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & filterName == "Fishing Products") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. Esegui il blocco. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati studio](../assets/uc9-rstudio-results.png)


>[!ENDTABS]

+++
