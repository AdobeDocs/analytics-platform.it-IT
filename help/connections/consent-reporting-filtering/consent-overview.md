---
title: Panoramica sulla generazione di rapporti di consenso e sui filtri
description: Scopri come creare rapporti sull’iscrizione alla politica di consenso dei visitatori e filtrare i visitatori non consenzienti al momento dell’acquisizione in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 1058
ht-degree: 2%

---

# Panoramica sulla generazione di rapporti e sui filtri di consenso

La funzione di reporting e filtro del consenso utilizza i dati di iscrizione al criterio di consenso memorizzati nei set di dati del profilo Adobe Experience Platform per aiutarti a generare rapporti sul consenso dei visitatori e, facoltativamente, per escludere i visitatori non consenzienti prima che i loro dati vengano acquisiti in Customer Journey Analytics.

## Prerequisiti

Prima di configurare la generazione di rapporti e i filtri per il consenso, assicurati che:

* La tua organizzazione ha concesso la licenza ad Adobe Healthcare Shield o Privacy &amp; Security Shield.
* Si dispone delle autorizzazioni di amministratore di sistema in Customer Journey Analytics.
* La sandbox che desideri utilizzare contiene un set di dati profilo con dati di appartenenza ai criteri di consenso nel campo `consentPoliciesIDMap`.
* La connessione da configurare esiste già. Per ulteriori informazioni, vedere [Creare o modificare una connessione](/help/connections/create-connection.md).

Il diagramma seguente e la tabella associata mostrano una rappresentazione di alto livello del modo in cui la generazione rapporti e i filtri di consenso rendono i dati dei criteri di consenso disponibili in Analysis Workspace e filtrano i dati dei visitatori al momento dell’acquisizione:

![Panoramica sui report e i filtri del consenso](assets/consent-overview.png)

| Numero | Funzione | Funzione |
|---------|----------|---------|
| 1 | Configurazione di reporting e filtro del consenso | Interfaccia di configurazione in Customer Journey Analytics utilizzata per abilitare la generazione di rapporti sul consenso e, facoltativamente, il filtro del consenso. |
| 2 | Sandbox | Deve contenere il set di dati profilo che include i dati di iscrizione al criterio di consenso su cui desideri creare un rapporto. |
| 3 | Set di dati di profilo | Include i dati di iscrizione al criterio di consenso per ogni visitatore. L&#39;appartenenza ai criteri di consenso è archiviata nel campo `consentPoliciesIDMap` di un set di dati profilo. Questo set di dati profilo viene aggiunto alla connessione selezionata. <p>Nel profilo di ogni visitatore sono elencati i criteri di consenso corrispondenti al visitatore. Customer Journey Analytics legge questo campo per rendere i criteri di consenso disponibili per la generazione dei rapporti e per valutare quali visitatori includere durante l’acquisizione.</p> |
| 4 | Set di dati di ricerca dei criteri di consenso | Fornisce nomi descrittivi dei criteri e descrizioni per i rapporti. Il set di dati di ricerca viene creato automaticamente e mantenuto in sincronia con Experience Platform. Esiste un massimo di un set di dati di ricerca dei criteri di consenso per sandbox. |
| 5 | Connessione | La connessione in cui vengono applicati la segnalazione e il filtro del consenso. Tutte le visualizzazioni dati sotto la connessione ereditano la configurazione. |
| 6 | Componenti dei criteri di consenso | Nuove dimensioni, metriche e un campo derivato che rappresentano l’appartenenza ai criteri di consenso. Questi componenti vengono creati automaticamente e sono disponibili per il reporting in Analysis Workspace. |
| 7 | Filtro tempo di acquisizione | Quando il filtro è abilitato, i visitatori non consenzienti vengono esclusi durante l’acquisizione, in base alle azioni di marketing configurate. |

## Generazione di rapporti di consenso e filtro

La generazione di rapporti di consenso e il filtraggio sono due funzionalità separate. Puoi abilitare la segnalazione del consenso autonomamente oppure sia la segnalazione che il filtro insieme.

### Generazione di rapporti sul consenso

Quando abiliti la generazione rapporti di consenso, Customer Journey Analytics aggiunge un set di componenti dei criteri di consenso alle visualizzazioni dati nella connessione configurata. Questi componenti ti consentono di utilizzare Analysis Workspace per generare rapporti sui visitatori che corrispondono ai vari criteri di consenso, utilizzando i dati di iscrizione ai criteri di consenso nei set di dati del profilo di Experience Platform.

Per mantenere leggibile il reporting, Customer Journey Analytics sincronizza i nomi e le descrizioni dei criteri da Experience Platform in un set di dati di ricerca dei criteri di consenso. Quando un criterio viene creato, aggiornato, rinominato o eliminato in Experience Platform, il set di dati di ricerca viene aggiornato automaticamente.

Per informazioni sui componenti creati dal reporting del consenso, vedi [Analizzare i dati dei criteri di consenso](/help/connections/consent-reporting-filtering/consent-analyze.md).

### Filtro del consenso

>[!IMPORTANT]
>
>I dati di consenso esclusi non vengono memorizzati in Customer Journey Analytics e non possono essere recuperati per le date precedenti aggiornando la configurazione.

Quando abiliti il filtro del consenso, Customer Journey Analytics esclude i visitatori non consenzienti al momento del caricamento. Poiché il filtro si verifica al momento del caricamento, i dati per i visitatori esclusi non entrano mai in Customer Journey Analytics e non è disponibile per il reporting.

Quando utilizzi il filtro del consenso, tieni presente quanto segue:

* Customer Journey Analytics determina i criteri di consenso applicabili alle azioni di marketing configurate.

  Un’azione di marketing rappresenta una categoria di utilizzo dei dati. Customer Journey Analytics determina quali criteri di consenso si applicano a ogni azione di marketing e abiliti il filtro per ogni azione di marketing in modo indipendente durante la [creazione della configurazione](/help/connections/consent-reporting-filtering/consent-configure.md#create-a-configuration).

  | Azione di marketing | Descrizione |
  |---------|----------|
  | **[!UICONTROL Analytics]** | Generazione di rapporti standard su Customer Journey Analytics in Analysis Workspace. |
  | **[!UICONTROL Data science]** | Casi d’uso avanzati di analisi, apprendimento automatico e scienza dei dati. |

* I dati di un visitatore vengono acquisiti solo se il visitatore corrisponde a **tutti** i criteri di consenso applicabili. Se a un visitatore mancano i criteri applicabili, i dati del visitatore vengono esclusi.

## Configurare i rapporti e i filtri di consenso

Quando configuri la generazione rapporti e i filtri per il consenso, seleziona la sandbox e il set di dati profilo che contengono i dati di iscrizione ai criteri di consenso, scegli la connessione o le connessioni da configurare e scegli se filtrare i dati per ogni azione di marketing. Customer Journey Analytics crea quindi automaticamente il set di dati di ricerca dei criteri di consenso e i componenti dei criteri di consenso.

Per ulteriori informazioni, consulta [Configurare la generazione di rapporti e il filtro per il consenso](/help/connections/consent-reporting-filtering/consent-configure.md).

## Gestione delle configurazioni di reporting e filtro del consenso

Puoi gestire le configurazioni di reporting e filtro del consenso dopo averle create. Puoi visualizzare, modificare ed eliminare le configurazioni.

Per informazioni sulla gestione delle configurazioni esistenti, consulta [Gestire le configurazioni di reporting e filtro del consenso](/help/connections/consent-reporting-filtering/consent-manage.md).

## Analizzare i dati dei criteri di consenso

Con i dati dei criteri di consenso disponibili in Customer Journey Analytics, puoi creare rapporti su quali visitatori corrispondono ai criteri di consenso e utilizzare quell’insight per comprendere i tipi di pubblico consenzienti nei tuoi rapporti.

Per ulteriori informazioni, consulta [Analizzare i dati dei criteri di consenso](/help/connections/consent-reporting-filtering/consent-analyze.md).

## Ruolo di reporting e filtro del consenso e requisiti di autorizzazione

Per la generazione di rapporti e filtri sul consenso sono necessari i seguenti ruoli Customer Journey Analytics e autorizzazioni Experience Platform:

| Funzionalità | Requisiti del ruolo o delle autorizzazioni di Customer Journey Analytics | Requisiti delle autorizzazioni di Experience Platform |
|---------|----------|----------|
| [Creare configurazioni di reporting e filtro del consenso](/help/connections/consent-reporting-filtering/consent-configure.md) | Amministratore di sistema | <ul><li>Set di dati: lettura, scrittura</li><li>Schemi: lettura, scrittura</li></ul> <p>L’accesso in lettura è necessario per il set di dati profilo che contiene i dati di appartenenza ai criteri di consenso. È necessario l’accesso in scrittura perché viene creato e mantenuto sincronizzato un set di dati di ricerca dei criteri di consenso.</p> |
| Visualizzare i componenti dei criteri di consenso nella visualizzazione dati | Amministratore del profilo di prodotto per il profilo di prodotto a cui è assegnata la visualizzazione dati <p>Per ulteriori informazioni, vedere [Controllo degli accessi](/help/technotes/access-control.md).</p> | N/D |
| Utilizzare i componenti dei criteri di consenso in Analysis Workspace | Accesso a una visualizzazione dati in cui sono stati aggiunti i componenti del criterio di consenso | N/D |

## Casi d’uso di reporting e filtraggio del consenso

Ad esempio, casi d&#39;uso che evidenziano il valore fornito dalla generazione rapporti e filtri di consenso, vedi [Casi d&#39;uso relativi a segnalazioni e filtri di consenso](/help/connections/consent-reporting-filtering/consent-use-cases.md).

## Segnalazione del consenso e limiti di filtro

Considera i seguenti limiti durante la [configurazione della generazione di rapporti e filtri per il consenso](/help/connections/consent-reporting-filtering/consent-configure.md):

* Una singola sandbox può avere un solo set di dati di ricerca dei criteri di consenso. Più configurazioni nello stesso set di dati di ricerca condividono tale set di dati.

* Una connessione può essere associata a una sola configurazione di reporting e filtro del consenso.
