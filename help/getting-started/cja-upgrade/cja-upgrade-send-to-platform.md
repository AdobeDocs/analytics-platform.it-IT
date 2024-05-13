---
title: Inviare i dati ad Adobe Experience Platform durante la migrazione a Customer Journey Analytics
description: Inviare i dati ad Adobe Experience Platform durante la migrazione a Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 6cceeaa3b57808a82012b124435aa1b7dbf1b3f2
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 68%

---

# Passaggio 3: inviare dati a Adobe Experience Platform durante l&#39;aggiornamento

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di aggiornamento più ampio. Assicurati che tutti i passaggi precedenti dell’aggiornamento siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di aggiornamento precedenti.

Le informazioni contenute in questa pagina descrivono il passaggio 3 del processo di aggiornamento, come evidenziato nella tabella seguente:

| Attività di aggiornamento | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione all’aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Scopri i vantaggi dell’aggiornamento al Customer Journey Analytics e la procedura di aggiornamento di base. |
| **Passaggio 2: [Scegli il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Sono disponibili diversi metodi per l&#39;aggiornamento al Customer Journey Analytics. Scegli il metodo migliore per l’organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| <span class="preview">**Passaggio 3: inviare i dati ad Adobe Experience Platform**</span> | <span class="preview">Il processo di invio dei dati a Adobe Experience Platform varia a seconda del percorso di aggiornamento scelto nel passaggio 2.</span> |
| **Passaggio 4: [Conserva i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 5: [Esegui ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di aggiornamento, è necessario eseguire varie attività prima che l&#39;ambiente del Customer Journey Analytics sia pronto per l&#39;uso.<p>Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Inserimento di altri dati in Experience Platform</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Conversione dell’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Pianificazione dell’onboarding degli utenti</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++


Dopo di te [scegli il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md) questo è meglio per la tua organizzazione, puoi iniziare a inviare dati a Adobe Experience Platform per renderli disponibili in Customer Journey Analytics.

La procedura per l’invio dei dati all’Experience Platform per ogni percorso di aggiornamento è illustrata di seguito. Per informazioni dettagliate sulla configurazione, segui i collegamenti riportati nella tabella.

| Percorso di aggiornamento | Processo per inviare i dati a Platform | Informazioni aggiuntive |
|---------|----------|----------|
| Nuova implementazione di Experience Platform Web SDK | <ol><li>Creare uno schema XDM per l’organizzazione.<p>Collabora con il team di dati per progettare lo schema per Customer Journey Analytics ideale per la tua organizzazione.</p></li><li>Implementa Experience Platform Web SDK.</li><li>Inviare i dati a Platform.</li></ol><p>Per informazioni dettagliate su ciascuno di questi passaggi, consulta [Acquisire i dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md). | Poiché si tratta di una nuova implementazione di Experience Platform Web SDK, la mappatura dello schema non è necessaria, in quanto è necessario creare lo schema come uno dei primi passaggi durante l’implementazione. |
| Migrare l’implementazione di Adobe Analytics per utilizzare Web SDK | <ol><li>Sposta l’implementazione di Adobe Analytics esistente in Experience Platform Web SDK, quindi verifica che tutto funzioni in Adobe Analytics.<p>Per informazioni su come eseguire questa operazione, utilizza le risorse seguenti, a seconda che l’implementazione corrente sia l’estensione del tag di Analytics o AppMeasurement:</p><ul><li>Se utilizzi l’estensione del tag di Analytics, consulta [Migrare dall’estensione del tag di Adobe Analytics all’estensione del tag di Web SDK](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Se utilizzi AppMeasurement, consulta [Migrare da AppMeasurement a Web SDK](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Creare uno schema XDM per l’organizzazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Collabora con il team di dati per progettare lo schema per Customer Journey Analytics ideale per la tua organizzazione.</p></li><li>[Utilizza la preparazione dati per mappare tutti i campi nell’oggetto dati sullo schema XDM](https://experienceleague.adobe.com/it/docs/experience-platform/data-prep/home).</li><li>Inizia ad inviare i dati a Platform [impostando uno stream di dati](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configurare l’implementazione di Adobe Analytics Web SDK esistente per inviare i dati a Customer Journey Analytics | <ol><li>Inizia ad inviare i dati a Platform [impostando uno stream di dati](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).<p>Poiché l’implementazione di Adobe Analytics utilizza già Experience Platform Web SDK, puoi ignorare le altre sezioni in [Acquisire i dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</p><p>Se invii già dati a Platform con la tua implementazione di Adobe Analytics, questo passaggio non è necessario. È sufficiente creare una connessione tra i set di dati di Platform e il Customer Journey Analytics, come descritto più avanti in questa procedura.</p></li><li>(Facoltativo) [Creare uno schema XDM per l’organizzazione](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Collabora con il team di dati per progettare lo schema per Customer Journey Analytics ideale per la tua organizzazione.</p><p>Nota: per informazioni sui vantaggi della creazione di uno schema XDM, consulta [Scegli lo schema](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Condizionale) Se hai creato uno schema XDM, [utilizza la preparazione dati per mappare tutti i campi nell’oggetto dati sullo schema XDM](https://experienceleague.adobe.com/it/docs/experience-platform/data-prep/home).</li></ol> |
| Utilizzare il connettore di origine di Analytics | [Inserire e usare i dati dalla versione tradizionale di Adobe Analytics](/help/data-ingestion/analytics.md) | I dati di Adobe Analytics vengono mappati automaticamente sullo schema XDM quando si utilizza il connettore di origine di Analytics. Non è richiesta alcuna mappatura aggiuntiva. |

## Successivamente, conserva i dati storici

Successivamente, decidi come [conservare i dati storici di Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
