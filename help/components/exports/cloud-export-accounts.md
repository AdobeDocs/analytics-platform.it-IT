---
description: Configurare l’account di esportazione cloud a cui possono essere inviati i dati di Customer Journey Analytics
keywords: Analysis Workspace
title: Configurare account di esportazione cloud
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
role: User, Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1903'
ht-degree: 1%

---

# Configurare account di esportazione cloud

Prima di esportare i rapporti sul Customer Journey Analytics in una destinazione cloud come descritto in [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md), devi aggiungere e configurare la destinazione in cui desideri inviare i dati.

Questo processo consiste nell’aggiungere e configurare l’account (ad esempio Amazon S3, Google Cloud Platform e così via) come descritto in questo articolo, quindi aggiungere e configurare la posizione all’interno dell’account (ad esempio una cartella all’interno dell’account) come descritto in [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

Per informazioni su come gestire gli account esistenti, incluse la visualizzazione, la modifica e l&#39;eliminazione degli account, vedere [Gestire percorsi e account di esportazione cloud](/help/components/exports/manage-export-locations.md).

## Inizio creazione account esportazione cloud

1. Assicurati di soddisfare i requisiti [requisiti minimi](/help/analysis-workspace/export/export-cloud.md#minimum-requirements) per esportare report nel cloud.
1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].
1. Il giorno [!UICONTROL Exports] , seleziona la [!UICONTROL **Account ubicazione**] scheda.
1. Seleziona [!UICONTROL **Aggiungi account**].

   ![Esporta le opzioni di pagina che mostrano Aggiungi un altro account](assets/account-add.png)

   Viene visualizzata la finestra di dialogo Aggiungi account.

1. In [!UICONTROL **Nome account località**] , specificare un nome per il conto località. Questo nome viene visualizzato durante la creazione di una posizione.

1. In [!UICONTROL **Descrizione del conto di ubicazione**] fornire una breve descrizione del conto per distinguerlo da altri conti dello stesso tipo.

1. In [!UICONTROL **Tipo di account**] , seleziona il tipo di account cloud in cui stai effettuando l’esportazione. I tipi di account disponibili sono Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e AEP Data Landing Zone.

1. Continua con la sezione seguente che corrisponde a [!UICONTROL **Tipo di account**] hai selezionato.

   * [Area di destinazione dati AEP](#aep-data-landing-zone)

   * [ARN per ruolo Amazon S3](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### Area di destinazione dati AEP

>[!IMPORTANT]
>
>Quando esporti i rapporti sul Customer Journey Analytics nella Adobe Experience Platform Data Landing Zone, accertati di scaricare i dati entro 7 giorni, quindi eliminarli dalla AEP Data Landing Zone. Dopo 7 giorni, i dati vengono eliminati automaticamente dalla zona di destinazione dati di AEP.

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizio creazione account esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Seleziona [!UICONTROL **Salva**].

   Il [!UICONTROL **Account di esportazione creato**] viene visualizzata una finestra di dialogo.

   ![Finestra di dialogo Esporta account AEP Data Landing Zone](assets/export-account-aep.png)

1. Copia il contenuto del [!UICONTROL **URI SAS**] negli Appunti. Utilizzerai questo URI SAS per accedere ai dati esportati da Analysis Workspace dalla zona di destinazione dati di AEP.

   Se questo campo è vuoto, devi ottenere l’autorizzazione per accedere a Adobe Experience Platform.

1. In Adobe Experience Platform, configura il contenitore Data Landing Zone per utilizzare l’URI SAS copiato.

   >[!NOTE]
   >
   >Poiché l’account della zona di destinazione dati di AEP è basato su Azure, il modo più semplice per accedere ai rapporti esportati in AEP Data Landing Zone è utilizzare Azure Storage Explorer. I passaggi seguenti utilizzano questo metodo.

   1. Se non lo hai già fatto, scarica il [Esplora archivi di Microsoft Azure](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Nella documentazione di Adobe Experience Platform, segui i passaggi descritti in [Connettere il contenitore Data Landing Zone ad Azure Storage Explorer](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#connect-your-data-landing-zone-container-to-azure-storage-explorer).

      Puoi saltare le attività descritte nelle sezioni [Recuperare le credenziali per l’area di destinazione dati](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#retrieve-dlz-credentials) e [Aggiorna credenziali zona di destinazione dati](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#update-dlz-credentials), perché l&#39;URI copiato contiene queste credenziali.

   1. Quando segui la documentazione di Adobe Experience Platform e accedi al [!UICONTROL **URL SAS contenitore BLOB**] incolla l&#39;URI SAS copiato nel passaggio 3.

      >[!NOTE]
      >
      >È necessario eseguire questa azione ogni 7 giorni, perché l&#39;URI SAS scade 7 giorni dopo la creazione. Puoi creare uno script per automatizzare questo processo.


      ![Immettere la finestra Informazioni connessione che mostra il campo URL SAS](assets/blob-container-sas-uri.png)

   1. Seleziona [!UICONTROL **Successivo**] > [!UICONTROL **Connetti**].

1. Nel Customer Journey Analytics, nel [!UICONTROL **Account di esportazione creato**] finestra di dialogo, seleziona [!UICONTROL **OK**].

   ![Finestra di dialogo Esporta account AEP Data Landing Zone](assets/export-account-aep.png)

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### ARN per ruolo Amazon S3

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizio creazione account esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà account**] sezione del [!UICONTROL **Aggiungi account**] , specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ARN per ruolo**] | È necessario fornire un ARN per il ruolo (Amazon Resource Name) che l’Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, creare un criterio di autorizzazione IAM per l&#39;account di origine, associare il criterio a un utente e quindi creare un ruolo per l&#39;account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Il [!UICONTROL **Account di esportazione creato**] viene visualizzata una finestra di dialogo.

   ![Esporta account creato finestra di dialogo Amazon S3 Ruolo ARN](assets/export-account-amazons3.png)

1. Copia il contenuto del [!UICONTROL **ARN utente**] negli Appunti. L’ARN utente (Amazon Resource Name) è fornito da Adobe. È necessario collegare questo utente al criterio creato in ARN per il ruolo Amazon S3.

1. Seleziona [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizio creazione account esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà account**] sezione del [!UICONTROL **Aggiungi account**] , specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID Progetto**] | ID progetto Google Cloud copiato dall’account Google Cloud. Consulta la [Documentazione di Google Cloud sull’ottenimento di un ID progetto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Il [!UICONTROL **Account di esportazione creato**] viene visualizzata una finestra di dialogo.

   ![Finestra di dialogo di esportazione account creato](assets/export-account-gcp.png)

1. Copia il contenuto del [!UICONTROL **Entità**] negli Appunti, quindi assicurati di concedere all’Entità l’autorizzazione per caricare i file in questo bucket in Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this -->

1. Seleziona [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizio creazione account esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà account**] sezione del [!UICONTROL **Aggiungi account**] , specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI insieme di credenziali delle chiavi**] | <p>Percorso dell&#39;URI SAS nell&#39;insieme di credenziali delle chiavi di Azure.  Per configurare Azure SAS, è necessario memorizzare un URI SAS come segreto utilizzando Azure Key Vault. Per informazioni, vedere [Documentazione di Microsoft Azure su come impostare e recuperare un segreto dall&#39;insieme di credenziali delle chiavi di Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI dell’insieme di credenziali delle chiavi:<ul><li>Aggiungere un criterio di accesso nell&#39;insieme di credenziali delle chiavi per concedere l&#39;autorizzazione all&#39;applicazione Azure creata.</li><li>Assicurati che all’ID applicazione sia stato assegnato il `Key Vault Certificate User` ruolo predefinito per accedere all’URI dell’insieme di credenziali delle chiavi.</br><p>Per ulteriori informazioni, consulta [Ruoli incorporati di Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul><p>Per informazioni, vedere [Documentazione di Microsoft Azure su come assegnare un criterio di accesso all’insieme di credenziali delle chiavi](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nome segreto archivio chiavi**] | Nome segreto creato quando si aggiunge il segreto all&#39;insieme di credenziali delle chiavi di Azure. In Microsoft Azure, queste informazioni si trovano nell&#39;insieme di credenziali delle chiavi creato, nel **Key Vault** pagine delle impostazioni. Per informazioni, vedere [Documentazione di Microsoft Azure su come impostare e recuperare un segreto dall&#39;insieme di credenziali delle chiavi di Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Il [!UICONTROL **Account di esportazione creato**] viene visualizzata una finestra di dialogo.

   ![Finestra di dialogo di esportazione account creato](assets/export-account-azure.png)

1. Se non lo hai già fatto, assicurati di concedere le autorizzazioni per il bucket in Azure SAS. <!-- add link to Google Cloud docs on how to do this -->

1. Seleziona [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizio creazione account esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà account**] sezione del [!UICONTROL **Aggiungi account**] , specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Panoramica** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nel **Certificati e segreti** nell&#39;applicazione. Per ulteriori informazioni, vedere [Documentazione di Microsoft Azure su come registrare un’applicazione con la piattaforma Microsoft Identity](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Il [!UICONTROL **Account di esportazione creato**] viene visualizzata una finestra di dialogo.

   ![Finestra di dialogo di esportazione account creato](assets/export-account-azure.png)

1. Se non lo hai già fatto, assicurati di concedere le autorizzazioni per il bucket in Azure RBAC. <!-- add link to Google Cloud docs on how to do this -->

1. Seleziona [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizio creazione account esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà account**] sezione del [!UICONTROL **Aggiungi account**] , specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Identificatore account**] | Identifica in modo univoco un account di Snowflake all’interno dell’organizzazione e in tutta la rete globale di piattaforme cloud supportate dal Snowflake e aree geografiche cloud. <p>Devi ottenere l’identificatore dell’account di Snowflake, quindi incollare le informazioni qui.</p><p>Per informazioni su come ottenere queste informazioni, vedere [Pagina Identificatori account nella documentazione del Snowflake](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Utente**] | Nome di accesso dell&#39;utente che verrà utilizzato per la connessione. È consigliabile creare un nuovo utente da utilizzare specificamente, ad Adobe. Specificare qui il nome, quindi creare un utente in un Snowflake con lo stesso nome. È possibile creare un utente in un Snowflake utilizzando `CREATE USER` comando.  <p>Per ulteriori informazioni, vedere [Comandi utente, ruolo e privilegio](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **Ruolo**] | Ruolo che verrà assegnato all&#39;utente. È consigliabile creare un nuovo ruolo che verrà utilizzato specificamente, ad Adobe. Specifica qui il ruolo, quindi crea un ruolo nel Snowflake con lo stesso nome e concedi il ruolo all&#39;utente. È possibile creare un ruolo nel Snowflake utilizzando `CREATE ROLE` comando. <p>Per ulteriori informazioni, vedere [Comandi utente, ruolo e privilegio](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Il [!UICONTROL **Account di esportazione creato**] viene visualizzata una finestra di dialogo.

   ![Finestra di dialogo di esportazione account creato](assets/export-account-snowflake.png)

1. Copia il contenuto del [!UICONTROL **Chiave pubblica**] negli Appunti. La chiave pubblica è fornita da Adobe.

   Utilizza la chiave pubblica nel Snowflake per connetterti al tuo account di Snowflake. È necessario associare l&#39;utente creato a questa chiave pubblica.

   In Snowflake, ad esempio, specificare il comando seguente:

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   Per ulteriori informazioni, vedere [Pagina di autenticazione coppia di chiavi e rotazione della coppia di chiavi nella documentazione del Snowflake](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. Seleziona [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).
