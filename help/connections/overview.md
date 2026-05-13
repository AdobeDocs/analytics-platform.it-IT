---
title: Panoramica delle connessioni Customer Journey Analytics
description: Scopri le connessioni in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
TQID: https://experienceleague.adobe.com/2YaPpJFOi4jdLFkJGJsfBLpFtAYx3047ckpCG87lMF8
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 294
ht-degree: 88%

---

# Panoramica sulle connessioni

Le connessioni consentono agli amministratori di prodotto di Customer Journey Analytics di definire quali origini dati [!DNL  Experience Platform] acquisire, come set di dati di eventi, ricerca, profili e riepilogo. Le connessioni sono alla base di Customer Journey Analytics e determinano la disponibilità dei dati (campi) che è possibile definire in una [visualizzazione dati](/help/data-views/data-views.md) come dimensione o metriche.

>[!IMPORTANT]
>
>È possibile combinare più set di dati [!DNL Experience Platform] in una singola connessione.


## Flusso di lavoro Connessioni

![Flusso di lavoro Connessioni](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Connetti a origini dati](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]

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

