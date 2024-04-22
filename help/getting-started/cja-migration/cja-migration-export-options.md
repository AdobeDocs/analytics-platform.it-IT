---
title: Sostituisci feed di dati e Data Warehouse durante la migrazione al Customer Journey Analytics
description: Pianificare la migrazione da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# Passaggio 8: sostituire feed di dati e Data Warehouse durante la migrazione al Customer Journey Analytics

+++Le informazioni contenute in questa pagina fanno parte di un processo di migrazione più ampio. Espandi questa sezione per vedere dove si inseriscono queste informazioni nel processo di migrazione. </br></br>Prima di continuare con le informazioni presenti in questa pagina, è necessario completare tutti i passaggi precedenti della migrazione.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di migrazione precedenti.

Le informazioni in questa pagina riguardano il Passaggio 8, come evidenziato nella tabella seguente:

| Attività di migrazione | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| **Passaggio 2: [Scegli il metodo di migrazione](/help/getting-started/cja-migration/cja-migration-method.md)** | Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del metodo di migrazione scelto nel passaggio 1. |
| **Passaggio 4: [Pianificare la mappatura dei dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei metodi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p> |
| **Passaggio 5: [Conserva dati storici](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 6: [Pianificare l’onboarding degli utenti](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics. |
| **Passaggio 7: [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| <span class="preview">**Passaggio 8: [Sostituire feed dati e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per sostituire le funzioni Feed dati e Data Warehouse che stavi utilizzando in Adobe Analytics.</span> |
| **Passaggio 9: [Eseguire la migrazione di progetti e componenti](/help/getting-started/cja-migration/cja-migration-projects.md)** | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Se al momento utilizzi feed di dati o Data Warehouse in Adobe Analytics, utilizza la tabella seguente per scoprire le varie opzioni di esportazione disponibili in Customer Journey Analytics:

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| Feed dati | Valuta i casi di utilizzo dei feed di dati, quindi utilizza qualsiasi combinazione di metodi di esportazione alternativi disponibili in Customer Journey Analytics: <ul><li>Per esportare i set di dati non elaborati: [esportare i set di dati nelle destinazioni dell’archiviazione cloud](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets).&#x200B;</li><li>Per le esportazioni a livello di pubblico o di evento utilizzando l’ID persona o la marca temporale, utilizza [Esportazione tabella completa](/help/analysis-workspace/export/export-cloud.md).&#x200B;</li><li>Per l’integrazione diretta con Power BI e Tableau, utilizza [Estensione Customer Journey Analytics BI](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension).&#x200B;</li><li>Per l&#39;accesso diretto SQL ai dati in Adobe Experience Platform, utilizzare [Servizio query Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | Modificare le esportazioni di Adobe Analytics Data Warehouse da utilizzare [Esportazione tabella completa](/help/analysis-workspace/export/export-cloud.md) nel Customer Journey Analytics.<p>Esportazione tabella completa Customer Journey Analytics è l’evoluzione dei rapporti Data Warehouse in Adobe Analytics, con molte nuove funzioni spesso richieste che oggi non sono disponibili in Data Warehouse.</p> |

{style="table-layout:auto"}

## Quindi, esegui la migrazione di progetti e componenti.

Utilizza l’area di migrazione dei componenti in Adobe Analytics per: [migrazione di progetti e dei relativi componenti associati](/help/getting-started/cja-migration/cja-migration-projects.md) da Adobe Analytics a Customer Journey Analytics.
