---
title: Unione account B2B
description: Scopri in che modo l’unione degli account B2B in Customer Journey Analytics arricchisce i set di dati evento con le informazioni sull’account e consente un’analisi completa del percorso tra i dati B2B.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2:
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a4ff89823bf1e4e4aa6d299b74567ed8cb486d06
workflow-type: tm+mt
source-wordcount: 1924
ht-degree: 13%

---

# Unione di account B2B

L’unione degli account B2B arricchisce i set di dati dell’evento con le identità dell’account e consente un’analisi completa nell’intero percorso di clienti in Customer Journey Analytics. Quando gli eventi non dispongono di un ID account, richiesto da Customer Journey Analytics B2B edition per l&#39;acquisizione, l&#39;unione degli account deriva e aggiunge automaticamente tali informazioni utilizzando un [set di dati di mappatura persona-account](#prerequisites) fornito.

Senza l’unione degli account, qualsiasi evento che non contiene un ID account viene eliminato durante l’acquisizione. L’unione di account risolve questo limite ricercando l’account associato alla persona in ogni evento, aggiungendo l’ID account sia durante l’acquisizione dell’evento sia retroattivamente.

>[!NOTE]
>
>L&#39;unione di account B2B richiede l&#39;accesso a [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) nell&#39;ambiente prima di poter configurare la funzionalità.

L’unione di account esegue le seguenti operazioni sui set di dati:

* **Elevare l&#39;identità della persona**: l&#39;ID persona in ogni evento è elevato allo spazio dei nomi dell&#39;identità configurato utilizzando il grafico delle identità.
* **Aggiungi identità account mancanti**: per gli eventi che contengono un ID persona, viene utilizzata la [mappatura persona-account](#prerequisites) per derivare e aggiungere l&#39;identità account. Qualsiasi identità account nell’evento stesso viene utilizzata come metodo di fallback.

## Funzionamento dell’unione di account B2B

Per illustrare il funzionamento dell’unione di account B2B, il set di dati mostrato di seguito viene utilizzato come punto di partenza.

### Set di dati evento di base

In Customer Journey Analytics B2B edition, gli eventi senza ID account in questo set di dati evento di esempio non unito vengono ignorati e non acquisiti (![DeleteOutline](/help/assets/icons/DeleteOutline.svg)).

| Azione | Marca temporale | ID persistente | ID account | ID persona | Tipo di evento |
|:---:|--:|--|---|---|---|
| ![AggiungiDati](/help/assets/icons/DataAdd.svg) | 1/3/25 | 1234 | Adobe | matt@adobe.com | Page view |
| ![EliminazioneFiltro](/help/assets/icons/DeleteOutline.svg) | 1/3/25 | 5678 |  | | |
| ![AggiungiDati](/help/assets/icons/DataAdd.svg) | 3/4/25 | 9012 | Ubiquità | cory@sky.com |  |
| ![AggiungiDati](/help/assets/icons/DataAdd.svg) | 3/7/25 | 4321 | Cielo | emily@sky.com | Call center |
| ![EliminazioneFiltro](/help/assets/icons/DeleteOutline.svg) | 5/5/25 | 6106 | | carmen@adobe.com |  |
| ![AggiungiDati](/help/assets/icons/DataAdd.svg) | 6/1/25 | 8989 | Ubiquità | cassidy@ubiquity.com | |
| ![EliminazioneFiltro](/help/assets/icons/DeleteOutline.svg) | 6/2/25 | 1111 |  | | |

L’unione di account B2B impedisce che gli eventi vengano ignorati e non acquisiti utilizzando le operazioni seguenti:

* [Elevare le identità della persona](#elevate-person-identities).
* [Aggiungi identità account mancanti](#add-missing-account-identitiers).


### Privilegiare le identità delle persone

+++ Dettagli

Per supportare l’unione degli account B2B, fornisci un set di dati di mappatura persona-account. Ad esempio:

| ID CRM | ID account |
|---|---|
| 12hsd123 | Adobe |
| f82jsd32 | Cielo |
| hg2023m2 | Cielo |
| b978bbw9 | Ubiquità |
| fs453ghi | Adobe |

Il set di dati di mappatura persona-account è elevato utilizzando l’unione basata su grafico. Ad esempio, puoi fornire e-mail come namespace da utilizzare. Il risultato è un set di dati di mappatura persona-account aggiornato con ID persona elevati.

| ID CRM | ID persona elevata | ID account |
|---|---|---|
| 12hsd123 | matt@adobe.com | Adobe |
| f82jsd32 | emily@sky.com | Cielo |
| hg2023m2 | cory@sky.com | Cielo |
| b978bbw9 | cassidy@ubiquity.com | Ubiquità |
| fs453ghi | carmen@adobe.com | Adobe |

L’unione basata su grafico viene utilizzata anche per elevare gli ID persona nel set di dati dell’evento esperienza. Ad esempio, vedere il valore aggiornato per **emily@adobe.com**.

| Marca temporale | ID persistente | ID account originale | ID persona originale | ID persona elevata |
|--|--|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | matt@adobe.com |
| 1/3/25 | 5678 |  | | **emily@adobe.com** |
| 3/4/25 | 9012 | Ubiquità | cory@sky.com | cory@sky.com |
| 3/7/25 | 4321 | Cielo | emily@sky.com | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | carmen@adobe.com |
| 6/1/25 | 8989 | Ubiquità | cassidy@ubiquity.com | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 111 | 111 |


+++

### Aggiungi identificatori account mancanti

+++ Dettagli

Il set di dati da persona a account viene ancora una volta utilizzato per elevare gli ID account nel set di dati dell’evento esperienza. Ad esempio, vedi il valore aggiunto **Sky** per emily@sky.com e **Adobe** per carmen@adobe.com. E il valore aggiornato **Sky** (da Ubiquity) per cory@sky.com.

| Marca temporale | ID persistente | ID account originale | ID persona originale | ID account con privilegi elevati | ID persona elevata |
|---|---|---|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | Adobe | matt@adobe.com |
| 1/3/25 | 5678 | | | **Cielo** | **emily@sky.com** |
| 3/4/25 | 9012 | Ubiquità | cory@sky.com | **Cielo** | cory@sky.com |
| 3/7/25 | 4321 | Cielo | emily@sky.com | Cielo | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | **Adobe** | carmen@adobe.com |
| 6/1/25 | 8989 | Ubiquità | cassidy@ubiquity.com | Ubiquità | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 1111 |  | 1111 |

+++

### Risultato

Questo esempio mostra come l’unione degli account B2B aggiorna i dati dell’evento esperienza con identificatori di persona mancanti e identificatori di account mancanti o errati, in base al set di dati di mappatura persona-account fornito come input.


## Prerequisiti

Prima di abilitare l’unione di account B2B, prepara i seguenti set di dati in Adobe Experience Platform:

| Set di dati | Obbligatorio | Descrizione |
|---|---|---|
| **set di dati persona-account** | Obbligatorio | Un set di dati di ricerca (record, serie non temporali) che contiene almeno un ID persona (con spazio dei nomi) e un ID account. Questi ID vengono utilizzati per derivare la mappa di relazione tra persone e account. |

>[!IMPORTANT]
>
>Il campo ID persona nel set di dati **[!UICONTROL persona per account]** deve essere contrassegnato come identità nello schema.

## Abilita unione account {#enable-account-stitching}

Innanzitutto, abilita e configura l’unione degli account B2B a livello di connessione. Quando l’unione di account B2B è configurata per una connessione, puoi quindi attivare l’unione di account sui singoli set di dati evento all’interno di tale connessione.

### Configurare le impostazioni di unione delle identità B2B {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="Configurare l’unione delle identità in account B2B"
>abstract="Seleziona **[!UICONTROL Apri configurazione di unione identità B2B]** per configurare l’unione delle identità in account B2B. Se la connessione non è ancora stata salvata, la configurazione sarà etichettata con **[!UICONTROL _Modifiche non salvate_]**."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="Spazio dei nomi identificatori persona"
>abstract="Seleziona lo spazio dei nomi dell’identità della persona più rilevante per la generazione dei rapporti. Ad esempio, E-mail. Qualsiasi set di dati evento con **[!UICONTROL unione da persona a account]** abilitata ha l&#39;ID persona elevato a questo spazio dei nomi dell&#39;identificatore della persona."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="Set di dati Persona ad account"
>abstract="Seleziona il set di dati di ricerca che associa gli ID persona agli ID account."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="ID persona"
>abstract="Seleziona il campo nel set di dati che contiene gli ID persona. Lo spazio dei nomi di questo campo può essere diverso o uguale allo spazio dei nomi dell’identificatore della persona selezionato. Se differiscono, i due spazi dei nomi devono essere collegati nel grafo delle identità."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="ID account"
>abstract="Seleziona il campo nel set di dati che contiene i valori dell’identificatore univoco dell’account. Le informazioni sull&#39;ID account saranno rese disponibili nelle righe di qualsiasi set di dati evento con **[!UICONTROL unione da persona a account]** abilitata."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="Ora di inizio"
>abstract="Seleziona un campo di marca temporale che indichi quando la relazione persona-account è diventata attiva."


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_mapping_creation_time"
>title="Tempo di creazione della mappatura"
>abstract="È possibile selezionare il campo che rappresenta la data e l&#39;ora di creazione del mapping persona-conto. Utile per scenari in cui una persona cambia più account nel tempo."


1. In Customer Journey Analytics, passa a **[!UICONTROL Connessioni]** e [crea una nuova connessione](/help/connections/create-connection.md#create-a-connection) o [modifica una connessione esistente](/help/connections/create-connection.md#edit-a-connection).

1. In **[!UICONTROL Impostazioni connessione]**, impostare **[!UICONTROL ID primario]** su ![Generazione](/help/assets/icons/Building.svg) **[!UICONTROL Account]**.

1. Accertati di selezionare i **[!UICONTROL contenitori opzionali]** che desideri utilizzare nella connessione B2B. Non puoi modificare la selezione di questi contenitori dopo aver salvato una configurazione di unione B2B.

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
      | **[!UICONTROL ID persona]** | ![Obbligatorio](/help/assets/icons/Required.svg) | Seleziona il campo nel set di dati che contiene l’ID di persona. Il campo deve essere contrassegnato come identità e non può essere uguale al campo **[!UICONTROL ID account]** o **[!UICONTROL Ora inizio]**. |
      | **[!UICONTROL ID account]** | ![Obbligatorio](/help/assets/icons/Required.svg) | Seleziona il campo nel set di dati che contiene l’ID di account. Il campo non può essere uguale al campo **[!UICONTROL ID persona]** o **[!UICONTROL Ora inizio]**. |
      | **Ora di creazione mappatura** | | È possibile selezionare il campo che rappresenta la data e l&#39;ora di creazione del mapping persona-conto. Utile per scenari in cui una persona cambia più account nel tempo.<br/><br/>**Esempio** (quando è selezionato il campo **update_date**):<table><thead><tr><th>update_date</th><th>persona</th><th>account</th></tr></thead><tbody><tr><td>20260401</td><td>a@b.com</td><td>Apple</td></tr><tr><td>20260501</td><td>a@b.com</td><td>Adobe</td></tr></tbody></table><ul><li>Per tutti gli eventi con una marca temporale nel campo **[!UICONTROL update_date]** prima del 1° maggio 2026: a@b.com è mappato ad Apple.</li><li>Per tutti gli eventi con una marca temporale nel campo **[!UICONTROL update_date]** il o dopo il 1° maggio 2026: a@b.com è mappato ad Adobe.</li></ul>Se non viene specificato alcun tempo di mappatura, viene utilizzato il primo account lessicografico. Lo stesso algoritmo viene utilizzato anche quando due nomi di account diversi hanno lo stesso valore **[!UICONTROL update_date]** e viene specificato un orario di creazione della mappatura. |

      >[!NOTE]
      >
      >Se si verifica un errore durante il caricamento delle opzioni del campo, i menu a discesa vengono visualizzati vuoti e sotto ogni campo interessato viene visualizzato un indicatore di errore. Verifica lo schema del set di dati e riprova.

   1. Seleziona **[!UICONTROL Salva]** per chiudere la finestra di dialogo **[!UICONTROL Configurazione di unione B2B]** e tornare alle impostazioni di connessione.

   1. L&#39;indicatore **[!UICONTROL _Modifiche non salvate_]** viene visualizzato accanto al pulsante **Apri configurazione unione B2B** fino a quando non si [salva](#save) la connessione.

### Abilitare l’unione delle identità B2B nei set di dati evento


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="Abilita unione delle identità persona-account"
>abstract="Se abilitato, questo set di dati utilizza la persona B2B per l’unione degli account. I valori **[!UICONTROL ID persona]** verranno elevati a quelli configurati dello spazio dei nomi **[!UICONTROL Identificatore persona]**, quindi verranno utilizzati per cercare l&#39;ID account in base al set di dati da persona a account.<br/>Se disabilitato, questo set di dati non utilizza la persona B2B per l&#39;unione degli account. Devi selezionare invece un **[!UICONTROL ID account]** richiesto."
>additional-url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/stitching/b2b-account-stitching#configure-b2b-stitching-settings" text="Configurare le impostazioni di unione delle identità B2B"

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
>Una volta salvata una connessione, la configurazione dell’unione B2B diventa immutabile. Per visualizzare le impostazioni dopo il salvataggio, selezionare **Apri configurazione di unione B2B**. Tutti i campi sono di sola lettura. Inoltre, se il set di dati utilizzato per [il mapping tra persone e account](#prerequisites) viene eliminato in Experience Platform, la connessione verrà eliminata.

## Pianificazione aggiornamento dati

L&#39;unione di account deriva la mappa di identità dal [set di dati persona-account](#prerequisites) al giorno e utilizza queste informazioni per aggiornare i set di dati abilitati per l&#39;unione sia a breve che a lungo termine secondo la seguente pianificazione:

| Ripetizione | Frequenza | Finestra dati |
|---|---|---|
| A breve termine | Settimanale | Ultimi 7 giorni |
| A lungo termine | Mensile | Ultimi 3 mesi (pacchetto Prime)<br/>Ultimi 6 mesi (pacchetto Ultimate) |

## Privacy e igiene dei dati

L’unione degli account rispetta le richieste standard di privacy e igiene per le identità delle persone, in linea con il comportamento dell’unione B2C. Se un ID persona viene successivamente rimosso tramite una richiesta di accesso a dati personali o di igiene, l’unione associata eseguita utilizzando il grafico delle identità viene annullata.

Le entità B2B come account, ID account e ID account globali aggiunti agli eventi tramite l’unione non vengono rimosse durante le richieste di privacy o igiene. Questi valori non contengono informazioni personali identificabili, pertanto non esiste alcun obbligo legale di rimuovere tali valori.

>[!MORELIKETHIS]
>
>* [Panoramica dell&#39;unione](overview.md)
>* [Configurare una connessione per B2B](../connections/create-connection.md)
>* [Domande frequenti sull&#39;unione](faq.md)

