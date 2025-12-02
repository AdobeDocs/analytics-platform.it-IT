---
description: Configurare l’account di esportazione cloud a cui possono essere inviati i dati di Customer Journey Analytics
keywords: Analysis Workspace
title: Configurare account di esportazione cloud
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
role: User, Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '2246'
ht-degree: 28%

---

# Configurare account di esportazione cloud

Prima di poter esportare i report di Customer Journey Analytics in una destinazione cloud (da Analysis Workspace, come descritto in [Esportare i report di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md) o da Report Builder, come descritto in [Esportare i report da Report Builder](/help/report-builder/report-builder-export.md)), devi aggiungere e configurare la destinazione in cui desideri inviare i dati.

Questo processo consiste nell&#39;aggiungere e configurare l&#39;account (ad esempio Amazon S3, Google Cloud Platform e così via) come descritto in questo articolo, quindi aggiungere e configurare il percorso all&#39;interno dell&#39;account (ad esempio una cartella all&#39;interno dell&#39;account) come descritto in [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

Per informazioni su come gestire gli account esistenti, tra cui la visualizzazione, la modifica e l&#39;eliminazione degli account, vedere [Gestire i percorsi e gli account di esportazione cloud](/help/components/exports/manage-export-locations.md).

## Inizio creazione account esportazione cloud

1. Assicurati di soddisfare i [requisiti minimi](/help/analysis-workspace/export/export-cloud.md#minimum-requirements) per l&#39;esportazione di report nel cloud.
1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].
1. Nella pagina [!UICONTROL Esportazioni] selezionare la scheda [!UICONTROL **Account località**].

   ![Esporta le opzioni di pagina che mostrano Aggiungi un altro account](assets/account-add.png)

1. Seleziona [!UICONTROL **Aggiungi account**].

   Viene visualizzata la finestra di dialogo Aggiungi account.

1. Nel campo [!UICONTROL **Nome account località**], specificare un nome per l&#39;account località. Questo nome viene visualizzato durante la creazione di una posizione.

1. Nel campo [!UICONTROL **Descrizione account località**], fornisci una breve descrizione dell&#39;account per distinguerlo da altri account dello stesso tipo.

1. Abilita l&#39;opzione [!UICONTROL **Rendi l&#39;account disponibile a tutti gli utenti dell&#39;organizzazione**] se desideri consentire ad altri utenti dell&#39;organizzazione di utilizzare l&#39;account.

   Quando condividi gli account, tieni presente quanto segue:

   * Gli account condivisi non possono essere non condivisi.

   * Gli account condivisi possono essere modificati solo dal proprietario dell&#39;account.

   * Chiunque può creare una posizione per l&#39;account condiviso.

1. Nel campo [!UICONTROL **Tipo di account**], seleziona il tipo di account cloud in cui stai effettuando l&#39;esportazione. I tipi di account disponibili sono Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake e AEP Data Landing Zone.

1. Continua con la sezione seguente che corrisponde al [!UICONTROL **tipo di account**] selezionato.

   * [Zona di destinazione dei dati di AEP](#aep-data-landing-zone)

   * [Amazon S3 con ruolo ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### Zona di destinazione dei dati di AEP

>[!IMPORTANT]
>
>Quando utilizzi AEP Data Landing Zone per il tuo account di esportazione, tieni presente quanto segue:
>
> * Quando esporti i rapporti di Customer Journey Analytics nella Adobe Experience Platform Data Landing Zone, accertati di scaricare i dati entro 7 giorni, quindi eliminarli dalla AEP Data Landing Zone. Dopo 7 giorni, i dati vengono eliminati automaticamente dalla Data Landing Zone di AEP.
> * La Data Landing Zone di AEP utilizza l’archiviazione Azure o AWS. Se l’organizzazione utilizza una società di accesso configurata per utilizzare Azure, la zona di destinazione dati di AEP utilizza Azure. Se la società di accesso è configurata per l’utilizzo di AWS, AEP Data Landing Zone utilizza AWS.
>

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un account di esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esporta tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Dopo aver selezionato **[!UICONTROL Area di destinazione dati di AEP]** nel campo **[!UICONTROL Tipo account]**, seleziona [!UICONTROL **Salva**].

   Viene visualizzata una delle seguenti finestre di dialogo, a seconda che l’area di destinazione dati di AEP sia configurata per l’utilizzo dell’archiviazione di Azure o AWS:

   * **Archiviazione Azure:**

     Viene visualizzata la finestra di dialogo [!UICONTROL **Account di esportazione creato**].

     ![Finestra di dialogo Esporta account Area di destinazione dati di AEP](assets/export-account-aep.png)

   * **Archiviazione AWS:**

     >[!AVAILABILITY]
     >
     >Questa sezione viene applicata alle implementazioni di Experience Platform in esecuzione su Amazon Web Services (AWS). Experience Platform in esecuzione su AWS è attualmente disponibile per un numero limitato di clienti. Per ulteriori informazioni sull’infrastruttura Experience Platform supportata, consulta la [Panoramica multi-cloud di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/landing/multi-cloud).

     Viene visualizzata la finestra di dialogo [!UICONTROL **Account creato**].

     ![Finestra di dialogo Esporta account Area di destinazione dati di AEP](assets/export-account-aep-aws.png)

1. (Condizionale) Se utilizzi l’archiviazione Azure:

   1. Copia il contenuto del campo [!UICONTROL **URI SAS**] negli Appunti. Utilizzerai questo URI SAS per accedere ai dati esportati da Analysis Workspace dall’area di destinazione dati di AEP.

      Se questo campo è vuoto, devi ottenere l’autorizzazione per accedere a Adobe Experience Platform.

   1. In Adobe Experience Platform, configura il contenitore Data Landing Zone per utilizzare l’URI SAS copiato.

      >[!NOTE]
      >
      >Quando utilizzi un account AEP Data Landing Zone basato su Azure, il modo più semplice per accedere ai rapporti esportati in AEP Data Landing Zone è utilizzare Azure Storage Explorer. I passaggi seguenti utilizzano questo metodo.

      1. Se non lo hai già fatto, scarica [Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

      1. Nella documentazione di Adobe Experience Platform, segui i passaggi descritti in [Connettere il contenitore Data Landing Zone ad Azure Storage Explorer](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#connect-your-data-landing-zone-container-to-azure-storage-explorer).

         È possibile saltare le attività descritte nelle sezioni [Recuperare le credenziali per l&#39;area di destinazione dati](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#retrieve-dlz-credentials) e [Aggiornare le credenziali dell&#39;area di destinazione dati](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#update-dlz-credentials), perché l&#39;URI copiato contiene queste credenziali.

      1. Quando segui la documentazione di Adobe Experience Platform e accedi al campo [!UICONTROL **URL SAS contenitore Blob**], incolla l&#39;URI SAS copiato nel passaggio 3.

         >[!NOTE]
         >
         >È necessario eseguire questa azione ogni 7 giorni, perché l&#39;URI SAS scade 7 giorni dopo la creazione. Puoi creare uno script per automatizzare questo processo.

         ![Immettere la finestra Informazioni connessione che mostra il campo URL SAS](assets/blob-container-sas-uri.png)

   1. Seleziona [!UICONTROL **Avanti**] > [!UICONTROL **Connetti**].

   1. In Customer Journey Analytics, nella finestra di dialogo [!UICONTROL **Esporta account creato**], selezionare [!UICONTROL **OK**].

      ![Finestra di dialogo Esporta account Area di destinazione dati di AEP](assets/export-account-aep.png)

1. (Condizionale) Se utilizzi l’archiviazione AWS:

   1. Copia negli Appunti il contenuto dei campi seguenti (utilizzerai queste informazioni per accedere ai dati esportati da Analysis Workspace dalla Data Landing Zone di AEP):

      * [!UICONTROL **ID chiave di accesso**]

      * **[!UICONTROL Chiave di accesso segreta]**

      * **[!UICONTROL Token sessione]**

      * **[!UICONTROL Nome del bucket]**

      * **[!UICONTROL Cartella DLZ]**

      ![Finestra di dialogo Esporta account Area di destinazione dati di AEP](assets/export-account-aep-aws.png)

   1. Selezionare [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Amazon S3 con ruolo ARN

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un account di esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esporta tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Nella sezione [!UICONTROL **Proprietà account**] della finestra di dialogo [!UICONTROL **Aggiungi account**], specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Ruolo ARN**] | È necessario fornire un ruolo ARN (nome risorsa Amazon - Amazon Resource Name) che Adobe può utilizzare per accedere all’account Amazon S3. A tale scopo, crea un criterio di autorizzazione IAM per l’account di origine, associa il criterio a un utente e quindi crea un ruolo per l’account di destinazione. Per informazioni specifiche, consulta [questa documentazione di AWS](https://repost.aws/it/knowledge-center/cross-account-access-iam). |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Account di esportazione creato**].

   ![Esporta account creato finestra di dialogo Ruolo Amazon S3 ARN](assets/export-account-amazons3.png)

1. Copia il contenuto del campo [!UICONTROL **ARN**] utente negli Appunti. L’utente ARN (nome risorsa Amazon) è fornito da Adobe. È necessario collegare questo utente al criterio creato in ARN per il ruolo Amazon S3.

1. Selezionare [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un account di esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esporta tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Nella sezione [!UICONTROL **Proprietà account**] della finestra di dialogo [!UICONTROL **Aggiungi account**], specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID Progetto**] | ID progetto Google Cloud copiato dall’account Google Cloud. Consulta la [Documentazione di Google Cloud su come ottenere un ID progetto](https://cloud.google.com/resource-manager/docs/creating-managing-projects?hl=it#identifying_projects). |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Account di esportazione creato**].

   ![Finestra di dialogo di esportazione account creata](assets/export-account-gcp.png)

1. Copia il contenuto del campo [!UICONTROL **Principal**] negli Appunti, quindi accertati di concedere all&#39;entità l&#39;autorizzazione per caricare i file in questo bucket in Google Cloud Platform. <!-- add link to Google Cloud docs on how to do this -->

1. Selezionare [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un account di esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esporta tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Nella sezione [!UICONTROL **Proprietà account**] della finestra di dialogo [!UICONTROL **Aggiungi account**], specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **URI di Key Vault**] | <p>Percorso per l’URI SAS in Azure Key Vault.  Per configurare Azure SAS, è necessario memorizzare un URI SAS come segreto utilizzando Azure Key Vault. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto da Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Dopo la creazione dell’URI di Key Vault:<ul><li>Aggiungi un criterio di accesso a Key Vault per concedere l’autorizzazione all’applicazione Azure creata.<p><p>Per informazioni, consulta [Documentazione di Microsoft Azure su come assegnare un criterio di accesso a Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p>Oppure</p><p>Se si desidera concedere direttamente un ruolo di accesso senza creare un criterio di accesso, vedere la [documentazione di Microsoft Azure relativa all&#39;assegnazione dei ruoli di Azure tramite il portale di Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Questo aggiunge l’assegnazione del ruolo per l’ID applicazione per accedere all’URI dell’insieme di credenziali delle chiavi. </p></li><li>Assicurati che all’ID applicazione sia stato assegnato il ruolo incorporato di `Key Vault Certificate User` per accedere all’URI di Key Vault</br><p>Per ulteriori informazioni, consulta [Ruoli incorporati di Azure](https://learn.microsoft.com/it-it/azure/role-based-access-control/built-in-roles).</p></li></ul> |
   | [!UICONTROL **Nome segreto di Key Vault**] | Nome segreto creato quando si aggiunge il segreto ad Azure Key Vault. In Microsoft Azure, queste informazioni si trovano nel Key Vault creato, nelle pagine delle impostazioni di **Key Vault**. Per informazioni, consulta [Documentazione di Microsoft Azure su come impostare e recuperare un segreto Azure Key Vault](https://learn.microsoft.com/it-it/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, vedere la [documentazione di Microsoft Azure relativa alla registrazione di un&#39;applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Account di esportazione creato**].

   ![Finestra di dialogo di esportazione account creata](assets/export-account-azure.png)

1. Se non lo hai già fatto, assicurati di concedere le autorizzazioni per il bucket in Azure SAS. <!-- add link to Google Cloud docs on how to do this -->

1. Selezionare [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un account di esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esporta tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Nella sezione [!UICONTROL **Proprietà account**] della finestra di dialogo [!UICONTROL **Aggiungi account**], specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID applicazione**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **ID tenant**] | Copia questo ID dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Panoramica** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |
   | [!UICONTROL **Segreto account località**] | Copia il segreto dall’applicazione Azure creata. In Microsoft Azure, queste informazioni si trovano nella scheda **Certificati e segreti** all’interno dell’applicazione. Per ulteriori informazioni, consulta la [Documentazione di Microsoft Azure su come registrare un’applicazione con Microsoft Identity Platform](https://learn.microsoft.com/it-it/entra/identity-platform/quickstart-register-app). |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Account di esportazione creato**].

   ![Finestra di dialogo di esportazione account creata](assets/export-account-azure.png)

1. Se non lo hai già fatto, assicurati di concedere le autorizzazioni per il bucket in Azure RBAC. <!-- add link to Google Cloud docs on how to do this -->

1. Selezionare [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. Inizia a creare un account di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un account di esportazione cloud](#begin-creating-a-cloud-export-account)

   * Quando [esporta tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. Nella sezione [!UICONTROL **Proprietà account**] della finestra di dialogo [!UICONTROL **Aggiungi account**], specificare le informazioni seguenti:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Identificatore account**] | Identifica in modo univoco un account Snowflake all’interno della tua organizzazione e in tutta la rete globale di piattaforme cloud supportate da Snowflake e aree geografiche del cloud. <p>Devi ottenere l’identificatore dell’account dal tuo account Snowflake, quindi incollare le informazioni qui.</p><p>Per sapere dove ottenere queste informazioni, consulta la pagina [Identificatori account nella documentazione di Snowflake](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Utente**] | Nome di accesso dell&#39;utente che verrà utilizzato per la connessione. Si consiglia di creare un nuovo utente che verrà utilizzato specificamente per Adobe. Specifica qui il nome, quindi crea un utente in Snowflake con lo stesso nome. È possibile creare un utente in Snowflake utilizzando il comando `CREATE USER`.  <p>Per ulteriori informazioni, vedere [Comandi utente, ruolo e privilegio](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **Ruolo**] | Ruolo che verrà assegnato all&#39;utente. È consigliabile creare un nuovo ruolo da utilizzare in modo specifico per Adobe. Specifica qui il ruolo, quindi crea un ruolo in Snowflake con lo stesso nome e concedi il ruolo all’utente. È possibile creare un ruolo in Snowflake utilizzando il comando `CREATE ROLE`. <p>Per ulteriori informazioni, vedere [Comandi utente, ruolo e privilegio](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Account di esportazione creato**].

   ![Finestra di dialogo di esportazione account creata](assets/export-account-snowflake.png)

1. Copia il contenuto del campo [!UICONTROL **Chiave pubblica**] negli Appunti. La chiave pubblica è fornita da Adobe.

   Utilizza la chiave pubblica in Snowflake per connetterti al tuo account Snowflake. È necessario associare l&#39;utente creato a questa chiave pubblica.

   In Snowflake, ad esempio, specificare il comando seguente:

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   Per ulteriori informazioni, vedere la pagina [Autenticazione coppia di chiavi e rotazione coppia di chiavi nella documentazione di Snowflake](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. Selezionare [!UICONTROL **OK**].

1. Continua con [Configurare i percorsi di esportazione cloud](/help/components/exports/cloud-export-locations.md).
