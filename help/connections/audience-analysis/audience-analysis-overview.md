---
title: Panoramica dell’analisi del pubblico
description: Scopri come analizzare i tipi di pubblico da RTCDP in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 2b91c0592ac4ec0e0b5ffa3db91758466563abaf
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 4%

---

# Panoramica dell’analisi del pubblico

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md and this article: /help/analysis-workspace/templates/use-templates.md-->

>[!NOTE]
>
>L’analisi del pubblico è diversa dalla pubblicazione del pubblico, che consente di creare e pubblicare su Adobe Experience Platform i tipi di pubblico rilevati in Customer Journey Analytics per la personalizzazione e il targeting dei clienti. Per informazioni sulla pubblicazione di tipi di pubblico, vedere [Panoramica sulla pubblicazione di tipi di pubblico](/help/components/audiences/audiences-overview.md).

L’analisi del pubblico consente di acquisire i dati sull’iscrizione del pubblico dai set di dati del profilo di Experience Platform in una connessione Customer Journey Analytics. I tipi di pubblico diventano disponibili come nuove dimensioni da utilizzare in Analysis Workspace.

Il diagramma seguente e la tabella associata mostrano una rappresentazione di alto livello del modo in cui una configurazione di analisi del pubblico in Customer Journey Analytics rende disponibili i dati sul pubblico di Experience Platform in Analysis Workspace:

![Panoramica dell&#39;analisi del pubblico](assets/audience-analysis-overview.png)

| Numero | Funzione | Funzione |
|---------|----------|---------|
| 1 | Configurazione dell’analisi del pubblico | Interfaccia di configurazione in Customer Journey Analytics utilizzata per configurare l’analisi del pubblico. |
| 2 | Sandbox | Deve contenere il set di dati profilo che desideri aggiungere alla connessione. |
| 3 | Set di dati di profilo | Deve includere i dati sul pubblico di Experience Platform che desideri analizzare. Questo set di dati profilo viene aggiunto alla connessione selezionata. |
| 4 | Criterio di unione | Il criterio di unione associato ai tipi di pubblico di Experience Platform che desideri analizzare. |
| 5 | Dati profilo | I dati di profilo associati al criterio di unione selezionato. Questi dati sono disponibili nei set di dati di Experience Platform. |
| 6 | Nuovo set di dati di ricerca | Fornisce nomi descrittivi per le nuove dimensioni pubblico create. Il set di dati di ricerca viene creato e aggiunto automaticamente alla connessione, insieme al set di dati profilo selezionato. |
| 7 | Connessione | La connessione in cui desideri aggiungere il set di dati profilo selezionato. |
| 8 | Nuove dimensioni del pubblico | Nuove dimensioni di pubblico<!--and metrics?--> che rappresentano i tipi di pubblico di Experience Platform inclusi nel set di dati del profilo selezionato e disponibili per il reporting in Analysis Workspace. Queste quote vengono create automaticamente. |
| 9 | Visualizzazioni dati | Le visualizzazioni dati selezionate associate alla connessione. Queste sono le visualizzazioni dati che desideri utilizzare per analizzare i dati del pubblico di Experience Platform in Analysis Workspace. Queste visualizzazioni dati vengono configurate automaticamente con i dati del pubblico di Experience Platform a scopo di reporting. |
| 10 | Analysis Workspace | L’area all’interno di Customer Journey Analytics in cui puoi creare rapporti che includono i tipi di pubblico di Experience Platform che vengono acquisiti. |

## Configurare l’analisi del pubblico

Quando configuri l’analisi del pubblico, seleziona la sandbox e il criterio di unione associati ai tipi di pubblico di Experience Platform che desideri analizzare. Customer Journey Analytics crea un nuovo set di dati di ricerca, quindi aggiunge automaticamente il set di dati di ricerca e il set di dati del profilo alla connessione scelta.

Per ulteriori informazioni, vedere [Configurare l&#39;analisi del pubblico](/help/connections/audience-analysis/audience-analysis-configure.md).

## Analizzare i dati del pubblico in Customer Journey Analytics

Con i dati sul pubblico disponibili in Customer Journey Analytics, puoi ottenere informazioni fruibili sul comportamento dei membri del pubblico su vari canali.

Ad esempio, puoi tenere traccia del comportamento dei singoli clienti inclusi nella stessa promozione e-mail. Con il pubblico disponibile in Customer Journey Analytics, puoi visualizzare i seguenti tipi di informazioni su ciascun membro del pubblico:

* Click-through dall’e-mail al sito che alla fine ha generato un acquisto

* Membri del pubblico che alla fine hanno effettuato un acquisto in-store

Per ulteriori informazioni, consulta [Analizzare il pubblico di Experience Platform in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).










