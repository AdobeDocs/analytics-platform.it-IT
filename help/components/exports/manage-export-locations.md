---
description: Gestisci il percorso di esportazione cloud in cui possono essere inviati i dati del Customer Journey Analytics
keywords: Analysis Workspace
title: Gestire percorsi e account di esportazione cloud
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
source-git-commit: 8fc8e3e4057663bd4bdf38e41bb3129df442f749
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 1%

---

# Gestire percorsi e account di esportazione cloud

Puoi visualizzare, modificare ed eliminare i percorsi di esportazione cloud.

Per informazioni su come creare un nuovo percorso, vedere [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

## Filtrare e cercare i percorsi

Per trovare le informazioni necessarie, puoi filtrare l’elenco delle posizioni o cercare una posizione.

### Filtra l’elenco delle posizioni

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la scheda [!UICONTROL **Percorsi**].

1. Seleziona l&#39;icona **Filtro**.

   <!-- add screenshot -->

   Puoi filtrare in base ai seguenti criteri:

   | Filtro | Descrizione |
   |---------|----------|
   | [!UICONTROL **Tipo di posizione**]<!--should this be changed to Account type?--> | Tipo di conto a cui è associata l&#39;ubicazione. Possono essere disponibili i seguenti tipi di account: <ul><li>[!UICONTROL **Area di destinazione dati AEP**]</li><li>[!UICONTROL **ARN per ruolo Amazon S3**]</li><li>[!UICONTROL **SAS di Azure**]</li><li>[!UICONTROL **RBAC di Azure**]</li><li>[!UICONTROL **Piattaforma cloud Google**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Account**] | Il nome dell’account a cui è associata la posizione. |
   | [!UICONTROL **Creato da**] | L’indirizzo e-mail dell’utente che ha creato la posizione. |

   {style="table-layout:auto"}

### Cerca posizioni

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la scheda [!UICONTROL **Percorsi**].

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare l&#39;opzione [!UICONTROL **Visualizza percorsi per tutti gli utenti**] per visualizzare i percorsi creati da tutti gli utenti dell&#39;organizzazione.

1. Nel campo di ricerca, iniziare a digitare le informazioni associate alla posizione che si sta cercando. Puoi cercare dati da qualsiasi colonna disponibile nella tabella.

## Modifica posizioni

Una posizione può essere modificata solo dall’utente che l’ha creata o da un amministratore di sistema.

Per modificare una posizione:

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la scheda [!UICONTROL **Percorsi**].

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare l&#39;opzione [!UICONTROL **Visualizza percorsi per tutti gli utenti**] per visualizzare i percorsi creati da tutti gli utenti dell&#39;organizzazione.

1. Seleziona la posizione da modificare.

   ![Finestra di esportazione che mostra la scheda Percorsi e l&#39;elenco dei percorsi.](assets/locations-edit.png)

1. Seleziona [!UICONTROL **Modifica**].

1. Apporta le modifiche desiderate, quindi seleziona [!UICONTROL **Salva**].

## Elimina posizioni

Se si elimina una posizione, vengono eliminate anche tutte le esportazioni che la utilizzano. Controlla la finestra di dialogo di conferma durante l’eliminazione per assicurarti che non siano associate alla posizione esportazioni.

Per eliminare una posizione:

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la scheda [!UICONTROL **Percorsi**].

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare l&#39;opzione [!UICONTROL **Visualizza percorsi per tutti gli utenti**] per visualizzare i percorsi creati da tutti gli utenti dell&#39;organizzazione.

1. Seleziona una o più posizioni da eliminare.

   ![Finestra Esporta che mostra la scheda Percorsi e l&#39;elenco dei percorsi](assets/locations-edit.png)

1. Seleziona [!UICONTROL **Elimina**].

   Viene visualizzata la finestra di dialogo Elimina posizione.

1. Nella finestra di dialogo Elimina posizione, accertati che la posizione non sia associata ad alcuna esportazione prima di confermare l’eliminazione.

   ![Finestra di conferma eliminazione percorso](assets/delete-location-confirmation-dialog.png)

1. Seleziona di nuovo [!UICONTROL **Elimina**] per confermare.

## Modifica account

Un account può essere modificato solo dall’utente che lo ha creato o da un amministratore di sistema.

Per modificare un account:

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Account località**].

   ![Finestra Esporta con la scheda Account località](assets/account-add.png)

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare l&#39;opzione [!UICONTROL **Visualizza account per tutti gli utenti**] per visualizzare i percorsi creati da tutti gli utenti dell&#39;organizzazione.

1. Selezionare [!UICONTROL **Visualizza dettagli**] sull&#39;account che si desidera modificare.

1. Apporta le modifiche desiderate, quindi seleziona [!UICONTROL **Salva**].

## Visualizza chiavi account

Dopo aver creato un account, puoi visualizzare tutte le chiavi di account associate per tale account. Potrebbe essere necessario visualizzare queste informazioni se non hai completato la configurazione dell&#39;account con il provider cloud [al momento della configurazione originale dell&#39;account](/help/components/exports/cloud-export-accounts.md).

Per visualizzare le chiavi associate a un account di esportazione:

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Account località**].

   ![Finestra Esporta con la scheda Account località](assets/account-add.png)

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare l&#39;opzione [!UICONTROL **Visualizza account per tutti gli utenti**] per visualizzare i percorsi creati da tutti gli utenti dell&#39;organizzazione.

1. Seleziona l&#39;icona a tre punti dell&#39;account da modificare, quindi seleziona [!UICONTROL **Chiavi account**].

## Elimina account

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Account località**].

   ![Finestra Esporta con la scheda Account località](assets/account-add.png)

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare l&#39;opzione [!UICONTROL **Visualizza account per tutti gli utenti**] per visualizzare i percorsi creati da tutti gli utenti dell&#39;organizzazione.

1. Seleziona l&#39;icona a tre punti dell&#39;account da modificare, quindi seleziona [!UICONTROL **Elimina account**].

1. Seleziona di nuovo [!UICONTROL **Elimina**] nella finestra di dialogo di conferma.

## Configurare le impostazioni a livello di società (solo amministratori)

Gli amministratori di sistema possono impedire agli utenti di creare account e posizioni, oppure limitare i tipi di account che gli utenti possono creare e utilizzare.

![Scheda Impostazioni amministratore](assets/locations-admin-settings.png)

### Stabilire se gli utenti possono creare e modificare gli account

Per impostazione predefinita, tutti gli utenti dell&#39;organizzazione possono creare account e modificarli nell&#39;ambiente di Customer Journey Analytics, come descritto in [configurazione degli account di esportazione cloud](/help/components/exports/cloud-export-accounts.md).

Puoi impedire agli utenti di creare account. In questo caso, gli utenti possono comunque utilizzare gli account già creati, ma non possono più modificarli. È possibile eliminare gli account creati dagli utenti, come descritto in [Eliminare un account](#delete-an-account).

Per impedire a tutti gli utenti di creare e modificare account:

1. In Customer Journey Analytics, selezionare **[!UICONTROL Components]** > **[!UICONTROL Exports]**, quindi selezionare la scheda [!UICONTROL **Impostazioni amministratore**].

1. Nella sezione [!UICONTROL **Account località**] deselezionare l&#39;opzione [!UICONTROL **Consenti agli utenti di creare e gestire account località**].

1. Seleziona [!UICONTROL **Salva**].

1. (Facoltativo) Eliminare tutti gli account creati dagli utenti che non si desidera più utilizzare, come descritto in [Eliminare un account](#delete-an-account).

### Stabilire se gli utenti possono creare e modificare le posizioni

Per impostazione predefinita, tutti gli utenti dell&#39;organizzazione possono creare percorsi e modificarli nell&#39;ambiente di Customer Journey Analytics, come descritto in [configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

Puoi impedire agli utenti di creare posizioni. In questo caso, gli utenti possono comunque utilizzare le posizioni già create, ma non possono più modificarle. È possibile eliminare i percorsi creati dagli utenti, come descritto in [Elimina percorsi](#delete-a-location).

Per impedire a tutti gli utenti di creare e modificare posizioni:

1. In Customer Journey Analytics, selezionare **[!UICONTROL Components]** > **[!UICONTROL Eports]**, quindi selezionare la scheda [!UICONTROL **Impostazioni amministratore**].

1. Nella sezione [!UICONTROL **Percorsi**], deseleziona l&#39;opzione [!UICONTROL **Consenti agli utenti di creare e gestire i percorsi**].

1. Seleziona [!UICONTROL **Salva**].

1. (Facoltativo) Eliminare i percorsi creati dagli utenti che non si desidera più utilizzare, come descritto in [Eliminare un percorso](#delete-a-location).

### Limitare i tipi di account che gli utenti possono creare e utilizzare

Puoi limitare i tipi di account visualizzati dagli utenti nelle seguenti circostanze:

* Durante la [creazione di nuovi account](/help/components/exports/cloud-export-accounts.md).
* Quando si sceglie quali account utilizzare per l&#39;esportazione di file mediante [esportazione di tabelle completa](/help/analysis-workspace/export/export-cloud.md).

Quando si limitano i tipi di account come descritto in questa sezione, tutti gli account del tipo limitato non sono più visibili agli utenti. Ciò significa che non è possibile creare nuovi account di quel tipo e non è possibile utilizzare account esistenti di quel tipo durante l&#39;esportazione di file mediante l&#39;esportazione di tabelle complete.

Tuttavia, gli account esistenti configurati per le esportazioni pianificate devono essere eliminati se si desidera impedirne l&#39;utilizzo.

#### Assicurati che gli account non vengano utilizzati per le esportazioni pianificate

Quando si limitano i tipi di conto, gli account esistenti vengono nascosti, non eliminati.

Se le pianificazioni sono già configurate per l&#39;invio di dati a un account del tipo limitato, le pianificazioni continueranno a essere eseguite anche dopo aver limitato il tipo di account e i dati continueranno a essere inviati all&#39;account. Ad esempio, se è pianificata un’esportazione di tabella completa per inviare dati a un tipo di account limitato, la pianificazione continuerà a essere eseguita.

Se devi assicurarti che gli account di un certo tipo non vengano utilizzati nelle esportazioni pianificate, puoi eliminarli prima di [limitare i tipi di account](#limit-the-account-types-that-are-available-to-users).

Per eliminare gli account:

1. Individuare i conti del tipo di conto che si prevede di limitare e che vengono utilizzati per le esportazioni programmate.

1. Eliminare gli account come descritto in [Eliminare un account](#delete-an-account).

1. Continua con la seguente sezione, [Limita i tipi di account disponibili per gli utenti](#limit-the-account-types-that-are-available-to-users).

#### Limita i tipi di account disponibili per gli utenti

Per limitare i tipi di account disponibili per gli utenti durante la creazione e l&#39;utilizzo degli account:

1. In Customer Journey Analytics, selezionare **[!UICONTROL Components]** > **[!UICONTROL Exports]**, quindi selezionare la scheda [!UICONTROL **Impostazioni amministratore**].

1. Individua la sezione [!UICONTROL **Tipi di account consentiti**].

   I seguenti tipi di account sono disponibili per impostazione predefinita per gli utenti. Deseleziona uno di questi tipi di account che desideri impedire agli utenti di utilizzare.

   * [!UICONTROL **Area di destinazione dati AEP**]

   * [!UICONTROL **ARN per ruolo Amazon S3**]

   * [!UICONTROL **Piattaforma cloud Google**]

   * [!UICONTROL **SAS di Azure**]

   * [!UICONTROL **RBAC di Azure**]

   * [!UICONTROL **Snowflake**]

1. Seleziona [!UICONTROL **Salva**].
