---
title: Mantieni i dati storici durante l'aggiornamento a Customer Journey Analytics
description: Scopri come conservare i dati storici durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 97d48d88af969705f2664781e7a972f20c1b4239
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 45%

---

# Passaggio 4: conservazione dei dati storici durante l&#39;aggiornamento

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di aggiornamento più ampio. Assicurati che tutti i passaggi precedenti dell’aggiornamento siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di aggiornamento precedenti.

Le informazioni contenute in questa pagina descrivono il passaggio 4 del processo di aggiornamento, come evidenziato nella tabella seguente:

| Attività di aggiornamento | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione all&#39;aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Scopri i vantaggi dell’aggiornamento a Customer Journey Analytics e il processo di aggiornamento di base. |
| **Passaggio 2: [Scegliere il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Sono disponibili diversi metodi per l&#39;aggiornamento a Customer Journey Analytics. Scegli il metodo migliore per l’organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati ad Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del percorso di aggiornamento scelto nel passaggio 2. |
| <span class="preview">**Passaggio 4: conservare i dati storici**</span> | <span class="preview">La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione.</span> |
| **Passaggio 5: [Esegui ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di aggiornamento, è necessario eseguire varie attività prima che l’ambiente Customer Journey Analytics sia pronto per l’uso.<p>Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Inserimento di altri dati in Experience Platform</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Conversione dell’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Pianificazione dell’onboarding degli utenti</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva di Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

<!--

>[!AVAILABILITY]
>
>The information on this page is being replaced with the following more comprehensive upgrade information: <ul><li>**Recommended upgrade steps**<p>For detailed information, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>A new upgrade guide is available that dynamically generates upgrade steps that are tailored for your organization and your unique circumstances.</p><p>To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.</p></li></ul>

-->

Scegli una delle seguenti opzioni per conservare i dati storici durante il passaggio da Adobe Analytics a Customer Journey Analytics:

>[!IMPORTANT]
>
>Quando scegli come conservare i dati storici, contatta il tuo rappresentante commerciale Adobe per determinare i prezzi.

## Utilizzare il connettore di origine di Analytics

È possibile utilizzare il [connettore di origine di Analytics](/help/data-ingestion/analytics.md) per conservare i dati storici. Indipendentemente dal percorso di aggiornamento scelto (anche se esegui l’aggiornamento utilizzando il Web SDK), puoi utilizzare il connettore di origine di Analytics per conservare i dati storici dall’ambiente Adobe Analytics.

Puoi utilizzare il connettore di origine di Analytics per conservare i dati storici inserendoli in una posizione dedicata, separata dai dati correnti.

Il connettore di origine di Analytics deve funzionare per tutto il tempo in cui hai bisogno di accedere ai dati storici.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Mantieni l’implementazione Adobe Analytics esistente

Puoi mantenere l’implementazione esistente di Adobe Analytics insieme alla nuova implementazione di Customer Journey Analytics per un arco temporale specifico (ad esempio, 1 anno). Quando scegli questa opzione, tieni presente quanto segue:

* I dati non sarebbero disponibili in Experience Platform.

* Pianifica di ritirare l’implementazione di Adobe Analytics dopo aver inserito una quantità sufficiente di dati in Customer Journey Analytics.

## Quindi, esegui ulteriori attività di implementazione

A questo punto del processo di aggiornamento, è necessario eseguire varie attività di implementazione prima che l’ambiente Customer Journey Analytics sia pronto per l’uso.

Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni Customer Journey Analytics.

Queste attività includono:

* Inserimento di altri dati in Experience Platform

* Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics

* Creazione di visualizzazioni dati

* Conversione dell’utilizzo dell’API di reporting

* Contabilità per i feed di dati e i casi d’uso di Data Warehouse

* Migrazione di progetti e componenti

* Pianificazione dell’onboarding degli utenti

Per ulteriori informazioni, inizia con il passaggio 2 nella [Guida introduttiva a Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
