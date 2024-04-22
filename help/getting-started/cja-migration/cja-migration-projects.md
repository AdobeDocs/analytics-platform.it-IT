---
title: Migra progetti e componenti al Customer Journey Analytics
description: Scopri come migrare i componenti per migrare progetti e componenti al Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 6e5c3ecf-6eba-4dfa-8bf2-e43d56cfc65f
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 11%

---

# Passaggio 9: migrazione di progetti e componenti al Customer Journey Analytics

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di migrazione più ampio. Assicurati che tutti i passaggi di migrazione precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di migrazione precedenti.

Le informazioni in questa pagina riguardano il Passaggio 9, come evidenziato nella tabella seguente:

| Attività di migrazione | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| **Passaggio 2: [Scegli il metodo di migrazione](/help/getting-started/cja-migration/cja-migration-method.md)** | Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del metodo di migrazione scelto nel passaggio 1. |
| **Passaggio 4: [Mappare i dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei metodi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p> |
| **Passaggio 5: [Conserva dati storici](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 6: [Pianificare l’onboarding degli utenti](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics. |
| **Passaggio 7: [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| **Passaggio 8: [Sostituire feed dati e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per sostituire le funzioni Feed dati e Data Warehouse che stavi utilizzando in Adobe Analytics. |
| <span class="preview">**Passaggio 9: [Eseguire la migrazione di progetti e componenti](/help/getting-started/cja-migration/cja-migration-projects.md)**</span> | <span class="preview">L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics.</span> |
| **Passaggio 10: [Eseguire attività successive alla migrazione](/help/getting-started/cja-getting-started.md)** | Dopo aver completato la migrazione, devi eseguire varie attività, tra cui inserire altri dati in Experienci Platform, creare connessioni tra set di dati e Customer Journey Analytics di Platform, creare visualizzazioni dati e imparare a creare rapporti sui dati multicanale in Analysis Workspace. |

{style="table-layout:auto"}

+++

L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics.

Il processo di migrazione include:

* mappatura dei progetti Adobe Analytics in Customer Journey Analytics;

* mappatura di dimensioni e metriche dalle suite di rapporti di Adobe Analytics alle dimensioni e alle metriche nelle visualizzazioni dati in Customer Journey Analytics.

Prima di iniziare la migrazione, [Prepara la migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=it).

Dopo aver fatto tutte le preparazioni necessarie, puoi [migrare i componenti e i progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=it).

## Quindi, esegui le attività di post-migrazione

Dopo di te [Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=it), è necessario eseguire varie attività per completare la configurazione dell’ambiente di Customer Journey Analytics. Tali attività includono l’Experience Platform di altri dati, la creazione di connessioni tra set di dati e Customer Journey Analytics di Platform, la creazione di visualizzazioni dati e l’apprendimento di come creare rapporti sui dati multicanale in Analysis Workspace.

Ulteriori informazioni su queste attività di migrazione sono disponibili in [Guida introduttiva al Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
