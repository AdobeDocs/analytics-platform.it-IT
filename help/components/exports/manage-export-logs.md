---
description: Gestire i registri per le esportazioni esistenti
keywords: Analysis Workspace
title: Gestire i registri di esportazione
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 3%

---

# Gestire i registri di esportazione

I registri di esportazione forniscono dettagli su ogni esportazione e vengono generati ogni volta che i dati di Analysis Workspace vengono esportati nel cloud. (Per informazioni su come esportare i dati nel cloud, vedere [Esportare i report di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md).)

Per le esportazioni pianificate, i registri riflettono le impostazioni di esportazione così come erano quando il registro è stato inviato. I registri non possono essere eliminati.

## Visualizzare i registri di esportazione

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Registri**].

   ![Finestra di esportazione con la scheda Registri](assets/export-logs-tab.png)

   I dettagli di ciascun registro vengono visualizzati nelle colonne disponibili.

1. Esegui una delle operazioni seguenti:

   * [Personalizzare le colonne](#configure-columns) visualizzate.

   * Seleziona l&#39;**icona Informazioni** ![icona Informazioni](assets/information-icon.png) accanto al nome del registro per visualizzare l&#39;esportazione associata al registro.

   * Seleziona l&#39;**icona Modifica esportazione** ![icona Informazioni](assets/edit-export-icon.png) accanto al nome del registro per modificare l&#39;esportazione associata al registro.

     Per ulteriori informazioni sulla modifica di un&#39;esportazione, vedere [Esportare i report di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md).

## Filtrare e cercare i registri

Per trovare le informazioni necessarie, puoi filtrare l’elenco dei registri o cercare un registro.

### Filtrare l’elenco dei registri

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Registri**].

1. Seleziona l&#39;icona **Filtro**.

   ![Finestra Esporta che mostra l&#39;elenco dei filtri per tipo di account](assets/export-log-filters.png)

   Puoi filtrare in base ai seguenti criteri:

   | Filtro | Descrizione |
   |---------|----------|
   | [!UICONTROL **ID esportazione**] | Specifica l’ID di esportazione del registro di esportazione da visualizzare. |
   | [!UICONTROL **Tipo di account**] | Tipo di account a cui è associato il registro. Sono disponibili i seguenti tipi di account: <ul><li>[!UICONTROL **Area di destinazione dati AEP**]</li><li>[!UICONTROL **ARN per ruolo Amazon S3**]</li><li>[!UICONTROL **SAS di Azure**]</li><li>[!UICONTROL **RBAC di Azure**]</li><li>[!UICONTROL **Piattaforma cloud Google**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Stato**] | Stato dell’esportazione. Sono disponibili i seguenti stati: <ul><li>[!UICONTROL **In sospeso**]: un&#39;istanza specifica di un&#39;esportazione è stata avviata ma non è ancora stata completata.<p>La riesecuzione di un’esportazione con lo stato In sospeso ritarda il processo di esportazione.</p></li><li>[!UICONTROL **Completata**]: un&#39;istanza specifica di un&#39;esportazione ha completato l&#39;elaborazione ed è disponibile nell&#39;account di esportazione.</li><li>[!UICONTROL **Non riuscito**]<p>Varie situazioni possono causare un’esportazione non riuscita. Passa il cursore del mouse sullo stato Non riuscito per visualizzare i dettagli dell’errore.<p>Per ulteriori informazioni sui possibili motivi di un errore, vedere [Risoluzione dei problemi relativi alle esportazioni non riuscite](/help/components/exports/troubleshoot-exports.md).</p> |

   {style="table-layout:auto"}

### Cerca registri

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Registri**].

1. Nel campo di ricerca, inizia a digitare le informazioni associate al registro che stai cercando. Puoi cercare dati da qualsiasi colonna disponibile nella tabella.

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## Modificare un’esportazione

Puoi modificare l’esportazione associata a un registro specifico.

Questa opzione non è disponibile quando si selezionano più registri.

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Registri**].

1. Individuare il registro associato all&#39;esportazione che si desidera modificare.

1. Seleziona l&#39;icona **Modifica esportazione** ![icona di esportazione registro](assets/export-icon.png) accanto al nome del registro.

   Oppure

   Seleziona la casella di controllo accanto al registro, quindi seleziona [!UICONTROL **Modifica esportazione**].

## Configurare le colonne

È possibile aggiungere o rimuovere colonne nella scheda [!UICONTROL Logs] per configurare le informazioni visualizzate.

Seleziona un’intestazione di colonna per ordinare i registri in base a tale colonna. Per impostazione predefinita, i registri vengono ordinati in base alla data e all’ora di inizio dell’esportazione.

Per configurare le colonne nella scheda [!UICONTROL Logs]:

1. In Customer Journey Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Selezionare la scheda [!UICONTROL **Registri**].

1. Selezionare l&#39;icona **Personalizza tabella** ![Personalizza tabella](assets/customize-table-icon.png) in alto a destra nella pagina [!UICONTROL Logs].

   Sono disponibili le seguenti colonne:

   | Colonna disponibile | Descrizione |
   |---------|----------|
   | Nome esportazione | Nome dell’esportazione. Gli utenti assegnano un nome alle esportazioni al momento della creazione, come descritto in [Esporta report Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md). |
   | ID esportazione | L’ID assegnato automaticamente all’esportazione al momento della creazione. <!-- True? --> |
   | ID istanza | ID dell’istanza del Customer Journey Analytics. <!-- True? --> |
   | Nome delle visualizzazioni dati | Nome della visualizzazione dati associata all’esportazione. Gli utenti possono selezionare la visualizzazione dati al momento della creazione dell&#39;esportazione, come descritto in [Esporta report di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Numero di file | Numero di file inclusi nell&#39;esportazione. |
   | Dimensione | Dimensione dell&#39;esportazione.<p>La dimensione del file viene calcolata con una base di 1024, che a volte viene rappresentata come KIB e MIB. Se il provider di cloud calcola le dimensioni in base a 1000, le dimensioni visualizzate nel provider potrebbero essere leggermente diverse da quelle visualizzate qui.</p> |
   | Posizione | Posizione dell&#39;account in cui sono stati esportati i dati. |
   | Account | Account in cui sono stati esportati i dati. |
   | Stato | Stato dell’esportazione. Gli stati disponibili sono [!UICONTROL Pending], [!UICONTROL Delivered] e [!UICONTROL Failed]. |
   | Data di consegna | La data in cui è avvenuta l’esportazione. |
   | Tipo di account | Tipo di account cloud in cui sono stati esportati i dati. I tipi di account disponibili sono [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake] e [!UICONTROL Adobe Experience Platform]. |
   | Numero di righe | Numero di righe incluse nella tabella esportata. |

   {style="table-layout:auto"}

1. Assicurati che tutte le colonne che desideri visualizzare siano selezionate. Le colonne selezionate vengono visualizzate nella pagina [!UICONTROL Logs] e le relative informazioni.

## Visualizzare i registri di audit

Le esportazioni di tabelle complete vengono anche tracciate nei [registri di controllo del Customer Journey Analytics](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
