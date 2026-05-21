---
title: Unione account B2B
description: Scopri in che modo l’unione degli account B2B in Customer Journey Analytics arricchisce i set di dati evento con le informazioni sull’account e consente un’analisi completa del percorso tra i dati B2B.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2: id: d3f42e9e-bb51-4077-a732-358b801d8b29id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 5964c5f87364e5ba78e866d753819d7e7f605b30
workflow-type: tm+mt
source-wordcount: 1169
ht-degree: 2%

---

# Unione di account B2B

L’unione degli account B2B arricchisce i set di dati dell’evento con le informazioni sull’account e consente un’analisi completa nell’intero percorso di clienti in Customer Journey Analytics. Quando gli eventi non dispongono di un ID account, richiesto da Customer Journey Analytics B2B edition per l&#39;acquisizione, l&#39;unione degli account deriva e aggiunge automaticamente tali informazioni utilizzando un [set di dati di mappatura persona-account](#prerequisites) fornito.

Senza l’unione degli account, qualsiasi evento che non contiene un ID account viene eliminato durante l’acquisizione. l’unione di account elimina questa barriera ricercando l’account associato alla persona in ogni evento, aggiungendo l’ID account sia durante l’acquisizione dell’evento che retroattivamente.

>[!NOTE]
>
>L&#39;unione di account B2B richiede l&#39;accesso a [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) nell&#39;ambiente prima di poter configurare la funzionalità.

L’unione di account esegue le seguenti operazioni sui set di dati:

* **Elevare l&#39;identità della persona**: l&#39;ID persona in ogni evento è elevato allo spazio dei nomi dell&#39;identità configurato utilizzando il grafico delle identità.
* **Aggiungi informazioni account mancanti**: per gli eventi che contengono un ID persona, viene utilizzata la [mappatura persona-account](#prerequisites) per derivare e aggiungere le informazioni sull&#39;account. Tutte le informazioni sull’account relative all’evento vengono utilizzate come metodo di fallback.

## Prerequisiti

Prima di abilitare l’unione di account B2B, prepara i seguenti set di dati in Adobe Experience Platform:

| Set di dati | Obbligatorio | Descrizione |
|---|---|---|
| **set di dati persona-account** | Obbligatorio | Un set di dati di ricerca (record, serie non temporali) che contiene almeno un ID persona (con spazio dei nomi) e un ID account. Questi ID vengono utilizzati per derivare la mappa di relazione tra persone e account. |

>[!IMPORTANT]
>
>Il campo ID persona nel set di dati **[!UICONTROL persona per account]** deve essere contrassegnato come identità nello schema.

## Abilita unione account {#enable-account-stitching}

Abilita e configura l’unione di account B2B a livello di connessione, quindi attiva l’unione di account sui singoli set di dati evento all’interno di tale connessione.

### Configurare le impostazioni di unione B2B {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="Configurare l’unione di account B2B"
>abstract="Seleziona **[!UICONTROL Apri configurazione unione B2B]** per configurare l&#39;unione degli account B2B. Se la connessione non è ancora stata salvata, la configurazione sarà contrassegnata con **[!UICONTROL _Modifiche non salvate_]**."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="Spazio dei nomi identificatore della persona"
>abstract="Seleziona uno spazio dei nomi dell’identificatore della persona, ad esempio E-mail, al quale desideri che venga elevato qualsiasi ID persona."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="Set di dati da persona a account"
>abstract="Seleziona il set di dati di ricerca che associa gli ID persona agli ID account."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="Persona"
>abstract="Seleziona il campo nel set di dati che contiene l’ID persona. Il campo deve essere contrassegnato come identità e non può essere uguale al campo **[!UICONTROL Account]** o **[!UICONTROL Ora inizio]**."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="Account"
>abstract="Seleziona il campo nel set di dati che contiene l’ID account. Il campo non può essere uguale al campo **[!UICONTROL Persona]** o **[!UICONTROL Ora inizio]**."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="Ora di inizio"
>abstract="Selezionare un campo timestamp che indichi quando la relazione persona-account è diventata attiva."
>additional-url=""
additional-url=""


1. In Customer Journey Analytics, passa a **[!UICONTROL Connessioni]** e [crea una nuova connessione](/help/connections/create-connection.md#create-a-connection) o [modifica una connessione esistente](/help/connections/create-connection.md#edit-a-connection).

1. In **[!UICONTROL Impostazioni connessione]**, impostare **[!UICONTROL ID primario]** su ![Generazione](/help/assets/icons/Building.svg) **[!UICONTROL Account]**.

1. Seleziona **[!UICONTROL Apri configurazione di unione B2B]**.

   ![Configurazione titolazione saccount B2B](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >Una configurazione di unione B2B configurata in precedenza per una connessione non salvata è indicata con **[!UICONTROL _Modifiche non salvate_]**. Impossibile modificare **[!UICONTROL Contenitori facoltativi]** per una configurazione di unione B2B configurata in precedenza.

1. Nella finestra di dialogo **[!UICONTROL Configurazione unione B2B]**:

   ![Configurazione dell&#39;unione B2B](assets/b2b-stitching-configuration.png)

   1. Configura la sezione **[!UICONTROL Persona]**:

      * Seleziona uno spazio dei nomi **[!UICONTROL Identificatore persona]**, ad esempio **[!UICONTROL E-mail]**, al quale desideri che venga elevato qualsiasi ID persona. Questo campo è obbligatorio.

   1. Configura la sezione **[!UICONTROL Account]** sotto **[!UICONTROL Persona all&#39;account]**.

      | Campo | Obbligatorio | Descrizione |
      |---|:---:|---|
      | **[!UICONTROL Set di dati da persona a account]** | ![Obbligatorio](/help/assets/icons/Required.svg) | Seleziona la ricerca (record o set di dati di serie non temporali) che mappa le persone sugli account. |
      | **[!UICONTROL Persona]** | ![Obbligatorio](/help/assets/icons/Required.svg) | Seleziona il campo nel set di dati che contiene l’ID persona. Il campo deve essere contrassegnato come identità e non può essere uguale al campo **[!UICONTROL Account]** o **[!UICONTROL Ora inizio]**. |
      | **[!UICONTROL Account]** | ![Obbligatorio](/help/assets/icons/Required.svg) | Seleziona il campo nel set di dati che contiene l’ID account. Il campo non può essere uguale al campo **[!UICONTROL Persona]** o **[!UICONTROL Ora inizio]**. |
      | **Ora di inizio** | | Selezionare un campo timestamp che indichi quando la relazione persona-account è diventata attiva. |

      >[!NOTE]
      >
      >Se si verifica un errore durante il caricamento delle opzioni del campo, i menu a discesa vengono visualizzati vuoti e sotto ogni campo interessato viene visualizzato un indicatore di errore. Verifica lo schema del set di dati e riprova.

   1. Seleziona **[!UICONTROL Salva]** per chiudere la finestra di dialogo **[!UICONTROL Configurazione di unione B2B]** e tornare alle impostazioni di connessione.

   1. L&#39;indicatore **[!UICONTROL _Modifiche non salvate_]** viene visualizzato accanto al pulsante **Apri configurazione unione B2B** fino a quando non si [salva](#save) la connessione.


### Abilitare l’unione B2B nei set di dati evento


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="Abilita unione persona-account"
>abstract="Se abilitato, questo set di dati utilizza l’unione di account B2B. L’ID persona selezionato viene utilizzato per cercare l’ID account in base al set di dati da persona a account.<br/>Se disabilitato, questo set di dati *non* utilizza l&#39;unione di account B2B."
>additional-url=""
additional-url=""


Dopo aver configurato l’unione B2B a livello di connessione, devi abilitare l’unione degli account B2B singolarmente per ogni set di dati evento da unire.

1. In Impostazioni connessione selezionare **[!UICONTROL Aggiungi set di dati]** o aprire le impostazioni per un set di dati evento esistente.<br/>Per ulteriori informazioni, vedere [Aggiungere set di dati](/help/connections/create-connection.md#add-datasets) o [Modificare un set di dati](/help/connections/create-connection.md#edit-a-dataset).

1. Per il set di dati evento specifico per il quale si desidera configurare l&#39;unione dell&#39;account B2B, attivare **[!UICONTROL Attiva unione da persona a account]**.

>[!BEGINTABS]

>[!TAB Il]

Quando **[!UICONTROL Abilita unione persona a account]** è **su**, hai configurato l&#39;unione di account B2B per il set di dati.

* È necessario configurare un ID persona. L&#39;ID persona viene utilizzato per cercare l&#39;ID account in base al [set di dati persona-account](#prerequisites).
* La configurazione di un ID account è facoltativa.

![Unione di account B2B nel set di dati dell&#39;evento il](assets/b2b-event-dataset-stitching-on.png)

>[!TAB Disattivato]

Quando **[!UICONTROL Abilita unione persona a account]** è **off**, l&#39;unione dell&#39;account B2B per il set di dati è configurata da *not*.

* È necessaria la configurazione di un ID account.
* La configurazione di un ID persona è facoltativa.

![Unione account B2B nel set di dati evento disattivata](assets/b2b-event-dataset-stitching-off.png)


>[!ENDTABS]




### Salva

Dopo aver configurato la configurazione dell&#39;unione B2B e aver completato l&#39;aggiunta o la modifica dei set di dati, seleziona **[!UICONTROL Salva]** per salvare la connessione.

>[!IMPORTANT]
>
>Una volta salvata una connessione, la configurazione dell’unione B2B diventa immutabile. Per visualizzare le impostazioni dopo il salvataggio, selezionare **Apri configurazione di unione B2B**. Tutti i campi verranno visualizzati in sola lettura. Inoltre, se il set di dati utilizzato per il [mapping tra persone e account](#prerequisites) viene eliminato in Experience Platform, la connessione verrà eliminata.

## Pianificazione aggiornamento dati

L&#39;unione di account deriva la mappa di identità dal [set di dati persona-account](#prerequisites) al giorno e utilizza queste informazioni per aggiornare i set di dati abilitati per l&#39;unione nella seguente pianificazione:

| Ripetizione | Frequenza | Finestra dati |
|---|---|---|
| A breve termine | Settimanale | Ultimi 7 giorni |
| A lungo termine | Mensile | Ultimi 3 mesi |

## Privacy e igiene dei dati

L’unione degli account rispetta le richieste standard di privacy e igiene per le identità delle persone, in linea con il comportamento dell’unione B2C. Se un ID persona viene successivamente rimosso tramite una richiesta di accesso a dati personali o di igiene, l’unione associata eseguita utilizzando il grafico delle identità viene annullata.

Le entità B2B come account, ID account e ID account globali che vengono aggiunti agli eventi tramite l’unione non vengono rimosse come parte delle richieste di privacy o igiene. Questi valori non contengono informazioni personali identificabili, pertanto non esiste alcun obbligo legale di rimuovere tali valori.

>[!MORELIKETHIS]
>
>* [Panoramica dell&#39;unione](overview.md)
>* [Configurare una connessione per B2B](../connections/create-connection.md)
>* [Domande frequenti sull&#39;unione](faq.md)

