---
title: Unione Persona-Account B2B
description: Scopri come l’unione di persone B2B e account in Customer Journey Analytics arricchisce i set di dati evento con le informazioni sull’account e consente un’analisi completa del percorso tra i dati B2B.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
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
source-git-commit: e3936b74ba4b4cf23e1b7235e545091a8cb546ed
workflow-type: tm+mt
source-wordcount: 2116
ht-degree: 15%

---

# Unione persona-account B2B

L’unione da persona a account B2B arricchisce i set di dati dell’evento con le identità dell’account e consente un’analisi completa nell’intero percorso di clienti in Customer Journey Analytics. Quando gli eventi non dispongono di un ID account, richiesto da Customer Journey Analytics B2B edition per l&#39;acquisizione, l&#39;unione da persona a account deriva e aggiunge automaticamente tali informazioni utilizzando un [set di dati di mappatura da persona a account](#prerequisites) fornito.

Senza unione da persona a account, qualsiasi evento che non contiene un ID account viene eliminato durante l’acquisizione. L’unione da persona a account risolve questo limite ricercando l’account associato alla persona in ogni evento, aggiungendo l’ID account sia durante l’acquisizione dell’evento che retroattivamente.

>[!NOTE]
>
>Per poter configurare la funzionalità, l&#39;unione di utenti B2B e account richiede l&#39;accesso a [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) nell&#39;ambiente.

L’unione da persona a account esegue le seguenti operazioni sui set di dati:

* **Elevare l&#39;identità della persona**: in modo analogo all&#39;approccio di unione [B2C](/help/stitching/overview.md), verrà configurato un campo contenente gli ID persona persistenti. Utilizzando il grafo delle identità, l’ID persona persistente in ogni evento è elevato a un ID persona dallo spazio dei nomi dell’identificatore della persona configurato.
* **Aggiungi identità account mancanti**: dopo aver ottenuto le informazioni sull&#39;ID persona per un evento, viene utilizzata la [mappatura persona-account](#prerequisites) per derivare e aggiungere le informazioni sull&#39;identità dell&#39;account. Qualsiasi identità account disponibile nell’evento stesso viene utilizzata come metodo di fallback.

## Funzionamento dell’unione di persone e account B2B

Per illustrare il funzionamento dell’unione di persona B2B con l’account, come punto di partenza viene utilizzato il set di dati mostrato di seguito.

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

L’unione da persona a account B2B impedisce che gli eventi vengano ignorati e non acquisiti utilizzando le operazioni seguenti:

* [Elevare le identità della persona](#elevate-person-identities).
* [Aggiungi identità account mancanti](#add-missing-account-identitiers).


### Privilegiare le identità delle persone

+++ Dettagli

Per supportare l’unione di persona-account B2B, fornisci un set di dati di mappatura persona-account. Ad esempio:

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

L’unione basata su grafico viene utilizzata anche per elevare gli ID persona nel set di dati dell’evento esperienza. Ad esempio, puoi configurare il campo ID persistente (ECID) da utilizzare come ID persona persistente quando [attivi l&#39;unione nel set di dati](#enable-b2b-person-to-account-stitching-on-event-datasets). In base a `5678` come valore ECID e `emily@adobe.com` come valore E-mail, `emily@adobe.com` viene impostato come ID persona con privilegi elevati per l&#39;evento correlato.

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

Questo esempio mostra come l’unione di persone B2B e account aggiorna i dati dell’evento esperienza con identificatori di persona mancanti o identificatori di account mancanti o errati, in base al set di dati di mappatura persona-account fornito come input.


## Prerequisiti

Prima di abilitare la persona B2B all’unione di account, prepara i seguenti set di dati in Adobe Experience Platform:

| Set di dati | Obbligatorio | Descrizione |
|---|---|---|
| **set di dati persona-account** | Obbligatorio | Un set di dati di ricerca (record, serie non temporali) che contiene almeno un ID persona (con spazio dei nomi) e un ID account. Questi ID vengono utilizzati per derivare la mappa di relazione tra persone e account. |

>[!IMPORTANT]
>
>Il campo ID persona nel set di dati **[!UICONTROL persona per account]** deve essere contrassegnato come identità nello schema.

## Abilita unione delle identità persona-account {#enable-account-stitching}

Innanzitutto, abilita e configura l’unione B2B a livello di connessione. Quando l’unione B2B è configurata per una connessione, puoi quindi attivare l’unione da persona a account sui singoli set di dati evento all’interno di tale connessione.

### Configurare le impostazioni di unione della persona B2B con l’account {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="Configurare l’unione B2B"
>abstract="Seleziona **[!UICONTROL Apri configurazione unione B2B]** per configurare la persona B2B per l&#39;unione account. Se la connessione non è ancora stata salvata, la configurazione sarà etichettata con **[!UICONTROL _Modifiche non salvate_]**."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="Spazio dei nomi identificatori persona"
>abstract="Seleziona lo spazio dei nomi identità della persona più pertinente per il reporting. Ad esempio, E-mail. Qualsiasi set di dati evento con **[!UICONTROL unione da persona a account]** abilitata ha l&#39;ID persona persistente elevato a questo spazio dei nomi dell&#39;identificatore della persona."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="Set di dati Da persona ad account"
>abstract="Seleziona il set di dati di ricerca per la mappatura degli ID persona agli ID account."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="ID persona"
>abstract="Seleziona il campo nel set di dati che contiene gli ID persona. Lo spazio dei nomi di questo campo può essere diverso o uguale allo spazio dei nomi dell’identificatore della persona selezionato. Se differiscono, i due spazi dei nomi devono essere collegati nel grafo di identità."

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


1. In Customer Journey Analytics, passa a **[!UICONTROL Connessioni]** e [crea una nuova connessione](/help/connections/create-connection.md#create-a-connection).

1. In **[!UICONTROL Impostazioni connessione]**, impostare **[!UICONTROL ID primario]** su ![Generazione](/help/assets/icons/Building.svg) **[!UICONTROL Account]**.

1. Accertati di selezionare i **[!UICONTROL contenitori opzionali]** che desideri utilizzare nella connessione B2B. Non puoi modificare la selezione di questi contenitori dopo aver salvato una persona B2B nella configurazione di unione degli account.

1. Seleziona **[!UICONTROL Apri configurazione di unione B2B]**.

   ![Configurazione titolazione saccount B2B](../assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >Una persona B2B configurata in precedenza per la configurazione di unione degli account per una connessione non salvata è indicata con **[!UICONTROL _Modifiche non salvate_]**. Non puoi modificare **[!UICONTROL Contenitori opzionali]** per una persona B2B configurata in precedenza per la configurazione di unione degli account.

1. Nella finestra di dialogo **[!UICONTROL Configurazione unione B2B]**:

   ![Configurazione di unione da persona B2B a account](../assets/b2b-stitching-configuration.png)

   1. Configura la sezione **[!UICONTROL Persona]**:

      * Seleziona lo spazio dei nomi dell’identità della persona più rilevante per la generazione dei rapporti, ad esempio E-mail. Qualsiasi set di dati evento con l’unione da persona a account abilitata ha l’ID persona persistente elevato a questo spazio dei nomi dell’identificatore della persona. Questo campo è obbligatorio.

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

### Abilitare la persona B2B all’unione di account nei set di dati dell’evento


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="Abilita unione delle identità persona-account"
>abstract="Se questa opzione è abilitata, questo set di dati utilizza l’unione delle identità B2B Da persona ad account. I valori **[!UICONTROL ID persona persistente]** verranno elevati a quelli configurati per lo spazio dei nomi **[!UICONTROL Identificatore persona]**, quindi verranno utilizzati per ricercare l&#39;ID account in base al set di dati da persona a account.<br/>Se disabilitato, questo set di dati non utilizza la persona B2B per l&#39;unione degli account. Devi selezionare invece un **[!UICONTROL ID account]** richiesto."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/b2b/b2b-person-to-account-stitching#configure-b2b-stitching-settings" text="Configurare le impostazioni di unione della persona B2B con l’account"

Dopo aver configurato l’unione B2B a livello di connessione, devi abilitare la persona B2B per l’unione di account singolarmente per ogni set di dati evento da unire.

1. In Impostazioni connessione selezionare **[!UICONTROL Aggiungi set di dati]** o aprire le impostazioni per un set di dati evento esistente.<br/>Per ulteriori informazioni, vedere [Aggiungere set di dati](/help/connections/create-connection.md#add-datasets) o [Modificare un set di dati](/help/connections/create-connection.md#edit-a-dataset).

1. Per il set di dati evento specifico per il quale si desidera configurare la persona B2B per l&#39;unione di account, attivare **[!UICONTROL Attiva unione da persona a account]**.

>[!BEGINTABS]

>[!TAB Il]

Quando **[!UICONTROL Abilita unione persona per account]** è **su**, hai configurato una persona B2B per l&#39;unione account per il set di dati.

* È necessario configurare un ID persona. L&#39;ID persona viene utilizzato per cercare l&#39;ID account in base al [set di dati persona-account](#prerequisites).
* La configurazione di un ID account è facoltativa.

![Unione di persona B2B con account nel set di dati evento il](../assets/b2b-event-dataset-stitching-on.png)

>[!TAB Disattivato]

Quando **[!UICONTROL Abilita unione persona per account]** è **off**, *not* ha configurato una persona B2B per l&#39;unione account per il set di dati.

* È necessaria la configurazione di un ID account.
* La configurazione di un ID persona è facoltativa.

![Unione di persona B2B con account nel set di dati evento disattivata](../assets/b2b-event-dataset-stitching-off.png)

>[!ENDTABS]


### Salva

Dopo aver configurato la persona B2B per la configurazione di unione degli account e aver completato l&#39;aggiunta o la modifica dei set di dati, seleziona **[!UICONTROL Salva]** per salvare la connessione.

>[!IMPORTANT]
>
>Una volta salvata una connessione, la configurazione dell’unione di persona B2B con l’account diventa immutabile. Per visualizzare le impostazioni dopo il salvataggio, selezionare **Apri configurazione di unione B2B**. Tutti i campi sono di sola lettura. Inoltre, se il set di dati utilizzato per il [mapping tra persone e account](#prerequisites) viene eliminato in Experience Platform, la configurazione di unione viene eliminata e la connessione passa a uno stato non valido, segnalato con un messaggio di avviso nell&#39;interfaccia utente.

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
>* [Panoramica dell&#39;unione](../overview.md)
>* [Configurare una connessione per B2B](/help/connections/create-connection.md)
>* [Domande frequenti sull&#39;unione](../faq.md)

