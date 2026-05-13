---
title: Guida rapida a Customer Journey Analytics
description: Scopri i prerequisiti e il flusso di lavoro necessari per implementare Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/qYz2G6gugkSMH-BITMExxjkheGHrYFvDTZbR66c-Rr0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 837
ht-degree: 85%

---

# Guida rapida

Per implementare Customer Journey Analytics, devi seguire questo flusso di lavoro. Alcune attività iniziali vengono eseguite in Adobe Experience Platform, altre in Customer Journey Analytics.

## Prerequisiti

Customer Journey Analytics è disponibile per i clienti che

* dispongono del provisioning per [Adobe Experience Platform](https://www.adobe.com/it/experience-platform.html) e
* hanno acquistato la SKU (Stock Keeping Unit) di Customer Journey Analytics.

## Flusso di lavoro

| Attività | Dettagli |
| --- | --- |
| **Passaggio 1: se stai eseguendo l’aggiornamento da Adobe Analytics a Customer Journey Analytics: scegli un percorso di aggiornamento e invia i dati ad Adobe Experience Platform** | Sono disponibili vari percorsi per l’aggiornamento da Adobe Analytics a Customer Journey Analytics. Ogni possibile percorso di aggiornamento presenta vantaggi e svantaggi propri e un percorso adatto a un’organizzazione potrebbe non avere senso per un&#39;altra. <p>Per iniziare l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics, effettua una delle seguenti operazioni:</p><ul><li>Segui il percorso di aggiornamento consigliato da Adobe. Per ulteriori informazioni, consulta il [Percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</li><li>Scopri tutti i percorsi di aggiornamento disponibili e scegli quello più adatto all’organizzazione. Per ulteriori informazioni, consulta [Introduzione all’aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md).</li></ul> |
| **Passaggio 2: trasferire i dati in Adobe Experience Platform** | Questo passaggio, eseguito in Adobe Experience Platform, prevede diversi passaggi secondari:<ul><li>**Passaggio 2a: preparare lo schema dati**. Utilizza [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) per standardizzare i dati sull’esperienza del cliente e [definire schemi](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=it) per la gestione della customer experience.</li><li>**Passaggio 2b: creare un set di dati basato sullo schema**: i dati in Platform sono costituiti da set di dati, ad esempio set di dati e-mail, CRM, POS, Adobe Analytics e così via. Ogni set di dati è costituito da uno schema e da batch di dati. Puoi [creare un set di dati in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=it).</li><li>**Passaggio 2c: inserire dati in Experience Platform**. Sono disponibili diverse opzioni.</li></ul> |
| **Passaggio 3: creare connessioni tra set di dati di Platform e Customer Journey Analytics** | Una connessione consente di integrare set di dati da Adobe Experience Platform in Workspace. Per creare rapporti sui set di dati di Experience Platform, devi innanzitutto stabilire una connessione tra i set di dati in Experience Platform e Workspace.<br>Consulta [Creare o modificare una connessione](/help/connections/create-connection.md). |
| **Passaggio 4: creare visualizzazioni dati** | Una visualizzazione dati è una visualizzazione “filtrata” dei dati. Puoi creare diverse visualizzazioni dati per la stessa connessione, con impostazioni diverse per timeout visita, attribuzione e così via. Puoi creare più visualizzazioni dati per un singolo set di dati.<br>Consulta [Creare una visualizzazione dati](/help/data-views/create-dataview.md). |
| **Passaggio 5: trasferire l’utilizzo dell’API di reporting**</br> Applicabile solo se la migrazione parte da Adobe Analytics | L’API di reporting di Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Trasferisci l’utilizzo dell’API di reporting di Adobe Analytics a quella di Customer Journey Analytics. |
| **Passaggio 6: account per feed di dati e casi di utilizzo di Data Warehouse**</br> Applicabile solo se la migrazione parte da Adobe Analytics | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per replicare nel modo migliore i feed di dati e le funzioni di Data Warehouse che stavi utilizzando in Adobe Analytics. <!-- link to docs Rob is creating --> |
| **Passaggio 7: eseguire la migrazione di progetti e componenti**</br> Applicabile solo se la migrazione parte da Adobe Analytics | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics a Customer Journey Analytics.<p>Il processo di migrazione include:</p><ul><li>mappatura dei progetti Adobe Analytics in Customer Journey Analytics;</li><li>mappatura di dimensioni e metriche dalle suite di rapporti di Adobe Analytics alle dimensioni e alle metriche nelle visualizzazioni dati in Customer Journey Analytics.</li></ul><p>Prima di iniziare la migrazione, [Prepara la migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=it).</p><p>Dopo aver fatto tutte le preparazioni necessarie, puoi [migrare i componenti e i progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=it).</p> |
| **Passaggio 8: pianificare l’onboarding degli utenti** | Come in Adobe Analytics, Analysis Workspace è lo strumento principale rivolto all’utente in Customer Journey Analytics. Tuttavia, quando si utilizza Analysis Workspace in Customer Journey Analytics, gli utenti devono essere consapevoli di alcune differenze chiave.<p>Dovresti lasciare agli utenti il tempo necessario (3 - 6 mesi) per familiarizzare con le differenze chiave dell’utilizzo di Analysis Workspace in Customer Journey Analytics.</p><p>Per informazioni su alcune delle differenze principali tra Adobe Analytics e Customer Journey Analytics, consulta [Guida per gli utenti di Adobe Analytics](/help/getting-started/aa-to-cja-user.md).</p> |
| **Passaggio 9: creare rapporti sui dati multicanale in Workspace** | Dopo aver creato connessioni e visualizzazioni dati, analizza i dati inseriti utilizzando la potenza e la flessibilità di Analysis Workspace.<br>Consulta [Eseguire analisi di base](/help/analysis-workspace/perform-basic-analysis.md) e [Eseguire analisi avanzate](/help/analysis-workspace/perform-adv-analysis.md). |

## Guide rapide

La sezione [Acquisizione dei dati](../data-ingestion/data-ingestion.md) fornisce guide rapide sul flusso di lavoro di cui sopra. Queste guide rapide illustrano come acquisire i dati da diverse origini (incluso Adobe Analytics) in Adobe Experience Platform e utilizzarli in Customer Journey Analytics.
