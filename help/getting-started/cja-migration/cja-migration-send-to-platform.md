---
title: Invia dati a Adobe Experience Platform durante la migrazione al Customer Journey Analytics
description: Invia dati a Adobe Experience Platform durante la migrazione al Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 1%

---

# Passaggio 3: inviare dati a Adobe Experience Platform durante la migrazione al Customer Journey Analytics

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di migrazione più ampio. Assicurati che tutti i passaggi di migrazione precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di migrazione precedenti.

Le informazioni in questa pagina riguardano il Passaggio 3, come evidenziato nella tabella seguente:

| Attività di migrazione | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| **Passaggio 2: [Scegli il metodo di migrazione](/help/getting-started/cja-migration/cja-migration-method.md)** | Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| <span class="preview">**Passaggio 3: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">Il processo di invio dei dati a Adobe Experience Platform varia a seconda del metodo di migrazione scelto nel passaggio 1.</span> |
| **Passaggio 4: [Mappare i dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei metodi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p> |
| **Passaggio 5: [Conserva dati storici](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 6: [Pianificare l’onboarding degli utenti](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics. |
| **Passaggio 7: [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| **Passaggio 8: [Sostituire feed dati e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per sostituire le funzioni Feed dati e Data Warehouse che stavi utilizzando in Adobe Analytics. |
| **Passaggio 9: [Eseguire la migrazione di progetti e componenti](/help/getting-started/cja-migration/cja-migration-projects.md)** | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics. |

{style="table-layout:auto"}

+++


Dopo di te [scegli il metodo di migrazione](#step-2-choose-your-customer-journey-analytics-migration-method) questo è meglio per la tua organizzazione, puoi iniziare a inviare dati a Adobe Experience Platform per renderli disponibili in Customer Journey Analytics.

Di seguito è illustrata la procedura per l’invio dei dati all’Experienci Platform per ciascun metodo di migrazione. Per informazioni più dettagliate, consulta i collegamenti nella tabella seguente.

| Metodo di migrazione | Processo per l’invio di dati a Platform |
|---------|----------|
| Nuova implementazione del Web SDK | [Inserire dati tramite Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) |
| Migrare l’implementazione di Adobe Analytics per utilizzare l’SDK per web | Se utilizzi l’estensione tag Analytics: [Migrare dall’estensione tag Adobe Analytics all’estensione tag Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)<p>Oppure</p><p>Se utilizzi AppMeasurement: [Migrare da AppMeasurement a Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| Configura l’implementazione Adobe Analytics Web SDK esistente per inviare dati al Customer Journey Analytics | [Configurare un flusso di dati](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream) in [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) |
| Connettore di origine di Analytics | [Inserire e usare i dati dalla versione tradizionale di Adobe Analytics](/help/data-ingestion/analytics.md) |

## Quindi, mappa i dati sullo schema XDM.

Dopo aver inviato i dati a Experienci Platform seguendo i collegamenti nella tabella precedente, potrebbe essere necessario [mappare i dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md), a seconda del metodo di implementazione scelto.

I seguenti metodi di implementazione richiedono il mapping dei dati allo schema XDM:

* Migrare dall’estensione tag Adobe Analytics all’estensione tag Web SDK

* Configura l’implementazione Adobe Analytics Web SDK esistente per inviare dati al Customer Journey Analytics

In alternativa, se scegli di eseguire una nuova implementazione dell’SDK per web, non è necessario eseguire una mappatura in quanto è già stato [configurare un nuovo schema XDM](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) come parte della nuova implementazione.

Se hai scelto di utilizzare il connettore di origine di Analytics per la migrazione, non è necessario effettuare una mappatura in quanto il connettore di origine di Analytics utilizza lo schema Adobe Analytics esistente anziché lo schema XDM.
