---
title: Abilita unione
description: Scopri come abilitare l’unione nell’interfaccia utente Connessioni.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 8f7c1f2a89c10be9b33f6e06fcff287e275767cf
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 2%

---

# Abilitare l’unione delle identità

Puoi abilitare l’unione su uno o più set di dati evento configurati come parte della connessione. Il pacchetto Customer Journey Analytics per il quale hai concesso la licenza determina il numero di set di dati evento che puoi abilitare per l’unione.

Abilita l&#39;unione come parte delle [impostazioni del set di dati](/help/connections/create-connection.md#dataset-settings) per un set di dati evento quando [crei una connessione](/help/connections/create-connection.md) o quando [modifichi una connessione](/help/connections/manage-connections.md#edit-a-connection).

## Prerequisiti

È necessario verificare e soddisfare i prerequisiti per il metodo di unione specificato: [unione basata sui campi](fbs.md#prerequisites) o [unione basata sui grafi](gbs.md#prerequisites).


## Controlli di verifica preliminare

Se soddisfi i prerequisiti, prima di abilitare l’unione di identità potresti voler eseguire alcuni controlli di verifica preliminare sui dati nel set di dati dell’evento:

* Se utilizzi i campi dello schema XDM per l’ID persistente o l’ID persona, assicurati che le identità siano contrassegnate correttamente nello schema per il set di dati dell’evento. [Consulta la panoramica dello spazio dei nomi delle identità](https://experienceleague.adobe.com/it/docs/experience-platform/identity/features/namespaces).
* Verifica la copertura delle identità sia per l’ID persistente che per l’ID persona:

   * **ID persistente**

     Esegui la query di 7 giorni di dati in cui il campo ID persistente non è nullo e dividi per una query di 7 giorni di dati per tutti gli eventi nel set di dati. Tale percentuale dovrebbe essere superiore al 95%.

     Esempio di query da utilizzare per la verifica:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Dove:

      * `{PERSISTENT_ID_FIELD}` è il campo per l&#39;ID persistente. Ad esempio: `identityMap.ecid[0]`.
      * `{DATASET_TABLE_NAME}` è il nome della tabella per il set di dati evento.
      * `{FORMAT_STRING}` è la stringa di formato per il campo timestamp. Ad esempio: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE} ` è la data di inizio. Ad esempio: `2024-01-01 00:00:00`.
      * `{END_DATE}` è la data di fine in formato standard. Ad esempio: `2024-01-08 00:00:00`.


   * **ID persona**
      * Per l’unione basata su grafico, assicurati che il grafo delle identità contenga frammenti che collegano i valori ID dallo spazio dei nomi ID persistente e dallo spazio dei nomi ID persona selezionati. Puoi eseguire un test andando sul [visualizzatore grafico identità di Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"} ed eseguire una query sul grafico in base ad alcuni valori ID persistenti del test. Verifica se questi valori ID persistenti sono collegati ai valori ID persona nel grafico.
      * Per l’unione basata sui campi, esegui la query per 7 giorni di dati in cui il campo ID persona non è nullo e dividi per una query di 7 giorni di dati per tutti gli eventi nel set di dati. Questa percentuale dovrebbe idealmente superare il 5%.

        Esempio di query da utilizzare per la verifica:

        ```sql
        SELECT
          COUNT(*) AS total_events,
          COUNT({PERSON_ID_FIELD}) AS events_with_personid,
          ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
        FROM 
          {DATASET_TABLE_NAME}
        WHERE
          TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
          AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
        ```

        Dove:

         * `{PERSON_ID_FIELD}` è il campo per l&#39;ID persona. Ad esempio: `identityMap.crmId[0]`.
         * `{DATASET_TABLE_NAME}` è il nome della tabella per il set di dati evento.
         * `{FORMAT_STRING}` è la stringa di formato per il campo timestamp. Ad esempio: `MM/DD/YY HH12:MI AM`.
         * `{START_DATE}` è la data di inizio. Ad esempio: `2024-01-01 00:00:00`.
         * `{END_DATE}` è la data di fine in formato standard. Ad esempio: `2024-01-08 00:00:00`.



## Abilitare l’unione di identità

Per abilitare l&#39;unione, nella sezione del set di dati evento della finestra di dialogo **[!UICONTROL Aggiungi set di dati]** o **[!UICONTROL Modifica set di dati]**:

![Opzioni di unione identità quando si abilita l&#39;unione identità](assets/identity-stitching-ui.png)

1. Selezionare **[!UICONTROL Abilita unione identità]**.

   Se si abilita o si disabilita l&#39;unione per un set di dati evento salvato nella connessione, nella finestra di dialogo **[!UICONTROL Modifica ID persona]** verranno visualizzate le implicazioni di una modifica dell&#39;ID persona. Seleziona **[!UICONTROL Continua]** per continuare.

   La finestra di dialogo **[!UICONTROL Abilita unione identità]** riepiloga le conseguenze dell&#39;unione di identità. Seleziona **[!UICONTROL Continua]** per continuare.

1. Selezionare un ID persistente dal menu a discesa **[!UICONTROL ID persistente]**.

   Se si seleziona **[!UICONTROL Mappa identità]** per l&#39;ID persistente, è necessario selezionare uno spazio dei nomi. Sono disponibili due opzioni:

   * Abilita **[!UICONTROL Utilizza lo spazio dei nomi dell&#39;identità primaria]** per utilizzare lo spazio dei nomi dell&#39;identità primaria.
   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Spazio dei nomi]**.

1. Selezionare un ID persona dal menu a discesa **[!UICONTROL ID persona]**.

   Se selezioni **[!UICONTROL Identity Map]** per l&#39;ID persona, devi selezionare uno spazio dei nomi. Sono disponibili due opzioni:

   * Abilita **[!UICONTROL Utilizza lo spazio dei nomi dell&#39;identità primaria]** per utilizzare lo spazio dei nomi dell&#39;identità primaria.
   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Spazio dei nomi]**.


   Se selezioni **[!UICONTROL Grafico identità]** per l&#39;ID persona (per utilizzare [unione basata su grafico](/help/stitching/gbs.md)), devi selezionare uno spazio dei nomi.

   >[!NOTE]
   >
   >Assicurati di essere autorizzato a utilizzare il grafo delle identità.
   >

   In precedenza, veniva visualizzata una finestra di dialogo **[!UICONTROL Modifica al grafo delle identità]** per verificare che la configurazione del grafo delle identità per il set di dati sia stata completata come parte dei [prerequisiti basati sul grafo](/help/stitching/gbs.md#prerequisites) prima di utilizzare il grafo delle identità per l&#39;unione. Seleziona **[!UICONTROL Continua]** per continuare.

   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Spazio dei nomi]**.


1. Selezionare una finestra di riproduzione dal menu a discesa **[!UICONTROL Finestra di riproduzione]**. Le opzioni disponibili dipendono dal pacchetto Customer Journey Analytics a cui hai diritto.

Dopo aver salvato una connessione, il processo di unione per i set di dati abilitati per l’unione si attiva all’avvio dell’acquisizione dei dati per questi set di dati.

>[!CAUTION]
>
>Per i set di dati abilitati per l&#39;unione nell&#39;interfaccia Connessioni, lo stato di backfill viene segnalato immediatamente e in modo errato come ![Stato verde](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _backfill completati]**per il numero di backfill completati. Utilizza altri modi per verificare se i dati del set di dati uniti vengono recuperati.
>


## Limitazioni

Oltre alle [limitazioni relative all&#39;unione basata sui campi](/help/stitching/fbs.md#limitations) e alle [limitazioni relative all&#39;unione basata sui grafi](/help/stitching/gbs.md#limitations), quando si abilita l&#39;unione nell&#39;interfaccia Connessioni vengono applicate le seguenti limitazioni:

* È possibile unire un set di dati evento una sola volta come parte di una singola connessione. Non è possibile definire lo stesso set di dati evento più di una volta e utilizzare una configurazione di unione separata per ogni istanza. Se desideri applicare diverse configurazioni di unione sullo stesso set di dati, utilizza una connessione separata per ogni configurazione.


## Migrazione

L’unione abilitata nell’interfaccia Connessioni può coesistere senza alcun problema con l’unione basata su richieste.

Ad esempio, nel data lake sono presenti set di dati uniti basati sul web in seguito a richieste di unione precedenti o correnti. Puoi aggiungere dati uniti da un set di dati di call center utilizzando l’interfaccia Connessioni per combinare tali dati con quelli basati sul web.

Successivamente, Adobe migrerà i set di dati uniti basati su richieste nella nuova esperienza di unione nelle connessioni.
