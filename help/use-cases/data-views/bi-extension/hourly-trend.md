---
title: Tendenza oraria
description: Caso di utilizzo dell’andamento orario per l’estensione BI in vari strumenti di business intelligence in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Tendenza oraria


## Tendenza oraria

In questo caso d’uso, vuoi visualizzare una tabella e una semplice visualizzazione delle linee che mostri una tendenza oraria di occorrenze(eventi) per il 1° gennaio 2023.

+++ Customer Journey Analytics

Un esempio di pannello **[!UICONTROL Tendenza oraria]** per il caso d&#39;uso:

![Visualizzazioni delle tendenze orarie di Customer Journey Analytics](../assets/cja_hourly_trend.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Verificare di aver convalidato [una connessione, di avere la possibilità di elencare le visualizzazioni dati e di utilizzare una visualizzazione dati](connect-and-validate.md) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Desktop Power BI]

![AlertRed](/help/assets/icons/AlertRed.svg) Power BI **non** comprende come gestire i campi data-ora, pertanto dimensioni come **[!UICONTROL daterangehour]** e **[!UICONTROL daterangeminute]** non sono supportate.

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Foglio 1]** nella parte inferiore per passare da **[!UICONTROL Origine dati]**. Nella visualizzazione **[!UICONTROL Foglio 1]**:
   1. Trascina la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tabelle]** nel riquadro **[!UICONTROL Dati]** e rilasciala nello scaffale **[!UICONTROL Filtri]**.
   1. Nella finestra di dialogo **[!UICONTROL Campo filtri \[Daterange\]]**, seleziona **[!UICONTROL Intervallo di date]** e seleziona **[!UICONTROL Avanti >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Daterange\]]**, seleziona **[!UICONTROL Intervallo di date]** e specifica un periodo compreso tra `01/01/2023` e `02/01/2023`.

      ![Filtro Desktop Tableau](../assets/uc3-tableau-filter.png)

   1. Trascina **[!UICONTROL Daterangehour]** dall&#39;elenco **[!UICONTROL Tabelle]** nel riquadro **[!UICONTROL Dati]** e rilascia la voce nel campo accanto a **[!UICONTROL Colonne]**.
      * Seleziona **[!UICONTROL Altro]** > **[!UICONTROL Ore]** dal menu a discesa **[!UICONTROL Daterangeday]**, in modo che il valore venga aggiornato a **[!UICONTROL ORA(Daterangeday)]**.
   1. Trascina e rilascia **[!UICONTROL Occorrenze]** dall&#39;elenco **[!UICONTROL Tabelle (*Nomi misure*)]** nel riquadro **[!UICONTROL Dati]** e rilascia la voce nel campo accanto a **[!UICONTROL Righe]**. Il valore viene convertito automaticamente in **[!UICONTROL SUM(Occurrences)]**.
   1. Modificare **[!UICONTROL Standard]** in **[!UICONTROL Vista intera]** dal menu a discesa **[!UICONTROL Adatta]** nella barra degli strumenti.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Grafico Desktop Tableau](../assets/uc3-tableau-graph.png)

1. Selezionare **[!UICONTROL Duplica]** dal menu di scelta rapida della scheda **[!UICONTROL Foglio 1]** per creare un secondo foglio.
1. Selezionare **[!UICONTROL Rinomina]** dal menu di scelta rapida della scheda **[!UICONTROL Foglio 1]** per rinominare il foglio in `Graph`.
1. Selezionare **[!UICONTROL Rinomina]** dal menu di scelta rapida della scheda **[!UICONTROL Foglio 1 (2)]** per rinominare il foglio in `Data`.
1. Verifica che il foglio **[!UICONTROL Dati]** sia selezionato. Nella visualizzazione **[!UICONTROL Dati]**:
   1. Seleziona **[!UICONTROL Mostra]** in alto a destra e seleziona **[!UICONTROL Tabella di testo]** (visualizzazione in alto a sinistra) per modificare il contenuto della visualizzazione dati in una tabella.
   1. Trascina **[!UICONTROL HOUR(Daterangeday)]** da **[!UICONTROL Columns]** a **[!UICONTROL Rows]**.
   1. Modificare **[!UICONTROL Standard]** in **[!UICONTROL Vista intera]** dal menu a discesa **[!UICONTROL Adatta]** nella barra degli strumenti.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dati Desktop Tableau](../assets/uc3-tableau-data.png)

1. Seleziona il pulsante della scheda **[!UICONTROL Nuovo dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascina e rilascia il foglio del **[!UICONTROL Grafico]** dallo scaffale **[!UICONTROL Fogli]** nella visualizzazione **[!UICONTROL Dashboard 1]** che contiene *Rilascia qui i fogli*.
   1. Trascina e rilascia il foglio **[!UICONTROL Dati]** dallo scaffale **[!UICONTROL Fogli]** sotto il foglio **[!UICONTROL Grafico]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Selezionare il foglio **[!UICONTROL Dati]** nella visualizzazione e modificare **[!UICONTROL Vista intera]** in **[!UICONTROL Larghezza fissa]**.

      La visualizzazione **[!UICONTROL Dashboard 1]** dovrebbe essere simile a quella riportata di seguito.

      ![Dashboard desktop Tableau 1](../assets/uc3-tableau-dashboard.png)


>[!TAB Ricerca]


1. Nell&#39;interfaccia **[!UICONTROL Esplora]** di Looker, assicurati di avere una configurazione pulita. In caso contrario, selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Rimuovi campi e filtri]**.
1. Seleziona **[!UICONTROL + Filtro]** sotto **[!UICONTROL Filtri]**.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi filtro]**:
   1. Seleziona **[!UICONTROL ‣ Visualizzazione Dati Cc]**
   1. Dall&#39;elenco dei campi, selezionare **[!UICONTROL ‣ Data intervallo]** e quindi **[!UICONTROL Data intervallo]**.
      ![Filtro ricerca](../assets/uc2-looker-filter.png)
1. Specifica Il Filtro **[!UICONTROL Cc Data Daterange Visualizzazione Dati]** Perché **[!UICONTROL È Compreso Nell&#39;Intervallo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL Fino A (Prima)]** **[!UICONTROL 2023/01/02]**.
1. Dalla sezione **[!UICONTROL Visualizzazione dati Cc]** nella barra a sinistra,
   1. Seleziona **[!UICONTROL ‣ Data Daterangehour]**, quindi **[!UICONTROL Ora]** dall&#39;elenco di **[!UICONTROL DIMENSIONI]**.
   1. Seleziona **[!UICONTROL Conteggio]** sotto **[!UICONTROL MISURE]** nella barra a sinistra (in basso).
1. Seleziona **[!UICONTROL Esegui]**.
1. Selezionare **[!UICONTROL ‣ Visualizzazione]** per visualizzare la visualizzazione delle linee.

Dovresti visualizzare una visualizzazione e una tabella simili a quelle mostrate di seguito.

![Tendenza giornaliera risultati ricerca](../assets/uc3-looker-result.png)


>[!TAB Blocco appunti Jupyter]

1. Immettere le istruzioni seguenti in una nuova cella.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangehour AS Hour, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-01-02' \
               GROUP BY 1 \
                ORDER BY Hour ASC
   df = data.DataFrame()
   df = df.groupby('Hour', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Hour', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc3-jupyter-results.png)


>[!TAB StudioRS]

1. Immettere le istruzioni seguenti tra ` ```{r} ` e ` ``` ` in un nuovo blocco.

   ```R
   ## Hourly Events
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-01-02") %>%
      group_by(daterangehour) %>%
      count() %>%
      arrange(daterangehour, .by_group = FALSE)
   ggplot(df, aes(x = daterangehour, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Esegui il blocco. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati studio](../assets/uc3-rstudio-results.png)

>[!ENDTABS]

+++
