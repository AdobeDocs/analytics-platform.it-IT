---
title: Abilita unione
description: Abilita l’unione delle identità per i set di dati evento in Customer Journey Analytics. Scopri come configurare ID persistenti, ID persona e finestre di ripetizione nell’interfaccia utente Connessioni per unire i dati.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 1e0d028db957743416bc7840f5a3682206a3edf3
workflow-type: tm+mt
source-wordcount: '1808'
ht-degree: 5%

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
      * Per l’unione basata su grafico, assicurati che il grafo delle identità contenga frammenti che collegano i valori ID dallo spazio dei nomi ID persistente e dallo spazio dei nomi ID persona selezionati. Puoi eseguire un test andando sul [visualizzatore grafico identità di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"} ed eseguire una query sul grafico in base ad alcuni valori di ID persistenti campione. Verifica se questi valori ID persistenti sono collegati ai valori ID persona nel grafico.
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



## Abilitare l’unione di identità {#enable-identity-stitching}

Puoi abilitare l&#39;unione delle identità quando [aggiungi](/help/connections/create-connection.md#add-datasets) o [modifichi](/help/connections/create-connection.md#edit-a-dataset) un set di dati evento in una connessione basata su persona. L’unione delle identità non è disponibile per le connessioni basate su account.

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="Passare al grafo identità"
>abstract="Assicurati di aver completato la configurazione del grafo delle identità prima di utilizzarlo per l’unione."
>additional-url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/gbs" text="Unione delle identità basata su grafo"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="ID persona"
>abstract="Seleziona un ID persona (l’identificatore univoco di una persona) tra le identità disponibili. Se la licenza include l&#39;unione basata su grafico e si desidera utilizzare il metodo di unione, selezionare **[!UICONTROL Grafico identità]**."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics"
>title="Metriche di unione"
>abstract="Le metriche di unione vengono calcolate utilizzando un set di dati campione con una marca temporale di eventi negli ultimi 7 giorni.<br>Questo set di dati di esempio è in genere diverso dai dati di esempio utilizzati nella tabella **[!UICONTROL Anteprima]**."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_gbs_personidcoverage"
>title="Copertura ID persona"
>abstract="Copertura dell’ID persona selezionato utilizzato per l’identificazione durante il processo di unione (in tempo reale e ripetizione).<br/>Per ottenere i migliori risultati nell&#39;unione, nel grafo delle identità deve essere presente una relazione (ID persistente, ID persona) per ogni ID persistente."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_fbs_personidcoverage"
>title="Copertura ID persona"
>abstract="Copertura dell’ID persona selezionato utilizzato per l’identificazione durante il processo di unione (in tempo reale e ripetizione).<br/>Per ottenere i migliori risultati nell&#39;unione, è necessario inviare l&#39;ID persona (informazioni utente) ad almeno un evento per ogni ID persistente (informazioni dispositivo)."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_persistentidcoverage"
>title="Copertura ID persistente"
>abstract="Questo valore viene utilizzato per l’identificazione durante il processo di unione (live e replay), nel caso in cui non sia possibile rilevare un ID persona. <br/>Gli eventi senza ID persistente e senza ID persona vengono eliminati dai dati. Per risultati di unione ottimali, un ID persistente deve essere presente in tutti gli eventi."


>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_badids"
>title="ID non validi"
>abstract="Gli ID non validi sono valori ID che influiscono gravemente sui dati di reporting."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/badids" text="ID non validi"


### Impostazioni del set di dati

Per abilitare l&#39;unione, nella sezione **[!UICONTROL Impostazioni dei set di dati]** dell&#39;evento **[!UICONTROL Aggiungi set di dati]** o **[!UICONTROL Modifica set di dati]**:

![Opzioni di unione identità quando si abilita l&#39;unione identità](assets/identity-stitching-ui.png)

1. Selezionare **[!UICONTROL Abilita unione identità]**.

   Se si abilita o si disabilita l&#39;unione per un set di dati evento salvato nella connessione, nella finestra di dialogo **[!UICONTROL Modifica ID persona]** verranno visualizzate le implicazioni di una modifica dell&#39;ID persona. Seleziona **[!UICONTROL Continua]** per continuare.

   La finestra di dialogo **[!UICONTROL Abilita unione identità]** riepiloga le conseguenze dell&#39;unione di identità. Seleziona **[!UICONTROL Continua]** per continuare.

1. Selezionare un ID persistente dal menu a discesa **[!UICONTROL ID persistente]**.

   Se si seleziona **[!UICONTROL Mappa identità]** per l&#39;ID persistente, è necessario selezionare uno spazio dei nomi. Sono disponibili due opzioni:

   * Selezionare **[!UICONTROL Usa spazio dei nomi dell&#39;identità primaria]** per utilizzare lo spazio dei nomi dell&#39;identità primaria.
   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Spazio dei nomi]**.

1. Selezionare un ID persona dal menu a discesa **[!UICONTROL ID persona]**.

   Se selezioni **[!UICONTROL Identity Map]** per l&#39;ID persona, devi selezionare uno spazio dei nomi. Sono disponibili due opzioni:

   * Selezionare **[!UICONTROL Usa spazio dei nomi dell&#39;identità primaria]** per utilizzare lo spazio dei nomi dell&#39;identità primaria.
   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Spazio dei nomi]**.


   Se selezioni **[!UICONTROL Grafico identità]** per l&#39;ID persona (per utilizzare [unione basata su grafico](/help/stitching/gbs.md)), devi selezionare uno spazio dei nomi.

   >[!NOTE]
   >
   >Assicurati di essere autorizzato a utilizzare il grafo delle identità.
   >

   In precedenza, veniva visualizzata una finestra di dialogo **[!UICONTROL Modifica al grafo delle identità]** per verificare che la configurazione del grafo delle identità per il set di dati sia stata completata. Questa configurazione fa parte dei [prerequisiti basati su grafico](/help/stitching/gbs.md#prerequisites) prima di poter utilizzare il grafo delle identità per l&#39;unione. Seleziona **[!UICONTROL Continua]** per continuare.

   * Selezionare uno spazio dei nomi dal menu a discesa **[!UICONTROL Spazio dei nomi]**.

1. Selezionare una finestra di riproduzione dal menu a discesa **[!UICONTROL Finestra di riproduzione]**. Le opzioni disponibili dipendono dal pacchetto Customer Journey Analytics a cui hai diritto.

1. Seleziona **[!UICONTROL Avanti]** per visualizzare un&#39;anteprima del set di dati dell&#39;evento soggetto a unione.


### Anteprima dei set di dati

>[!AVAILABILITY]
>
>L&#39;interfaccia **[!UICONTROL Anteprima set di dati]** migliorata (incluse **[!UICONTROL Metriche di unione]** e **[!UICONTROL ID non validi]**) descritta in questa sezione si trova nella fase Test limitati del rilascio e potrebbe non essere ancora disponibile nell&#39;ambiente. Se non disponibile, l&#39;anteprima del set di dati verrà visualizzata come parte dell&#39;interfaccia **[!UICONTROL Impostazioni set di dati]**. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Customer Journey Analytics, consulta [Rilascio delle funzioni di Customer Journey Analytics](/help/release-notes/releases.md).
>

Oltre all&#39;interfaccia standard **[!UICONTROL Anteprima set di dati]**, quando [aggiungi](/help/connections/create-connection.md#add-datasets) o [modifichi](/help/connections/create-connection.md#edit-a-dataset) set di dati in una connessione basata su persona, sono disponibili due pannelli di informazioni aggiuntivi.

>[!NOTE]
>Per i clienti che hanno implementato Customer Journey Analytics su AWS, questa funzionalità è in attesa di rilascio.
>

![Opzioni di unione identità quando si abilita l&#39;unione identità](assets/identity-stitching-ui-preview.png)

#### Metriche di unione

**[!UICONTROL Le metriche di unione]** vengono calcolate utilizzando un set di dati di esempio con una marca temporale di eventi negli ultimi 7 giorni. Questo set di dati di esempio è in genere diverso dai dati di esempio utilizzati nella tabella **[!UICONTROL Anteprima]**. Le metriche di unione forniscono dettagli per:

* **[!UICONTROL Copertura ID persona]**: copertura dell&#39;ID persona selezionato utilizzata per l&#39;identificazione durante il processo di unione (in tempo reale e ripetizione).
   * Per ottenere i migliori risultati con le unioni basate sui campi, è necessario inviare un ID persona (informazioni utente) su almeno un evento per ogni ID persistente (informazioni dispositivo).
   * Per ottenere i migliori risultati con le unioni basate su grafico, nel grafo delle identità per ogni ID persistente deve essere presente una relazione (ID persistente, ID persona).

  La copertura dell’ID persona viene visualizzata come percentuale e confrontata con quanto consigliato per uno sviluppo stabile o in una configurazione di produzione. Maggiore è il valore di copertura, migliori saranno i risultati di unione ottenuti con l’ID persona selezionato.

* **[!UICONTROL Copertura ID persistente]**: questo valore viene utilizzato per l&#39;identificazione durante il processo di unione (in tempo reale e ripetizione), nel caso in cui non sia possibile rilevare un valore ID persona. Gli eventi senza ID persistente e senza ID persona vengono eliminati dai dati. Per risultati di unione ottimali, un ID persistente deve essere presente in tutti gli eventi.

  La copertura ID persistente viene visualizzata come percentuale e confrontata con il minimo consigliato per uno sviluppo stabile o una configurazione di produzione.


#### ID non validi

>[!INFO]
>
>Nell’interfaccia di Customer Journey Analytics, gli ID non validi sono anche denominati BAVID.
> 

In Customer Journey Analytics, un ID errato è un identificatore:

* con un valore ID specifico che ha origine da un campo ID persistente o ID persona nei set di dati abilitati per l&#39;unione, **e**
* si trova su più di un milione (1.000.000) eventi nei dati della connessione, entro un mese.

Quando un valore ID è contrassegnato come ID errato, tutti gli eventi futuri che contengono tale valore ID vengono eliminati dai dati della connessione e non vengono visualizzati nel reporting.

Esempi di casi di utilizzo di ID non validi:

* Nel campo ID persona sono presenti valori personalizzati o segnaposto (ad esempio, `undefined`). Tali valori possono inoltre influire sulla [qualità dei dati di unione e reporting](/help/stitching/faq.md#undefined-person-id-values).
* In una configurazione di unione basata sui campi, se più persone condividono un dispositivo e il numero totale di transizioni tra gli utenti supera 50.000. In questo caso, il processo di unione si interrompe per utilizzare le informazioni ID persona per quel dispositivo e utilizza solo informazioni ID persistenti. Di conseguenza, tutti gli eventi del set di dati da tale dispositivo vengono inviati ai dati di connessione con l’identità ID persistente, con un’alta probabilità di causare una situazione di ID non validi.


>[!NOTE]
>Le **[!UICONTROL metriche di unione]**, inclusi **[!UICONTROL ID non validi]**, vengono calcolate in base a un set limitato di dati. Per identificare la presenza di ID non validi per un set di dati che intendi utilizzare per l&#39;unione, consulta la [nota tecnica sugli ID non validi](/help/technotes/badids.md).
>


### Salva

Dopo aver salvato una connessione, il processo di unione per i set di dati abilitati viene avviato non appena inizia l’acquisizione dei dati per questi set di dati.

>[!CAUTION]
>
>Per i set di dati abilitati per l&#39;unione nell&#39;interfaccia Connessioni, lo stato di backfill viene segnalato immediatamente e in modo errato come ![Stato verde](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _backfill completati]**&#x200B;per il numero di backfill completati. Utilizza altri modi per verificare se i dati del set di dati uniti vengono recuperati.
>


## Limitazioni

Oltre alle [limitazioni relative all&#39;unione basata sui campi](/help/stitching/fbs.md#limitations) e alle [limitazioni relative all&#39;unione basata sui grafi](/help/stitching/gbs.md#limitations), quando si abilita l&#39;unione nell&#39;interfaccia Connessioni vengono applicate le seguenti limitazioni:

* È possibile unire un set di dati evento una sola volta come parte di una singola connessione. Non è possibile definire lo stesso set di dati evento più di una volta e utilizzare una configurazione di unione separata per ogni istanza. Se desideri applicare diverse configurazioni di unione sullo stesso set di dati, utilizza una connessione separata per ogni configurazione.


## Migrazione

L’unione abilitata nell’interfaccia Connessioni può coesistere senza alcun problema con l’unione basata su richieste.

Ad esempio, nel data lake sono presenti set di dati uniti basati sul web in seguito a richieste di unione precedenti o correnti. Puoi aggiungere dati uniti da un set di dati di call center utilizzando l’interfaccia Connessioni per combinare tali dati con quelli basati sul web.

Successivamente, Adobe migrerà i set di dati uniti basati su richieste nella nuova esperienza di unione nelle connessioni.
