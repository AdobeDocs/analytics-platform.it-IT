---
title: Mappa i dati sullo schema XDM durante la migrazione al Customer Journey Analytics
description: Scopri come mappare i dati sullo schema XDM durante la migrazione al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 0%

---

# Passaggio 4: mappare i dati sullo schema XDM durante la migrazione al Customer Journey Analytics

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di migrazione più ampio. Assicurati che tutti i passaggi di migrazione precedenti siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di migrazione precedenti.

Le informazioni in questa pagina riguardano il Passaggio 4, come evidenziato nella tabella seguente:

| Attività di migrazione | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| **Passaggio 2: [Scegli il percorso di migrazione](/help/getting-started/cja-migration/cja-migration-path.md)** | Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| <span class="preview">**Passaggio 3: [Mappare i dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei percorsi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p></span> |
| **Passaggio 4: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del percorso di migrazione scelto nel passaggio 2. |
| **Passaggio 5: [Conserva dati storici](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 6: [Pianificare l’onboarding degli utenti](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics. |
| **Passaggio 7: [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| **Passaggio 8: [Sostituire feed dati e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per sostituire le funzioni Feed dati e Data Warehouse che stavi utilizzando in Adobe Analytics. |
| **Passaggio 9: [Eseguire la migrazione di progetti e componenti](/help/getting-started/cja-migration/cja-migration-projects.md)** | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics. |

{style="table-layout:auto"}

+++

[Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei percorsi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p>

Non tutti i percorsi di migrazione richiedono la mappatura dei dati di Adobe Analytics sullo schema XDM. La tabella seguente mostra quali metodi di implementazione richiedono la mappatura dello schema XDM:


| Percorso di migrazione | È richiesta la mappatura XDM? | Ulteriori informazioni |
|---------|----------|---------|
| **Nuova implementazione di Experienci Platform Web SDK**<p>I passaggi di base sono i seguenti:</p><ol><li>Creare uno schema XDM per l’organizzazione</li><li>Implementare l’SDK per web</li><li>Inviare dati a Platform</li></ol> | No | Non è richiesta alcuna mappatura perché hai già [configurare un nuovo schema XDM](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) come parte della nuova implementazione. |
| **Migrare l’implementazione di Adobe Analytics per utilizzare l’SDK per web**<p>I passaggi di base sono i seguenti:</p><ol><li>Sposta l’implementazione Adobe Analytics esistente nell’SDK per web e verifica che tutto funzioni lì.</li><li>Crea uno schema XDM per la tua organizzazione non appena hai tempo.</li><li>Utilizza la mappatura dello stream di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.</li><li>Inviare dati a Platform</li></ol> | Sì | Lavorando con il team di dati, identifica la progettazione dello schema ideale per il Customer Journey Analytics della tua organizzazione, quindi determina come mappare eVar e proprietà su XDM.</br>[Utilizza Preparazione dati per mappare tutti i campi nell’oggetto dati sullo schema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Configura l’implementazione Adobe Analytics Web SDK esistente per inviare dati al Customer Journey Analytics**<p>I passaggi di base sono i seguenti:</p><ol><li>Inizia a inviare dati al Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Facoltativo) Crea uno schema XDM per la tua organizzazione non appena hai tempo.</li><li>Utilizza la mappatura dello stream di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.</li></ol> | Sì | Lavorando con il team di dati, identifica la progettazione dello schema ideale per il Customer Journey Analytics della tua organizzazione, quindi determina come mappare eVar e proprietà su XDM.</br>[Utilizza Preparazione dati per mappare tutti i campi nell’oggetto dati sullo schema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Connettore di origine di Analytics**</br> Se la tua implementazione di Adobe Analytics è AppMeasurement o l’estensione Analytics, puoi iniziare a inviare dati a una visualizzazione dati nel Customer Journey Analytics.<p>Questo è il modo più semplice per portare i dati al Customer Journey Analytics, ma è il metodo meno efficace a lungo termine.</p> | No | Non è richiesta alcuna mappatura perché il connettore di origine di Analytics utilizza lo schema Adobe Analytics esistente anziché lo schema XDM. |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## Quindi, invia i dati a Adobe Experience Platform

Dopo aver utilizzato le informazioni precedenti per scegliere un percorso di migrazione, scopri come [inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) a seconda del percorso di migrazione scelto.
