---
title: Guida introduttiva di Customer Journey Analytics
description: Scopri i prerequisiti e il flusso di lavoro necessari per implementare Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 51%

---

# Guida introduttiva di Customer Journey Analytics

Per implementare Customer Journey Analytics, devi seguire questo flusso di lavoro. Alcune attività iniziali vengono eseguite in Adobe Experience Platform, altre in Customer Journey Analytics.

## Prerequisiti

Customer Journey Analytics è disponibile per i clienti che

* dispongono del provisioning per [Adobe Experience Platform](https://www.adobe.com/it/experience-platform.html) e
* hanno acquistato la SKU (Stock Keeping Unit) di Customer Journey Analytics.

## Flusso di lavoro

| Attività | Dettagli |
| --- | --- |
| **Passaggio 1: se stai eseguendo la migrazione da Adobe Analytics a Customer Journey Analytics: scegli un percorso di migrazione e invia i dati a Adobe Experience Platform** | Sono disponibili vari percorsi per la migrazione da Adobe Analytics a Customer Journey Analytics. Ogni possibile percorso di migrazione presenta vantaggi e svantaggi propri e un percorso adatto a un&#39;organizzazione potrebbe non avere senso per un&#39;altra. <p>Per iniziare la migrazione da Adobe Analytics a Customer Journey Analytics, consulta [Introduzione alla migrazione al Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-getstarted.md). <!-- [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) --> </p> |
| **Passaggio 2: trasferire i dati in Adobe Experience Platform** | Questo passaggio, eseguito in Adobe Experience Platform, prevede diversi passaggi secondari:<ul><li>**Passaggio 2a: preparare lo schema dati**. Utilizza [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) per standardizzare i dati sull’esperienza del cliente e [definire schemi](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) per la gestione della customer experience.</li><li>**Passaggio 2b: creare un set di dati basato sullo schema**. I dati in Platform sono costituiti da set di dati, ad esempio e-mail, CRM, POS, Adobe Analytics e così via. Ciascun set di dati è costituito da uno schema e da batch di dati. Puoi [creare un set di dati in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=it).</li><li>**Passaggio 2c: inserire dati in Experience Platform**. Sono disponibili diverse opzioni.</li></ul> |
| **Passaggio 3: creare connessioni tra set di dati di Platform e Customer Journey Analytics** | Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti sui set di dati bisogna prima stabilire una connessione tra i set di dati in Experience Platform e Workspace.<br>Consulta [Creare o modificare una connessione](/help/connections/create-connection.md). |
| **Passaggio 4: creare visualizzazioni dati** | Una visualizzazione dati è una visualizzazione “filtrata” dei dati. Puoi creare diverse visualizzazioni dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Puoi creare più visualizzazioni dati per un singolo set di dati.<br>Consulta [Creare una visualizzazione dati](/help/data-views/create-dataview.md). |
| **Passaggio 5: trasferire l’utilizzo dell’API di reporting**</br> Applicabile solo durante la migrazione da Adobe Analytics | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| **Passaggio 6: Account per feed di dati e casi di utilizzo di Data Warehouse**</br> Applicabile solo durante la migrazione da Adobe Analytics | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per replicare nel modo migliore i feed di dati e le funzioni di Data Warehouse che stavi utilizzando in Adobe Analytics. <!-- link to docs Rob is creating --> |
| **Passaggio 7: eseguire la migrazione di progetti e componenti**</br> Applicabile solo durante la migrazione da Adobe Analytics | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics.<p>Per informazioni sulla replica dei progetti Adobe Analytics nel Customer Journey Analytics e sulla mappatura dei componenti di progetto da una suite di rapporti di Adobe Analytics a una visualizzazione dati del Customer Journey Analytics, vedi [Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html?lang=it).</p> |
| **Passaggio 8: pianificazione dell’onboarding degli utenti** | Come in Adobe Analytics, Analysis Workspace è lo strumento principale rivolto all’utente in Customer Journey Analytics. Tuttavia, quando si utilizza Analysis Workspace in Customer Journey Analytics, gli utenti devono essere consapevoli di alcune differenze chiave.<p>Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics.</p><p>Per informazioni su alcune delle differenze principali tra Adobe Analytics e Customer Journey Analytics, consulta [Guida utente per gli utenti di Adobe Analytics](/help/getting-started/aa-to-cja-user.md).</p> |
| **Passaggio 9: creare rapporti sui dati multicanale in Workspace** | Dopo aver creato connessioni e visualizzazioni dati, analizza i dati che hai immesso utilizzando la potenza e la flessibilità di Analysis Workspace.<br>Consulta [Eseguire analisi di base](/help/analysis-workspace/perform-basic-analysis.md) ed [Eseguire analisi avanzate](/help/analysis-workspace/perform-adv-analysis.md). |

## Guide rapide

La sezione [Acquisizione dei dati](../data-ingestion/data-ingestion.md) fornisce guide rapide sul flusso di lavoro di cui sopra. Queste guide rapide illustrano come acquisire i dati da diverse origini (incluso Adobe Analytics) in Adobe Experience Platform e utilizzarli in Customer Journey Analytics.
