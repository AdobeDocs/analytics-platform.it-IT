---
description: Gestisci il percorso di esportazione cloud in cui possono essere inviati i dati del Customer Journey Analytics
keywords: Analysis Workspace
title: Gestire percorsi e account di esportazione cloud
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 3%

---

# Gestire percorsi e account di esportazione cloud

Puoi visualizzare, modificare ed eliminare i percorsi di esportazione cloud.

Per informazioni su come creare una nuova posizione, consulta [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

## Filtrare e cercare i percorsi

Per trovare le informazioni necessarie, puoi filtrare l’elenco delle posizioni o cercare una posizione.

### Filtra l’elenco delle posizioni

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Posizioni**] scheda.

1. Seleziona la **Filtro** icona.

   <!-- add screenshot -->

   Puoi filtrare in base ai seguenti criteri:

   | Filtro | Descrizione |
   |---------|----------|
   | [!UICONTROL **Tipo di posizione**]<!--should this be changed to Account type?--> | Tipo di conto a cui è associata l&#39;ubicazione. Possono essere disponibili i seguenti tipi di account: <ul><li>[!UICONTROL **Area di destinazione dati AEP**]</li><li>[!UICONTROL **ARN per ruolo Amazon S3**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Account**] | Il nome dell’account a cui è associata la posizione. |
   | [!UICONTROL **Creato da**] | L’indirizzo e-mail dell’utente che ha creato la posizione. |

   {style="table-layout:auto"}

### Cerca posizioni

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Posizioni**] scheda.

1. Nel campo di ricerca, iniziare a digitare le informazioni associate alla posizione che si sta cercando. Puoi cercare dati da qualsiasi colonna disponibile nella tabella.

## Modifica posizioni

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Posizioni**] , quindi selezionare la posizione da modificare.

   ![Finestra Esporta che mostra la scheda Ubicazioni e l&#39;elenco delle ubicazioni.](assets/locations-edit.png)

1. Seleziona [!UICONTROL **Modifica**].

1. Apporta le modifiche desiderate, quindi seleziona [!UICONTROL **Salva**].

## Elimina posizioni

Se si elimina una posizione, vengono eliminate anche tutte le esportazioni che la utilizzano. Controlla la finestra di dialogo di conferma durante l’eliminazione per assicurarti che non siano associate alla posizione esportazioni.

Per eliminare una posizione:

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Posizioni**] , quindi selezionare una o più posizioni da eliminare.

   ![Finestra Esporta con la scheda Ubicazioni e l&#39;elenco delle ubicazioni](assets/locations-edit.png)

1. Seleziona [!UICONTROL **Elimina**].

   Viene visualizzata la finestra di dialogo Elimina posizione.

1. Nella finestra di dialogo Elimina posizione, accertati che la posizione non sia associata ad alcuna esportazione prima di confermare l’eliminazione.

   ![Finestra di conferma Elimina posizione](assets/delete-location-confirmation-dialog.png)

1. Seleziona [!UICONTROL **Elimina**] di nuovo per confermare.

## Modifica account

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Account ubicazione**] scheda.

   ![Finestra Esportazioni con la scheda Account ubicazione](assets/account-add.png)

1. Seleziona [!UICONTROL **Visualizza dettagli**] sull&#39;account che si desidera modificare.

1. Apporta le modifiche desiderate, quindi seleziona [!UICONTROL **Salva**].

## Visualizza chiavi account

Dopo aver creato un account, puoi visualizzare tutte le chiavi di account associate per tale account. Potrebbe essere necessario visualizzare queste informazioni se non hai completato la configurazione dell’account con il provider cloud [quando hai configurato originariamente l’account](/help/components/exports/cloud-export-accounts.md).

Per visualizzare le chiavi associate a un account di esportazione:

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Account ubicazione**] scheda.

   ![Finestra Esportazioni con la scheda Account ubicazione](assets/account-add.png)

1. Seleziona l’icona a tre punti sull’account da modificare, quindi seleziona [!UICONTROL **Chiavi account**].

## Elimina account

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Account ubicazione**] scheda.

   ![Finestra Esportazioni con la scheda Account ubicazione](assets/account-add.png)

1. Seleziona l’icona a tre punti sull’account da modificare, quindi seleziona [!UICONTROL **Elimina account**].

1. Seleziona [!UICONTROL **Elimina**] nella finestra di dialogo di conferma.
