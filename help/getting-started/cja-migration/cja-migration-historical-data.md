---
title: Mantieni i dati storici durante la migrazione al Customer Journey Analytics
description: Scopri come conservare i dati storici durante la migrazione al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Passaggio 5: conservazione dei dati storici durante la migrazione al Customer Journey Analytics

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di migrazione più ampio. Assicurati che tutti i passaggi di migrazione precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di migrazione precedenti.

Le informazioni in questa pagina riguardano il Passaggio 5, come evidenziato nella tabella seguente:

| Attività di migrazione | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| **Passaggio 2: [Scegli il metodo di migrazione](/help/getting-started/cja-migration/cja-migration-method.md)** | Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del metodo di migrazione scelto nel passaggio 1. |
| **Passaggio 4: [Mappare i dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei metodi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p> |
| <span class="preview">**Passaggio 5: [Conserva dati storici](/help/getting-started/cja-migration/cja-migration-historical-data.md)**</span> | <span class="preview">La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione.</span> |
| **Passaggio 6: [Pianificare l’onboarding degli utenti](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics. |
| **Passaggio 7: [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| **Passaggio 8: [Sostituire feed dati e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per sostituire le funzioni Feed dati e Data Warehouse che stavi utilizzando in Adobe Analytics. |
| **Passaggio 9: [Eseguire la migrazione di progetti e componenti](/help/getting-started/cja-migration/cja-migration-projects.md)** | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Scegli una delle seguenti opzioni per conservare i dati storici durante il passaggio da Adobe Analytics a Customer Journey Analytics:

## Utilizzare il connettore di origine di Analytics

È possibile utilizzare [Connettore di origine di Analytics](/help/data-ingestion/analytics.md) per conservare i dati storici. Indipendentemente dal metodo di migrazione scelto (anche se esegui la migrazione utilizzando Web SDK), puoi utilizzare il connettore di origine di Analytics per conservare i dati storici dal tuo ambiente Adobe Analytics.

Puoi utilizzare il connettore di origine di Analytics per conservare i dati storici nei seguenti modi:

* Inserisci i dati storici nella sua posizione dedicata, separata dai dati correnti.

* Mappa i dati storici in modo da poterli collegare ai nuovi dati. <!-- Possible? Explain -->

## Gestisci l’implementazione Adobe Analytics esistente

Puoi mantenere l’implementazione esistente di Adobe Analytics insieme alla nuova implementazione del Customer Journey Analytics per un intervallo di tempo specifico (ad esempio, 1 anno). Quando scegli questa opzione, devi pianificare la rimozione delle autorizzazioni dall’implementazione di Adobe Analytics dopo aver ottenuto dati sufficienti in Customer Journey Analytics.

Contatta il rappresentante del tuo account di Adobe per determinare i prezzi per questa opzione.

## Quindi, pianifica l’onboarding degli utenti

[Pianificare l’onboarding degli utenti al Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-onboarding.md). Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics.
