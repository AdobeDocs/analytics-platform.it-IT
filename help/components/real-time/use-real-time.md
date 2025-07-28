---
description: Scopri come utilizzare il reporting in tempo reale in Analysis Workspace.
title: Usa reporting in tempo reale
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: c26fbe37270171c80d77c96966dd21f2dd7c7ce9
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 15%

---

# Utilizzare rapporti in tempo reale {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="Aggiornamento in tempo reale"
>abstract="Abilita questa opzione per aggiornare dati e visualizzazioni nel pannello in tempo reale."

{{release-limited-testing}}

Per utilizzare la generazione rapporti in tempo reale, abilita **[!UICONTROL Real-time refresh]** in uno dei seguenti pannelli del progetto Workspace:

* [Pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md)
* [A forma libera](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Attribuzione](/help/analysis-workspace/c-panels/attribution.md)
* [Elemento successivo o precedente](/help/analysis-workspace/c-panels/next-previous.md)
* [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md)

Viene visualizzato un messaggio con la marca temporale dell’aggiornamento più recente dei dati. Esempio: [!UICONTROL  *Ultimo aggiornamento alle 17:01:00:55.*]

Dal menu a discesa, seleziona il periodo in tempo reale su cui desideri creare un rapporto. Le opzioni disponibili sono:

* [!UICONTROL Last 15 minutes]
* [!UICONTROL Last 30 minutes]
* [!UICONTROL Last hour]
* [!UICONTROL Last 8 hours]
* [!UICONTROL Last 24 hours]

Tutte le visualizzazioni nel pannello ora vengono aggiornate ogni minuto per un massimo di 30 minuti mentre è attiva la scheda del browser con il pannello con aggiornamento in tempo reale abilitato.

Ad esempio, vedere di seguito uno snapshot di un **[!UICONTROL Real-time reporting panel]** che aggiorna la visualizzazione a barre di **[!UICONTROL Total Revenue / Hour]** e la tabella a forma libera di **[!UICONTROL Total Revenue / Hour]** mentre il tempo si sposta da **[!UICONTROL *06:26pm*]** a **[!UICONTROL *06:27 pm *]**.

![Aggiornamento in tempo reale](assets/real-time-refresh.gif)

Dopo 30 minuti o quando la scheda del browser diventa inattiva, l&#39;interruttore **[!UICONTROL Real-time refesh]** viene disattivato automaticamente e gli aggiornamenti in tempo reale vengono interrotti.
