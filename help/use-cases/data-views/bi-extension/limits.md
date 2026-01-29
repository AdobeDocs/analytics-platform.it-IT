---
title: Limiti
description: Limita il caso di utilizzo dell’estensione BI in vari strumenti di BI in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 0%

---

# Limiti


In questo caso d’uso, vuoi segnalare le prime 5 occorrenze dei nomi di prodotto nel 2023.

+++ Customer Journey Analytics

Esempio di pannello **[!UICONTROL Limit]** per il caso d&#39;uso:

![Pannello Limite Customer Journey Analytics](../assets/cja-limit.png)

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
   1. Seleziona **[!UICONTROL product_name]**.
   1. Seleziona **[!UICONTROL somma occorrenze]**.

1. Nel riquadro **[!UICONTROL Filtri]**:
   1. Seleziona **[!UICONTROL l&#39;intervallo di dati è (Tutto)]** da **[!UICONTROL Filtri per questo elemento visivo]**.
   1. Seleziona **[!UICONTROL Data relativa]** come **[!UICONTROL Tipo filtro]**.
   1. Definisci il filtro per **[!UICONTROL mostrare gli elementi quando il valore]** **[!UICONTROL è negli ultimi]** `1` **[!UICONTROL anni di calendario]**.
   1. Selezionare **[!UICONTROL Applica filtro]**.
   1. Seleziona **[!UICONTROL product_name è (All)]** da **[!UICONTROL Filtri per questo elemento visivo]**.
   1. Seleziona **[!UICONTROL Top N]** come **[!UICONTROL Tipo filtro]**.
   1. Seleziona **[!UICONTROL Mostra elementi]** **[!UICONTROL Primi]** `5` **[!UICONTROL Per valore]**.
   1. Trascina e rilascia **[!UICONTROL somma occorrenze]** dal riquadro **[!UICONTROL Dati]** e rilasciala in **[!UICONTROL Aggiungi campi dati qui]**.
   1. Selezionare **[!UICONTROL Applica filtro]**.

1. Nel riquadro di visualizzazione:
   * Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere l&#39;intervallo di dati dalle colonne.

   Il desktop Power BI dovrebbe essere simile a quello riportato di seguito.

   ![Desktop Power BI Con Nomi Di Intervalli Di Date Per Filtrare](../assets/uc12-powerbi-final.png)

La query eseguita da Power BI Desktop tramite l&#39;estensione BI include un&#39;istruzione `limit` ma non quella prevista. Il limite alle prime 5 occorrenze viene applicato da Power BI Desktop utilizzando risultati espliciti del nome del prodotto.

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

1. Selezionare la scheda **[!UICONTROL Foglio 1]** nella parte inferiore per passare da **[!UICONTROL Origine dati]**. Nella visualizzazione **[!UICONTROL Foglio 1]**:
   1. Trascina la voce **[!UICONTROL Daterange]** dall&#39;elenco **[!UICONTROL Tabelle]** nello scaffale **[!UICONTROL Filtri]**.
   1. Nella finestra di dialogo **[!UICONTROL Campo filtro \[Daterange\]]**, seleziona **[!UICONTROL Intervallo di date]** e seleziona **[!UICONTROL Avanti >]**.
   1. Nella finestra di dialogo **[!UICONTROL Filtro \[Daterange\]]**, seleziona **[!UICONTROL Date relative]**, **[!UICONTROL Anni]** e **[!UICONTROL Anni precedenti]**. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.
   1. Trascina **[!UICONTROL Nome prodotto]** dall&#39;elenco **[!UICONTROL Tabelle]** a **[!UICONTROL Righe]**.
   1. Trascina **[!UICONTROL Occorrenze]** dall&#39;elenco **[!UICONTROL Tabelle]** e rilascia la voce nel campo accanto a **[!UICONTROL Colonne]**. Il valore diventa **[!UICONTROL SUM(Occurrences)]**.
   1. Seleziona **[!UICONTROL Tabella di testo]** da **[!UICONTROL Mostra]**.
   1. Selezionare **[!UICONTROL Adatta larghezza]** dal menu a discesa **[!UICONTROL Adatta]**.
   1. Seleziona **[!UICONTROL Nome prodotto]** in **[!UICONTROL Righe]**. Seleziona **[!UICONTROL Filtro]** dal menu a discesa.
      1. Nella finestra di dialogo **[!UICONTROL Filtro \[Nome prodotto\]]**, seleziona la scheda **[!UICONTROL Primi]**.
      1. Seleziona **[!UICONTROL Per campo:]** **[!UICONTROL Primi]** `5` **[!UICONTROL Per Occorrenze]** **[!UICONTROL Somma]**.
      1. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.

         ![AlertRed](/help/assets/icons/AlertRed.svg) La tabella non verrà più visualizzata. Se si selezionano i primi 5 nomi di prodotto in base alle occorrenze, **non** funziona correttamente utilizzando questo filtro.
      1. Selezionare **[!UICONTROL Nome prodotto]** nello scaffale **[!UICONTROL Filtro]** e dal menu a discesa selezionare **[!UICONTROL Rimuovi]**. Viene visualizzata di nuovo la tabella.
   1. Selezionare **[!UICONTROL SUM(Occurrences)]** nello scaffale **[!UICONTROL Marks]**. Seleziona **[!UICONTROL Filtro]** dal menu a discesa.
      1. Nella finestra di dialogo **[!UICONTROL Filtro \[Occorrenze\]]**, seleziona **[!UICONTROL Almeno]**.
      1. Immetti `47.799` come valore. Questo valore assicura che nella tabella vengano visualizzati solo i primi 5 elementi. Selezionare **[!UICONTROL Applica]** e **[!UICONTROL OK]**.

         Il desktop Tableau dovrebbe essere simile al seguente.

         ![Limiti Desktop Tableau](../assets/uc12-tableau-final.png)

Come mostrato sopra, questa query eseguita da Tableau Desktop, quando si definisce un filtro delle prime 5 occorrenze sui nomi dei prodotti, ha esito negativo.

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

Di seguito è riportata la query eseguita da Tableau Desktop durante la definizione di un filtro Top 5 per le occorrenze. Il limite non è visibile nella query e applicato sul lato client.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!TAB Ricerca]

1. Nell&#39;interfaccia **[!UICONTROL Esplora]** di Looker, aggiorna la connessione. Selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Cancella cache e aggiorna]**.
1. Nell&#39;interfaccia **[!UICONTROL Esplora]** di Looker, assicurati di avere una configurazione pulita. In caso contrario, selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Rimuovi campi e filtri]**.
1. Seleziona **[!UICONTROL + Filtro]** sotto **[!UICONTROL Filtri]**.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi filtro]**:
   1. Seleziona **[!UICONTROL ‣ Visualizzazione Dati Cc]**
   1. Dall&#39;elenco dei campi, selezionare **[!UICONTROL ‣ Data intervallo]** e quindi **[!UICONTROL Data intervallo]**.
      ![Filtro ricerca](../assets/uc2-looker-filter.png)
1. Specifica Il Filtro **[!UICONTROL Cc Data Daterange Visualizzazione Dati]** Perché **[!UICONTROL È Compreso Nell&#39;Intervallo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL Fino A (Prima)]** **[!UICONTROL 2024/01/01]**.
1. Dalla sezione **[!UICONTROL ‣ Cc Data View]** nella barra a sinistra:
   1. Selezionare **[!UICONTROL Nome prodotto]**.
   1. Seleziona **[!UICONTROL Conteggio]** sotto **[!UICONTROL MISURE]** nella barra a sinistra (in basso).
1. Accertati di selezionare **[!UICONTROL ↓]** (**[!UICONTROL Decrescente, Ordinamento: 1]**) nella colonna **[!UICONTROL Ricavi acquisti]**.
1. Accertati di selezionare **[!UICONTROL ↓]** (**[!UICONTROL Decrescente, Ordinamento: 1]**) nella colonna **[!UICONTROL Ricavi acquisti]**.
1. Seleziona **[!UICONTROL Esegui]**.
1. Selezionare **[!UICONTROL ‣ Visualizzazione]**.

Dovresti visualizzare una visualizzazione e una tabella simili a quelle mostrate di seguito.

![Conteggio valori univoci](../assets/uc12-looker-result.png)

La query generata da Looker tramite l&#39;estensione BI include `FETCH NEXT 5 ROWS ONLY`, il che implica che il limite viene eseguito tramite Looker e l&#39;estensione BI.

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"a8f3b1ebd5712413ca1ae695090f70db","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COUNT(*) AS "cc_data_view.count"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 5 ROWS ONLY
```


>[!TAB Blocco appunti Jupyter]

1. Immettere le istruzioni seguenti in una nuova cella.

   ```python
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. Eseguire la cella. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati Jupyter Notebook](../assets/uc12-jupyter-results.png)

La query viene eseguita dall’estensione BI come definito in Jupyter Notebook.

>[!TAB StudioRS]

1. Immettere le istruzioni seguenti tra ` ` ``{r} ` e ` `` ` ` in un nuovo blocco.

   ```R
   ## Dimension 1 Limited
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE) %>%
      head(5)
   print(df)
   ```

1. Esegui il blocco. Dovresti visualizzare un output simile alla schermata seguente.

   ![Risultati studio](../assets/uc12-rstudio-results.png)

La query generata da Studio utilizzando l&#39;estensione BI include `LIMIT 5`, il che implica che il limite viene applicato tramite Studio e l&#39;estensione BI.

```sql
SELECT "product_name", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2024-01-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "n" DESC
LIMIT 5
```

>[!ENDTABS]

+++
