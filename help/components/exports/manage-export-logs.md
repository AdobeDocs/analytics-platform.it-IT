---
description: Gestire i registri per le esportazioni esistenti
keywords: Analysis Workspace
title: Gestire i registri di esportazione
feature: Components
hide: true
hidefromtoc: true
source-git-commit: f070f998758cead3709f6c48412b22b29de00164
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 3%

---

# Gestire i registri di esportazione

{{select-package}}

I registri di esportazione forniscono dettagli su ogni esportazione e vengono generati ogni volta che i dati di Analysis Workspace vengono esportati nel cloud. (Per informazioni su come esportare i dati nel cloud, vedi [Esporta dati di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md).)

Per le esportazioni pianificate, i registri riflettono le impostazioni di esportazione così come erano quando il registro è stato inviato. I registri non possono essere eliminati.

## Filtrare e cercare i registri

Per trovare le informazioni necessarie, puoi filtrare l’elenco dei registri o cercare un registro.

### Filtrare l’elenco dei registri

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Log**] scheda.

1. Seleziona la **Filtro** icona.

   ![Informazioni filtro](assets/export-log-filters.png)

   Puoi filtrare in base ai seguenti criteri:

   | Filtro | Descrizione |
   |---------|----------|
   | [!UICONTROL **Tipo di account**] | Tipo di account a cui è associato il registro. Sono disponibili i seguenti tipi di account: <ul><li>[!UICONTROL **ARN per ruolo Amazon S3**]</li><li>[!UICONTROL **Piattaforma Google Cloud**]</li><li>[!UICONTROL **SAS di Azure**]</li><li>[!UICONTROL **RBAC di Azure**]</li><li>[!UICONTROL **Snowflake**]</li><li>[!UICONTROL **Adobe Experience Manager**]</li></ul>. |
   | [!UICONTROL **Stato**] | Stato dell’esportazione. Sono disponibili i seguenti stati: <ul><li>[!UICONTROL **In sospeso**]: un’istanza specifica di un’esportazione è stata avviata ma non è ancora completa.<p>La riesecuzione di un’esportazione con lo stato In sospeso ritarda il processo di esportazione.</p></li><li>[!UICONTROL **Completato**]: l’elaborazione di un’istanza specifica di un’esportazione è stata completata ed è disponibile nell’account di esportazione.</li><li>[!UICONTROL **Non riuscito**]<p>Le situazioni seguenti possono causare un’esportazione non riuscita. Passa il cursore del mouse sullo stato Non riuscito per visualizzare i dettagli dell’errore. <ul><li>Scadenza esportazione pianificata</li><li>Limite di righe raggiunto per l’esportazione pianificata </li></ul> </p></li></ul> |

   {style="table-layout:auto"}

### Cerca registri

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Log**] scheda.

1. Nella scheda di ricerca, inizia a digitare le informazioni associate al registro che stai cercando. Puoi cercare dati da qualsiasi colonna disponibile nella tabella.

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## Modificare un’esportazione

Puoi modificare l’esportazione associata a un registro specifico.

Questa opzione non è disponibile quando si selezionano più registri.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Registri**] , quindi selezionare un registro.

   <!-- add screenshot? -->

1. Seleziona [!UICONTROL **Modifica**].

## Configurare le colonne

È possibile aggiungere o rimuovere colonne nel [!UICONTROL Log] per configurare le informazioni visualizzate.

Seleziona un’intestazione di colonna per ordinare i registri in base a tale colonna. Per impostazione predefinita, i registri vengono ordinati in base alla data e all’ora di inizio dell’esportazione.

Per configurare le colonne in [!UICONTROL Log] scheda:

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Log**] scheda.

1. Seleziona la **Personalizza tabella** icona ![personalizza tabella](assets/customize-table-icon.png) in alto a destra nella [!UICONTROL Log] pagina.

   Sono disponibili le seguenti colonne:

   | Colonna disponibile | Descrizione |
   |---------|----------|
   | Nome esportazione | Nome dell’esportazione. Gli utenti assegnano un nome alle esportazioni quando le creano, come descritto in [Esporta dati di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md). |
   | ID esportazione | L’ID assegnato automaticamente all’esportazione al momento della creazione. <!-- True? --> |
   | ID istanza | ID dell’istanza del Customer Journey Analytics. <!-- True? --> |
   | Nome delle visualizzazioni dati | Nome della visualizzazione dati associata all’esportazione. Gli utenti possono selezionare la visualizzazione dati al momento della creazione dell’esportazione, come descritto in [Esporta dati di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Numero di file | Numero di file inclusi nell&#39;esportazione. |
   | Dimensione | Dimensione dell&#39;esportazione.<p>La dimensione del file viene calcolata con una base di 1024, che a volte viene rappresentata come KIB e MIB. Se il provider di cloud calcola le dimensioni in base a 1000, le dimensioni visualizzate nel provider potrebbero essere leggermente diverse da quelle visualizzate qui.</p> |
   | Posizione | Posizione dell&#39;account in cui sono stati esportati i dati. |
   | Account | Account in cui sono stati esportati i dati. |
   | Stato | Stato dell’esportazione. Gli stati disponibili sono [!UICONTROL Pending], [!UICONTROL Delivered], e [!UICONTROL Failed]. |
   | Data di consegna | La data in cui è avvenuta l’esportazione. |
   | Tipo di account | Tipo di account cloud in cui sono stati esportati i dati. I tipi di account disponibili sono [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], e [!UICONTROL Adobe Experience Platform]. |
   | Numero di righe | Numero di righe incluse nella tabella esportata. |

   {style="table-layout:auto"}

1. Assicurati che tutte le colonne che desideri visualizzare siano selezionate. Le colonne selezionate vengono visualizzate nel [!UICONTROL Log] e visualizza le informazioni pertinenti.

## Visualizzare i registri di audit

Le esportazioni di tabelle complete vengono tracciate anche nel [Registri di controllo del Customer Journey Analytics](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->