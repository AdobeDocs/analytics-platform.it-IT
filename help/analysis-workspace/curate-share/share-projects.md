---
description: Scopri come condividere i progetti in Analysis Workspace.
keywords: Condivisione di Analysis Workspace
title: Condividere progetti
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 76%

---

# Condividere progetti {#share-projects}

>[!CONTEXTUALHELP]
>id="workspace_shareprojects"
>title="Condividere progetti"
>abstract="Puoi condividere uno di questi ruoli di progetto con altri utenti dell’organizzazione."



Puoi condividere un progetto di Analysis Workspace con i seguenti tipi di persone:

* Utenti e gruppi della tua organizzazione che hanno accesso a Customer Journey Analytics

  È possibile condividere l’accesso a Modifica, Duplica o Visualizza

* Utenti e gruppi dell’organizzazione che non hanno accesso a Customer Journey Analytics

  I destinatari dispongono di accesso di sola lettura

* Persone esterne all’organizzazione

  I destinatari dispongono di accesso di sola lettura

Qualsiasi [cura](curate.md) applichi prima della condivisione, viene visualizzata all’apertura del progetto da parte dei destinatari.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Condivisione dei progetti in Analysis Workspace](https://video.tv.adobe.com/v/40037/?quality=12&learn=on&captions=ita){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]


## Condividere con utenti e gruppi nella tua organizzazione {#Add}

Puoi condividere un progetto con utenti o gruppi di Analysis Workspace esistenti nella tua organizzazione. Quando condividi un progetto come descritto in questa sezione, gli utenti con cui condividi devono già disporre di un account Customer Journey Analytics.

Puoi condividere un ruolo specifico con utenti o gruppi, oppure un collegamento.

* [Condividere un ruolo di progetto specifico](#share-a-specific-project-role)

* [Condividere un collegamento a un progetto](#share-a-link-to-a-project)

## Condividere un ruolo di progetto specifico

Quando condividi un ruolo di progetto specifico con utenti e gruppi dell’organizzazione, considera quanto segue:

* I ruoli di progetto  (**[!UICONTROL Edit original]**, **[!UICONTROL Edit copy]**, e **[!UICONTROL Read only]**) sono legati all’ID dell’utente e del progetto specifico. I ruoli di progetto sono indipendenti dalle autorizzazioni utente gestite in [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/it/docs/core-services/interface/administration/admin-getting-started).

* In Customer Journey Analytics, i gruppi sono definiti dai profili di prodotto in [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/it/docs/core-services/interface/administration/admin-getting-started). Gli amministratori possono condividere con qualsiasi gruppo, compresi *Tutti*. Gli utenti non amministratori possono condividere con qualsiasi gruppo di cui sono membri, ad eccezione di *Tutti*.

* Un destinatario posizionato in più ruoli, avrà sempre l’esperienza di livello più elevato. Questo scenario può verificarsi se un utente viene aggiunto sia come singolo utente che come parte di un gruppo. Ad esempio, se a un utente viene assegnato il ruolo **[!UICONTROL Edit original]** come singolo utente e il ruolo **[!UICONTROL Read only]** come membro di un gruppo, l&#39;utente riceve un&#39;esperienza di progetto **[!UICONTROL Edit original]**.

* Gli amministratori inseriti in un ruolo **[!UICONTROL Edit copy]** o **[!UICONTROL Read only]** riceveranno tali esperienze limitate quando aprono un progetto. Un amministratore può modificare il proprio ruolo in **[!UICONTROL Edit original]** condividendo il progetto con se stesso e assegnando il ruolo Modifica, come descritto nella procedura seguente.

* Se selezioni più progetti da condividere, i destinatari vengono aggiunti all’elenco esistente di destinatari per ciascun progetto.

  Ad esempio, il progetto A è già condiviso con i destinatari 1, 2 e 3, mentre il progetto B è già condiviso con i destinatari 4, 5 e 6.

  I progetti A e B sono quindi condivisi con i destinatari 4 e 7. Il nuovo elenco di condivisione per il progetto A è ora 1, 2, 3, 4 e 7, mentre il nuovo elenco di condivisione per il progetto B è 4, 5, 6 e 7.

Per condividere un ruolo di progetto specifico con utenti o gruppi dell’organizzazione:

1. In Customer Journey Analytics, seleziona la scheda [!UICONTROL **Workspace**], quindi seleziona [!UICONTROL **Progetti**] nel pannello a sinistra.

1. Seleziona la casella di controllo accanto a uno o più progetti da condividere, quindi seleziona [!UICONTROL **Condividi**].

   Oppure

   Per condividere solo un singolo progetto, puoi aprire il progetto da condividere e poi selezionare **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**.
In presenza di modifiche non salvate, ti verrà richiesto di salvare prima il progetto.

   Viene visualizzata la finestra di dialogo Condividi progetto. Le sezioni [!UICONTROL **Condividi tramite collegamento**] e [!UICONTROL **Impostazioni**] della finestra di dialogo sono visibili solo quando si condivide un singolo progetto.

   ![Finestra Condividi progetto.](assets/share-proj-modal.png)

1. Aggiungi destinatari o gruppi di destinatari in uno dei campi ruolo forniti:

   **Modifica originale:** i destinatari possono **[!UICONTROL Save]** le modifiche a un progetto e fungere da co-proprietari. Questo ruolo è utile se desideri gestire un progetto con altri colleghi. Questo ruolo include la modifica, l’eliminazione e la modifica degli elenchi dei destinatari per un progetto condiviso. <br>Nota: Analysis Workspace al momento non supporta la collaborazione in tempo reale, pertanto si consiglia di modificare un progetto solo un utente alla volta. Se i progetti vengono salvati contemporaneamente, viene mantenuta l’ultima versione.

   **Modifica copia:** i destinatari possono **[!UICONTROL Save as]** e avere accesso al pannello di sinistra. Le interazioni del progetto non sono limitate a questo ruolo. Questo ruolo è utile se desideri condividere un progetto con utenti che conoscono i dati della tua organizzazione e sanno come utilizzare Analysis Workspace. Tuttavia, non desideri che questi utenti modifichino il tuo progetto.

   **Sola lettura:** i destinatari non possono **[!UICONTROL Save]** o **[!UICONTROL Save as]** e non hanno accesso al pannello di sinistra. Anche le interazioni del progetto sono limitate. Questo ruolo è utile se desideri condividere un progetto con utenti che hanno meno familiarità con la struttura dei dati dell’organizzazione, con Analysis Workspace o con Customer Journey Analytics in genere. Tuttavia, desideri comunque che utilizzino dati e informazioni in un ambiente sicuro. Scopri di più sull’[esperienza di progetto di Sola lettura](/help/analysis-workspace/curate-share/view-only-projects.md).

1. (Condizionale) Se condividi un singolo progetto, scegli se abilitare le seguenti opzioni durante la condivisione:

   * **Condividi componenti di progetto incorporati:** condividi segmenti, metriche calcolate e intervalli di date con tutti i destinatari. Una volta condivisi, tali componenti sono disponibili nel menu a discesa Componenti nell’interfaccia Workspace del destinatario. Questa impostazione non è persistente: è una singola azione da eseguire al momento della condivisione.

   * **Imposta come pagina di destinazione per i destinatari:** imposta questa pagina come pagina di destinazione per i destinatari. Questa impostazione non è persistente: è una singola azione da eseguire al momento della condivisione.

1. Seleziona **[!UICONTROL Share]**. Se il progetto è già stato condiviso, seleziona [!UICONTROL **Aggiorna**].

   Oppure

   Fai clic su **[!UICONTROL Curate and Share]** per applicare automaticamente la cura del progetto. (Se il progetto è già stato condiviso, seleziona **[!UICONTROL Curate & Update]**). Ulteriori informazioni su [cura del progetto](curate.md).


## Condividere un collegamento a un progetto

Quando condividi un collegamento come descritto in questa sezione, prendi in considerazione quanto segue:

* Gli utenti che utilizzano un collegamento devono accedere a Customer Journey Analytics prima di poter accedere al progetto.

* Se a un destinatario non è stato assegnato un ruolo, per impostazione predefinita gliene verrà assegnato uno quando riceve un [collegamento condivisibile](/help/analysis-workspace/curate-share/shareable-links.md) al progetto (**[!UICONTROL Share]>[!UICONTROL Get project link]**). Gli amministratori ricevono **[!UICONTROL Edit original]** e i non amministratori **[!UICONTROL Edit copy]**.

Per condividere il collegamento del progetto con gli utenti dell’organizzazione:

1. Salva il progetto. In presenza di modifiche non salvate, ti verrà richiesto di salvare prima il progetto prima di condividere un collegamento.

1. Seleziona **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**, quindi seleziona **[!UICONTROL Copy]** accanto al campo **[!UICONTROL Share by link]**.

   ![Condividi progetto evidenzia il campo Condividi tramite collegamento.](assets/share-proj-modal.png)

1. Condividi il collegamento con gli utenti della tua organizzazione. Ad esempio, puoi incollarlo in un’e-mail, in un sito web interno e così via.

## Condividere un progetto con chiunque (accesso non richiesto) {#share-public-link}

>[!CONTEXTUALHELP]
>id="workspace_share_with_anyone_require_aec_authentication"
>title="Richiedere l’autenticazione Experience Cloud"
>abstract="La tua organizzazione richiede che gli utenti abbiano effettuato l’accesso ad Experience Cloud per utilizzare questo collegamento."


Puoi consentire l’[accesso di sola lettura](/help/analysis-workspace/curate-share/view-only-projects.md) ai progetti di Analysis Workspace a coloro che non hanno accesso a Customer Journey Analytics. Questo accesso concesso può includere:

* Persone esterne all’organizzazione

* Persone dell’organizzazione che non hanno accesso a Customer Journey Analytics

>[!NOTE]
>
>Quando condividi un progetto di Analysis Workspace con persone che non hanno accesso a Customer Journey Analytics, considera quanto segue:
>
>* La possibilità di condividere un progetto in questo modo può essere disabilitata dall’amministratore di Customer Journey Analytics, come descritto in [Preferenze](/help/analysis-workspace/user-preferences.md). Se non riesci a condividere un progetto come descritto in questa sezione, l’amministratore di Customer Journey Analytics ha disabilitato questa possibilità.
>
>* I progetti con più di 50 visualizzazioni espanse possono essere condivisi solo con persone che hanno accesso a Customer Journey Analytics.
>
>* Gli utenti con cui effettui la condivisione possono visualizzare tutti i segmenti applicati al progetto durante la [cura](curate.md).
> 
>* Gli utenti con cui condividi possono modificare l’intervallo di date del progetto. L’intervallo di date impostato per il progetto viene visualizzato per impostazione predefinita.
>
>* Un progetto potrebbe diventare inaccessibile se molti utenti tentano di accedere contemporaneamente a un determinato collegamento. Per impostazione predefinita, più di 190 persone possono accedere a un singolo collegamento ogni 5 minuti. Se l’organizzazione raggiunge questo limite, attendi 5 minuti e prova di nuovo ad accedere al collegamento.
>
>* Per entrambe le licenze [!DNL Healthcare Shield] e [!DNL Privacy & Security Shield], la funzione [!UICONTROL Share with anyone] richiede l’autenticazione Experience Cloud. Per chi usa [!DNL Healthcare Shield], viene visualizzato un avviso di “conformità HIPAA”, ma è comunque possibile utilizzare questa funzione dopo l’autenticazione in Experience Cloud.

>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Condividere con chiunque](https://video.tv.adobe.com/v/3452466/?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


Per condividere un progetto Analysis Workspace con chiunque:

1. Apri il progetto Analysis Workspace che desideri condividere.

1. Seleziona **[!UICONTROL Share]** > **[!UICONTROL Share with anyone]**.

   In presenza di modifiche non salvate, ti verrà richiesto di salvare il progetto.

   <!-- Add screen shot of new modal -->

1. Abilita l’opzione **[!UICONTROL Link is active]** se non è già abilitata.

   Selezionando questa opzione viene creato un collegamento al progetto che può essere condiviso con chiunque. Disattivando questa opzione è possibile disattivare l’accesso al progetto in qualsiasi momento.

   Il proprietario del progetto è anche il proprietario di questo collegamento. La proprietà del collegamento può essere trasferita a un altro utente solo quando viene trasferita la proprietà del progetto, come descritto in [Trasferire le risorse utente](/help/tools/asset-transfer/transfer-assets.md) nella guida per l’amministratore di Analytics.

1. Scegli se abilitare la seguente opzione di sicurezza (questa opzione può essere controllata dall’amministratore di Customer Journey Analytics):

   * **[!UICONTROL Require Experience Cloud authentication]:**

     Quando questa opzione è abilitata, gli unici utenti che possono accedere al progetto sono quelli che possono accedere all’organizzazione Adobe Experience Cloud in cui è stato creato il progetto condiviso. Tuttavia, gli utenti con cui condividi non hanno bisogno di avere l’accesso ad Adobe Analytics.

     Gli amministratori di Customer Journey Analytics possono configurare questa preferenza per l’azienda, come descritto in [Preferenze](/help/analysis-workspace/user-preferences.md). A seconda della configurazione di questa opzione da parte dell’amministratore, potrebbero verificarsi gli scenari seguenti:

      * Se questa opzione non è visibile, l’amministratore di Customer Journey Analytics non ha abilitato questa funzione.

      * Se questa opzione è abilitata e non puoi disabilitarla, significa che l’amministratore di Customer Journey Analytics richiede l’autenticazione di Experience Cloud per tutti gli utenti che accedono ai progetti Analysis Workspace. Questo è sempre il caso delle organizzazioni che dispongono della licenza Healthcare Shield.

1. Accanto al campo **[!UICONTROL Share with anyone (no login required)]**, seleziona ![Collegamento](/help/assets/icons/Link.svg) per copiare il collegamento negli Appunti di sistema.

1. Condividi il collegamento con le persone che desideri possano accedere al progetto. Ad esempio, puoi incollare il collegamento in un messaggio e-mail.

   Qualsiasi persona con cui condividi il collegamento può visualizzare il progetto Analysis Workspace.

1. (Facoltativo) Puoi selezionare l’![icona Genera nuovo collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) per rimuovere l’accesso da utenti che hanno precedentemente ricevuto un collegamento al progetto. Viene generato un nuovo collegamento che puoi condividere con gli utenti che desideri accedano al progetto.

1. Seleziona **[!UICONTROL Close]** per chiudere la finestra di dialogo condividi. Le modifiche vengono salvate automaticamente.

## Visualizza progetti condivisi con te

Quando qualcuno condivide un progetto con te tramite la [condivisione di un ruolo di progetto specifico](#share-a-specific-project-role), puoi accedere ai progetti condivisi dalla [scheda Progetti della pagina di destinazione di Analytics](/help/getting-started/landing.md#navigate-the-projects-tab).

Quando qualcuno condivide un progetto con te condividendo un collegamento (dalla [scheda Condividi progetto](#share-a-link-to-a-project) o utilizzando un collegamento [condividi con altri utenti](#share-a-project-with-anyone-no-login-required)), devi utilizzare il collegamento condiviso con te per accedere al progetto. Ad esempio, il collegamento potrebbe essere stato condiviso in un’e-mail, in un sito web interno e così via.

## Condividere componenti incorporati

Puoi condividere i componenti incorporati che fanno parte del progetto.

>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Condividere componenti incorporati in Analysis Workspace](https://video.tv.adobe.com/v/329425/?quality=12&learn=on&captions=ita){target="_blank"}.

{{videoaa}}

>[!ENDSHADEBOX]


## Domande frequenti {#FAQs}

| Domanda | Risposta |
|---|---|
| Cosa succede se due editor salvano un progetto contemporaneamente? | Le modifiche non vengono unite e viene mantenuta l’ultima versione del progetto salvata. Analysis Workspace non supporta attualmente la collaborazione in tempo reale. |
| In qualità di amministratore, quale esperienza di progetto visualizzo? | Gli amministratori inseriti in una mansione **[!UICONTROL Edit copy]** o **[!UICONTROL Read only]** ricevono tali esperienze limitate quando aprono un progetto. Se necessario, un amministratore può elevare il proprio ruolo a **[!UICONTROL Edit original]** in qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Cosa succede se un destinatario viene collocato in un ruolo come singolo utente e in un altro ruolo come membro di un gruppo? | Se un destinatario viene posizionato in più ruoli, riceve sempre l’esperienza di livello più elevato. Ad esempio, se a un destinatario viene assegnato il ruolo **[!UICONTROL Edit original]** come singolo utente e il ruolo **[!UICONTROL Can view]** come membro di un gruppo, l&#39;utente riceve un&#39;esperienza di progetto **[!UICONTROL Edit original]**. |
| Quale esperienza riceve un destinatario se apre un collegamento al progetto? | I destinatari ricevono il ruolo che li hai inseriti nel modale di condivisione. Se a un destinatario non viene assegnato un ruolo e riceve un collegamento al progetto (**[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]** e seleziona **[!UICONTROL Copy]** accanto al campo **[!UICONTROL Share by link]**), il viene inserito in un ruolo predefinito. Gli amministratori ricevono **[!UICONTROL Edit original]** e i non amministratori ricevono **[!UICONTROL Edit copy]** ruoli. |
