---
description: Configura il percorso di esportazione cloud in cui possono essere inviati i dati del Customer Journey Analytics
keywords: Analysis Workspace
title: Configurare i percorsi di esportazione cloud
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 1bf36f60b0b3aec04bb1452e5f63f97051d9bb50
workflow-type: tm+mt
source-wordcount: '1928'
ht-degree: 19%

---

# Configurare i percorsi di esportazione cloud

Prima di esportare i rapporti sul Customer Journey Analytics in una destinazione cloud come descritto in [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md), devi aggiungere e configurare il percorso in cui desideri inviare i dati.

Questo processo consiste nell’aggiungere e configurare l’account (ad esempio Amazon S3, Google Cloud Platform e così via) come descritto in [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md), quindi aggiungendo e configurando il percorso all’interno dell’account (ad esempio una cartella all’interno dell’account) come descritto in questo articolo.

Per informazioni su come gestire le posizioni esistenti, incluse la visualizzazione, la modifica e l’eliminazione, consulta [Gestire percorsi e account di esportazione cloud](/help/components/exports/manage-export-locations.md).

## Inizia a creare un percorso di esportazione cloud

1. È necessario aggiungere un account prima di poter aggiungere una posizione. Se non lo hai già fatto, aggiungi un account come descritto in [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md).

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Posizioni**] , quindi seleziona [!UICONTROL **Aggiungi posizione**].

   ![Finestra Esporta con la scheda Posizione selezionata che evidenzia il pulsante Aggiungi posizione](assets/location-add.png)

   Oppure

   Seleziona la [!UICONTROL **Account ubicazione**] , seleziona l’icona a 3 punti di un account esistente in cui desideri aggiungere una posizione, quindi seleziona [!UICONTROL **Aggiungi posizione**].

   ![Account GCP e menu a discesa con i puntini di sospensione visualizzati come Aggiungi posizione selezionata](assets/add-location-existing-account.png)

   Viene visualizzata la finestra di dialogo Posizione.

1. Specifica le seguenti informazioni: |Campo | Funzione | ---------- --------- | [!UICONTROL **Nome**] | Nome della posizione.  | | [!UICONTROL **Descrizione**] | Fornisci una breve descrizione della posizione per distinguerla dalle altre posizioni sull’account. | | [!UICONTROL **Rendi la posizione disponibile a tutti gli utenti dell’organizzazione**] | **Nota:** Questa funzionalità si trova nella fase di test limitato del rilascio e potrebbe non essere ancora disponibile nell’ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Customer Journey Analytics](/help/release-notes/releases.md). <p>Abilita questa opzione per consentire ad altri utenti dell’organizzazione di utilizzare la posizione.</p> <p>Quando condividi le posizioni, tieni presente quanto segue:</p><ul><li>Le posizioni condivise non possono essere annullate.</li><li>Le posizioni condivise possono essere modificate solo dal proprietario della posizione.</li><li>Le posizioni possono essere condivise solo se è condiviso anche l’account a cui è associata la posizione.</li></ul> | | [!UICONTROL **Account località**] | Selezionare l&#39;account in cui si desidera creare la posizione. Per informazioni su come creare un account, consulta [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md). |

1. Nella sezione [!UICONTROL **Proprietà posizione**], specifica le informazioni specifiche sul tipo di account dell’account di posizione.

   Continua con la sezione seguente che corrisponde al tipo di account selezionato in [!UICONTROL **Account località**] campo.

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

1. Inizia a creare un percorso di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un percorso di esportazione cloud](#begin-creating-a-cloud-export-location)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà posizione**] sezione del [!UICONTROL **Aggiungi posizione**] specifica le seguenti informazioni per configurare una posizione di zona di destinazione dati di Adobe Experience Platform:

   <!-- still need to update; can't create AEP account -->

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra dopo il nome per creare la cartella. Ad esempio: `folder_name/` |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

1. Ora puoi esportare dati da Analysis Workspace all’account e alla posizione configurati. Per informazioni su come esportare i dati nel cloud, consulta [Esportare i dati del progetto nel cloud](/help/analysis-workspace/export/export-cloud.md).

1. Il modo più semplice per accedere ai dati nell’area di destinazione dati di AEP è utilizzare Microsoft Azure Storage Explorer. Questo è lo stesso strumento utilizzato nelle istruzioni per configurare [Account zona di destinazione dati AEP](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. Apri [Esplora archivi di Microsoft Azure](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. Vai a [!UICONTROL **Account di archiviazione**] > [!UICONTROL **(Contenitori allegati)**] > [!UICONTROL **Contenitori BLOB**] > **[!UICONTROL cjaexport-_numero_]** > ***nome_contenitore***.

      >[!NOTE]
      >
      >Nome della cartella **[!UICONTROL cjaexport-_numero_]** è il nome predefinito fornito da Azure Storage Explorer. Se all&#39;URI SAS è associata una sola connessione (operazione normale), il nome della cartella sarà **[!UICONTROL cjaexport-1]**.


      ![Accedere ai file in Azure Storage Explorer](assets/azure-storage-explorer-access.png)

   1. Seleziona l’esportazione da scaricare, quindi seleziona [!UICONTROL **Scarica**] per il download.

### ARN per ruolo Amazon S3

1. Inizia a creare un percorso di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un percorso di esportazione cloud](#begin-creating-a-cloud-export-location)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà posizione**] sezione del [!UICONTROL **Aggiungi posizione**] specifica le seguenti informazioni per configurare una posizione ARN per il ruolo Amazon S3:

   <!-- still need to update; can't create S3 role ARN account -->

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Customer Journey Analytics. <p>Assicurati che l&#39;ARN utente fornito da Adobe disponga del `S3:PutObject` per caricare i file in questo bucket. </p><p>I nomi dei bucket devono soddisfare regole di denominazione specifiche. Ad esempio, devono contenere da 3 a 63 caratteri, possono essere composte solo da lettere minuscole, numeri, punti (.) e trattini (-) e devono iniziare e terminare con una lettera o un numero. [Un elenco completo delle regole di denominazione è disponibile nella documentazione di AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html?lang=it). </p> |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra dopo il nome per creare la cartella. Ad esempio, folder_name/ |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

1. Ora puoi esportare dati da Analysis Workspace all’account e alla posizione configurati. Per informazioni su come esportare i dati nel cloud, consulta [Esportare i dati del progetto nel cloud](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. Inizia a creare un percorso di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un percorso di esportazione cloud](#begin-creating-a-cloud-export-location)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà posizione**] sezione del [!UICONTROL **Aggiungi posizione**] , specificare le informazioni seguenti per configurare una posizione della piattaforma Google Cloud:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Customer Journey Analytics. <p>Assicurati di aver concesso il `roles/storage.objectCreator` autorizzazione per l’entità fornita dall’Adobe. (L’entità viene fornita quando [configurazione dell’account di Google Cloud Platform](/help/components/exports/cloud-export-accounts.md).) <p>Per informazioni sulla concessione delle autorizzazioni, consulta [Aggiungere un’entità principale a un criterio a livello di bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions?hl=it#bucket-add) nella documentazione di Google Cloud.</p><p>Se l’organizzazione utilizza [Vincoli dei criteri dell&#39;organizzazione](https://cloud.google.com/storage/docs/org-policy-constraints?hl=it) per accettare solo l’account Google Cloud Platform nel tuo elenco consentiti, è necessario il seguente ID organizzazione di Google Cloud Platform di proprietà di Adobe: <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra dopo il nome per creare la cartella. Ad esempio, folder_name/ |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

1. Ora puoi esportare dati da Analysis Workspace all’account e alla posizione configurati. Per informazioni su come esportare i dati nel cloud, consulta [Esportare i dati del progetto nel cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. Inizia a creare un percorso di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un percorso di esportazione cloud](#begin-creating-a-cloud-export-location)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà posizione**] sezione del [!UICONTROL **Aggiungi posizione**] , specificare le informazioni seguenti per configurare un percorso SAS di Azure:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome contenitore**] | Contenitore all’interno dell’account specificato in cui desideri inviare i dati di Customer Journey Analytics. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra dopo il nome per creare la cartella. Ad esempio: `folder_name/`<p>Accertati che che l’archivio dei token SAS specificato nel campo Nome segreto di Key Vault durante la configurazione dell’account SAS di Azure abbia l’autorizzazione `Write`. Questo consente al token SAS di creare file nel contenitore Azure. <p>Se desideri che il token SAS sovrascriva anche i file, assicurati che l’archivio dei token SAS disponga dell’autorizzazione `Delete`.</p><p>Per ulteriori informazioni, consulta [Risorse di archiviazione BLOB](https://learn.microsoft.com/it-it/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) nella documentazione dell’archiviazione BLOB di Azure.</p> |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

1. Ora puoi esportare dati da Analysis Workspace all’account e alla posizione configurati. Per informazioni su come esportare i dati nel cloud, consulta [Esportare i dati del progetto nel cloud](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. Inizia a creare un percorso di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un percorso di esportazione cloud](#begin-creating-a-cloud-export-location)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà posizione**] sezione del [!UICONTROL **Aggiungi posizione**] , specificare le informazioni seguenti per configurare un percorso RBAC di Azure:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Contenitore**] | Contenitore all’interno dell’account specificato in cui desideri inviare i dati di Customer Journey Analytics. Assicurati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra dopo il nome per creare la cartella. Ad esempio: `folder_name/`<p>Accertati che l’ID applicazione specificato durante la configurazione dell’account RBAC di Azure disponga del ruolo `Storage Blob Data Contributor` per accedere al contenitore (cartella).</p> <p>Per ulteriori informazioni, consulta [Ruoli incorporati di Azure](https://learn.microsoft.com/it-it/azure/role-based-access-control/built-in-roles).</p> |
   | [!UICONTROL **Account**] | Account di archiviazione Azure. |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

1. Ora puoi esportare dati da Analysis Workspace all’account e alla posizione configurati. Per informazioni su come esportare i dati nel cloud, consulta [Esportare i dati del progetto nel cloud](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. Inizia a creare un percorso di esportazione cloud in uno dei seguenti modi:

   * Dalla pagina Esportazioni come descritto in precedenza, in [Inizia a creare un percorso di esportazione cloud](#begin-creating-a-cloud-export-location)

   * Quando [esportazione di tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. In [!UICONTROL **Proprietà posizione**] sezione del [!UICONTROL **Aggiungi posizione**] , specificare le informazioni seguenti per configurare una posizione di Snowflake:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **DB**] | Il database specificato deve essere esistente. Il ruolo creato deve disporre dei privilegi necessari per accedere al database.<p>Database associato al nome dell&#39;area di visualizzazione.</p><p>È possibile concedere i privilegi di questo ruolo al database nel Snowflake utilizzando il comando seguente: `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>Per ulteriori informazioni, vedere [Database, schema e comandi di condivisione nella documentazione del Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Schema**] | Lo schema specificato deve essere uno schema esistente. Il ruolo creato deve disporre dei privilegi necessari per accedere a questo schema.<p>Schema associato al nome dell&#39;area di visualizzazione.<p>È possibile concedere i privilegi per il ruolo creato allo schema nel Snowflake utilizzando il comando seguente: `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>Per ulteriori informazioni, vedere [Database, schema e comandi di condivisione nella documentazione del Snowflake](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **Nome fase**] | Il nome della fase interna in cui i file di dati vengono memorizzati nel Snowflake.<p>Verificare che il ruolo specificato nell&#39;account disponga dell&#39;accesso in lettura e scrittura al nome della fase. Poiché si concede l&#39;accesso in lettura e scrittura, si consiglia di utilizzare una fase utilizzata solo da Adobe.<p>È possibile concedere l&#39;accesso in lettura e scrittura al nome dell&#39;area di visualizzazione nel Snowflake utilizzando il comando seguente: `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>Per informazioni sulla concessione di privilegi a un ruolo, vedere [Concedere i privilegi nella documentazione del Snowflake](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>Per ulteriori informazioni sul nome della fase, vedere [Scelta di una pagina Stage interno per file locali nella documentazione del Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Percorso stage**] | Percorso del percorso in cui sono memorizzati i file di dati nel Snowflake. <p>Per ulteriori informazioni, vedere [Scelta di una pagina Stage interno per file locali nella documentazione del Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Salva**].

1. Ora puoi esportare dati da Analysis Workspace all’account e alla posizione configurati. Per informazioni su come esportare i dati nel cloud, consulta [Esportare i dati del progetto nel cloud](/help/analysis-workspace/export/export-cloud.md).
