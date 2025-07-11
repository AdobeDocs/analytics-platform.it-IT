---
description: Scopri come utilizzare il reporting in tempo reale in Analysis Workspace.
title: Usa reporting in tempo reale
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 6%

---


# Utilizzare rapporti in tempo reale

{{release-limited-testing}}

Per utilizzare la generazione rapporti in tempo reale, abilita **[!UICONTROL Real-time refresh]** in uno dei seguenti pannelli del progetto Workspace:



* [Pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md)
* [Pannello a forma libera](/help/analysis-workspace/c-panels/freeform-panel.md)
* ...

Viene visualizzato un messaggio con la marca temporale dell’aggiornamento più recente dei dati. Esempio: [!UICONTROL  *Ultimo aggiornamento alle 19:55*].

Dal menu a discesa, seleziona il periodo in tempo reale su cui desideri creare un rapporto. Le opzioni disponibili sono:

* [!UICONTROL Last 15 minutes]
* [!UICONTROL Last 30 minutes]
* [!UICONTROL Last hour]
* [!UICONTROL Last 8 hours]
* [!UICONTROL Last 24 hours]

Ora tutte le visualizzazioni vengono aggiornate ogni minuto per un massimo di 30 minuti, mentre è attiva la scheda del browser con il pannello con aggiornamento in tempo reale abilitato.

![Aggiornamento in tempo reale](assets/real-time-refresh.gif)

Dopo 30 minuti o quando la scheda del browser diventa inattiva, l&#39;interruttore **[!UICONTROL Real-time refesh]** viene disattivato automaticamente e gli aggiornamenti in tempo reale vengono interrotti.
