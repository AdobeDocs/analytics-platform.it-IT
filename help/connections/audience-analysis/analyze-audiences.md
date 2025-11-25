---
title: Analizzare i tipi di pubblico di Experience Platform in Customer Journey Analytics
description: Scopri come analizzare il pubblico di Experience Platform in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 2b91c0592ac4ec0e0b5ffa3db91758466563abaf
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Analizzare i tipi di pubblico di Experience Platform in Customer Journey Analytics {#analyze-audiences-RTCDP}

Puoi iniziare ad analizzare i tipi di pubblico di Experience Platform in Customer Journey Analytics dopo aver [creato una configurazione di analisi del pubblico](/help/connections/audience-analysis/audience-analysis-configure.md), quando i dati sul pubblico sono disponibili come nuove dimensioni in Analysis Workspace.

In Customer Journey Analytics è disponibile un modello di panoramica del pubblico.

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? -->

Per informazioni su come accedere al modello di panoramica del pubblico, vedere [Accedere ed eseguire un modello](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) in [Utilizzare i modelli](/help/analysis-workspace/templates/use-templates.md).

Il modello Panoramica pubblico contiene i pannelli seguenti:

## Pannello Panoramica utilizzo

Mostra i dati per tutti i tipi di pubblico con eventi di utilizzo associati alla visualizzazione dati selezionata. I dati di iscrizione al pubblico vengono aggiornati ogni giorno da Experience Platform. I dati vengono sempre visualizzati per il giorno precedente, pertanto la modifica dell’intervallo di date del pannello causa dati imprecisi.

Utilizza la tabella in questo pannello per comprendere meglio il comportamento del pubblico. Trascina la dimensione Descrizione del pubblico dalla visualizzazione dati selezionata e aggiungila come raggruppamento. In alternativa, utilizza qualsiasi altra dimensione di interazione (ad esempio Pagina, Azione e così via) come suddivisione.

## Pannello Origini del pubblico principale

Mostra dove è stato creato il pubblico, in RTCDP, Customer Journey Analytics e così via.

Utilizza la tabella in questo pannello per comprendere meglio in che modo l’origine del pubblico potrebbe influenzare altri fattori. Trascina la dimensione Nome pubblico dalla visualizzazione dati selezionata e aggiungilo come raggruppamento. In alternativa, utilizza qualsiasi altra dimensione di interazione (ad esempio Pagina, Azione e così via) come suddivisione.

## Pannello di sovrapposizione del pubblico

Mostra i dati per tutti i tipi di pubblico con eventi di utilizzo associati alla visualizzazione dati selezionata. I dati vengono sempre visualizzati per il giorno precedente, pertanto la modifica dell’intervallo di date del pannello causa dati imprecisi.

Seleziona fino a tre tipi di pubblico nella tabella di questo pannello per vedere in che modo si sovrappongono nel diagramma di Venn corrispondente.

## Pannello utilizzo pubblico chiuso

Mostra i dati per tutti i tipi di pubblico esistenti con eventi di utilizzo associati alla visualizzazione dati selezionata. I dati vengono sempre visualizzati per il giorno precedente, pertanto la modifica dell’intervallo di date del pannello causa dati imprecisi. I &quot;tipi di pubblico in uscita&quot; sono tipi di pubblico in cui le persone con eventi di utilizzo sono usciti o usciti ieri.

Utilizza la tabella in questo pannello per comprendere meglio il comportamento del pubblico. Trascina la dimensione Descrizione del pubblico esistente dalla visualizzazione dati selezionata e aggiungilo come raggruppamento. In alternativa, utilizza qualsiasi altra dimensione o metrica di interazione (ad esempio Pagina, Azione e così via) come suddivisione.

## Pannello Origini del pubblico più alto uscito

Mostra dove è stato creato originariamente ogni pubblico in uscita, in RTCDP, Customer Journey Analytics e così via.

Utilizza la tabella in questo pannello per comprendere meglio in che modo l’origine del pubblico potrebbe influenzare altri fattori. Trascina la dimensione Nome pubblico in uscita dalla visualizzazione dati selezionata e aggiungilo come raggruppamento. In alternativa, utilizza qualsiasi altra dimensione o metrica di interazione (ad esempio Pagina, Azione e così via) come suddivisione.








