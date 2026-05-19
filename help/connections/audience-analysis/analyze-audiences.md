---
title: Analizzare Il Pubblico Di Experience Platform In Customer Journey Analytics
description: Scopri come analizzare il pubblico di Experience Platform in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 095cae34-1337-464a-9682-3c899295c0a8
autotag-review: '2026-05-19T10:44:54.802Z'
TQID: 'https://experienceleague.adobe.com/ljj9CIUW58m27w8Mo9HlRJ0kgYXGIgqwuarPR2wNUjw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 0%

---

# Analizzare i tipi di pubblico di Experience Platform in Customer Journey Analytics {#analyze-audiences-RTCDP}

Dopo aver [creato una configurazione di analisi del pubblico](/help/connections/audience-analysis/audience-analysis-configure.md), i dati del pubblico diventano disponibili come nuove dimensioni nelle visualizzazioni dati in cui configurarle per la creazione. Puoi utilizzare le nuove dimensioni pubblico in qualsiasi punto di Analysis Workspace se hai accesso a una visualizzazione dati in cui sono state aggiunte le dimensioni di analisi del pubblico.

## Utilizzare il modello di panoramica sul pubblico

In Customer Journey Analytics è disponibile un modello di panoramica del pubblico.

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

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

Utilizza la tabella in questo pannello per comprendere meglio il comportamento del pubblico. Trascina la dimensione Descrizione del pubblico in uscita dalla visualizzazione dati selezionata e aggiungila come raggruppamento. In alternativa, utilizza qualsiasi altra dimensione o metrica di interazione (ad esempio Pagina, Azione e così via) come suddivisione.

## Pannello Origini del pubblico più alto uscito

Mostra dove è stato creato originariamente ogni pubblico in uscita, in RTCDP, Customer Journey Analytics e così via.

Utilizza la tabella in questo pannello per comprendere meglio in che modo l’origine del pubblico potrebbe influenzare altri fattori. Trascina la dimensione Nome pubblico in uscita dalla visualizzazione dati selezionata e aggiungilo come raggruppamento. In alternativa, utilizza qualsiasi altra dimensione o metrica di interazione (ad esempio Pagina, Azione e così via) come suddivisione.
