---
title: Panoramica sulle connessioni Customer Journey Analytics
description: Scopri le connessioni in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 09a6ae258d27f8fe9c9a1fc7ed63273620c67c1b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 80%

---

# Panoramica sulle connessioni

Le connessioni consentono agli amministratori di prodotto di Customer Journey Analytics di definire quali origini dati [!DNL &#x200B; Experience Platform], ad esempio eventi, ricerche, profili e set di dati di riepilogo, vengono acquisite. Le connessioni sono alla base di Customer Journey Analytics e determinano la disponibilità dei dati (campi) che è possibile definire in una [visualizzazione dati](/help/data-views/data-views.md) come dimensione o metriche.

>[!IMPORTANT]
>
>È possibile combinare più set di dati [!DNL Experience Platform] in una singola connessione.


## Flusso di lavoro Connessioni

![Flusso di lavoro Connessioni](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

A un livello elevato, il flusso di lavoro Connessioni consente di:

| Interfaccia | Descrizione |
|:---:|---|
| ➊ | [Gestire le connessioni e l’utilizzo complessivo](manage-connections.md) di Customer Journey Analytics da Gestione connessioni. |
| ➋ | [Verificare i dettagli di una connessione](manage-connections.md#connection-details), ad esempio i record di set di dati acquisiti, ignorati o eliminati. |
| ➌ | [Creare o modificare la configurazione di una connessione](create-connection.md#create-or-edit-a-connection), come una finestra di dati continua, la sandbox da utilizzare, quali set di dati fanno parte della connessione e altro ancora. |
| ➍ | [Aggiungere set di dati a una connessione](create-connection.md#add-datasets). La connessione deve avere almeno un set di dati di eventi o di riepilogo, ma può contenere diversi set di dati di eventi, profili, ricerca e riepilogo. |
| ➎ | [Configurare le impostazioni](create-connection.md#dataset-settings) per i set di dati aggiunti. Puoi determinare come collegare diversi set di dati in base a un comune identificatore basato su persona o su account [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. |
| ➏ | [Modificare le impostazioni per un set di dati esistente](create-connection.md#edit-a-dataset). Puoi sempre rivedere le impostazioni del set di dati in un secondo momento. |



## Controllo degli accessi

L’accesso alla gestione delle connessioni deve essere limitato a un gruppo di gestione di base. Le configurazioni delle connessioni hanno implicazioni contrattuali per quanto riguarda l’assegnazione di volumi per i dati inseriti in Customer Journey Analytics.

>[!MORELIKETHIS]
>
>[Controllo degli accessi](/help/technotes/access-control.md).

