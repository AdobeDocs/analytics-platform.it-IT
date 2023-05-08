---
description: Condivisione e ruoli dei progetti in Workspace
keywords: Condivisione di Analysis Workspace
title: Condividere progetti
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: dab154ce10b0b4f7fb2873d92a1ce9ceb7478b26
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Condividere progetti

Puoi condividere un progetto Analysis Workspace con i seguenti tipi di persone:

* Utenti e gruppi della tua organizzazione che hanno accesso ad Adobe Customer Journey Analytics

   È possibile condividere l&#39;accesso Modifica, Duplica o Visualizza

* Utenti e gruppi dell’organizzazione che non hanno accesso al Customer Journey Analytics

   I destinatari hanno accesso in sola lettura

* Persone esterne all’organizzazione

   I destinatari hanno accesso in sola lettura

Qualsiasi [cura](curate.md) quando i destinatari aprono il progetto, viene visualizzata l’applicazione prima della condivisione.

Ecco una panoramica video della condivisione dei progetti:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Condividi con Customer Journey Analytics e gruppi della tua organizzazione {#Add}

Puoi condividere un progetto con utenti o gruppi di Customer Journey Analytics esistenti nell’organizzazione. Quando condividi un progetto come descritto in questa sezione, gli utenti con cui condividi devono già disporre di un account di Customer Journey Analytics.

Puoi condividere un ruolo specifico con utenti o gruppi oppure un collegamento.

* [Condividere un ruolo di progetto specifico](#share-a-specific-project-role)

* [Condivisione di un collegamento a un progetto](#share-a-link-to-a-project)

## Condividere un ruolo di progetto specifico

Quando condividi un ruolo di progetto specifico con utenti e gruppi dell’organizzazione, considera quanto segue:

* Ruoli di progetto (**[!UICONTROL Can edit]**, **[!UICONTROL Can duplicate]** e **[!UICONTROL Can view]**) sono legate all’utente e all’ID del progetto specifico. I ruoli di progetto sono indipendenti dalle autorizzazioni utente gestite nella [Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it).

* In Customer Journey Analytics, i gruppi sono definiti dai profili di prodotto nell’[Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it). Gli amministratori possono condividere con qualsiasi gruppo, incluso &quot;All&quot;. I non amministratori possono condividere con qualsiasi gruppo di cui sono membri, ad eccezione di &quot;All&quot;.

* Un utente posizionato in più ruoli ottiene sempre l’esperienza più elevata. Ciò potrebbe verificarsi se un utente viene aggiunto sia come singolo utente che come parte di un gruppo. Ad esempio, se a un utente viene assegnato il **[!UICONTROL Can edit]** il ruolo individuale e **[!UICONTROL Can view]** come membro di un gruppo, riceveranno un **[!UICONTROL Can edit]** esperienza del progetto.

* Gli amministratori inseriti nella **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** Quando aprono un progetto, il ruolo riceve le esperienze limitate. Se necessario, un amministratore può elevare il proprio ruolo a **[!UICONTROL Can edit]** in qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**.

Per condividere un ruolo di progetto specifico con utenti o gruppi dell’organizzazione:

1. Passa al progetto da condividere, quindi fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**.
In caso di modifiche non salvate, viene richiesto di salvare prima il progetto.

   ![](assets/share-proj-modal.png)

   Per informazioni sulla condivisione simultanea di più progetti, consulta [Condivisione di progetti nel Project manager](#share-projects-in-the-project-manager).

1. Aggiungi destinatari o gruppi di destinatari in uno dei campi ruolo forniti:

   **Può modificare:** I destinatari possono **[!UICONTROL Save]** modifiche a un progetto e funzioni come co-proprietari. Questo ruolo è utile se desideri gestire un progetto con altri colleghi; ciò include la modifica e l’eliminazione degli elenchi dei destinatari per un progetto condiviso. <br>Nota: Analysis Workspace al momento non supporta la collaborazione in tempo reale, pertanto si consiglia di modificare un progetto solo un utente alla volta. Se i progetti vengono salvati contemporaneamente, viene mantenuta l’ultima versione.

   **Può duplicare:** I destinatari possono **[!UICONTROL Save as]** e hanno accesso alla barra a sinistra. Le interazioni del progetto non sono limitate in questo ruolo. Questo ruolo è utile se desideri condividere un progetto con utenti che conoscono i dati dell’organizzazione e sanno come utilizzare Analysis Workspace, ma non desideri che il progetto venga modificato.

   **Può visualizzare:** I destinatari non possono **[!UICONTROL Save]** o **[!UICONTROL Save as]** e non hanno accesso alla barra a sinistra. Anche le interazioni del progetto sono limitate. Questo ruolo è utile se desideri condividere un progetto con utenti che hanno meno familiarità con la struttura dati della tua organizzazione, Analysis Workspace o in genere il Customer Journey Analytics. Tuttavia, desideri comunque che utilizzino dati e informazioni in un ambiente sicuro. Scopri di più sull’[esperienza di progetto Can view](/help/analysis-workspace/curate-share/view-only-projects.md).

1. Scegli se abilitare le seguenti opzioni quando condividi il progetto:

   * **Condividi componenti di progetto incorporati:** Condivide segmenti, metriche calcolate e intervalli di date con tutti i destinatari. Una volta condivisi, tali componenti sono disponibili nel menu a discesa Components nell’interfaccia Workspace del destinatario. Questa impostazione non è persistente, ma è un’azione una tantum al momento della condivisione.

   * **Imposta come pagina di destinazione per i destinatari:** Imposta questa pagina come pagina di destinazione per i destinatari. Questa impostazione non è persistente, ma è un’azione una tantum al momento della condivisione.

1. Fai clic su **[!UICONTROL Share]**. Se il progetto è già stato condiviso, fai clic su [!UICONTROL **Aggiorna**].)

   Oppure

   Fai clic su **[!UICONTROL Curate and Share]** per applicare automaticamente la cura del progetto. Se il progetto è già stato condiviso, fai clic su **[!UICONTROL Curate & Update]**.) Ulteriori informazioni sulla [cura dei progetti](curate.md).

## Condivisione di un collegamento a un progetto

Quando condividi un collegamento come descritto in questa sezione, considera quanto segue:

* I destinatari che utilizzano il collegamento devono accedere al Customer Journey Analytics prima di accedere al progetto.

* Se a un destinatario non viene assegnato un ruolo e riceve un [collegamento](/help/analysis-workspace/curate-share/shareable-links.md) al progetto (**[!UICONTROL Share]>[!UICONTROL Get project link]**), viene loro assegnato un ruolo per impostazione predefinita. Gli amministratori ricevono **[!UICONTROL Can edit]** e non amministratori ricevono **[!UICONTROL Can duplicate]**.

Per condividere il collegamento al progetto con gli utenti dell’organizzazione:

1. Salva il progetto. In caso di modifiche non salvate, viene richiesto di salvare il progetto prima di condividere un collegamento.

1. Seleziona **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**, quindi seleziona **[!UICONTROL Copy]** accanto al **[!UICONTROL Share by link]** campo .

   ![](assets/share-proj-modal.png)

1. Condividi il collegamento con gli utenti della tua organizzazione. Ad esempio, puoi incollarlo in un’e-mail, in un sito web interno e così via.

## Condivisione di un progetto con altri utenti (accesso non richiesto) {#share-public-link}

{{release-limited-testing-section}}

Puoi concedere [accesso in sola lettura](/help/analysis-workspace/curate-share/view-only-projects.md) ad Analysis Workspace progetti per persone che non hanno accesso al Customer Journey Analytics. Ciò può includere:

* Persone esterne all’organizzazione

* Persone all’interno della tua organizzazione che non dispongono del provisioning con il Customer Journey Analytics

>[!NOTE]
>
>Quando condividi un progetto Analysis Workspace con persone che non hanno accesso a CJA, considera quanto segue:
>
>* L’amministratore CJA può disattivare la possibilità di condividere un progetto in questo modo, come descritto in [Preferenze](/help/analysis-workspace/user-preferences.md). Se non puoi condividere un progetto come descritto in questa sezione, l’amministratore di CJA ha disattivato questa funzionalità.
>
>* I progetti con più di 50 visualizzazioni estese non possono essere condivisi con persone che non hanno accesso a CJA.
>
>* Gli utenti con cui condividi possono visualizzare tutti i filtri applicati al progetto durante [cura](curate.md).
> 
>* Gli utenti con cui condividi possono modificare l’intervallo di date del progetto. L’intervallo di date impostato per il progetto viene visualizzato per impostazione predefinita.
>
>* Un progetto potrebbe diventare inaccessibile se molti utenti tentano di accedere contemporaneamente a un determinato collegamento. Per impostazione predefinita, più di 190 persone possono accedere a un singolo collegamento ogni 5 minuti. Se l’organizzazione raggiunge questo limite, attendi 5 minuti e prova ad accedere nuovamente al collegamento.


Per condividere un progetto Analysis Workspace con chiunque:

1. Apri il progetto Analysis Workspace da condividere.

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share with anyone]**.

   In caso di modifiche non salvate, viene richiesto di salvare il progetto.

   <!-- Add screen shot of new modal -->

1. Abilita la **[!UICONTROL Link is active]** se non è già abilitata.

   Selezionando questa opzione viene creato un collegamento al progetto che può essere condiviso con chiunque. Per disattivare l’accesso al progetto in qualsiasi momento, disattiva questa opzione.

   Il proprietario del progetto è anche il proprietario del collegamento. La proprietà del collegamento può essere trasferita a un altro utente solo quando la proprietà del progetto viene trasferita, come descritto in [Trasferimento delle risorse utente o impostazione della scadenza dell&#39;account](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=en) nella guida per l’amministrazione di Analytics.

1. Scegli se abilitare la seguente opzione di sicurezza (questa opzione può essere controllata dall’amministratore CJA):

   * **[!UICONTROL Require Experience Cloud authentication]:**

      Quando questa opzione è abilitata, solo gli utenti che possono accedere all’organizzazione Adobe Experience Cloud in cui è stato creato il progetto che stai condividendo possono accedere al progetto.

      Gli amministratori di CJA possono configurare questa preferenza per l’azienda, come descritto in [Preferenze](/help/analysis-workspace/user-preferences.md). È possibile che si verifichino i seguenti scenari, a seconda di come l’amministratore ha configurato questa opzione:

      * Se questa opzione non è visibile, l’amministratore di CJA non ha abilitato questa funzione.

      * Se questa opzione è abilitata e disattivata, l’amministratore di CJA richiede l’autenticazione Experience Cloud per tutti gli utenti che accedono ai progetti Analysis Workspace.

1. Accanto al **[!UICONTROL Share with anyone (no login required)]** fai clic sul campo **Copia collegamento** icona ![Icona Copia collegamento](assets/copy-link-icon.png) per copiare il collegamento negli Appunti del sistema.

1. Condividi il collegamento con le persone a cui desideri accedere al progetto. Ad esempio, puoi incollare il collegamento in un messaggio e-mail.

   Qualsiasi persona con cui condividi il collegamento può visualizzare il progetto Analysis Workspace.

1. (Facoltativo) Puoi fare clic sul pulsante **Genera nuovo collegamento** icona ![Icona Genera collegamento](assets/regenerate-link.png) per rimuovere l’accesso dagli utenti che hanno precedentemente ricevuto un collegamento al progetto. Viene generato un nuovo collegamento che puoi condividere con gli utenti a cui desideri accedere al progetto.

1. Seleziona **[!UICONTROL Close]** per chiudere la finestra di dialogo di condivisione. Le modifiche vengono salvate automaticamente.

## Condivisione di progetti nel Project manager {#Manager}

I progetti possono essere condivisi anche da **[!UICONTROL Components]>[!UICONTROL Projects]**. Un singolo progetto può essere condiviso seguendo gli stessi passaggi indicati sopra.  Se sono stati selezionati più progetti da condividere, i destinatari verranno aggiunti all’elenco esistente di destinatari per ciascun progetto.

Ad esempio:

* Il progetto A è condiviso con i destinatari 1, 2, 3
* Il progetto B è condiviso con i destinatari 4, 5, 6

Con i progetti A e B selezionati, i destinatari 4 e 7 vengono aggiunti agli elenchi di condivisione. Il nuovo elenco di condivisione per ciascun progetto ora è:

* Progetto A: 1, 2, 3, 4, 7
* Progetto B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Condividere componenti incorporati

Video sull’argomento:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Domande frequenti {#FAQs}

| Domanda | Risposta |
|---|---|
| Cosa succede se due editor salvano un progetto contemporaneamente? | Le modifiche non vengono unite e viene mantenuta l’ultima versione del progetto salvata. Analysis Workspace non supporta attualmente la collaborazione in tempo reale. |
| In qualità di amministratore, quale esperienza di progetto visualizzerò? | Gli amministratori inseriti in un ruolo **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** riceveranno tali esperienze limitate quando aprono un progetto. Se necessario, un amministratore può elevare il proprio ruolo a **[!UICONTROL Can edit]** in qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Cosa succede se un destinatario viene collocato in un ruolo come singolo utente e in un altro ruolo come membro di un gruppo? | Se un destinatario viene posizionato in più ruoli, riceverà sempre l’esperienza di livello più elevato. Ad esempio, se a un destinatario viene assegnato il ruolo **[!UICONTROL Can edit]** come singolo utente e il ruolo **[!UICONTROL Can view]** come membro di un gruppo, riceverà un’esperienza di progetto **[!UICONTROL Can edit]**. |
| Quale esperienza riceve un destinatario se apre un collegamento al progetto? | I destinatari ricevono il ruolo in cui li hai inseriti nella modalità di condivisione. Se a un destinatario non viene assegnato un ruolo e riceve un collegamento al progetto (**[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**, quindi seleziona **[!UICONTROL Copy]** accanto al **[!UICONTROL Share by link]** (campo ), verranno inseriti in un ruolo per impostazione predefinita. Gli amministratori ricevono **[!UICONTROL Can edit]** e i non amministratori **[!UICONTROL Can duplicate]**. |
