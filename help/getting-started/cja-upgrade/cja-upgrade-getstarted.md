---
title: Introduzione all’aggiornamento a Customer Journey Analytics
description: Pianificare l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: ht
source-wordcount: '715'
ht-degree: 100%

---

# Passaggio 1: introduzione all’aggiornamento a Customer Journey Analytics

>[!AVAILABILITY]
>
>Le informazioni contenute in questa pagina verranno sostituite dalle seguenti informazioni di aggiornamento più complete: <ul><li>**Passaggi di aggiornamento consigliati**<p>Per informazioni dettagliate, consulta [Percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guida per l’aggiornamento di Customer Journey Analytics**<p>È disponibile una nuova guida per l’aggiornamento che genera in modo dinamico passaggi di aggiornamento personalizzati per la situazione specifica della tua organizzazione.</p><p>Per accedere alla guida da Customer Journey Analytics, seleziona la scheda **[!UICONTROL Workspace]**, quindi seleziona **[!UICONTROL Upgrade to Customer Journey Analytics]** nel pannello a sinistra. Segui le istruzioni visualizzate sullo schermo.</p></li></ul>

Customer Journey Analytics è il prodotto di analisi di nuova generazione. Consente la raccolta dati multicanale (sia online che offline), combinata con potenti funzionalità di elaborazione al momento del rapporto (tramite la definizione di componenti e campi derivati nelle visualizzazioni dati).

Prima di iniziare il processo di aggiornamento da Adobe Analytics a Customer Journey Analytics, devi comprendere i vantaggi di Customer Journey Analytics e i passaggi necessari per completare correttamente l’aggiornamento.

## Comprendere i vantaggi di Customer Journey Analytics

Di seguito sono riportati alcuni dei vantaggi principali: (per un elenco completo e ulteriori informazioni su ciascuna di queste funzioni chiave, consulta [Funzioni disponibili solo in Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Generazione di rapporti multicanale](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics è combinato con la capacità di Experience Platform di contenere tutti i tipi e schemi di dati. Raccogli e genera rapporti su dati provenienti da più canali, ad esempio digitali (web), sistemi POS, dispositivi mobili, sistemi CRM e altro ancora.

* [Trasformazioni al momento del rapporto nelle visualizzazioni dati](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Le visualizzazioni dati in Customer Journey Analytics consentono di interpretare ulteriormente i dati da una connessione. Puoi modificare o rimuovere dati senza cambiare l’implementazione, utilizzare sottostringhe per manipolare le dimensioni, creare metriche da qualsiasi valore, segmentare gli eventi secondari o utilizzare campi derivati. Tutte queste trasformazioni sono non distruttive.

* [Le trasformazioni si applicano sia ai dati storici che ai nuovi dati](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  La manipolazione della visualizzazione dati può essere applicata sia ai dati storici che ai nuovi dati in modo non distruttivo.

* [Campi derivati](/help/data-views/derived-fields/derived-fields.md)

  I campi derivati consentono trasformazioni al momento dell’elaborazione del report. I dati possono essere combinati, corretti o creati immediatamente e si applicano retroattivamente a tutto il reporting.

* [Le visualizzazioni dati sostituiscono le suite di rapporti virtuali](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Le visualizzazioni dati riprendono il concetto delle suite di rapporti virtuali attuali e lo espandono per abilitare ulteriori controlli sui dati, messi a disposizione dalle connessioni. Con queste modifiche, impostazioni generali quali il fuso orario e gli intervalli di timeout della sessione diventano configurabili e retroattive.

* [Dimensioni e metriche illimitate per la clientela](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  I valori possono essere numerici, testo, oggetti, elenchi o combinazioni di questi. Le dimensioni possono essere nidificate o gerarchiche.

## Informazioni sul processo di aggiornamento

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
Le informazioni in questa pagina descrivono il passaggio 1 del processo di aggiornamento, come evidenziato nella tabella seguente. Completa tutti i passaggi di questa tabella per l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

| Attività di aggiornamento | Dettagli |
|---------|----------|
| <span class="preview">**Passaggio 1: introduzione all’aggiornamento**</span> | <span class="preview">Scopri i vantaggi dell’aggiornamento a Customer Journey Analytics e il processo di aggiornamento di base.</span> |
| **Passaggio 2: [scegli il percorso di aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Sono disponibili diversi metodi per l’aggiornamento a Customer Journey Analytics. Scegli il metodo migliore per l’organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine. |
| **Passaggio 3: [Inviare dati ad Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Il processo di invio dei dati ad Adobe Experience Platform varia a seconda del percorso di aggiornamento scelto nel passaggio 2. |
| **Passaggio 4: [Conserva i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 5: [Esegui ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di aggiornamento, devi eseguire varie attività prima che l’ambiente di Customer Journey Analytics sia pronto per l’uso.<p>Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni di Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Inserimento di altri dati in Experience Platform</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Conversione dell’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Pianificazione dell’onboarding degli utenti</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Scegliere innanzitutto il percorso di aggiornamento

Sono disponibili diversi metodi per l’aggiornamento a Customer Journey Analytics. [Scegli il metodo migliore per la tua organizzazione](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

La scelta del percorso di aggiornamento dipende dall’ambiente Adobe Analytics corrente e dagli obiettivi a lungo termine della tua organizzazione.
