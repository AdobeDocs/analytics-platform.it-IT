---
title: Conservare i dati storici durante l’aggiornamento a Customer Journey Analytics
description: Scopri come conservare i dati storici durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
TQID: https://experienceleague.adobe.com/8AM-LX5GllmfDt-OpG6CAZt6qMH4DfMj9x8kgDBrD7I
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 676
ht-degree: 97%

---

# Passaggio 4: Conservare i dati storici durante l’aggiornamento

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di aggiornamento più ampio. Assicurati che tutti i passaggi di aggiornamento precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati in primo luogo di aver completato tutte le attività di aggiornamento precedenti.

Le informazioni in questa pagina descrivono il passaggio 4 del processo di aggiornamento, come evidenziato nella tabella seguente:

| Attività di aggiornamento | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione all’aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Scopri i vantaggi dell’aggiornamento a Customer Journey Analytics e il processo di aggiornamento di base. |
| **Passaggio 2: [Scegliere il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Sono disponibili diversi metodi per l’aggiornamento a Customer Journey Analytics. Scegli il metodo migliore per l’organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati ad Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Il processo di invio dei dati ad Adobe Experience Platform varia a seconda del percorso di aggiornamento scelto al passaggio 2. |
| <span class="preview">**Passaggio 4: conservare i dati storici**</span> | <span class="preview">La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione.</span> |
| **Passaggio 5: [Esegui ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di aggiornamento, devi eseguire varie attività prima che l’ambiente di Customer Journey Analytics sia pronto per l’uso.<p>Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Inserimento di altri dati in Experience Platform</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Conversione dell’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Pianificazione dell’onboarding degli utenti</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Le informazioni contenute in questa pagina verranno sostituite dalle seguenti informazioni di aggiornamento più complete: <ul><li>**Passaggi di aggiornamento consigliati**<p>Per informazioni dettagliate, consulta [Percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guida per l’aggiornamento di Customer Journey Analytics**<p>È disponibile una nuova guida per l’aggiornamento che genera in modo dinamico passaggi di aggiornamento personalizzati per la situazione specifica della tua organizzazione.</p><p>Per accedere alla guida da Customer Journey Analytics, seleziona la scheda **[!UICONTROL Workspace]**, quindi seleziona **[!UICONTROL Aggiornamento a Customer Journey Analytics]** nel pannello a sinistra. Segui le istruzioni visualizzate sullo schermo.</p></li></ul>

Scegli una delle seguenti opzioni per conservare i dati storici durante il passaggio da Adobe Analytics a Customer Journey Analytics:

>[!IMPORTANT]
>
>Quando scegli come conservare i dati storici, contatta il tuo rappresentante commerciale Adobe per determinare i prezzi.

## Utilizzare il connettore di origine di Analytics

Puoi utilizzare il [Connettore di origine di Analytics](/help/data-ingestion/analytics.md) per conservare i dati storici. Indipendentemente dal percorso di aggiornamento scelto (anche se hai scelto di aggiornare con Web SDK), puoi utilizzare il connettore di origine di Analytics per conservare i dati storici del tuo ambiente di Adobe Analytics.

Puoi utilizzare il connettore di origine di Analytics per conservare i dati storici inserendoli in una posizione dedicata, separata dai dati correnti.

Il connettore di origine di Analytics deve funzionare per tutto il tempo in cui hai bisogno di accedere ai dati storici.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Mantieni l’implementazione Adobe Analytics esistente

Puoi mantenere l’implementazione esistente di Adobe Analytics insieme alla nuova implementazione di Customer Journey Analytics per un arco temporale specifico (ad esempio, 1 anno). Quando scegli questa opzione, tieni presente quanto segue:

* I dati non sarebbero disponibili in Experience Platform.

* Pianifica di ritirare l’implementazione di Adobe Analytics dopo aver inserito una quantità sufficiente di dati in Customer Journey Analytics.

## Quindi, esegui ulteriori attività di implementazione

A questo punto del processo di aggiornamento, è necessario eseguire varie attività di implementazione prima che l’ambiente di Customer Journey Analytics sia pronto per l’uso.

Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.

Queste attività includono:

* Inserimento di altri dati in Experience Platform

* Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics

* Creazione di visualizzazioni dati

* Conversione dell’utilizzo dell’API di reporting

* Contabilità per i feed di dati e i casi d’uso di Data Warehouse

* Migrazione di progetti e componenti

* Pianificazione dell’onboarding degli utenti

Per ulteriori informazioni, inizia con il passaggio 2 nella [Guida introduttiva a Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
