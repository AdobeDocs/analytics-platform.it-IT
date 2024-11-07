---
title: Casi d'uso per l'estensione BI nel Customer Journey Analytics
description: Diversi casi d’uso che mostrano come utilizzare l’estensione BI in vari strumenti di business intelligence nel Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
source-git-commit: 48310c12680feb30be2cb1ff62e73474ff59e534
workflow-type: tm+mt
source-wordcount: '6888'
ht-degree: 2%

---

# Casi di utilizzo dell’estensione BI

Questo articolo fornisce una serie di casi d’uso che illustrano come utilizzare la funzionalità dell’estensione BI in diversi strumenti di business intelligence.

Sono documentati i seguenti casi d’uso:

1. [Connetti ed elenca le visualizzazioni dati](#connect-and-list-data-views).
1. [Tendenza giornaliera](#daily-trend).
1. [Tendenza oraria](#hourly-trend).
1. [Tendenza mensile](#monthly-trend).
1. [Classificazione dimensione singola](#single-dimension-ranked).
1. [Più dimensioni classificate](#multiple-dimension-ranked).
1. [Conta valori di dimensione distinti](#count-distinct-dimension-values).
1. [Utilizzare i nomi degli intervalli di date per filtrare](#use-date-range-names-to-filter).
1. [Utilizzare i nomi dei filtri per filtrare](#use-filter-names-to-filter).
1. [Utilizzare i valori di dimensione per filtrare](#use-dimension-values-to-filter).
1. [Ordina](#sort).
1. [Limiti](#limits).
1. [Appiattire o meno](#to-flatten-or-not).
1. [Trasformazioni](#object-transformations).
1. [Visualizzazioni](#visualizations)

Il primo caso d’uso riguarda la modalità di connessione degli strumenti BI tramite l’estensione Customer Journey Analytics BI. Per tutti gli altri casi d’uso, sono disponibili istruzioni su come eseguire visualizzazioni di Customer Journey Analytics simili negli strumenti di business intelligence attualmente supportati:

* Power BI Desktop. La versione utilizzata è la 2.137.1102.0 a 64 bit (ottobre 2024).
* Tableau Desktop. La versione utilizzata è 2024.1.5 (20241.24.0705.0334) a 64 bit.


## Connettere ed elencare le visualizzazioni dati

Questo caso d’uso imposta la connessione dallo strumento BI al Customer Journey Analytics ed elenca le visualizzazioni dati disponibili per verificare la connessione.

+++ Customer Journey Analytics

Le istruzioni fanno riferimento a un esempio configurato con i seguenti oggetti:

* Visualizzazione dati **[!UICONTROL C&C - Data View]** ??.
* Dimension **[!UICONTROL Product Name]** ?? e **[!UICONTROL Product Category]** ??.
* Metriche **[!UICONTROL Purchase Revenue]** ?? e **[!UICONTROL Purchases]** ??.
* Filtra **[!UICONTROL Fishing Products]** ??.

![Configurazione base Customer Journey Analytics](assets/cja-base.png)

Quando segui le istruzioni, sostituisci questi oggetti di esempio con oggetti appropriati nel tuo ambiente specifico.

+++

+++ Strumenti BI

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Accedi alle credenziali e ai parametri richiesti dall’interfaccia utente di Experience Platform Query Service.

   1. Passa alla sandbox di Experience Platform.
   1. Seleziona ![Query](/help/assets/icons/DataSearch.svg) **[!UICONTROL Queries]** dalla barra a sinistra.
   1. Selezionare la scheda **[!UICONTROL Credentials]** nell&#39;interfaccia **[!UICONTROL Queries]**.
   1. Selezionare `prod:cja` dal menu a discesa **[!UICONTROL Database]**.

      ![Esegui query sulle credenziali del servizio](assets/queryservice-credentials.png)

1. Avviare Power BI Desktop.
   1. Dall&#39;interfaccia principale, selezionare **[!UICONTROL Get data from other sources]**.
   1. Nella finestra di dialogo **[!UICONTROL Get Data]** (Crea elemento dati):
      ![Database PostgreSQL di Power BI](assets/powerbi-postgresql.png)
      1. Cerca e seleziona **[!UICONTROL PostgreSQL database]**.
      1. Seleziona **[!UICONTROL Connect]** (Aggiungi elemento dati).
   1. Nella finestra di dialogo **[!UICONTROL PostgreSQL database]** (Crea elemento dati):
      ![Impostazioni server desktop e database PowerBI](assets/powerbi-serverdatabase.png)
      1. Utilizzare ![Copia](/help/assets/icons/Copy.svg) per copiare e incollare i valori **[!UICONTROL Host]** e **[!UICONTROL Port]** dal pannello Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]**, separati da `:` come valore per **[!UICONTROL Server]**. Ad esempio: `examplecompany.platform-query.adobe.io:80`.
      1. Utilizza ![Copia](/help/assets/icons/Copy.svg) per copiare e incollare il valore **[!UICONTROL Database]** dal pannello Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]**. Aggiungere `?FLATTEN` al valore incollato. Ad esempio: `prod:cja?FLATTEN`.
      1. Seleziona **[!UICONTROL DirectQuery]** come [!UICONTROL Data connectivity mode].
      1. Seleziona **[!UICONTROL OK]**.
   1. Nella finestra di dialogo **[!UICONTROL PostgreSQL database]** - **[!UICONTROL Database]**:
      ![Utente e password di PowerBI Desktop](assets/powerbi-userpassword.png)
      1. Utilizzare ![Copia](/help/assets/icons/Copy.svg) per copiare i valori **[!UICONTROL Username]** e **[!UICONTROL Password]** dal pannello Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** nei campi **[!UICONTROL User name]** e **[!UICONTROL Password]**. Se si utilizza una [credenziale senza scadenza](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), utilizzare la password delle credenziali senza scadenza.
      1. Verificare che il menu a discesa per **[!UICONTROL Select which level to apply these settings to]** sia impostato su **[!UICONTROL Server]** definito in precedenza.
      1. Seleziona **[!UICONTROL Connect]**.
   1. Nella finestra di dialogo **[!UICONTROL Navigator]**, le visualizzazioni dati vengono recuperate. Questo recupero può richiedere del tempo. Una volta recuperato:
      ![Power BI dati caricamento desktop](assets/powerbi-navigator-load.png)
      1. Seleziona **[!UICONTROL public.cc_data_view]** dall&#39;elenco nel pannello a sinistra.
      1. Sono disponibili due opzioni:
         1. Selezionare **[!UICONTROL Load]** per continuare e completare l&#39;installazione.
         1. Seleziona **[!UICONTROL Transform Data]**. Viene visualizzata una finestra di dialogo in cui è possibile applicare le trasformazioni come parte della configurazione.
            ![Power BI dati trasformazione desktop](assets/powerbi-transform-data.png)
            * Seleziona **[!UICONTROL Close & Apply]**.
   1. Dopo un po&#39;, **[!UICONTROL public cc_data_view]** viene visualizzato nel riquadro **[!UICONTROL Data]**. Seleziona ![ChevronRight](/help/assets/icons/ChevronRight.svg) per visualizzare dimensioni e metriche.
      ![Dati del server desktop di Power BI caricati](assets/powerbi-navigator-loaded.png)


>[!TAB Desktop Tableau]

1. Accedi alle credenziali e ai parametri richiesti dall’interfaccia utente di Experience Platform Query Service.

   1. Passa alla sandbox di Experience Platform.
   1. Seleziona ![Query](/help/assets/icons/DataSearch.svg) **[!UICONTROL Queries]** dalla barra a sinistra.
   1. Selezionare la scheda **[!UICONTROL Credentials]** nell&#39;interfaccia **[!UICONTROL Queries]**.
   1. Selezionare `prod:cja` dal menu a discesa **[!UICONTROL Database]**.

      ![Esegui query sulle credenziali del servizio](assets/queryservice-credentials.png)

1. Avvia Tableau.
   1. Seleziona **[!UICONTROL PostgreSQL]** dalla barra a sinistra sotto **[!UICONTROL To a Server]**. Se non disponibile, selezionare **[!UICONTROL More...]** e selezionare **[!UICONTROL PostgreSQL]** da **[!UICONTROL Installed Connectors]**.
      ![Connettori Tableau](assets/tableau-connectors.png)
   1. Nella scheda **[!UICONTROL General]** della finestra di dialogo **[!UICONTROL PostgreSQL]**:
      ![Finestra di dialogo Accesso a Tableau](assets/tableau-signin.png)
      1. Utilizza ![Copia](/help/assets/icons/Copy.svg) per copiare e incollare **[!UICONTROL Host]** dal pannello Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** in **[!UICONTROL Server]**.
      1. Utilizza ![Copia](/help/assets/icons/Copy.svg) per copiare e incollare **[!UICONTROL Port]** dal pannello Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** in **[!UICONTROL Port]**.
      1. Utilizza ![Copia](/help/assets/icons/Copy.svg) per copiare e incollare **[!UICONTROL Database]** dal pannello Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** in **[!UICONTROL Database]**. Aggiungere `%3FFLATTEN` al valore incollato. Ad esempio: `prod:cja%3FFLATTEN`.
      1. Selezionare **[!UICONTROL Username and Password]** dal menu a discesa **[!UICONTROL Authentication]**.
      1. Utilizza ![Copia](/help/assets/icons/Copy.svg) per copiare e incollare **[!UICONTROL Username]** dal pannello Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** in **[!UICONTROL Username]**.
      1. Utilizza ![Copia](/help/assets/icons/Copy.svg) per copiare e incollare **[!UICONTROL Password]** dal pannello Experience Platform **[!UICONTROL Query]** **[!UICONTROL Expiring Credentials]** in **[!UICONTROL Password]**. Se si utilizza una [credenziale senza scadenza](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), utilizzare la password delle credenziali senza scadenza.
      1. Verificare che **[!UICONTROL Require SSL]** sia selezionato.
      1. Seleziona **[!UICONTROL Sign In]**.

      Viene visualizzata una finestra di dialogo **[!UICONTROL Progressing Request]** mentre Tableau Desktop convalida la connessione.
   1. Nella finestra principale, nella pagina **[!UICONTROL Data Source]**, nel riquadro a sinistra:
      * Nome della connessione, sotto **[!UICONTROL Connections]**.
      * Il nome del database, sotto **[!UICONTROL Database]**.
      * Un elenco di tabelle, sotto **[!UICONTROL Table]**.
        ![Tableau connesso](assets/tableau-connected.png)
      1. Trascinare la voce **[!UICONTROL cc_data_view]** e rilasciare la voce nella visualizzazione principale che riporta **[!UICONTROL Drag tables]** qui.
   1. Nella finestra principale vengono visualizzati i dettagli della visualizzazione dati **[!UICONTROL cc_data_view]**.
      ![Tableau connesso](assets/tableau-validation.png)

>[!ENDTABS]

+++


## Tendenza giornaliera

In questo caso d’uso, desideri visualizzare una tabella e una visualizzazione a linee semplici che mostrino una tendenza giornaliera delle occorrenze (eventi) dal 1° gennaio 2023 al 31 gennaio 2023.

+++ Customer Journey Analytics

Un esempio di pannello **[!UICONTROL Daily Trend]** per il caso d&#39;uso:

![Pannello Tendenza giornaliera del Customer Journey Analytics](assets/cja_daily_trend.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL daterangeday]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ occurrences]** (Salva).

   Viene visualizzata una tabella che mostra le occorrenze del mese corrente. Per una migliore visibilità, ingrandisci la visualizzazione della tabella.

1. Nel riquadro **[!UICONTROL Filters]**:

   1. Selezionare **[!UICONTROL daterangeday is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Advanced filtering]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023.` Puoi utilizzare l&#39;icona del calendario per scegliere e selezionare le date.
   1. Seleziona **[!UICONTROL Apply filter]**.

   La tabella viene aggiornata con il filtro **[!UICONTROL daterangeday]** applicato.

1. Nel riquadro **[!UICONTROL Visualizations]** selezionare la visualizzazione **[!UICONTROL Line chart]**.

   Una visualizzazione con grafico a linee sostituisce la tabella utilizzando gli stessi dati della tabella. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Caso d&#39;uso Power BI Desktop 2 Filtro intervallo date](assets/uc2-pbi-daterange.png)

1. Nella visualizzazione Grafico a linee:

   1. Seleziona ![Altro](/help/assets/icons/More.svg).
   1. Dal menu di scelta rapida, selezionare **[!UICONTROL Show as a table]**.

   La vista principale viene aggiornata per mostrare sia una visualizzazione delle linee che una tabella. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Visualizzazione tendenze giornaliere finali caso d&#39;uso desktop Power BI 2](assets/uc2-pbi-final.png)

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare dalla visualizzazione **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciarla nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filters Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Range of dates]** e specificare un periodo compreso tra `01/01/2023` e `31/01/2023`.

      ![Filtro Desktop Tableau](assets/uc2-tableau-filter.png)

   1. Trascinare **[!UICONTROL Daterangeday]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciare la voce nel campo accanto a **[!UICONTROL Columns]**.
      * Selezionare **[!UICONTROL Day]** dal menu a discesa **[!UICONTROL Daterangeday]**, in modo che il valore venga aggiornato a **[!UICONTROL DAY(Daterangeday)]**.
   1. Trascinare **[!UICONTROL Occurrences]** dall&#39;elenco **[!UICONTROL Tables (*Nomi misure *)]**nel riquadro **[!UICONTROL Data]**e rilasciare la voce nel campo accanto a **[!UICONTROL Rows]**.
      * I valori vengono automaticamente convertiti in **[!UICONTROL SUM(Occurrences)]**.
   1. Modificare **[!UICONTROL Standard]** in **[!UICONTROL Entire View]** dal menu a discesa nella barra degli strumenti.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Grafico Desktop Tableau](assets/uc2-tableau-graph.png)

1. Selezionare **[!UICONTROL Duplicate]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per creare un secondo foglio.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per rinominare il foglio in `Graph`.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1 (2)]** per rinominare il foglio in `Data`.
1. Verificare che il foglio **[!UICONTROL Data]** sia selezionato. Nella visualizzazione Dati:
   1. Seleziona **[!UICONTROL Show me]** in alto a destra e seleziona **[!UICONTROL Text table]** (visualizzazione in alto a sinistra in alto) per modificare il contenuto della visualizzazione dati in una tabella.
   1. Selezionare **[!UICONTROL Swap Rows and Columns]** dalla barra degli strumenti.
   1. Modificare **[!UICONTROL Standard]** in **[!UICONTROL Entire View]** dal menu a discesa nella barra degli strumenti.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dati Desktop Tableau](assets/uc2-tableau-data.png)

1. Selezionare il pulsante della scheda **[!UICONTROL New Dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascinare e rilasciare il foglio **[!UICONTROL Graph]** dallo scaffale **[!UICONTROL Sheets]** nella visualizzazione **[!UICONTROL Dashboard 1]** che riporta *Rilasciare qui i fogli*.
   1. Trascinare il foglio **[!UICONTROL Data]** dallo scaffale **[!UICONTROL Sheets]** sotto il foglio **[!UICONTROL Graph]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Selezionare il foglio **[!UICONTROL Data]** nella visualizzazione e modificare **[!UICONTROL Entire View]** in **[!UICONTROL Fix Width]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dashboard desktop Tableau 1](assets/uc2-tableau-dashboard.png)

>[!ENDTABS]

+++


## Tendenza oraria

In questo caso d’uso, vuoi visualizzare una tabella e una semplice visualizzazione delle linee che mostri una tendenza oraria di occorrenze(eventi) per il 1° gennaio 2023.

+++ Customer Journey Analytics

Un esempio di pannello **[!UICONTROL Hourly Trend]** per il caso d&#39;uso:

![Visualizzazioni Tendenza Oraria Customer Journey Analytics](assets/cja_hourly_trend.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

![Alert](/help/assets/icons/Alert.svg) Il Power BI **not** comprende come gestire le colonne data-ora, pertanto dimensioni come **[!UICONTROL daterangehour]** e **[!UICONTROL daterangeminute]** non sono supportate.

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciarla nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filters Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Range of dates]** e specificare un periodo compreso tra `01/01/2023` e `02/01/2023`.

      ![Filtro Desktop Tableau](assets/uc3-tableau-filter.png)

   1. Trascinare **[!UICONTROL Daterangehour]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciare la voce nel campo accanto a **[!UICONTROL Columns]**.
      * Selezionare **[!UICONTROL More]** > **[!UICONTROL Hours]** dal menu a discesa **[!UICONTROL Daterangeday]**, in modo che il valore venga aggiornato a **[!UICONTROL HOUR(Daterangeday)]**.
   1. Trascinare **[!UICONTROL Occurrences]** dall&#39;elenco **[!UICONTROL Tables (*Nomi misure *)]**nel riquadro **[!UICONTROL Data]**e rilasciare la voce nel campo accanto a **[!UICONTROL Rows]**.
      * I valori vengono automaticamente convertiti in **[!UICONTROL SUM(Occurrences)]**.
   1. Modificare **[!UICONTROL Standard]** in **[!UICONTROL Entire View]** dal menu a discesa nella barra degli strumenti.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Grafico Desktop Tableau](assets/uc3-tableau-graph.png)

1. Selezionare **[!UICONTROL Duplicate]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per creare un secondo foglio.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per rinominare il foglio in `Graph`.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1 (2)]** per rinominare il foglio in `Data`.
1. Verificare che il foglio **[!UICONTROL Data]** sia selezionato. Nella visualizzazione Dati:
   1. Seleziona **[!UICONTROL Show me]** in alto a destra e seleziona **[!UICONTROL Text table]** (visualizzazione in alto a sinistra in alto) per modificare il contenuto della visualizzazione dati in una tabella.
   1. Trascina **[!UICONTROL HOUR(Daterangeday)]** da **[!UICONTROL Columns]** a **[!UICONTROL Rows]**.
   1. Modificare **[!UICONTROL Standard]** in **[!UICONTROL Entire View]** dal menu a discesa nella barra degli strumenti.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dati Desktop Tableau](assets/uc3-tableau-data.png)

1. Selezionare il pulsante della scheda **[!UICONTROL New Dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascinare e rilasciare il foglio **[!UICONTROL Graph]** dallo scaffale **[!UICONTROL Sheets]** nella visualizzazione **[!UICONTROL Dashboard 1]** che riporta *Rilasciare qui i fogli*.
   1. Trascinare il foglio **[!UICONTROL Data]** dallo scaffale **[!UICONTROL Sheets]** sotto il foglio **[!UICONTROL Graph]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Selezionare il foglio **[!UICONTROL Data]** nella visualizzazione e modificare **[!UICONTROL Entire View]** in **[!UICONTROL Fix Width]**.

      La visualizzazione **[!UICONTROL Dashboard 1]** dovrebbe essere simile alla seguente.

      ![Dashboard desktop Tableau 1](assets/uc3-tableau-dashboard.png)


>[!ENDTABS]

+++


## Tendenza mensile

In questo caso d’uso, vuoi visualizzare una tabella e una visualizzazione a linee semplici che mostrino una tendenza mensile di occorrenza (eventi) per il 2023.

+++ Customer Journey Analytics

Un esempio di pannello **[!UICONTROL Monthly Trend]** per il caso d&#39;uso:

![Visualizzazione tendenza mensile Customer Journey Analytics](assets/cja_monthly_trend.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL daterangemonth]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ occurrences]** (Salva).

   Viene visualizzata una tabella che mostra le occorrenze del mese corrente. Per una migliore visibilità, ingrandisci la visualizzazione della tabella.

1. Nel riquadro **[!UICONTROL Filters]**:

   1. Selezionare **[!UICONTROL daterangemonth is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Advanced filtering]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `1/1/2024.` Puoi utilizzare l&#39;icona del calendario per scegliere e selezionare le date.
   1. Seleziona **[!UICONTROL Apply filter]**.

   La tabella viene aggiornata con il filtro **[!UICONTROL daterangemonth]** applicato.

1. Nel riquadro **[!UICONTROL Visualizations]**:

   1. Selezionare la visualizzazione **[!UICONTROL Line chart]**.

   Una visualizzazione con grafico a linee sostituisce la tabella utilizzando gli stessi dati della tabella. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Caso d&#39;uso Power BI Desktop 2 Filtro intervallo date](assets/uc4-pbi-filter-daterange.png)

1. Nella visualizzazione Grafico a linee:

   1. Seleziona ![Altro](/help/assets/icons/More.svg).
   1. Dal menu di scelta rapida, selezionare **[!UICONTROL Show as a table]**.

   La vista principale viene aggiornata per mostrare sia una visualizzazione delle linee che una tabella. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Visualizzazione tendenze giornaliere finali caso d&#39;uso desktop Power BI 2](assets/uc4-pbi-filter-final.png)

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciarla nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filters Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Range of dates]** e specificare un periodo compreso tra `01/01/2023` e `01/01/2024`.

      ![Filtro Desktop Tableau](assets/uc4-tableau-filter.png)

   1. Trascinare **[!UICONTROL Daterangeday]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciare la voce nel campo accanto a **[!UICONTROL Columns]**.
      * Selezionare **[!UICONTROL MONTH]** dal menu a discesa **[!UICONTROL Daterangeday]**, in modo che il valore venga aggiornato a **[!UICONTROL MONTH(Daterangeday)]**.
   1. Trascinare **[!UICONTROL Occurrences]** dall&#39;elenco **[!UICONTROL Tables (*Nomi misure *)]**nel riquadro **[!UICONTROL Data]**e rilasciare la voce nel campo accanto a **[!UICONTROL Rows]**.
      * I valori vengono automaticamente convertiti in **[!UICONTROL SUM(Occurrences)]**.
   1. Modificare **[!UICONTROL Standard]** in **[!UICONTROL Entire View]** dal menu a discesa nella barra degli strumenti.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Grafico Desktop Tableau](assets/uc4-tableau-graph.png)

1. Selezionare **[!UICONTROL Duplicate]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per creare un secondo foglio.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per rinominare il foglio in `Graph`.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1 (2)]** per rinominare il foglio in `Data`.
1. Verificare che il foglio **[!UICONTROL Data]** sia selezionato. Nella visualizzazione Dati:
   1. Seleziona **[!UICONTROL Show me]** in alto a destra e seleziona **[!UICONTROL Text table]** (visualizzazione in alto a sinistra in alto) per modificare il contenuto della visualizzazione dati in una tabella.
   1. Trascina **[!UICONTROL MONTH(Daterangeday)]** da **[!UICONTROL Columns]** a **[!UICONTROL Rows]**.
   1. Modificare **[!UICONTROL Standard]** in **[!UICONTROL Entire View]** dal menu a discesa nella barra degli strumenti.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dati Desktop Tableau](assets/uc4-tableau-data.png)

1. Selezionare il pulsante della scheda **[!UICONTROL New Dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascinare e rilasciare il foglio **[!UICONTROL Graph]** dallo scaffale **[!UICONTROL Sheets]** nella visualizzazione **[!UICONTROL Dashboard 1]** che riporta *Rilasciare qui i fogli*.
   1. Trascinare il foglio **[!UICONTROL Data]** dallo scaffale **[!UICONTROL Sheets]** sotto il foglio **[!UICONTROL Graph]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Selezionare il foglio **[!UICONTROL Data]** nella visualizzazione e modificare **[!UICONTROL Entire View]** in **[!UICONTROL Fix Width]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dashboard desktop Tableau 1](assets/uc4-tableau-dashboard.png)

>[!ENDTABS]

+++


## Classificazione dimensione singola

In questo caso d’uso, vuoi visualizzare una tabella e una semplice visualizzazione a barre che mostrino i ricavi di acquisto e di acquisto per i nomi dei prodotti oltre il 2023.

+++ Customer Journey Analytics

Un esempio di pannello **[!UICONTROL Single Dimension Ranked]** per il caso d&#39;uso:

![Visualizzazione con classificazione dimensione singola Customer Journey Analytics](assets/cja-single-dimension-ranked.png)
+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL daterange]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL product_name]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ purchase_revenue]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ purchases]** (Salva).

   Viene visualizzata una tabella vuota contenente solo le intestazioni di colonna per l’elemento selezionato. Per una migliore visibilità, ingrandisci la visualizzazione della tabella.

1. Nel riquadro **[!UICONTROL Filters]**:

   1. Selezionare **[!UICONTROL daterange is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Relative date]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is in the last]** `1` **[!UICONTROL calendar years]**.
   1. Seleziona **[!UICONTROL Apply filter]**.

   La tabella viene aggiornata con il filtro **[!UICONTROL daterange]** applicato.

1. Nel riquadro **[!UICONTROL Visualization]**:

   1. Utilizzare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL daterange]** da **[!UICONTROL Columns]**.
   1. Trascinare **[!UICONTROL Sum of purchases_revenue]** sotto **[!UICONTROL Sum of purchases]** in **[!UICONTROL Columns]**.

1. Nella visualizzazione Tabella:

   1. Selezionare **[!UICONTROL Sum of purchase_revenue]** per ordinare i nomi dei prodotti nell&#39;ordine decrescente dei ricavi di acquisto. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Caso d&#39;uso Power BI Desktop 5 Stato tabella](assets/uc5-pbi-table.png)

1. Nel riquadro **[!UICONTROL Filters]**:

   1. Seleziona **[!UICONTROL product_name is (All)]**.
   1. Imposta il tipo di filtro su Top N.
   1. Definisci il filtro su **[!UICONTROL Show items]** **[!UICONTROL Top]** `10` **[!UICONTROL By value]**.
   1. Trascinare **[!UICONTROL purchase_revenue]** in **[!UICONTROL By value]** **[!UICONTROL Add data fields here]**.
   1. Seleziona **[!UICONTROL Apply filter]**.

   La tabella viene aggiornata con i valori dei ricavi dall’acquisto sincronizzati con la visualizzazione a forma libera in Analysis Workspace.

1. Nel riquadro **[!UICONTROL Visualizations]**:

   1. Selezionare la visualizzazione **[!UICONTROL Line and stacked column chart]**.

   La tabella viene sostituita da una visualizzazione con istogramma a linee e in pila, che utilizza gli stessi dati della tabella.

1. Trascina e rilascia gli acquisti sull’asse y della linea nel riquadro Visualizzazioni.

   L’istogramma a linee e in pila viene aggiornato. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Grafico del caso d&#39;uso Power BI Desktop 5](assets/uc5-pbi-chart.png)

1. Visualizzazione istogramma a linee e in pila:

   1. Seleziona ![Altro](/help/assets/icons/More.svg).
   1. Dal menu di scelta rapida, selezionare **[!UICONTROL Show as a table]**.

   La vista principale viene aggiornata per mostrare sia una visualizzazione delle linee che una tabella.

   ![Visualizzazione tendenze giornaliere finali caso d&#39;uso desktop Power BI 2](assets/uc5-pbi-final.png)

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciarla nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filters Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Range of dates]** e specificare un periodo compreso tra `01/01/2023` e `31/12/2024`. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.

      ![Filtro Desktop Tableau](assets/uc5-tableau-filter.png)

   1. Trascinare **[!UICONTROL Product Name]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciare la voce nel campo accanto a **[!UICONTROL Rows]**.
   1. Trascinare **[!UICONTROL Purchases]** dall&#39;elenco **[!UICONTROL Tables (*Nomi misure *)]**nel riquadro **[!UICONTROL Data]**e rilasciare la voce nel campo accanto a **[!UICONTROL Rows]**.
      * I valori vengono automaticamente convertiti in **[!UICONTROL SUM(Purchases)]**.
   1. Trascinare **[!UICONTROL Purchase Revenue]** dall&#39;elenco **[!UICONTROL Tables (*Nomi misure *)]**nel riquadro **[!UICONTROL Data]**e rilasciare la voce nel campo accanto a **[!UICONTROL Columns]**e a sinistra da **[!UICONTROL SUM(Purchases)]**.
      * I valori vengono automaticamente convertiti in **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Per ordinare entrambi i grafici in ordine decrescente di ricavi da acquisto, passa il puntatore del mouse sul titolo Ricavi da acquisto e seleziona l’icona di ordinamento.
   1. Per limitare il numero di voci nei grafici, selezionare SUM(Purchase Revenue) in Rows (Righe) e dal menu a discesa selezionare Filter (Filtro).
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Purchase Revenue\]]**, seleziona **[!UICONTROL Range of values]** e immetti i valori appropriati. Ad esempio: `1,000,000` - `2,000,000`. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Per convertire i due grafici a barre in un grafico a doppia combinazione, selezionare **[!UICONTROL SUM(Purchases)]** in **[!UICONTROL Rows]** e dal menu a discesa selezionare **[!UICONTROL Dual Axis]**. I grafici a barre diventano un grafico a dispersione.
   1. Per modificare il grafico a dispersione in un grafico a barre:
      1. Selezionare **[!UICONTROL SUM(Purchases)]** nell&#39;area **[!UICONTROL Marks]** e selezionare **[!UICONTROL Line]** dal menu a discesa.
      1. Selezionare **[!UICONTROL SUM(Purchase Revenue)]** nell&#39;area **[!UICONTROL Marks]** e selezionare **[!UICONTROL Bar]** dal menu a discesa.

   Il desktop Tableau dovrebbe essere simile al seguente.

   ![Grafico Desktop Tableau](assets/uc5-tableau-graph.png)

1. Selezionare **[!UICONTROL Duplicate]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per creare un secondo foglio.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per rinominare il foglio in `Data`.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1 (2)]** per rinominare il foglio in `Graph`.
1. Verificare che il foglio **[!UICONTROL Data]** sia selezionato.
   1. Seleziona **[!UICONTROL Show me]** in alto a destra e seleziona **[!UICONTROL Text table]** (visualizzazione in alto a sinistra) per modificare il contenuto dei due grafici in una tabella.
   1. Per ordinare i ricavi di acquisto in ordine decrescente, posizionare il cursore del mouse su **[!UICONTROL Purchase Revenue]** nella tabella e selezionare ![SortOrderDown](/help/assets/icons/SortOrderDown.svg).
   1. Selezionare **[!UICONTROL Entire View]** dal menu a discesa **[!UICONTROL Fit]**.

   Il desktop Tableau dovrebbe essere simile al seguente.

   ![Dati Desktop Tableau](assets/uc5-tableau-data.png)

1. Selezionare il pulsante della scheda **[!UICONTROL New Dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascinare e rilasciare il foglio **[!UICONTROL Graph]** dallo scaffale **[!UICONTROL Sheets]** nella visualizzazione **[!UICONTROL Dashboard 1]** che riporta *Rilasciare qui i fogli*.
   1. Trascinare il foglio **[!UICONTROL Data]** dallo scaffale **[!UICONTROL Sheets]** sotto il foglio **[!UICONTROL Graph]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Selezionare il foglio **[!UICONTROL Data]** nella visualizzazione e modificare **[!UICONTROL Entire View]** in **[!UICONTROL Fix Width]**.

   La visualizzazione **[!UICONTROL Dashboard 1]** dovrebbe essere simile alla seguente.

   ![Dashboard desktop Tableau 1](assets/uc5-tableau-dashboard.png)

>[!ENDTABS]

+++


## Classificazione di più dimensioni

In questo caso d’uso, vuoi visualizzare una tabella che suddivida i ricavi e gli acquisti di acquisto per i nomi dei prodotti all’interno delle categorie di prodotti nel corso del 2023. Inoltre, è necessario utilizzare alcune visualizzazioni per illustrare sia la distribuzione della categoria di prodotto che i contributi dei nomi dei prodotti all’interno di ogni categoria di prodotto.

+++ Customer Journey Analytics

Un esempio di pannello **[!UICONTROL Multiple Dimension Ranked]** per il caso d&#39;uso:

![Customer Journey Analytics Pannello con più Dimension classificati](assets/cja-multiple-dimension-ranked.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Per garantire che l&#39;intervallo di date sia valido per tutte le visualizzazioni, trascina **[!UICONTROL daterangeday]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Filters]** in questa pagina.
   1. Selezionare **[!UICONTROL daterangeday is (All)]** da **[!UICONTROL Filters on this page]**.
   1. Seleziona **[!UICONTROL Relative date]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Seleziona **[!UICONTROL Apply filter]**.

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL datarangeday]**.
   1. Selezionare **[!UICONTROL ∑ cm_product_name_count_distinct]**, che è la metrica calcolata definita nel Customer Journey Analytics.

1. Per modificare il grafico a barre verticale in un oggetto Table, verificare che la tabella sia selezionata e selezionare **[!UICONTROL Matrix]** dal riquadro **[!UICONTROL Visualizations]**.
   * Trascina **[!UICONTROL product_name]** da **[!UICONTROL Columns]** e rilascia il campo sotto **[!UICONTROL product_categor]**y in **[!UICONTROL Rows]** nel riquadro **[!UICONTROL Visualization]**.

1. Per limitare il numero di prodotti visualizzati nella tabella, selezionare **[!UICONTROL product_name is (All)]** nel riquadro **[!UICONTROL Filters]**.

   1. Seleziona **[!UICONTROL Advanced filtering]**.
   1. Selezionare **[!UICONTROL Filter type]** **[!UICONTROL Top N]** **[!UICONTROL Show items]** **[!UICONTROL Top]** `15` **[!UICONTROL By Value]**.
   1. Trascinare **[!UICONTROL purchases]**e dal riquadro **[!UICONTROL Data]** in **[!UICONTROL Add data fields here]**.
   1. Seleziona **[!UICONTROL Apply filter]**.

1. Per migliorare la leggibilità, seleziona **[!UICONTROL View]** dal menu principale, quindi seleziona **[!UICONTROL Page View]** > **[!UICONTROL Actual size]** e ridimensiona la visualizzazione della tabella.

1. Per suddividere ogni categoria nella tabella, selezionare **[!UICONTROL +]** a livello di categoria di prodotto. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI tabella matrice con classificazione più Dimension desktop](assets/uc6-powerbi-data.png)

1. Selezionare **[!UICONTROL Home]** dal menu principale e selezionare **[!UICONTROL New visual]**. Al report viene aggiunta una nuova visualizzazione.

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL product_category]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL product_name]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL purchase_revenue]** (Salva).

1. Per modificare l&#39;elemento visivo, selezionare il grafico a barre e selezionare **[!UICONTROL Treemap]** dal riquadro **[!UICONTROL Visualizations]**.
1. Verificare che **[!UICONTROL product_category]** sia elencato sotto **[!UICONTROL Category]** e che **[!UICONTROL product_name]** sia elencato sotto **[!UICONTROL Details]** nel riquadro **[!UICONTROL Visualizations]**.

   Il desktop Power BI dovrebbe essere simile al seguente.

   ![Mappa ad albero con classificazione più Dimension di Power BI Desktop](assets/uc6-powerbi-treemap.png)

1. Selezionare **[!UICONTROL Home]** dal menu principale e selezionare **[!UICONTROL New visual]**. Al report viene aggiunta una nuova visualizzazione.

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL product_category]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL purchase_revenue]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL purchase]** (Salva).

1. Nel riquadro **[!UICONTROL Visualizations]**:
   1. per modificare la visualizzazione, selezionare **[!UICONTROL Line and stacked column chart]**.
   1. Trascina **[!UICONTROL sum_of_purchases]** da **[!UICONTROL Column y-axis]** a **[!UICONTROL Line y-axis]**.

1. Nel rapporto, ridistribuisci le singole visualizzazioni.

   Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI desktop più Dimension classificati finali](assets/uc6-powerbi-final.png)


>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciarla nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filters Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Relative dates]**, selezionare **[!UICONTROL Years]** e specificare **[!UICONTROL Previous year]**. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Filtro con classificazione più Dimension per desktop Tableau](assets/uc6-tableau-filter.png)

   1. Trascinare **[!UICONTROL Product Category]** e rilasciare accanto a **[!UICONTROL Columns]**.
   1. Trascinare **[!UICONTROL Purchase Revenue]** e rilasciare accanto a **[!UICONTROL Rows]**. Il valore diventa **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Trascinare Purchases e rilasciare accanto a **[!UICONTROL Rows]**. Il valore diventa **[!UICONTROL SUM(Purchases)]**.
   1. Seleziona **[!UICONTROL SUM(Purchases)]** e dal menu a discesa seleziona **[!UICONTROL Dual Axis]**.
   1. Selezionare **[!UICONTROL SUM(Purchases)]** in **[!UICONTROL Marks]** e selezionare **[!UICONTROL Line]** dal menu a discesa.
   1. Selezionare **[!UICONTROL SUM(Purchase Revenue)]** in **[!UICONTROL Marks]** e selezionare **[!UICONTROL Bar]** dal menu a discesa.
   1. Selezionare **[!UICONTROL Entire View]** dal menu **[!UICONTROL Fit]**.
   1. Seleziona il titolo **[!UICONTROL Purchase Revenue]** nel grafico e assicurati che i ricavi dell&#39;acquisto siano in ordine crescente.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Categoria Classificazione Più Dimension Desktop Tableau](assets/uc6-tableau-category.png)

1. Rinomina il foglio **[!UICONTROL Sheet 1]** corrente in `Category`.
1. Selezionare **[!UICONTROL New Worksheet]** per creare un nuovo foglio e rinominarlo in `Data`.

   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciarla nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filters Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Relative dates]**, selezionare **[!UICONTROL Years]** e specificare **[!UICONTROL Previous year]**. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascina **[!UICONTROL Purchase Revenue]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Columns]**. Il valore diventa **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Trascina **[!UICONTROL Purchase]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Columns]**, accanto a **[!UICONTROL Purchase Revenue]**. Il valore diventa **[!UICONTROL SUM(Purchases)]**.
   1. Trascina **[!UICONTROL Product Category]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Rows]**.
   1. Trascina **[!UICONTROL Product Name]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Rows]**, accanto a **[!UICONTROL Product Category]**.
   1. Per trasformare le due barre orizzontali in una tabella, selezionare **[!UICONTROL Text Table]** da **[!UICONTROL Show Me]**.
   1. Per limitare il numero di prodotti, selezionare **[!UICONTROL Purchases]** in **[!UICONTROL Measure Values]**. Dal menu a discesa, selezionare **[!UICONTROL Filter]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Purchases\]]**, seleziona **[!UICONTROL At least]** e immetti `7000`. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Selezionare **[!UICONTROL Fit Width]** dal menu a discesa Adatta **[!UICONTROL the]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dati Classificati Più Dimension Desktop Tableau](assets/uc6-tableau-data.png)

1. Selezionare **[!UICONTROL New worksheet]** per creare un nuovo foglio e rinominarlo in **[!UICONTROL Treemap]**.
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciarla nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filters Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Relative dates]**, selezionare **[!UICONTROL Years]** e specificare **[!UICONTROL Previous year]**. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascina **[!UICONTROL Purchase Revenue]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Rows]**. I valori diventano **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Trascina **[!UICONTROL Purchase]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Rows]**, accanto a **[!UICONTROL Purchase Revenue]**. Il valore diventa **[!UICONTROL SUM(Purchases)]**.
   1. Trascina **[!UICONTROL Product Category]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Columns]**.
   1. Trascina **[!UICONTROL Product Name]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Columns]**.
   1. Per trasformare i due grafici a barre verticali in una mappa ad albero, selezionare **[!UICONTROL Treemap]** da **[!UICONTROL Show Me]**.
   1. Per limitare il numero di prodotti, selezionare **[!UICONTROL Purchases]** in **[!UICONTROL Measure Values]**. Dal menu a discesa, selezionare **[!UICONTROL Filter]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Purchases\]]**, seleziona **[!UICONTROL At least]** e immetti `7000`. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Selezionare **[!UICONTROL Fit Width]** dal menu a discesa **[!UICONTROL Fit]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Dati Classificati Più Dimension Desktop Tableau](assets/uc6-tableau-treemap.png)

1. Selezionare il pulsante della scheda **[!UICONTROL New Dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascinare e rilasciare il foglio **[!UICONTROL Category]** dallo scaffale **[!UICONTROL Sheets]** nella visualizzazione **[!UICONTROL Dashboard 1]** che riporta *Rilasciare qui i fogli*.
   1. Trascinare il foglio **[!UICONTROL Treemap]** dallo scaffale **[!UICONTROL Sheets]** sotto il foglio **[!UICONTROL Category]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Trascinare il foglio **[!UICONTROL Data]** dallo scaffale **[!UICONTROL Sheets]** sotto il foglio **[!UICONTROL Treemap]** nella visualizzazione **[!UICONTROL Dashboard 1]**.
   1. Ridimensionare ciascun foglio nella vista.

   La visualizzazione **[!UICONTROL Dashboard 1]** dovrebbe essere simile alla seguente.

   ![Dashboard desktop Tableau 1](assets/uc6-tableau-final.png)

>[!ENDTABS]

+++


## Conta valori di dimensione distinti

Desideri ottenere il numero distinto di nomi di prodotto che sono stati segnalati durante gennaio 2023.

+++ Customer Journey Analytics

Per generare report su un numero distinto di nomi di prodotto, è stata impostata una metrica calcolata nel Customer Journey Analytics, con **[!UICONTROL Title]** `Product Name (Count Distinct)` e **[!UICONTROL External Id]** `product_name_count_distinct`.

![Metrica calcolata per nome prodotto Customer Journey Analytics (conteggio valori univoci)](assets/cja-calc-metric-distinct-count-product-names.png)

È quindi possibile utilizzare tale metrica in un pannello di esempio **[!UICONTROL Count Distinct Dimension Values]** per il caso d&#39;uso:

![Valori conteggio Customer Journey Analytics distinti](assets/cja-count-distinct-dimension-values.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Per fare in modo che l&#39;intervallo di date venga applicato a tutte le visualizzazioni, trascina **[!UICONTROL daterangeday]** dal riquadro **[!UICONTROL Data]** a **[!UICONTROL Filters]** in questa pagina.
   1. Selezionare **[!UICONTROL daterangeday is (All)]** da **[!UICONTROL Filters on this page]**.
   1. Seleziona **[!UICONTROL RelAdvanced filtering]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Seleziona **[!UICONTROL Apply filter]**.

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL datarangeday]**.
   1. Selezionare **[!UICONTROL ∑ cm_product_name_count_distinct]**, che è la metrica calcolata definita nel Customer Journey Analytics.

1. Per modificare il grafico a barre verticale in un oggetto Table, verificare che il grafico sia selezionato e selezionare **[!UICONTROL Table]** dal riquadro **[!UICONTROL Visualizations]**.

   Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI tabella valori univoci conteggio multiplo desktop](assets/uc7-powerbi-table.png)

1. Seleziona la visualizzazione della tabella. Dal menu di scelta rapida, selezionare **[!UICONTROL Copy]** > **[!UICONTROL Copy visual]**.
1. Incolla la visualizzazione utilizzando la chiave **[!UICONTROL ctrl-v]**. La copia esatta della visualizzazione si sovrappone a quella originale. Spostala a destra nell’area del rapporto.
1. Per modificare la visualizzazione copiata da una tabella a una scheda, selezionare **[!UICONTROL Card]** da **[!UICONTROL Visualizations]**.

   Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI tabella valori univoci conteggio multiplo desktop](assets/uc7-powerbi-final.png)

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nel riquadro **[!UICONTROL Data]** e rilasciarla nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Range of dates]**, quindi selezionare `01/01/2023` - `31/1/2023`. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascina **[!UICONTROL Cm Product Name Count Distinct]** in **[!UICONTROL Rows]**. Il valore diventa **[!UICONTROL SUM(Cm Product Name Count Distinct)]**. Questo campo è la metrica calcolata definita in Customer Journey Analytics.
   1. Trascinare **[!UICONTROL Daterangeday]** e rilasciare accanto a **[!UICONTROL Columns]**. Seleziona **[!UICONTROL Daterangeday]** e dal menu a discesa seleziona **[!UICONTROL Day]**.
   1. Per modificare la visualizzazione delle linee in una tabella, selezionare **[!UICONTROL Text Table]** da **[!UICONTROL Show Me]**.
   1. Selezionare **[!UICONTROL Swap Rows and Columns]** dalla barra degli strumenti.
   1. Selezionare **[!UICONTROL Fit Width]** dal menu a discesa **[!UICONTROL Fit]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Filtro con classificazione più Dimension per desktop Tableau](assets/uc7-tableau-data.png)

1. Selezionare **[!UICONTROL Duplicate]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per creare un secondo foglio.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1]** per rinominare il foglio in `Data`.
1. Selezionare **[!UICONTROL Rename]** dal menu di scelta rapida della scheda **[!UICONTROL Sheet 1 (2)]** per rinominare il foglio in `Card`.

1. Verificare di aver selezionato la visualizzazione **[!UICONTROL Card]**.
1. Seleziona **[!UICONTROL DAY(Daterangeday)]** e dal menu a discesa seleziona **[!UICONTROL Month]**. Il valore diventa **[!UICONTROL MONTH(Daterangeday)]**.
1. Selezionare **[!UICONTROL SUM(Cm Product Name Count Distinct)]** in **[!UICONTROL Marks]** e dal menu a discesa selezionare **[!UICONTROL Format]**.
1. Per modificare la dimensione del carattere, nel riquadro **[!UICONTROL Format SUM(CM Product Name Count Distinct)]** selezionare **[!UICONTROL Font]** in **[!UICONTROL Default]** e **[!UICONTROL 72]** per la dimensione del carattere.
1. Per allineare il numero, selezionare **[!UICONTROL Automatic]** accanto a **[!UICONTROL Alignment]** e impostare **[!UICONTROL Horizontal]** su Centrato.
1. Per utilizzare numeri interi, selezionare **[!UICONTROL 123.456]** accanto a **[!UICONTROL Numbers]** e selezionare **[!UICONTROL Number (Custom)]**. Imposta **[!UICONTROL Decimal places]** su `0`.

   Il desktop Tableau dovrebbe essere simile al seguente.

   ![Filtro con classificazione più Dimension per desktop Tableau](assets/uc7-tableau-card.png)

1. Selezionare il pulsante della scheda **[!UICONTROL New Dashboard]** (in basso) per creare una nuova visualizzazione **[!UICONTROL Dashboard 1]**. Nella visualizzazione **[!UICONTROL Dashboard 1]**:
   1. Trascinare e rilasciare il foglio **[!UICONTROL Card]** dallo scaffale **[!UICONTROL Sheets]** nella visualizzazione **[!UICONTROL Dashboard 1]** che riporta *Rilasciare qui i fogli*.
   1. Trascinare il foglio **[!UICONTROL Data]** dallo scaffale **[!UICONTROL Sheets]** sotto il foglio **[!UICONTROL Card]** nella visualizzazione **[!UICONTROL Dashboard 1]**.

   La visualizzazione **[!UICONTROL Dashboard 1]** dovrebbe essere simile alla seguente.

   ![Dashboard desktop Tableau 1](assets/uc7-tableau-final.png)

>[!ENDTABS]

+++



## Utilizzare i nomi degli intervalli di date per filtrare

Desideri utilizzare un intervallo di date definito nel Customer Journey Analytics per filtrare e generare rapporti sulle occorrenze (eventi) dell’ultimo anno.

+++ Customer Journey Analytics

Per creare un report utilizzando un intervallo di date, impostare un intervallo di date in Customer Journey Analytics, con **[!UICONTROL Title]** `Last Year 2023`.

![Customer Journey Analytics Utilizza i nomi degli intervalli di date per filtrare](assets/cja-daterange.png)

È quindi possibile utilizzare tale intervallo di date in un pannello di esempio **[!UICONTROL Using Date Range Names To Filter]** per il caso d&#39;uso:

![Valori conteggio Customer Journey Analytics distinti](assets/cja-using-date-range-filter-names-to-filter.png)

L’intervallo di date definito nella visualizzazione a forma libera sovrascrive l’intervallo di date applicato al pannello.

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL daterangemonth]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL daterangeName]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ occurrences]** (Salva).

   Visualizzazione che visualizza **[!UICONTROL Error fetching data for this visual]**.

1. Nel riquadro **[!UICONTROL Filters]**:

   1. Selezionare **[!UICONTROL daterangeName is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Basic filtering]** come **[!UICONTROL Filter type]**.
   1. Sotto il campo **[!UICONTROL Search]**, selezionare **[!UICONTROL Last Year 2023]**, che è il nome dell&#39;intervallo di date definito nel Customer Journey Analytics.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL daterangeName]** da **[!UICONTROL Columns]**.

   La tabella viene aggiornata con il filtro **[!UICONTROL daterangeName]** applicato. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI Desktop Con Nomi Di Intervalli Di Date Per Filtrare](assets/uc8-powerbi-final.png)

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange Name]** dall&#39;elenco **[!UICONTROL Tables]** nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange Name\]]** assicurarsi che **[!UICONTROL Select from list]** sia selezionato e selezionare **[!UICONTROL Last Year 2023]** dall&#39;elenco. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascinare la voce **[!UICONTROL Daterangemonth]** dall&#39;elenco **[!UICONTROL Tables]** su **[!UICONTROL Rows]**. Selezionare **[!UICONTROL Daterangemonth]** e selezionare **[!UICONTROL Month]**. Il valore diventa **[!UICONTROL MONTH(Daterangemonth)]**.
   1. Trascinare la voce **[!UICONTROL Occurrences]** dall&#39;elenco **[!UICONTROL Tables]** su **[!UICONTROL Columns]**. Il valore diventa **[!UICONTROL SUM(Occurrences)]**.
   1. Selezionare **[!UICONTROL Text Table]** da **[!UICONTROL Show Me]**.
   1. Selezionare **[!UICONTROL Swap Rows and Columns]** dalla barra degli strumenti.
   1. Selezionare **[!UICONTROL Fit Width]** dal menu a discesa **[!UICONTROL Fit]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Filtro con classificazione più Dimension per desktop Tableau](assets/uc8-tableau-final.png)

>[!ENDTABS]

+++



## Utilizzare i nomi dei filtri per filtrare

Desideri utilizzare un filtro esistente per la categoria di prodotti della pesca, definita nel Customer Journey Analytics, per filtrare e segnalare i nomi dei prodotti e le occorrenze (eventi) durante gennaio 2023.

+++ Customer Journey Analytics

Inspect il filtro che desideri utilizzare nel Customer Journey Analytics.

![Customer Journey Analytics Utilizza Nomi Filtro Per Filtrare](assets/cja-fishing-products.png)

È quindi possibile utilizzare il filtro in un pannello di esempio **[!UICONTROL Using Date Range Names To Filter]** per il caso d&#39;uso:

![Valori conteggio Customer Journey Analytics distinti](assets/cja-using-filter-names-to-filter.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL daterange]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL filterName]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL product_name]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ occurrences]** (Salva).

Visualizzazione che visualizza **[!UICONTROL Error fetching data for this visual]**.

1. Nel riquadro **[!UICONTROL Filters]**:

   1. Selezionare **[!UICONTROL filterName is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Basic filtering]** come **[!UICONTROL Filter type]**.
   1. Sotto il campo **[!UICONTROL Search]**, selezionare **[!UICONTROL Fishing Products]**, che è il nome del filtro esistente definito nel Customer Journey Analytics.
   1. Selezionare **[!UICONTROL daterange is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Advanced filtering]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL filterName]** da **[!UICONTROL Columns]**.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL daterange]** da **[!UICONTROL Columns]**.

   La tabella viene aggiornata con il filtro **[!UICONTROL filterName]** applicato. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI Desktop Con Nomi Di Intervalli Di Date Per Filtrare](assets/uc9-powerbi-final.png)


>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Filter Name]** dall&#39;elenco **[!UICONTROL Tables]** nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Filter Name\]]** assicurarsi che **[!UICONTROL Select from list]** sia selezionato e selezionare **[!UICONTROL Fishing Products]** dall&#39;elenco. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Range of dates]**, quindi selezionare `01/01/2023` - `1/2/2023`. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascinare **[!UICONTROL Product Name]** dall&#39;elenco **[!UICONTROL Tables]** a **[!UICONTROL Rows]**.
   1. Trascinare la voce **[!UICONTROL Occurrences]** dall&#39;elenco **[!UICONTROL Tables]** su **[!UICONTROL Columns]**. Il valore diventa **[!UICONTROL SUM(Occurrences)]**.
   1. Selezionare **[!UICONTROL Text Table]** da **[!UICONTROL Show Me]**.
   1. Selezionare **[!UICONTROL Fit Width]** dal menu a discesa **[!UICONTROL Fit]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Filtro con classificazione più Dimension per desktop Tableau](assets/uc9-tableau-final.png)

>[!ENDTABS]

+++


## Utilizzare i valori di dimensione per filtrare

Crea un nuovo filtro nel Customer Journey Analytics che filtra i prodotti della categoria di prodotti di caccia. Quindi desideri utilizzare il nuovo filtro per generare rapporti sui nomi dei prodotti e sulle occorrenze (eventi) per i prodotti della categoria di caccia durante gennaio 2023.

+++ Customer Journey Analytics

Crea un nuovo filtro con **[!UICONTROL Title]** `Hunting Products` nel Customer Journey Analytics.

![Customer Journey Analytics Usa Valori Dimension Per Filtrare](assets/cja-hunting-products.png)

È quindi possibile utilizzare il filtro in un pannello di esempio **[!UICONTROL Using Date Range Names To Filter]** per il caso d&#39;uso:

![Valori conteggio Customer Journey Analytics distinti](assets/cja-using-dimension-values-to-filter.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Selezionare **[!UICONTROL Home]** dal menu, quindi selezionare **[!UICONTROL Refresh]** dalla barra degli strumenti. È necessario aggiornare la connessione per raccogliere il nuovo filtro appena definito in Customer Journey Analytics.

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL daterange]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL filterName]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL product_name]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ occurrences]** (Salva).

Visualizzazione che visualizza **[!UICONTROL Error fetching data for this visual]**.

1. Nel riquadro **[!UICONTROL Filters]**:
   1. Selezionare **[!UICONTROL filterName is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Basic filtering]** come **[!UICONTROL Filter type]**.
   1. Sotto il campo **[!UICONTROL Search]**, selezionare **[!UICONTROL Hunting Products]**, che è il nome del filtro esistente definito nel Customer Journey Analytics.
   1. Selezionare **[!UICONTROL daterange is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Advanced filtering]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL filterName]** da **[!UICONTROL Columns]**.
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere **[!UICONTROL daterange]** da **[!UICONTROL Columns]**.

   La tabella viene aggiornata con il filtro **[!UICONTROL filterName]** applicato. Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI Desktop Con Nomi Di Intervalli Di Date Per Filtrare](assets/uc10-powerbi-final.png)



>[!TAB Desktop Tableau]

1. Nella visualizzazione **[!UICONTROL Data Source]**, sotto **[!UICONTROL Data]**, dal menu di scelta rapida in **[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**, selezionare **[!UICONTROL Refresh]**.
1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Filter Name]** dall&#39;elenco **[!UICONTROL Tables]** nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Filter Name\]]** assicurarsi che **[!UICONTROL Select from list]** sia selezionato e selezionare **[!UICONTROL Hunting Products]** dall&#39;elenco. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Range of dates]**, quindi selezionare `01/01/2023` - `1/2/2023`. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascinare **[!UICONTROL Product Name]** dall&#39;elenco **[!UICONTROL Tables]** a **[!UICONTROL Rows]**.
   1. Trascinare la voce **[!UICONTROL Occurrences]** dall&#39;elenco **[!UICONTROL Tables]** su **[!UICONTROL Columns]**. Il valore diventa **[!UICONTROL SUM(Occurrences)]**.
   1. Selezionare **[!UICONTROL Text Table]** da **[!UICONTROL Show Me]**.
   1. Selezionare **[!UICONTROL Fit Width]** dal menu a discesa **[!UICONTROL Fit]**.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Filtro con classificazione più Dimension per desktop Tableau](assets/uc10-tableau-final.png)

>[!ENDTABS]

+++



## Ordina

Sintesi del caso d’uso

+++ Customer Journey Analytics

Desideri generare rapporti sui ricavi e sugli acquisti per nomi di prodotto nel mese di gennaio 2023, ordinati in ordine decrescente di ricavi di acquisto.

Un esempio di pannello **[!UICONTROL Sort]** per il caso d&#39;uso:

![Pannello Ordinamento Customer Journey Analytics](assets/cja-sort.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL daterange]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL product_namr]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ purchase_revenue]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ purchases]** (Salva).

1. Nel riquadro **[!UICONTROL Filters]**:
   1. Selezionare **[!UICONTROL daterange is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Advanced filtering]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.

1. Nel riquadro Visualizzazioni:
   1. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere l&#39;intervallo di dati dalle colonne.
   1. Trascina Somma di purchase_revenue nella parte inferiore degli elementi Colonna.

1. Nel rapporto, seleziona Somma di purchase_revenue per ordinare la tabella in ordine decrescente di ricavi da acquisto.

   Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI Desktop Con Nomi Di Intervalli Di Date Per Filtrare](assets/uc11-powerbi-final.png)

La query eseguita da Power BI Desktop tramite l&#39;estensione BI non include un&#39;istruzione `sort`. L&#39;assenza di un&#39;istruzione `sort` implica che l&#39;ordinamento in ordine decrescente è basato su client.

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]]**, selezionare **[!UICONTROL Range of dates]**, quindi selezionare `01/01/2023` - `1/2/2023`. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascinare **[!UICONTROL Product Name]** dall&#39;elenco **[!UICONTROL Tables]** a **[!UICONTROL Rows]**.
   1. Trascinare la voce **[!UICONTROL Purchases]** dall&#39;elenco **[!UICONTROL Tables]** su **[!UICONTROL Columns]**. Il valore diventa **[!UICONTROL SUM(Purchases)]**.
   1. Trascinare la voce **[!UICONTROL Purchase Revenue]** dall&#39;elenco **[!UICONTROL Tables]** su **[!UICONTROL Columns]**, accanto a **[!UICONTROL SUM(Purchases)]**. Il valore diventa **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Selezionare **[!UICONTROL Text Table]** da **[!UICONTROL Show Me]**.
   1. Selezionare **[!UICONTROL Fit Width]** dal menu a discesa **[!UICONTROL Fit]**.
   1. Selezionare l&#39;intestazione di colonna **[!UICONTROL Purchase Revenue]** e ordinare la tabella in base a questa colonna in ordine decrescente.

      Il desktop Tableau dovrebbe essere simile al seguente.

      ![Ordine Desktop Tableau](assets/uc11-tableau-final.png)

La query eseguita da Tableau Desktop tramite l&#39;estensione BI non include un&#39;istruzione `sort`. L&#39;assenza di questa istruzione `sort` implica che l&#39;ordinamento in ordine decrescente è basato su client.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!ENDTABS]

+++

## Limiti

Desideri creare un rapporto sulle prime 5 occorrenze dei nomi dei prodotti durante il 2023.

+++ Customer Journey Analytics

Un esempio di pannello **[!UICONTROL Limit]** per il caso d&#39;uso:

![Pannello Limite Customer Journey Analytics](assets/cja-limit.png)

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

1. Nel riquadro **[!UICONTROL Data]**:
   1. Seleziona **[!UICONTROL daterange]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL product_name]** (Aggiungi set di dati).
   1. Seleziona **[!UICONTROL ∑ occurrences]** (Salva).

1. Nel riquadro **[!UICONTROL Filters]**:
   1. Selezionare **[!UICONTROL daterange is (All)]** da **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Relative date]** come **[!UICONTROL Filter type]**.
   1. Definisci il filtro su **[!UICONTROL Show items when the value]** **[!UICONTROL is in the last]** `1` **[!UICONTROL calendar years]**.
   1. Seleziona **[!UICONTROL Apply filter]**.
   1. Selezionare product_name is (All) from **[!UICONTROL Filters on this visual]**.
   1. Seleziona **[!UICONTROL Top N]** come **[!UICONTROL Filter type]**.
   1. Selezionare **[!UICONTROL Show Items]** **[!UICONTROL Top]** `5` **[!UICONTROL By value]**.
   1. Trascinare **[!UICONTROL ∑ occurrences]** dal riquadro **[!UICONTROL Data]** e rilasciarlo su **[!UICONTROL Add data fields here]**.
   1. Seleziona **[!UICONTROL Apply filter]**.

1. Nel riquadro di visualizzazione:
   * Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere l&#39;intervallo di dati dalle colonne.

   Il desktop Power BI dovrebbe essere simile al seguente.

   ![Power BI Desktop Con Nomi Di Intervalli Di Date Per Filtrare](assets/uc12-powerbi-final.png)

La query eseguita da Power BI Desktop tramite l&#39;estensione BI include un&#39;istruzione `limit` ma non quella prevista. I risultati espliciti del nome del prodotto restituiti dal client applicano implicitamente il limite alle prime 5 occorrenze.

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Desktop Tableau]

1. Selezionare la scheda **[!UICONTROL Sheet 1]** in basso per passare da **[!UICONTROL Data source]**. Nella visualizzazione **[!UICONTROL Sheet 1]**:
   1. Trascinare la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tables]** nello scaffale **[!UICONTROL Filters]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter Field \[Daterange\]]**, seleziona **[!UICONTROL Range of Dates]** e **[!UICONTROL Next >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filter \[Daterange]}**, selezionare **[!UICONTROL Relative dates]**, **[!UICONTROL Years]** e **[!UICONTROL Previous years]**. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.
   1. Trascinare **[!UICONTROL Product Name]** dall&#39;elenco **[!UICONTROL Tables]** a **[!UICONTROL Rows]**.
   1. Trascinare la voce **[!UICONTROL Occurrences]** dall&#39;elenco **[!UICONTROL Tables]** su **[!UICONTROL Columns]**. Il valore diventa **[!UICONTROL SUM(Occurrences)]**.
   1. Selezionare **[!UICONTROL Text Table]** da **[!UICONTROL Show Me]**.
   1. Selezionare **[!UICONTROL Fit Width]** dal menu a discesa **[!UICONTROL Fit]**.
   1. Seleziona Nome prodotto nelle righe. Seleziona Filtro dal menu a discesa.
      1. Nella finestra di dialogo **[!UICONTROL Filter \[Product Name\]]**, seleziona la scheda **[!UICONTROL Top]**.
      1. Selezionare **[!UICONTROL By field:]** **[!UICONTROL Top]** `5` **[!UICONTROL by Occurrences]** **[!UICONTROL Sum]**.
      1. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.

         La tabella scompare. La selezione dei primi 5 nomi di prodotto per occorrenze non funziona correttamente utilizzando questo filtro.
      1. Selezionare **[!UICONTROL Product Name]** nello scaffale **[!UICONTROL Filter]** e dal menu a discesa selezionare **[!UICONTROL Remove]**. Viene visualizzata di nuovo la tabella.
   1. Selezionare **[!UICONTROL SUM(Occurrences)]** nello scaffale **[!UICONTROL Marks]**. Selezionare **[!UICONTROL Filter]** dal menu a discesa.
      1. Nella finestra di dialogo **[!UICONTROL Filter \[Occurrences\]]**, seleziona **[!UICONTROL At least]**.
      1. Immetti `47.799` come valore. Questo valore assicura che nella tabella vengano visualizzati solo i primi 5 elementi. Selezionare **[!UICONTROL Apply]** e **[!UICONTROL OK]**.

         Il desktop Tableau dovrebbe essere simile al seguente.

         ![Limiti Desktop Tableau](assets/uc12-tableau-final.png)

La query eseguita da Tableau Desktop, utilizzando l’estensione BI, durante la definizione di un filtro delle prime 5 occorrenze sui nomi dei prodotti è mostrata di seguito.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

La query eseguita da Tableau Desktop, utilizzando l’estensione BI, durante la definizione di un filtro Top 5 per le occorrenze è mostrata di seguito. Il limite non è visibile nella query e viene applicato solo a livello di client.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!ENDTABS]

+++


## Per APPIATTIRE o meno

Vuoi capire se devi utilizzare un parametro `FLATTEN` aggiuntivo per il database quando ti connetti al Customer Journey Analytics utilizzando l&#39;estensione BI.

+++ Customer Journey Analytics

Customer Journey Analytics fornisce informazioni su come connettersi nell’interfaccia Experience Platform.

1. Passa alla sandbox di Experience Platform.
1. Seleziona ![Query](/help/assets/icons/DataSearch.svg) **[!UICONTROL Queries]** dalla barra a sinistra.
1. Selezionare la scheda **[!UICONTROL Credentials]** nell&#39;interfaccia **[!UICONTROL Queries]**.
1. Selezionare `prod:cja` dal menu a discesa **[!UICONTROL Database]**.

![Esegui query sulle credenziali del servizio](assets/queryservice-credentials.png)


+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso. Per informazioni sulle opzioni esplicite del parametro `FLATTEN` necessarie per una connessione corretta, vedere la sezione Strumenti BI.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

| Parametro FLATTEN | Esempio | Supportati | Osservazioni |
|---|---|:---:|---|
| Nessuno | `prod:cja` | ![CerchioSegno di spunta](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CerchioSegno di spunta](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![ChiudiCerchio](/help/assets/icons/CloseCircle.svg) | Power BI Desktop visualizza l&#39;errore: **[!UICONTROL We couldn't authenticate with the credentials provided. Please try again.]** |

>[!TAB Desktop Tableau]

| Parametro FLATTEN | Esempio | Supportati | Osservazioni |
|---|---|:---:|---|
| Nessuno | `prod:cja` | ![CerchioSegno di spunta](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CerchioSegno di spunta](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CerchioSegno di spunta](/help/assets/icons/CheckmarkCircle.svg) | |

>[!ENDTABS]

+++



## Trasformazioni

Desideri comprendere le trasformazioni degli oggetti di Customer Journey Analytics come dimensioni, metriche, filtri, metriche calcolate e intervalli di date da parte dei vari strumenti di business intelligence.

+++ Customer Journey Analytics

In Customer Journey Analytics, puoi definire in una [visualizzazione dati](/help/data-views/data-views.md) quali e come i componenti dei set di dati vengono esposti come [dimensioni](/help/components/dimensions/overview.md) e [metriche](/help/components/apply-create-metrics.md). Tale definizione di dimensione e metriche viene esposta agli strumenti BI utilizzando l’estensione BI.
Componenti come [Filtri](/help/components/filters/filters-overview.md), [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md) e [Intervalli di date](/help/components/date-ranges/overview.md) vengono utilizzati come parte dei progetti Workspace. Questi componenti vengono esposti anche agli strumenti BI utilizzando l’estensione BI.

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Assicurarsi di aver convalidato una connessione [riuscita e di poter elencare le visualizzazioni dati](#connect-and-list-data-views) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Power BI desktop]

Gli oggetti Customer Journey Analytics sono disponibili nel riquadro **[!UICONTROL Data]** e vengono recuperati dalla tabella selezionata in Power BI Desktop. Ad esempio, **[!UICONTROL public.cc_data_view]**. Il nome della tabella è uguale all’ID esterno definito per la visualizzazione dati nel Customer Journey Analytics. Ad esempio, visualizzazione dati con **[!UICONTROL Title]** `C&C - Data View` e **[!UICONTROL External ID]** `cc_data_view`.

**Dimension**
I Dimension dal Customer Journey Analytics sono identificati da [!UICONTROL Component ID]. [!UICONTROL Component ID] è definito nella visualizzazione dati del Customer Journey Analytics. La dimensione **[!UICONTROL Product Name]** nel Customer Journey Analytics, ad esempio, ha un [!UICONTROL Component ID] **[!UICONTROL product_name]**, che è il nome della dimensione in Power BI Desktop.
Le dimensioni dell&#39;intervallo di date dal Customer Journey Analytics, come **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** e altre sono disponibili come **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]** e altre.

**Metriche**
Le metriche del Customer Journey Analytics sono identificate da [!UICONTROL Component ID]. [!UICONTROL Component ID] è definito nella visualizzazione dati del Customer Journey Analytics. La metrica **[!UICONTROL Purchase Revenue]** nel Customer Journey Analytics, ad esempio, ha [!UICONTROL Component ID] **[!UICONTROL purchase_revenue]**, che è il nome della metrica in Power BI Desktop. Un **[!UICONTROL ∑]** indica le metriche. Quando utilizzi una metrica in una visualizzazione, questa viene rinominata **[!UICONTROL Sum of *metrica *]**.

**Filtri**
I filtri definiti nel Customer Journey Analytics sono disponibili nel campo **[!UICONTROL filterName]**. Quando si utilizza un campo **[!UICONTROL filterName]** in Power BI Desktop, è possibile specificare il filtro da utilizzare.

**Metriche calcolate**
Le metriche calcolate definite nel Customer Journey Analytics sono identificate dai [!UICONTROL External ID] definiti per la metrica calcolata. La metrica calcolata **[!UICONTROL Product Name (Count Distinct)]**, ad esempio, contiene [!UICONTROL External ID] **[!UICONTROL product_name_count_distinct]** ed è visualizzata come **[!UICONTROL cm_product_name_count_distinc]**t in Power BI Desktop.

**Intervalli di date**
Gli intervalli di date definiti nel Customer Journey Analytics sono disponibili nel campo **[!UICONTROL daterangeName]**. Quando si utilizza un campo **[!UICONTROL daterangeName]**, è possibile specificare l&#39;intervallo di date da utilizzare.


>[!TAB Desktop Tableau]

Gli oggetti Customer Journey Analytics sono disponibili nella barra laterale **[!UICONTROL Data]** ogni volta che si lavora in un foglio. E vengono recuperati dalla tabella selezionata come parte della pagina **[!UICONTROL Data source]** in Tableau. Ad esempio, **[!UICONTROL cc_data_view]**. Il nome della tabella è uguale all’ID esterno definito per la visualizzazione dati nel Customer Journey Analytics. Ad esempio, visualizzazione dati con **[!UICONTROL Title]** `C&C - Data View` e **[!UICONTROL External ID]** `cc_data_view`.

**Dimension**
I Dimension dal Customer Journey Analytics sono identificati da [!UICONTROL Component name]. [!UICONTROL Component name] è definito nella visualizzazione dati del Customer Journey Analytics. La dimensione **[!UICONTROL Product Name]** nel Customer Journey Analytics, ad esempio, ha [!UICONTROL Component name] **[!UICONTROL Product Name]**, che è il nome della dimensione in Tableau. Tutte le dimensioni sono identificate da **[!UICONTROL Abc]**.
Le dimensioni dell&#39;intervallo di date dal Customer Journey Analytics, come **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** e altre sono disponibili come **[!UICONTROL Daterangeday]**, **[!UICONTROL Daterangeweek]**, **[!UICONTROL Daterangemonth]** e altre.

**Metriche**
Le metriche del Customer Journey Analytics sono identificate da [!UICONTROL Component Name]. [!UICONTROL Component Name] è definito nella visualizzazione dati del Customer Journey Analytics. La metrica **[!UICONTROL Purchase Revenue]** nel Customer Journey Analytics, ad esempio, ha [!UICONTROL Component Name] **[!UICONTROL Purchase Revenue]**, che è il nome della metrica in Tableau. Tutte le metriche sono identificate da **[!UICONTROL #]**. Quando utilizzi una metrica in una visualizzazione, questa viene rinominata **[!UICONTROL Sum(*metrica *)]**.

**Filtri**
I filtri definiti nel Customer Journey Analytics sono disponibili nel campo **[!UICONTROL Filter Name]**. Quando si utilizza un campo **[!UICONTROL Filter Name]** in Tableau, è possibile specificare il filtro da utilizzare.

**Metriche calcolate**
Le metriche calcolate definite nel Customer Journey Analytics sono identificate dai [!UICONTROL Title] definiti per la metrica calcolata. Ad esempio, la metrica calcolata **[!UICONTROL Product Name (Count Distinct)]** ha [!UICONTROL Title] **[!UICONTROL Product Name (Count Distinct)]** ed è visualizzata come **[!UICONTROL Cm Product Name Count Distinct]** in Tableau.

**Intervalli di date**
Gli intervalli di date definiti nel Customer Journey Analytics sono disponibili nel campo **[!UICONTROL Daterange Name]**. Quando si utilizza un campo **[!UICONTROL Daterange Name]**, è possibile specificare l&#39;intervallo di date da utilizzare.

>[!ENDTABS]

+++



## Visualizzazioni

In questo caso d’uso voglio capire in che modo le visualizzazioni disponibili in Customer Journey Analytics possono essere create in modo simile utilizzando le visualizzazioni disponibili negli strumenti di business intelligence.

+++ Customer Journey Analytics

Il Customer Journey Analytics dispone di diverse visualizzazioni. Consulta [Visualizzazioni](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) per un&#39;introduzione e una panoramica di tutte le visualizzazioni possibili.

+++

+++ Strumenti BI

>[!BEGINTABS]

>[!TAB Power BI desktop]

Le seguenti visualizzazioni di Customer Journey Analytics sono in un’esperienza simile disponibile in Power BI Desktop.

| Icona | Visualizzazione Customer Journey Analytics | Visualizzazione Power BI Desktop |
| :---: | --- | ---| 
| ![AreaGrafica](/help/assets/icons/GraphArea.svg) | [Superfici](/help/analysis-workspace/visualizations/area.md) | [Grafico ad area, grafico ad area sovrapposta e grafico ad area 100%](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#area-charts-basic-layered-and-stacked) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analysis-workspace/visualizations/bar.md) | [Istogramma cluster](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barre sovrapposte](/help/analysis-workspace/visualizations/bar.md) | [Istogramma in pila e istogramma in pila al 100%](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Grafico bullet](/help/assets/icons/GraphBullet.svg)</p> | [Bullet](/help/analysis-workspace/visualizations/bullet-graph.md) |  |
| ![Testo numerato](/help/assets/icons/TextNumbered.svg) | [Tabella coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Grafico a linee e istogramma in pila e Grafico a linee e istogramma in cluster](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#combo-charts) |
| ![Grafico ad anello](/help/assets/icons/GraphDonut.svg) | [Anello](/help/analysis-workspace/visualizations/donut.md) | [Grafico ad anello](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#doughnut-charts) |
| ![Funnel di conversione](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [Funnel](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#funnel-charts). |
| ![PercorsiGrafici](/help/assets/icons/GraphPathing.svg) | [Flusso](/help/analysis-workspace/visualizations/c-flow/flow.md) | Albero di scomposizione? |
| ![VisualizzaTabella](/help/assets/icons/ViewTable.svg)</p> | [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tabella](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#tables) e [Matrice](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#matrix) |
| ![Istogramma](/help/assets/icons/Histogram.svg) | [Istogramma](/help/analysis-workspace/visualizations/histogram.md) |  |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Grafico a barre cluster](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![BarraGraficaOrizzontaleSovrapposta](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barre orizzontali sovrapposte](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Grafico a barre in pila e Grafico a barre in pila 100%](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Ramo3](/help/assets/icons/Branch3.svg) | [Area di lavoro Percorsi](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | [Struttura di decomposizione](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#decomposition-tree) |
| ![MetricheChiave](/help/assets/icons/KeyMetrics.svg) | [Riepilogo delle metriche chiave](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Linee](/help/analysis-workspace/visualizations/line.md) | [Grafico a linee](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#line-charts) |
| ![Grafico a dispersione](/help/assets/icons/GraphScatter.svg) | [A dispersione](/help/analysis-workspace/visualizations/scatterplot.md) | [Grafico a dispersione](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#scatter) |
| ![RegolaPagina](/help/assets/icons/PageRule.svg) | [Intestazione sezione](/help/analysis-workspace/visualizations/section-header.md) | [Casella di testo](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![Sposta verso l’alto o il basso](/help/assets/icons/MoveUpDown.svg) | [Variazione di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md) | [Scheda](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![123](/help/assets/icons/123.svg)</p> | [Numero di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md) | [Scheda](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![Testo](/help/assets/icons/Text.svg) | [Testo](/help/analysis-workspace/visualizations/text.md) | [Casella di testo](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Mappa ad albero](/help/analysis-workspace/visualizations/treemap.md)<p> | [Mappa ad albero](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#treemaps) |
| ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


>[!TAB Desktop Tableau]


Le seguenti visualizzazioni di Customer Journey Analytics sono in un’esperienza simile disponibile in Tableau.

| Icona | Visualizzazione Customer Journey Analytics | Visualizzazione Power BI Desktop |
| :---: | --- | ---| 
| ![AreaGrafica](/help/assets/icons/GraphArea.svg) | [Superfici](/help/analysis-workspace/visualizations/area.md) | [Grafico a superficie](https://help.tableau.com/current/pro/desktop/en-us/qs_area_charts.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analysis-workspace/visualizations/bar.md) | [Grafico a barre](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barre sovrapposte](/help/analysis-workspace/visualizations/bar.md) |  |
| ![Grafico bullet](/help/assets/icons/GraphBullet.svg)</p> | [Bullet](/help/analysis-workspace/visualizations/bullet-graph.md) | [Grafico bullet](https://help.tableau.com/current/pro/desktop/en-us/qs_bullet_graphs.htm) |
| ![Testo numerato](/help/assets/icons/TextNumbered.svg) | [Tabella coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Grafici combinati](https://help.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm) |
| ![Grafico ad anello](/help/assets/icons/GraphDonut.svg) | [Anello](/help/analysis-workspace/visualizations/donut.md) | |
| ![Funnel di conversione](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | |
| ![PercorsiGrafici](/help/assets/icons/GraphPathing.svg) | [Flusso](/help/analysis-workspace/visualizations/c-flow/flow.md) |  |
| ![VisualizzaTabella](/help/assets/icons/ViewTable.svg)</p> | [Tabella a forma libera](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tabella testo](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm) |
| ![Istogramma](/help/assets/icons/Histogram.svg) | [Istogramma](/help/analysis-workspace/visualizations/histogram.md) | [Istogramma](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm) |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barre orizzontali](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Grafico a barre](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![BarraGraficaOrizzontaleSovrapposta](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barre orizzontali sovrapposte](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Grafico a barre](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![Ramo3](/help/assets/icons/Branch3.svg) | [Area di lavoro Percorsi](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | |
| ![MetricheChiave](/help/assets/icons/KeyMetrics.svg) | [Riepilogo delle metriche chiave](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Linee](/help/analysis-workspace/visualizations/line.md) | [Grafico a linee](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm) |
| ![Grafico a dispersione](/help/assets/icons/GraphScatter.svg) | [A dispersione](/help/analysis-workspace/visualizations/scatterplot.md) | [Scatter Plot (Dispersione)](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm) |
| ![RegolaPagina](/help/assets/icons/PageRule.svg) | [Intestazione sezione](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![Sposta verso l’alto o il basso](/help/assets/icons/MoveUpDown.svg) | [Variazione di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![123](/help/assets/icons/123.svg)</p> | [Numero di riepilogo](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![Testo](/help/assets/icons/Text.svg) | [Testo](/help/analysis-workspace/visualizations/text.md) | |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [Mappa ad albero](/help/analysis-workspace/visualizations/treemap.md)<p> | [Mappa ad albero](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_treemap.htm) |
| ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |

>[!ENDTABS]

+++


