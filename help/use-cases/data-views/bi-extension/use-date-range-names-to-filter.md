---
title: Utilizza Nomi Di Intervallo Di Date Per Filtrare
description: Utilizzare i nomi degli intervalli di date per filtrare il caso d’uso per l’estensione BI in vari strumenti di business intelligence in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 1%

---

# Utilizzare i nomi degli intervalli di date per filtrare

In questo caso d’uso desideri utilizzare un intervallo di date definito in Customer Journey Analytics per filtrare e segnalare le occorrenze (eventi) dell’ultimo anno.

+++ Customer Journey Analytics

Per creare rapporti utilizzando un intervallo di date, devi impostare un intervallo in Customer Journey Analytics, con **[!UICONTROL Titolo]** `Last Year 2023`.

![Customer Journey Analytics usa i nomi degli intervalli di date per filtrare](../assets/cja-daterange.png)

Puoi quindi utilizzare tale intervallo di date in un esempio **[!UICONTROL Utilizzo dei nomi degli intervalli di date per filtrare]** il pannello del caso d&#39;uso:

![Valori conteggio valori univoci Customer Journey Analytics](../assets/cja-using-date-range-filter-names-to-filter.png)

L’intervallo di date definito nella visualizzazione a forma libera sovrascrive l’intervallo di date applicato al pannello.

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Verificare di aver convalidato [una connessione, di avere la possibilità di elencare le visualizzazioni dati e di utilizzare una visualizzazione dati](connect-and-validate.md) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Desktop Power BI]

1. Nel riquadro **[!UICONTROL Dati]**:
   1. Seleziona **[!UICONTROL daterangemonth]**.
   1. Selezionare **[!UICONTROL daterangeName]**.
   1. Seleziona **[!UICONTROL somma occorrenze]**.

   Visualizzazione con **[!UICONTROL Errore durante il recupero dei dati per questo oggetto visivo]**.

1. Nel riquadro **[!UICONTROL Filtri]**:

   1. Seleziona **[!UICONTROL daterangeName uguale a (All)]** da **[!UICONTROL Filtri per questo oggetto visivo]**.
   1. Selezionare **[!UICONTROL Filtro base]** come **[!UICONTROL Tipo filtro]**.
   1. Sotto il campo **[!UICONTROL Ricerca]**, seleziona **[!UICONTROL Ultimo anno 2023]**, che è il nome dell&#39;intervallo di date definito in Customer Journey Analytics.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL daterangeName]** da **[!UICONTROL Columns]**.

   La tabella viene aggiornata con il filtro **[!UICONTROL daterangeName]** applicato. Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.

   ![Desktop Power BI Con Nomi Di Intervalli Di Date Per Filtrare](../assets/uc8-powerbi-final.png)

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Foglio 1]** nella parte inferiore per passare da **[!UICONTROL Origine dati]**. Nella visualizzazione **[!UICONTROL Foglio 1]**:
   1. Trascina la voce **[!UICONTROL Daterange Name]** dall&#39;elenco **[!UICONTROL Tables]** nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Nome Daterange\]]** verifica che sia selezionato **[!UICONTROL Seleziona dall&#39;elenco]** e seleziona **[!UICONTROL Ultimo anno 2023]** dall&#39;elenco. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Trascina la voce **[!UICONTROL Daterangemonth]** dall&#39;elenco **[!UICONTROL Tabelle]** e rilascia la voce nel campo accanto a **[!UICONTROL Righe]**. Seleziona **[!UICONTROL Daterangemonth]** e seleziona **[!UICONTROL Month]**. Il valore diventa **[!UICONTROL MONTH(Daterangemonth)]**.
   1. Trascina **[!UICONTROL Occorrenze]** dall&#39;elenco **[!UICONTROL Tabelle]** e rilascia la voce nel campo accanto a **[!UICONTROL Colonne]**. Il valore diventa **[!UICONTROL SUM(Occurrences)]**.
   1. Seleziona **[!UICONTROL Tabella di testo]** da **[!UICONTROL Mostra]**.
   1. Selezionare **[!UICONTROL Scambia righe e colonne]** nella barra degli strumenti.
   1. Selezionare **[!UICONTROL Adatta larghezza]** dal menu a discesa **[!UICONTROL Adatta]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      Dimension ![Filtro Classificato Multiplo Desktop Tableau](../assets/uc8-tableau-final.png)

>[!TAB Ricerca]

1. Nell&#39;interfaccia **[!UICONTROL Esplora]** di Looker, assicurati di avere una configurazione pulita. In caso contrario, selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Rimuovi campi e filtri]**.
1. Seleziona **[!UICONTROL + Filtro]** sotto **[!UICONTROL Filtri]**.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi filtro]**:
   1. Seleziona **[!UICONTROL ‣ Visualizzazione Dati Cc]**
   1. Dall&#39;elenco dei campi, selezionare **[!UICONTROL ‣ Nome intervallo]**.
1. Specifica il filtro **[!UICONTROL Cc Data View Daterange Name]** come **[!UICONTROL is]** e seleziona **[!UICONTROL Last Year 2023]** dall&#39;elenco di valori.
1. Dalla sezione **[!UICONTROL ‣ Cc Data View]** nella barra a sinistra:
   1. Seleziona **[!UICONTROL Mese periodo]**, quindi **[!UICONTROL Mese]**.
   1. Seleziona **[!UICONTROL Conteggio]** sotto **[!UICONTROL MISURE]** nella barra a sinistra (in basso).
1. Seleziona **[!UICONTROL Esegui]**.
1. Selezionare **[!UICONTROL ‣ Visualizzazione]**.

Dovresti visualizzare una visualizzazione e una tabella simili a quelle mostrate di seguito.

![Conteggio valori univoci](../assets/uc8-looker-result.png)


>[!TAB Blocco appunti Jupyter]

1. Immettere le istruzioni seguenti in una nuova cella.

   ```python
   data = %sql SELECT daterangeName FROM cc_data_view;
   style = {'description_width': 'initial'}
   daterange_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Date Range Name:',
      style=style
   )
   display(daterange_name)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc8-jupyter-input.png)

1. Seleziona **[!UICONTROL Prodotti della pesca]** dal menu a discesa.

1. Immettere le istruzioni seguenti in una nuova cella.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterangeName = '{daterange_name.value}' \
               GROUP BY 1 \
               ORDER BY Month ASC
   df = data.DataFrame()
   df = df.groupby('Month', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Month', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc8-jupyter-results.png)


>[!TAB StudioRS]

1. Immettere le istruzioni seguenti tra ` ` ``{r} ` e ` `` ` ` in un nuovo blocco. Assicurati di utilizzare il nome dell’intervallo di date appropriato. Ad esempio: `Last Year 2023`.

   ```R
   ## Monthly Events for Last Year
   df <- dv %>%
      filter(daterangeName == "Last Year 2023") %>%
      group_by(daterangemonth) %>%
      count() %>%
      arrange(daterangemonth, .by_group = FALSE)
   ggplot(df, aes(x = daterangemonth, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Esegui il blocco. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati studio](../assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++

