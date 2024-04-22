---
title: Introduzione alla migrazione al Customer Journey Analytics
description: Pianificare la migrazione da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a23322ab189e6469783a179e2de7aa0195eda737
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 8%

---

# Passaggio 1: introduzione alla migrazione al Customer Journey Analytics

Il Customer Journey Analytics è la nuova generazione di analisi. Consente la raccolta dati multicanale (sia online che offline), combinata con potenti funzionalità di elaborazione al momento del reporting (tramite la definizione di componenti e campi derivati nelle visualizzazioni dati).

Prima di iniziare la migrazione da Adobe Analytics al Customer Journey Analytics, è necessario comprendere i vantaggi del Customer Journey Analytics e i passaggi necessari per completare correttamente la migrazione.

## Comprendere i vantaggi del Customer Journey Analytics

Di seguito sono riportati alcuni dei vantaggi principali: (per un elenco completo e ulteriori informazioni su ciascuna di queste funzioni chiave, consulta [Funzioni disponibili solo nel Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Reporting multicanale](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics è combinato con la capacità di Experience Platform di contenere tutti i tipi di schemi e tipi di dati. Raccogli e genera rapporti su dati provenienti da più canali, ad esempio digitali (web), sistemi POS, mobili, sistemi CRM e altro ancora.

* [Trasformazioni al momento del reporting nelle visualizzazioni dati](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Le visualizzazioni dati in Customer Journey Analytics consentono di interpretare ulteriormente i dati di una connessione. Puoi modificare o rimuovere dati senza modificare l’implementazione, utilizzare sottostringhe per manipolare le dimensioni, creare metriche da qualsiasi valore, filtrare eventi secondari o utilizzare campi derivati. Tutte queste trasformazioni non sono distruttive.

* [Le trasformazioni si applicano ai dati storici e ai nuovi dati](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  La manipolazione della visualizzazione dati può essere applicata sia ai dati storici che a quelli nuovi in modo non distruttivo.

* [Campi derivati](/help/data-views/derived-fields/derived-fields.md)

  I campi derivati consentono trasformazioni al momento dell’elaborazione del report. I dati possono essere combinati, corretti o creati immediatamente e si applicano retroattivamente a tutto il reporting.

* [Le visualizzazioni dati sostituiscono le suite di rapporti virtuali](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Le visualizzazioni dati adottano il concetto delle attuali suite di rapporti virtuali e lo espandono per abilitare ulteriori controlli sui dati resi disponibili dalle connessioni. Con queste modifiche, impostazioni generali quali fuso orario e intervalli di timeout della sessione diventano configurabili e retroattive.

* [Dimensioni e metriche cliente illimitate](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  I valori possono essere numerici, testo, oggetti, elenchi o combinazioni di tutti. I Dimension possono essere nidificati o gerarchici.

## Comprendere il processo di migrazione

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Questa pagina rappresenta il passaggio 1 della migrazione, come illustrato nella tabella seguente. Completa tutti i passaggi descritti in questa tabella per migrare da Adobe Analytics a Customer Journey Analytics.

| Attività | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione alla migrazione](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Scopri i vantaggi della migrazione ad Adobe Analytics e il processo di migrazione di base. |
| **Passaggio 2: [Scegli il metodo di migrazione](/help/getting-started/cja-migration/cja-migration-method.md)** | Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del metodo di migrazione scelto nel passaggio 1. |
| **Passaggio 4: [Pianificare la mappatura dei dati sullo schema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Schemi XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) vengono utilizzati in Adobe Experience Platform per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i sistemi, diventa più semplice mantenere un significato e quindi ottenere valore dai dati.<p>La maggior parte dei metodi di migrazione richiede la creazione di un nuovo schema XDM o la mappatura dello schema Adobe Analytics esistente su XDM tramite la mappatura dello stream di dati.</p> |
| **Passaggio 5: [Conserva dati storici](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 6: [Pianificare l’onboarding degli utenti](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Dovresti dare agli utenti un periodo di tempo sufficiente (3 - 6 mesi) per familiarizzare con le differenze chiave di Analysis Workspace nel Customer Journey Analytics. |
| **Passaggio 7: [Porta l’utilizzo dell’API di reporting](/help/getting-started/cja-migration/cja-migration-api.md)** | L’API di reporting del Customer Journey Analytics è nello stesso formato, ma utilizza un endpoint diverso. Porta l’utilizzo dell’API di reporting dall’API di reporting di Adobe Analytics all’API di reporting di Customer Journey Analytics. |
| **Passaggio 8: [Sostituire feed dati e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decidi come utilizzare le opzioni di esportazione disponibili in Customer Journey Analytics per sostituire le funzioni Feed dati e Data Warehouse che stavi utilizzando in Adobe Analytics. |
| **Passaggio 9: [Eseguire la migrazione di progetti e componenti](/help/getting-started/cja-migration/cja-migration-projects.md)** | L’area di migrazione dei componenti in Adobe Analytics consente di migrare i progetti e i relativi componenti associati da Adobe Analytics al Customer Journey Analytics. |

{style="table-layout:auto"}

## Scegli innanzitutto il metodo di migrazione

Sono disponibili diversi metodi per la migrazione al Customer Journey Analytics. [Scegli il metodo migliore per la tua organizzazione](/help/getting-started/cja-migration/cja-migration-method.md).

Il metodo di migrazione scelto dipende dall’ambiente Adobe Analytics corrente della tua organizzazione e dagli obiettivi a lungo termine.