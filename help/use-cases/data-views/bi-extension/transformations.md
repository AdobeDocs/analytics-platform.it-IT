---
title: Trasformazioni
description: Caso di utilizzo delle trasformazioni per l’estensione BI in vari strumenti BI in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 0%

---

# Trasformazioni


Desideri comprendere le trasformazioni di oggetti Customer Journey Analytics come dimensioni, metriche, filtri, metriche calcolate e intervalli di date da parte dei vari strumenti di business intelligence.

+++ Customer Journey Analytics

In Customer Journey Analytics, puoi definire in una [visualizzazione dati](/help/data-views/data-views.md) quali e come i componenti dei set di dati vengono esposti come [dimensioni](/help/components/dimensions/overview.md) e [metriche](/help/components/apply-create-metrics.md). Tale definizione di dimensione e metriche viene esposta agli strumenti BI utilizzando l’estensione BI.
Componenti come [Filtri](/help/components/segments/seg-overview.md), [Metriche calcolate](/help/components/calc-metrics/calc-metr-overview.md) e [Intervalli di date](/help/components/date-ranges/overview.md) vengono utilizzati come parte dei progetti Workspace. Questi componenti vengono esposti anche agli strumenti BI utilizzando l’estensione BI.

+++

+++ Strumenti BI

>[!PREREQUISITES]
>
>Verificare di aver convalidato [una connessione, di avere la possibilità di elencare le visualizzazioni dati e di utilizzare una visualizzazione dati](connect-and-validate.md) per lo strumento BI per il quale si desidera provare questo caso d&#39;uso.
>

>[!BEGINTABS]

>[!TAB Desktop Power BI]

Gli oggetti Customer Journey Analytics sono disponibili nel riquadro **[!UICONTROL Dati]** e vengono recuperati dalla tabella selezionata in Power BI Desktop. Ad esempio, **[!UICONTROL public.cc_data_view]**. Il nome della tabella è uguale all’ID esterno definito per la visualizzazione dati in Customer Journey Analytics. Ad esempio, visualizzazione dati con **[!UICONTROL Titolo]** `C&C - Data View` e **[!UICONTROL ID esterno]** `cc_data_view`.

**Dimensioni**
Le dimensioni di Customer Journey Analytics sono identificate dal [!UICONTROL ID componente]. [!UICONTROL ID componente] definito nella visualizzazione dati di Customer Journey Analytics. La dimensione **[!UICONTROL Nome prodotto]** in Customer Journey Analytics, ad esempio, ha un [!UICONTROL ID componente] **[!UICONTROL nome_prodotto]**, che è il nome della dimensione in Power BI Desktop.
Le dimensioni dell&#39;intervallo di date da Customer Journey Analytics, come **[!UICONTROL Giorno]**, **[!UICONTROL Settimana]**, **[!UICONTROL Mese]** e altre sono disponibili come **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]** e altre.

**Metriche**
Le metriche di Customer Journey Analytics sono identificate dal [!UICONTROL ID componente]. [!UICONTROL ID componente] definito nella visualizzazione dati di Customer Journey Analytics. La metrica **[!UICONTROL Ricavi acquisti]** in Customer Journey Analytics, ad esempio, ha un [!UICONTROL ID componente] **[!UICONTROL ricavi acquisti]**, che è il nome della metrica in Power BI Desktop. Un **[!UICONTROL ∑]** indica le metriche. Quando utilizzi una metrica in una visualizzazione, questa viene rinominata **[!UICONTROL Somma di *metrica *]**.

**Filtri**
I filtri definiti in Customer Journey Analytics sono disponibili nel campo **[!UICONTROL filterName]**. Quando si utilizza un campo **[!UICONTROL filterName]** in Power BI Desktop, è possibile specificare il filtro da utilizzare.

**Metriche calcolate**
Le metriche calcolate definite in Customer Journey Analytics sono identificate dal [!UICONTROL ID esterno] definito per la metrica calcolata. Ad esempio, la metrica calcolata **[!UICONTROL Nome prodotto (Conteggio distinto)]** ha [!UICONTROL ID esterno] **[!UICONTROL nome_prodotto_conteggio_distinto]** ed è visualizzata come **[!UICONTROL cm_nome_prodotto_conteggio_distinto]**t in Power BI Desktop.

**Intervalli di date**
Gli intervalli di date definiti in Customer Journey Analytics sono disponibili nel campo **[!UICONTROL daterangeName]**. Quando si utilizza un campo **[!UICONTROL daterangeName]**, è possibile specificare l&#39;intervallo di date da utilizzare.

**Trasformazioni personalizzate**
Power BI Desktop fornisce funzionalità di trasformazione personalizzate utilizzando [Espressioni di analisi dei dati (DAX)](https://learn.microsoft.com/en-us/dax/dax-overview). Ad esempio, desideri eseguire il caso d&#39;uso [Classificazione singola della dimensione](#single-dimension-ranked) con i nomi dei prodotti in minuscolo.

1. Nella vista Rapporto, seleziona la visualizzazione a barre.
1. Seleziona **[!UICONTROL product_name]** nel riquadro Dati.
1. Seleziona **[!UICONTROL Nuova colonna]** nella barra degli strumenti.
1. Nell&#39;editor formule, definire una nuova colonna denominata `product_name_lower`, ad esempio `product_name_lower = LOWER('public.cc_data_view[product_name])`.
   ![Trasformazione desktop Power BI in inferiore](../assets/uc14-powerbi-transformation.png)
1. Assicurati di selezionare la nuova colonna **[!UICONTROL product_name_lower]** nel riquadro **[!UICONTROL Data]** invece della colonna **[!UICONTROL product_name]**.
1. Seleziona **[!UICONTROL Rapporto come tabella]** da ![Altro](/help/assets/icons/More.svg) nella visualizzazione tabella.

   Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.
   ![Trasformazione desktop Power BI finale](../assets/uc14-powerbi-final.png)

La trasformazione personalizzata risulta in un aggiornamento delle query SQL. Vedere l&#39;utilizzo della funzione `lower` nell&#39;esempio SQL seguente:

```sql
select "_"."product_name_lower",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name_lower" as "product_name_lower",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterange" as "daterange",
            "_"."product_name" as "product_name",
            "_"."purchase_revenue" as "purchase_revenue",
            "_"."purchases" as "purchases",
            lower("_"."product_name") as "product_name_lower"
        from 
        (
            select "_"."daterange",
                "_"."product_name",
                "_"."purchase_revenue",
                "_"."purchases"
            from 
            (
                select "daterange",
                    "product_name",
                    "purchase_revenue",
                    "purchases"
                from "public"."cc_data_view" "$Table"
            ) "_"
            where ("_"."daterange" < date '2024-01-01' and "_"."daterange" >= date '2023-01-01') and ("_"."product_name" in ('4G Cellular Trail Camera', '4K Wildlife Trail Camera', 'Wireless Trail Camera', '8-Person Cabin Tent', '20MP No-Glow Trail Camera', 'HD Wildlife Camera', '4-Season Mountaineering Tent', 'Trail Camera', '16MP Trail Camera with Solar Panel', '10-Person Family Tent'))
        ) "_"
    ) "rows"
    group by "product_name_lower"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```

>[!TAB Desktop Tableau]

Gli oggetti Customer Journey Analytics sono disponibili nella barra laterale **[!UICONTROL Dati]** ogni volta che si lavora in un foglio. E vengono recuperati dalla tabella selezionata come parte della pagina **[!UICONTROL Origine dati]** in Tableau. Ad esempio, **[!UICONTROL cc_data_view]**. Il nome della tabella è uguale all’ID esterno definito per la visualizzazione dati in Customer Journey Analytics. Ad esempio, visualizzazione dati con **[!UICONTROL Titolo]** `C&C - Data View` e **[!UICONTROL ID esterno]** `cc_data_view`.

**Dimensioni**
Le dimensioni di Customer Journey Analytics sono identificate dal [!UICONTROL nome componente]. Il [!UICONTROL nome componente] è definito nella visualizzazione dati di Customer Journey Analytics. Ad esempio, la dimensione **[!UICONTROL Nome prodotto]** in Customer Journey Analytics ha un [!UICONTROL Nome componente] **[!UICONTROL Nome prodotto]**, che è il nome della dimensione in Tableau. Tutte le dimensioni sono identificate da **[!UICONTROL Abc]**.
Le dimensioni dell&#39;intervallo di date da Customer Journey Analytics, come **[!UICONTROL Giorno]**, **[!UICONTROL Settimana]**, **[!UICONTROL Mese]** e altre sono disponibili come **[!UICONTROL Daterangeday]**, **[!UICONTROL Daterangeweek]**, **[!UICONTROL Daterangemonth]** e altre. Quando utilizzi una dimensione intervallo di date, devi selezionare una definizione appropriata di data o ora da applicare a tale dimensione intervallo di date dal menu a discesa. Ad esempio, **[!UICONTROL Anno]**, **[!UICONTROL Trimestre]**, **[!UICONTROL Mese]**, **[!UICONTROL Giorno]**.

**Metriche**
Le metriche di Customer Journey Analytics sono identificate dal [!UICONTROL nome componente]. Il [!UICONTROL Nome componente] è definito nella visualizzazione dati di Customer Journey Analytics. Ad esempio, la metrica **[!UICONTROL Ricavi da acquisto]** in Customer Journey Analytics ha un [!UICONTROL Nome componente] **[!UICONTROL Ricavi da acquisto]**, che è il nome della metrica in Tableau. Tutte le metriche sono identificate da **[!UICONTROL #]**. Quando utilizzi una metrica in una visualizzazione, questa viene rinominata in **[!UICONTROL Sum(*metric*)]**.

**Filtri**
I filtri definiti in Customer Journey Analytics sono disponibili nel campo **[!UICONTROL Nome filtro]**. Quando si utilizza un campo **[!UICONTROL Nome filtro]** in Tableau, è possibile specificare il filtro da utilizzare.

**Metriche calcolate**
Le metriche calcolate definite in Customer Journey Analytics sono identificate dal [!UICONTROL Titolo] definito per la metrica calcolata. Ad esempio, la metrica calcolata **[!UICONTROL Nome prodotto (conteggio distinto)]** ha [!UICONTROL Titolo] **[!UICONTROL Nome prodotto (conteggio distinto)]** ed è visualizzata come **[!UICONTROL Cm Nome prodotto conteggio distinto]** in Tableau.

**Intervalli di date**
Gli intervalli di date definiti in Customer Journey Analytics sono disponibili come parte del campo **[!UICONTROL Nome intervallo]**. Quando si utilizza un campo **[!UICONTROL Nome intervallo di date]**, è possibile specificare l&#39;intervallo di date da utilizzare.

**Trasformazioni personalizzate**
Tableau Desktop fornisce funzionalità di trasformazione personalizzate utilizzando [Campi calcolati](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm). Ad esempio, desideri eseguire il caso d&#39;uso [Classificazione singola della dimensione](#single-dimension-ranked) con i nomi dei prodotti in minuscolo.

1. Selezionare **[!UICONTROL Analisi]** > **[!UICONTROL Crea campo calcolato]** dal menu principale.
   1. Definisci **[!UICONTROL Nome prodotto in minuscolo]** utilizzando la funzione `LOWER([Product Name])`.
      ![Campo Calcolato Tableau](../assets/uc14-tableau-calculated-field.png)
   1. Selezionare **[!UICONTROL OK]**.
1. Selezionare il foglio **[!UICONTROL Dati]**.
   1. Trascina **[!UICONTROL Nome prodotto in minuscolo]** da **[!UICONTROL Tabelle]** e rilascia la voce nel campo accanto a **[!UICONTROL Righe]**.
   1. Rimuovi **[!UICONTROL Nome prodotto]** da **[!UICONTROL Righe]**.
1. Selezionare la visualizzazione **[!UICONTROL Dashboard 1]**.

Il desktop Tableau dovrebbe essere simile al seguente.

![Desktop Tableau dopo la trasformazione](../assets/uc14-tableau-final.png)

La trasformazione personalizzata risulta in un aggiornamento delle query SQL. Vedere l&#39;utilizzo della funzione `LOWER` nell&#39;esempio SQL seguente:

```sql
SELECT LOWER(CAST(CAST("cc_data_view"."product_name" AS TEXT) AS TEXT)) AS "Calculation_1562467608097775616",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-12-31')))
GROUP BY 1
HAVING ((SUM("cc_data_view"."purchase_revenue") >= 999999.99999998999) AND (SUM("cc_data_view"."purchase_revenue") <= 2000000.00000002))
```

>[!TAB Ricerca]

Gli oggetti Customer Journey Analytics sono disponibili nell&#39;interfaccia **[!UICONTROL Esplora]**. e vengono recuperati come parte della configurazione della connessione, del progetto e del modello in Looker. Ad esempio, **[!UICONTROL cc_data_view]**. Il nome della visualizzazione è uguale all’ID esterno definito per la visualizzazione dati in Customer Journey Analytics. Ad esempio, visualizzazione dati con **[!UICONTROL Titolo]** `C&C - Data View` e **[!UICONTROL ID esterno]** `cc_data_view`.

**Dimensioni**
Le dimensioni di Customer Journey Analytics sono elencate come **[!UICONTROL DIMENSION]** nella barra a sinistra di **[!UICONTROL Cc Data View]**. La dimensione è definita nella visualizzazione dati di Customer Journey Analytics. La dimensione **[!UICONTROL Nome prodotto]** in Customer Journey Analytics, ad esempio, ha un **[!UICONTROL DIMENSION]** **[!UICONTROL Nome prodotto]**, che è il nome della dimensione in Looker.
Le dimensioni dell&#39;intervallo di date da Customer Journey Analytics, come **[!UICONTROL Giorno]**, **[!UICONTROL Settimana]**, **[!UICONTROL Mese]** e altre sono disponibili come **[!UICONTROL Data Daterangeday]**, **[!UICONTROL Data Daterangeweek]**, **[!UICONTROL Data Daterangemonth]** e altre.  Quando utilizzi una dimensione di intervallo di date, devi selezionare una definizione appropriata di data o ora. Ad esempio, **[!UICONTROL Anno]**, **[!UICONTROL Trimestre]**, **[!UICONTROL Mese]**, **[!UICONTROL Data]**.

**Metriche**
Le metriche di Customer Journey Analytics sono elencate come **[!UICONTROL DIMENSION]** nella barra a sinistra di **[!UICONTROL Cc Data View]**. Ad esempio, la metrica **[!UICONTROL Ricavi da acquisto]** in Customer Journey Analytics ha un **[!UICONTROL DIMENSION]** **[!UICONTROL Ricavi da acquisto]**. Per utilizzare effettivamente come metrica, crea un campo misura personalizzato, come illustrato negli esempi precedenti, oppure utilizza il collegamento su una dimensione. Ad esempio, **[!UICONTROL ⋮]**, selezionare **[!UICONTROL Aggrega]**, quindi selezionare **[!UICONTROL Somma]**.

**Filtri**
I filtri definiti in Customer Journey Analytics sono disponibili nel campo **[!UICONTROL Nome filtro]**. Quando si utilizza un campo **[!UICONTROL Nome filtro]** in Looker, è possibile specificare il filtro da utilizzare.

**Metriche calcolate**
Le metriche calcolate definite in Customer Journey Analytics sono identificate dal [!UICONTROL Titolo] definito per la metrica calcolata. Ad esempio, la metrica calcolata **[!UICONTROL Nome prodotto (conteggio distinto)]** ha [!UICONTROL Titolo] **[!UICONTROL Nome prodotto (conteggio distinto)]** ed è visualizzata come **[!UICONTROL Cm Nome prodotto conteggio distinto]** in Looker.

**Intervalli di date**
Gli intervalli di date definiti in Customer Journey Analytics sono disponibili come parte del campo **[!UICONTROL Nome intervallo]**. Quando si utilizza un campo **[!UICONTROL Nome intervallo di date]**, è possibile specificare l&#39;intervallo di date da utilizzare.

**Trasformazioni personalizzate**
Looker fornisce funzionalità di trasformazione personalizzate utilizzando generatori di campi personalizzati, come mostrato sopra. Ad esempio, desideri eseguire il caso d&#39;uso [Classificazione singola della dimensione](#single-dimension-ranked) con i nomi dei prodotti in minuscolo.

1. Dalla sezione **[!UICONTROL ‣ Campi personalizzati]** nella barra a sinistra:
   1. Seleziona **[!UICONTROL Dimension personalizzato]** dal menu a discesa **[!UICONTROL + Aggiungi]**.
   1. Immettere `lower(${cc_data_view.product_name})` nell&#39;area di testo **[!UICONTROL Espressione]**. Quando si inizia a digitare `Product Name`, viene fornita la sintassi corretta.
      ![Esempio di trasformazione Looker](../assets/uc14-looker-transformation.png)
   1. Immetti `product name` come **[!UICONTROL Nome]**.
   1. Seleziona **[!UICONTROL Salva]**.

Dovresti vedere una tabella simile a quella mostrata di seguito.

![Risultato trasformazione ricerca](../assets/uc14-looker-result.png)


La trasformazione personalizzata risulta in un aggiornamento delle query SQL. Vedere l&#39;utilizzo della funzione `LOWER` nell&#39;esempio SQL seguente:

```sql
SELECT
    LOWER((cc_data_view."product_name")) AS "product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchase_revenue",
    COALESCE(SUM(CAST(( cc_data_view."purchases"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchases"
FROM public.cc_data_view  AS cc_data_view
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-01')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```

>[!TAB Blocco appunti Jupyter]

Gli oggetti Customer Journey Analytics (dimensioni, metriche, filtri, metriche calcolate e intervalli di date) sono disponibili come parte delle query SQL incorporate create. Vedi gli esempi precedenti.

**Trasformazioni personalizzate**

1. Immettere le istruzioni seguenti in una nuova cella.

   ```python
   data = %sql SELECT LOWER(product_category) AS `Product Category`, COUNT(*) AS EVENTS \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc13-jupyter-results.png)

La query viene eseguita dall’estensione BI come definito in Jupyter Notebook.

>[!TAB StudioRS]

I componenti Customer Journey Analytics (dimensioni, metriche, filtri, metriche calcolate e intervalli di date) sono disponibili come oggetti denominati simili nel linguaggio R. Consulta i componenti utilizzando il componente Consulta gli esempi precedenti.

**Trasformazioni personalizzate**

1. Immettere le istruzioni seguenti tra ` ```{r} ` e ` ``` ` in un nuovo blocco.

   ```R
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange <= "2024-01-01") %>%
      mutate(d2=lower(product_category)) %>%
      group_by(d2) %>%
      count() %>%
      arrange(d2, .by_group = FALSE)
   print(df)
   ```

1. Esegui il blocco. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati studio](../assets/uc13-rstudio-results.png)

La query generata da Studio utilizzando l&#39;estensione BI include `lower`, il che implica che la trasformazione personalizzata viene eseguita da Studio e dall&#39;estensione BI.

```sql
SELECT "d2", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*, lower("product_category") AS "d2"
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" <= '2024-01-01')
) AS "q01"
GROUP BY "d2"
ORDER BY "d2"
LIMIT 1000
```

>[!ENDTABS]

+++

