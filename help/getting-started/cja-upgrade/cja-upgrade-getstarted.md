---
title: Introduzione all’aggiornamento al Customer Journey Analytics
description: Pianifica l’aggiornamento da Adobe Analytics al Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 10%

---

# Passaggio 1: introduzione all’aggiornamento al Customer Journey Analytics

Il Customer Journey Analytics è la nuova generazione di analisi. Consente la raccolta dati multicanale (sia online che offline), combinata con potenti funzionalità di elaborazione al momento del reporting (tramite la definizione di componenti e campi derivati nelle visualizzazioni dati).

Prima di iniziare il processo di aggiornamento da Adobe Analytics a Customer Journey Analytics, è necessario comprendere i vantaggi del Customer Journey Analytics e i passaggi necessari per il corretto aggiornamento.

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

## Comprendere il processo di aggiornamento

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Le informazioni contenute in questa pagina descrivono il passaggio 1 del processo di aggiornamento, come evidenziato nella tabella seguente. Completa tutti i passaggi descritti in questa tabella per eseguire l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

| Attività di aggiornamento | Dettagli |
|---------|----------|
| <span class="preview">**Passaggio 1: introduzione all’aggiornamento**</span> | <span class="preview">Scopri i vantaggi dell’aggiornamento al Customer Journey Analytics e la procedura di aggiornamento di base.</span> |
| **Passaggio 2: [Scegli il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Sono disponibili diversi metodi per l&#39;aggiornamento al Customer Journey Analytics. Scegli il metodo migliore per la tua organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati a Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del percorso di aggiornamento scelto nel passaggio 2. |
| **Passaggio 4: [Conserva dati storici](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 5: [Eseguire ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di aggiornamento, è necessario eseguire varie attività prima che l&#39;ambiente del Customer Journey Analytics sia pronto per l&#39;uso.<p>Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Experience Platform di altri dati</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Portare l’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Onboarding degli utenti di Planning</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva al Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Scegli innanzitutto il percorso di aggiornamento

Sono disponibili diversi metodi per l&#39;aggiornamento al Customer Journey Analytics. [Scegli il metodo migliore per la tua organizzazione](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

Il percorso di aggiornamento scelto dipende dall’ambiente Adobe Analytics corrente della tua organizzazione e dagli obiettivi a lungo termine.
