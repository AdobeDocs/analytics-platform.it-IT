---
title: Inviare i dati ad Adobe Experience Platform durante la migrazione a Customer Journey Analytics
description: Inviare i dati ad Adobe Experience Platform durante la migrazione a Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '891'
ht-degree: 100%

---

# Passaggio 3: inviare i dati ad Adobe Experience Platform durante l’aggiornamento

+++Espandi questa sezione per vedere dove si inseriscono le informazioni di questa pagina nel processo di aggiornamento più ampio. Assicurati che tutti i passaggi di aggiornamento precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati in primo luogo di aver completato tutte le attività di aggiornamento precedenti.

Le informazioni in questa pagina descrivono il passaggio 3 del processo di aggiornamento, come evidenziato nella tabella seguente:

| Attività di aggiornamento | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione all’aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Scopri i vantaggi dell’aggiornamento a Customer Journey Analytics e il processo di aggiornamento di base. |
| **Passaggio 2: [Scegliere il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Sono disponibili diversi metodi per l’aggiornamento a Customer Journey Analytics. Scegli il metodo migliore per l’organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| <span class="preview">**Passaggio 3: inviare i dati ad Adobe Experience Platform**</span> | <span class="preview">Il processo di invio dei dati ad Adobe Experience Platform varia a seconda del percorso di aggiornamento scelto nel Passaggio 2.</span> |
| **Passaggio 4: [Conserva i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 5: [Esegui ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di aggiornamento, devi eseguire varie attività prima che l’ambiente di Customer Journey Analytics sia pronto per l’uso.<p>Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Inserimento di altri dati in Experience Platform</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Conversione dell’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Pianificazione dell’onboarding degli utenti</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Le informazioni contenute in questa pagina verranno sostituite dalle seguenti informazioni di aggiornamento più complete: <ul><li>**Passaggi di aggiornamento consigliati**<p>Per informazioni dettagliate, consulta il [Percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guida per l’aggiornamento di Customer Journey Analytics**<p>È disponibile una nuova guida per l’aggiornamento che genera in modo dinamico passaggi di aggiornamento personalizzati per la situazione specifica della tua organizzazione.</p><p>Per accedere alla guida da Customer Journey Analytics, seleziona la scheda **[!UICONTROL Workspace]**, quindi seleziona **[!UICONTROL Upgrade to Customer Journey Analytics]** nel pannello a sinistra. Segui le istruzioni visualizzate sullo schermo.</p></li></ul>

Una volta che [hai scelto il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md) più adatto per la tua organizzazione, puoi iniziare a inviare i dati ad Adobe Experience Platform per renderli disponibili in Customer Journey Analytics.

Di seguito è illustrata la procedura per inviare i dati a Experience Platform per ciascun percorso di aggiornamento. Per informazioni dettagliate sulla configurazione, segui i collegamenti riportati nella tabella.

| Percorso di aggiornamento | Processo per inviare i dati a Platform | Informazioni aggiuntive |
|---------|----------|----------|
| Nuova implementazione di Experience Platform Web SDK | <ol><li>Creare uno schema XDM per l’organizzazione.<p>Collabora con il team di dati per progettare lo schema per Customer Journey Analytics ideale per la tua organizzazione.</p></li><li>Implementa Experience Platform Web SDK.</li><li>Inviare i dati a Platform.</li></ol><p>Per informazioni dettagliate su ciascuno di questi passaggi, consulta [Acquisire i dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md). | Poiché si tratta di una nuova implementazione di Experience Platform Web SDK, la mappatura dello schema non è necessaria, in quanto è necessario creare lo schema come uno dei primi passaggi durante l’implementazione. |
| Migrare l’implementazione di Adobe Analytics per utilizzare Web SDK | <ol><li>Sposta l’implementazione di Adobe Analytics esistente in Experience Platform Web SDK, quindi verifica che tutto funzioni in Adobe Analytics.<p>Per informazioni su come eseguire questa operazione, utilizza le risorse seguenti, a seconda che l’implementazione corrente sia l’estensione del tag di Analytics o AppMeasurement:</p><ul><li>Se utilizzi l’estensione del tag di Analytics, consulta [Migrare dall’estensione del tag di Adobe Analytics all’estensione del tag di Web SDK](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Se utilizzi AppMeasurement, consulta [Migrare da AppMeasurement a Web SDK](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Creare uno schema XDM per l’organizzazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Collabora con il team di dati per progettare lo schema per Customer Journey Analytics ideale per la tua organizzazione.</p></li><li>[Utilizza la preparazione dati per mappare tutti i campi nell’oggetto dati sullo schema XDM](https://experienceleague.adobe.com/it/docs/experience-platform/data-prep/home).</li><li>Inizia ad inviare i dati a Platform [impostando uno stream di dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configurare l’implementazione di Adobe Analytics Web SDK esistente per inviare i dati a Platform | <ol><li>Inizia ad inviare i dati a Platform [impostando uno stream di dati](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).<p>Poiché l’implementazione di Adobe Analytics utilizza già Experience Platform Web SDK, puoi ignorare le altre sezioni in [Acquisire i dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</p><p>Se stai già inviando dati a Platform con l’implementazione di Adobe Analytics, questo passaggio non è necessario. Devi semplicemente creare una connessione tra i set di dati di Platform e Customer Journey Analytics, come descritto più avanti in questo processo.</p></li><li>(Facoltativo) [Creare uno schema XDM per l’organizzazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Collabora con il team di dati per progettare lo schema per Customer Journey Analytics ideale per la tua organizzazione.</p><p>Nota: per informazioni sui vantaggi della creazione di uno schema XDM, consulta [Scegli lo schema](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Condizionale) Se hai creato uno schema XDM, [utilizza la preparazione dati per mappare tutti i campi nell’oggetto dati sullo schema XDM](https://experienceleague.adobe.com/it/docs/experience-platform/data-prep/home).</li></ol> |  |
| Utilizzare il connettore di origine di Analytics | [Acquisire e usare i dati dalla versione tradizionale di Adobe Analytics](/help/data-ingestion/analytics.md) | I dati di Adobe Analytics vengono mappati automaticamente sullo schema XDM quando utilizzi il connettore di origine di Analytics. Non è richiesta alcuna mappatura aggiuntiva. |

## Successivamente, conserva i dati storici

Successivamente, decidi come [conservare i dati storici di Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
