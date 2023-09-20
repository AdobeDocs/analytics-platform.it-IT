---
description: Configura il percorso di esportazione cloud in cui possono essere inviati i dati del Customer Journey Analytics
keywords: Analysis Workspace
title: Configurare i percorsi di esportazione cloud
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 4%

---

# Configurare i percorsi di esportazione cloud

{{select-package}}

Prima di esportare i dati di Customer Journey Analytics in una destinazione cloud come descritto in [Esporta dati di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md), devi aggiungere e configurare il percorso in cui desideri inviare i dati.

Questo processo consiste nell’aggiungere e configurare l’account (ad esempio Amazon S3, Google Cloud Platform e così via) come descritto in [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md), quindi aggiungendo e configurando il percorso all’interno dell’account (ad esempio una cartella all’interno dell’account) come descritto in questo articolo.

Per informazioni su come gestire le posizioni esistenti, incluse la visualizzazione, la modifica e l’eliminazione, consulta [Gestire percorsi e account di esportazione cloud](/help/components/exports/manage-export-locations.md).

Per configurare un percorso di esportazione cloud:

1. È necessario aggiungere un account prima di poter aggiungere una posizione. Se non lo hai già fatto, aggiungi un account come descritto in [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md).
1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].
1. Il giorno [!UICONTROL Exports] , seleziona la [!UICONTROL **Posizioni**] scheda.
1. Seleziona [!UICONTROL **Aggiungi posizione**].

   ![pulsante aggiungi posizione](assets/location-add.png)

   Viene visualizzata la finestra di dialogo Posizione.

1. Specifica le seguenti informazioni: |Campo | Funzione | ---------- --------- | [!UICONTROL **Nome**] | Nome della posizione.  | | [!UICONTROL **Descrizione**] | Fornisci una breve descrizione del conto per distinguerlo da altri conti dello stesso tipo. | | [!UICONTROL **Account località**] | Seleziona l&#39;account località creato in [Configurare account di esportazione cloud](/help/components/exports/cloud-export-accounts.md). |

1. In [!UICONTROL **Proprietà posizione**] , specificare informazioni specifiche sul tipo di account dell&#39;account di posizione.

   Per le istruzioni di configurazione, espandi la sezione seguente che corrisponde al tipo di account selezionato in [!UICONTROL **Account ubicazione**] campo.

   +++ARN per ruolo Amazon S3

   Specifica le seguenti informazioni per configurare una posizione ARN per il ruolo Amazon S3:

   <!-- still need to update; can't create S3 role ARN account -->

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account Amazon S3 in cui desideri inviare i dati di Adobe Analytics. Assicurati che l’ARN utente fornito da Adobe abbia accesso al caricamento di file in questo bucket. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, nome_cartella/ |

   {style="table-layout:auto"}

+++

   +++Piattaforma Google Cloud

   Per configurare il percorso di una piattaforma Google Cloud, specifica le seguenti informazioni:

   <!-- still need to update; can't create GCP account -->

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Bucket**] | Il bucket all’interno dell’account GCP in cui desideri inviare i dati di Customer Journey Analytics. Assicurati di aver concesso all’entità fornita da Adobe l’autorizzazione per caricare i file in questo bucket. (L’entità viene fornita quando [configurazione dell’account di Google Cloud Platform](/help/components/exports/cloud-export-accounts.md).) Per informazioni sulla concessione delle autorizzazioni, consulta [Aggiungere un’entità a un criterio a livello di bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) nella documentazione di Google Cloud. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del bucket in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, nome_cartella/ |

   {style="table-layout:auto"}

+++

   +++SAS di Azure

   Specificare le informazioni seguenti per configurare un percorso SAS di Azure:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome contenitore**] | Contenitore all’interno dell’account specificato in cui desideri inviare i dati di Customer Journey Analytics. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++RBAC di Azure

   Specificare le informazioni seguenti per configurare un percorso RBAC di Azure:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **Contenitore**] | Il contenitore all’interno dell’account specificato nel punto in cui desideri inviare i dati di Adobe Analytics. Accertati di concedere le autorizzazioni per caricare i file nell’applicazione Azure creata in precedenza. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |
   | [!UICONTROL **Account**] | Account di archiviazione Azure. |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Specificare le informazioni seguenti per configurare un percorso di Snowflake:

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **DB**] | Il database predefinito da utilizzare dopo la connessione oppure specifica una stringa vuota. Il database specificato deve essere un database esistente per il quale il ruolo predefinito specificato dispone di privilegi. <p>Per ulteriori informazioni, vedere [Pagina di riferimento dei parametri di connessione del driver JDBC nella documentazione del Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Schema**] | Schema predefinito da utilizzare per il database specificato dopo la connessione o specifica una stringa vuota. Lo schema specificato deve essere uno schema esistente per il quale il ruolo predefinito specificato dispone di privilegi. <p>Per ulteriori informazioni, vedere [Pagina di riferimento dei parametri di connessione del driver JDBC nella documentazione del Snowflake](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Nome fase**] | Il nome del percorso in cui sono memorizzati i file di dati nel Snowflake. <p>Per ulteriori informazioni, vedere [Scelta di una pagina Stage interno per file locali nella documentazione del Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Percorso stage**] | Percorso del percorso in cui sono memorizzati i file di dati nel Snowflake. <p>Per ulteriori informazioni, vedere [Scelta di una pagina Stage interno per file locali nella documentazione del Snowflake](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

+++

   +++Adobe Experience Platform

   Specifica le seguenti informazioni per configurare un percorso Adobe Experience Platform:

   <!-- still need to update; can't create AEP account -->

   | Campo | Funzione |
   |---------|----------|
   | [!UICONTROL **ID organizzazione IMS**] | L’ID dell’organizzazione IMS è fornito da Adobe. Fai clic sull’icona Copia accanto a [!UICONTROL **ID organizzazione IMS**] per copiare il contenuto del campo, quindi utilizza l’ID nell’account Adobe Experience Platform. |
   | [!UICONTROL **Prefisso**] | La cartella all’interno del contenitore in cui desideri inserire i dati. Specifica il nome di una cartella, quindi aggiungi una barra rovesciata dopo il nome per creare la cartella. Ad esempio, `folder_name/` |

+++

1. Seleziona [!UICONTROL **Salva**].

1. Ora puoi esportare dati da Analysis Workspace all’account e alla posizione configurati. Per informazioni su come esportare i dati nel cloud, consulta [Esportare i dati del progetto nel cloud](/help/analysis-workspace/export/export-cloud.md).