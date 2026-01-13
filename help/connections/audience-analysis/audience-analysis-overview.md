---
title: Panoramica dell’analisi del pubblico
description: Scopri come analizzare i tipi di pubblico da RTCDP in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 9d9c4dbba13f61af4a47bbb0f87533fb950976bc
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 3%

---

# Panoramica dell’analisi del pubblico

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md and this article: /help/analysis-workspace/templates/use-templates.md-->

>[!NOTE]
>
>Comprendere la differenza tra analisi del pubblico e pubblicazione del pubblico:
>
>* **Analisi del pubblico**: consente di acquisire i dati di appartenenza al pubblico dai set di dati del profilo di Experience Platform in una connessione Customer Journey Analytics.
>* **Pubblicazione del pubblico**: ti consente di creare e pubblicare su Adobe Experience Platform i tipi di pubblico rilevati in Customer Journey Analytics per la personalizzazione e il targeting dei clienti. Per informazioni sulla pubblicazione di tipi di pubblico, vedere [Panoramica sulla pubblicazione di tipi di pubblico](/help/components/audiences/audiences-overview.md).

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
| 6 | Nuovo set di dati di ricerca | Fornisce nomi descrittivi per le nuove dimensioni pubblico create. <p>Il set di dati di ricerca viene creato e aggiunto automaticamente alla connessione, insieme al set di dati profilo selezionato.</p> |
| 7 | Connessione | La connessione in cui desideri aggiungere il set di dati profilo selezionato. |
| 8 | Nuove dimensioni del pubblico | Nuove dimensioni di pubblico<!--and metrics?--> che rappresentano i tipi di pubblico di Experience Platform inclusi nel set di dati del profilo selezionato e disponibili per il reporting in Analysis Workspace. Queste quote vengono create automaticamente. |
| 9 | Visualizzazioni dati | Le visualizzazioni dati selezionate associate alla connessione. Queste sono le visualizzazioni dati che desideri utilizzare per analizzare i dati del pubblico di Experience Platform in Analysis Workspace. Queste visualizzazioni dati vengono configurate automaticamente con i dati del pubblico di Experience Platform a scopo di reporting. |

## Configurare l’analisi del pubblico

Quando configuri l’analisi del pubblico, seleziona la sandbox e il criterio di unione associati ai tipi di pubblico di Experience Platform che desideri analizzare. Customer Journey Analytics crea un nuovo set di dati di ricerca, quindi aggiunge automaticamente il set di dati di ricerca e il set di dati del profilo alla connessione scelta.

>[!NOTE]
>
>I tipi di pubblico sono disponibili nelle visualizzazioni dati di Customer Journey Analytics il giorno successivo alla creazione della configurazione di analisi del pubblico.

Per ulteriori informazioni, vedere [Configurare l&#39;analisi del pubblico](/help/connections/audience-analysis/audience-analysis-configure.md).

## Gestire le configurazioni di analisi del pubblico

Puoi gestire le configurazioni di analisi del pubblico dopo averle create. Puoi visualizzare, modificare ed eliminare le configurazioni.

Per informazioni sulla gestione delle configurazioni di analisi del pubblico esistenti, consulta [Gestire le configurazioni di analisi del pubblico](/help/connections/audience-analysis/audience-analysis-manage.md).

## Analizzare i dati del pubblico in Customer Journey Analytics

Con i dati sul pubblico disponibili in Customer Journey Analytics, puoi ottenere informazioni fruibili sul comportamento dei membri del pubblico su vari canali.

Ad esempio, puoi tenere traccia del comportamento dei singoli clienti inclusi nella stessa promozione e-mail. Con il pubblico disponibile in Customer Journey Analytics, puoi visualizzare i seguenti tipi di informazioni su ciascun membro del pubblico:

* Click-through dall’e-mail al sito che alla fine ha generato un acquisto

* Membri del pubblico che alla fine hanno effettuato un acquisto in-store

Per ulteriori informazioni, consulta [Analizzare il pubblico di Experience Platform in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

## Ruolo di analisi del pubblico e requisiti delle autorizzazioni

Per l’analisi del pubblico sono necessari i seguenti ruoli Customer Journey Analytics e le seguenti autorizzazioni Experience Platform:

| Funzionalità | Requisiti del ruolo o delle autorizzazioni di Customer Journey Analytics | Requisiti delle autorizzazioni di Experience Platform |
|---------|----------|----------|
| [Crea configurazioni analisi del pubblico](/help/connections/audience-analysis/audience-analysis-configure.md) | Amministratore di sistema | <ul><li>Set di dati: autorizzazioni di lettura</li><li>Schemi: lettura, scrittura</li><li>Spazi dei nomi delle identità: lettura</li></ul> |
| [Visualizzare le dimensioni di analisi del pubblico nella visualizzazione dati](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | Amministratore del profilo di prodotto per il profilo di prodotto a cui è assegnata la visualizzazione dati <p>Per ulteriori informazioni, vedere [Controllo degli accessi](/help/technotes/access-control.md).</p> | N/D |
| Utilizzare le dimensioni di analisi del pubblico in Analysis Workspace | Accesso a una visualizzazione dati in cui sono state aggiunte le dimensioni di analisi del pubblico | N/D |

## Limiti dell’analisi del pubblico

Considera i seguenti limiti durante la [configurazione dell&#39;analisi del pubblico](/help/connections/audience-analysis/audience-analysis-configure.md):

* Una singola sandbox può supportare fino a 100 configurazioni di analisi del pubblico.

* Una connessione può essere associata a una sola configurazione di analisi del pubblico.








