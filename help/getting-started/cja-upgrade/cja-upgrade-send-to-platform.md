---
title: Invia dati a Adobe Experience Platform durante la migrazione al Customer Journey Analytics
description: Invia dati a Adobe Experience Platform durante la migrazione al Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 1%

---

# Passaggio 3: inviare dati a Adobe Experience Platform durante l&#39;aggiornamento

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di aggiornamento più ampio. Assicurati che tutti i passaggi precedenti dell’aggiornamento siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di aggiornamento precedenti.

Le informazioni contenute in questa pagina descrivono il passaggio 3 del processo di aggiornamento, come evidenziato nella tabella seguente:

| Attività di aggiornamento | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione all’aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Scopri i vantaggi dell’aggiornamento al Customer Journey Analytics e la procedura di aggiornamento di base. |
| **Passaggio 2: [Scegli il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Sono disponibili diversi metodi per l&#39;aggiornamento al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| <span class="preview">**Passaggio 3: inviare dati a Adobe Experience Platform**</span> | <span class="preview">Il processo di invio dei dati a Adobe Experience Platform varia a seconda del percorso di aggiornamento scelto nel passaggio 2.</span> |
| **Passaggio 4: [Conserva dati storici](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 5: [Eseguire ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di aggiornamento, è necessario eseguire varie attività prima che l&#39;ambiente del Customer Journey Analytics sia pronto per l&#39;uso.<p>Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Experience Platform di altri dati</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Portare l’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Onboarding degli utenti di Planning</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva al Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++


Dopo di te [scegli il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md) questo è meglio per la tua organizzazione, puoi iniziare a inviare dati a Adobe Experience Platform per renderli disponibili in Customer Journey Analytics.

La procedura per l’invio dei dati all’Experience Platform per ogni percorso di aggiornamento è illustrata di seguito. Per informazioni dettagliate sulla configurazione, segui i collegamenti riportati nella tabella.

| Percorso di aggiornamento | Processo per l’invio di dati a Platform | Informazioni aggiuntive |
|---------|----------|----------|
| Nuova implementazione di Experienci Platform Web SDK | <ol><li>Crea uno schema XDM per la tua organizzazione.<p>Collabora con il tuo team di dati per identificare la progettazione dello schema ideale per il Customer Journey Analytics per la tua organizzazione.</p></li><li>Implementa l’SDK per web di Experienci Platform.</li><li>Invia dati a Platform.</li></ol><p>Per informazioni dettagliate su ciascuno di questi passaggi, consulta [Inserire dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md). | Poiché si tratta di una nuova implementazione di Experienci Platform Web SDK, la mappatura dello schema non è necessaria, in quanto è necessario creare lo schema come uno dei primi passaggi durante l’implementazione. |
| Migrare l’implementazione di Adobe Analytics per utilizzare l’SDK per web | <ol><li>Sposta l’implementazione Adobe Analytics esistente nell’SDK per web di Experienci Platform, quindi verifica che tutto funzioni in Adobe Analytics.<p>Per informazioni su come eseguire questa operazione, utilizza le risorse seguenti, a seconda che l’implementazione corrente sia l’estensione o l’AppMeasurement di tag Analytics:</p><ul><li>Se utilizzi l’estensione tag Analytics, consulta [Migrare dall’estensione tag Adobe Analytics all’estensione tag Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Se utilizzi AppMeasurement, consulta [Migrare da AppMeasurement a Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Creare uno schema XDM per l’organizzazione](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Collabora con il tuo team di dati per identificare la progettazione dello schema ideale per il Customer Journey Analytics per la tua organizzazione.</p></li><li>[Utilizza Preparazione dati per mappare tutti i campi nell’oggetto dati sullo schema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>Inizio dell’invio dei dati a Platform entro il [impostazione di un flusso di dati](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configura l’implementazione Adobe Analytics Web SDK esistente per inviare dati al Customer Journey Analytics | <ol><li>Inizio dell’invio dei dati a Platform entro il [impostazione di un flusso di dati](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).<p>Poiché la tua implementazione di Adobe Analytics utilizza già Experienci Platform Web SDK, puoi ignorare le altre sezioni in [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</li><li>(Facoltativo) [Creare uno schema XDM per l’organizzazione](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Collabora con il tuo team di dati per identificare la progettazione dello schema ideale per il Customer Journey Analytics per la tua organizzazione.</p><p>Nota: per informazioni sui vantaggi della creazione di uno schema XDM, consulta [Scegli lo schema](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Condizionale) Se hai creato uno schema XDM, [utilizza la preparazione dati per mappare tutti i campi nell’oggetto dati sullo schema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |
| Utilizzare il connettore di origine di Analytics | [Inserire e usare i dati dalla versione tradizionale di Adobe Analytics](/help/data-ingestion/analytics.md) | I dati di Adobe Analytics vengono mappati automaticamente allo schema XDM quando si utilizza il connettore di origine di Analytics. Non è richiesta alcuna mappatura aggiuntiva. |

## Quindi, conserva i dati storici

Quindi, decidi come [conservazione dei dati storici Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).