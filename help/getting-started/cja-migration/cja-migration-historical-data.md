---
title: Mantieni i dati storici durante la migrazione al Customer Journey Analytics
description: Scopri come conservare i dati storici durante la migrazione al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Passaggio 5: conservazione dei dati storici durante la migrazione

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di migrazione più ampio. Assicurati che tutti i passaggi di migrazione precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di migrazione precedenti.

Le informazioni presenti in questa pagina riguardano il Passaggio 4 della **migrazione**, come evidenziato nella tabella seguente:

| Attività di migrazione | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| **Passaggio 2: [Scegli il percorso di migrazione](/help/getting-started/cja-migration/cja-migration-path.md)** | Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 4: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del percorso di migrazione scelto nel passaggio 2. |
| <span class="preview">**Passaggio 4: conservazione dei dati storici**</span> | <span class="preview">La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione.</span> |
| **Passaggio 5: [Eseguire ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di migrazione, è necessario eseguire varie attività prima che l’ambiente del Customer Journey Analytics sia pronto per l’uso.<p>Queste attività aggiuntive riguardano le migrazioni da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Experience Platform di altri dati</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Portare l’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Onboarding degli utenti di Planning</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva al Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Scegli una delle seguenti opzioni per conservare i dati storici durante il passaggio da Adobe Analytics a Customer Journey Analytics:

>[!IMPORTANT]
>
>Quando scegli come conservare i dati storici, contatta il rappresentante del tuo account di Adobe per determinare i prezzi.

## Utilizzare il connettore di origine di Analytics

È possibile utilizzare [Connettore di origine di Analytics](/help/data-ingestion/analytics.md) per conservare i dati storici. Indipendentemente dal percorso di migrazione scelto (anche se esegui la migrazione utilizzando Web SDK), puoi utilizzare il connettore di origine di Analytics per conservare i dati storici dal tuo ambiente Adobe Analytics.

Puoi utilizzare il connettore di origine di Analytics per conservare i dati storici inserendoli in una posizione dedicata, separata dai dati correnti.

Il connettore di origine di Analytics deve funzionare per tutto il tempo in cui hai bisogno di accedere ai dati storici.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Gestisci l’implementazione Adobe Analytics esistente

Puoi mantenere l’implementazione esistente di Adobe Analytics insieme alla nuova implementazione del Customer Journey Analytics per un intervallo di tempo specifico (ad esempio, 1 anno). Quando scegli questa opzione, considera quanto segue:

* I dati non sarebbero disponibili in Experienci Platform.

* Pianifica di disattivare l’implementazione di Adobe Analytics dopo aver inserito dati sufficienti nel Customer Journey Analytics.

## Quindi, esegui ulteriori attività di implementazione

A questo punto del processo di migrazione, è necessario eseguire varie attività di implementazione prima che l’ambiente del Customer Journey Analytics sia pronto per l’uso.

Queste attività aggiuntive riguardano le migrazioni da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.

Queste attività includono:

* Experience Platform di altri dati

* Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics

* Creazione di visualizzazioni dati

* Portare l’utilizzo dell’API di reporting

* Contabilità per i feed di dati e i casi di utilizzo di Data Warehouse

* Migrazione di progetti e componenti

* Onboarding degli utenti di Planning

Per ulteriori informazioni, iniziare con il passaggio 2 in [Guida introduttiva al Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
