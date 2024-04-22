---
title: Pianificare l’onboarding degli utenti durante la migrazione al Customer Journey Analytics
description: Pianificare l’onboarding degli utenti durante la migrazione al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34ccab37-a37f-4d69-aa96-ae1047b1f195
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---

# Passaggio 6: pianificare l’onboarding degli utenti durante la migrazione al Customer Journey Analytics

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di migrazione più ampio. Assicurati che tutti i passaggi di migrazione precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di migrazione precedenti.

Le informazioni in questa pagina riguardano il Passaggio 6, come evidenziato nella tabella seguente:

| Attività di migrazione | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| **Passaggio 2: [Scegli il metodo di migrazione](/help/getting-started/cja-migration/cja-migration-method.md)** | Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del metodo di migrazione scelto nel passaggio 1. |
| **Passaggio 4: [Mappare i dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei metodi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p> |
| **Passaggio 5: [Conserva dati storici](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| <span class="preview">**Passaggio 6: [Pianificare l’onboarding degli utenti](/help/getting-started/cja-migration/cja-migration-onboarding.md)**</span> | <span class="preview">Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics.</span> |
| **Passaggio 7: [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| **Passaggio 8: [Sostituire feed dati e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per sostituire le funzioni Feed dati e Data Warehouse che stavi utilizzando in Adobe Analytics. |
| **Passaggio 9: [Eseguire la migrazione di progetti e componenti](/help/getting-started/cja-migration/cja-migration-projects.md)** | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Gli utenti devono essere consapevoli di alcune differenze chiave tra Customer Journey Analytics e Adobe Analytics.

Come in Adobe Analytics, Analysis Workspace è lo strumento principale rivolto all’utente in Customer Journey Analytics. Tuttavia, quando si utilizza Analysis Workspace in Customer Journey Analytics, gli utenti devono essere consapevoli di alcune differenze chiave.

Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics.

Per informazioni su alcune delle differenze principali tra Adobe Analytics e Customer Journey Analytics, consulta [Guida utente per gli utenti di Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

## Quindi, porta l’utilizzo dell’API di reporting

L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md) dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics.
