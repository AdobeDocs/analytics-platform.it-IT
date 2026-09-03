---
description: Scopri come utilizzare il reporting in tempo reale in Analysis Workspace.
title: Usa reporting in tempo reale
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
autotag-review: '2026-05-19T08:47:15.932Z'
TQID: 'https://experienceleague.adobe.com/t20pdV4qS-FIBGrxOXAD5xAD58f4gtN74uheJ94sK4s'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: d1779026-aeed-458e-a1c7-839d4acac922
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 12%

---

# Utilizzare il reporting in tempo reale {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="Aggiornamento in tempo reale"
>abstract="Abilita questa opzione per aggiornare dati e visualizzazioni nel pannello in tempo reale."

Per utilizzare la generazione rapporti in tempo reale, abilita l&#39;opzione **[!UICONTROL Aggiornamento in tempo reale]** in uno dei seguenti pannelli del progetto Workspace:

* [Pannello vuoto](/help/analysis-workspace/c-panels/blank-panel.md)
* [A forma libera](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Attribuzione](/help/analysis-workspace/c-panels/attribution.md)
* [Elemento successivo o precedente](/help/analysis-workspace/c-panels/next-previous.md)

Viene visualizzato un messaggio con la marca temporale dell’aggiornamento più recente dei dati. Esempio: [!UICONTROL &#x200B; *Ultimo aggiornamento alle 19:55*].

Dal menu a discesa, seleziona il periodo in tempo reale su cui desideri creare un rapporto. Le opzioni disponibili sono:

* [!UICONTROL Ultimi 15 minuti]
* [!UICONTROL Ultimi 30 minuti]
* [!UICONTROL Ultima ora]
* [!UICONTROL Ultime 8 ore]
* [!UICONTROL Ultime 24 ore]

Tutte le visualizzazioni nel pannello ora vengono aggiornate ogni minuto per un massimo di 30 minuti mentre è attiva la scheda del browser con il pannello con aggiornamento in tempo reale abilitato.

Ad esempio, di seguito trovi un&#39;istantanea di un **[!UICONTROL pannello di reporting in tempo reale]** che aggiorna la visualizzazione a barre **[!UICONTROL Ricavi totali/Ora]** e la tabella a forma libera **[!UICONTROL Ricavi totali/Ora]** con lo spostamento dell&#39;ora dalle **[!UICONTROL *06:26 pm *]**&#x200B;alle&#x200B;**[!UICONTROL * 06:27 pm *]**.

![Aggiornamento in tempo reale](assets/real-time-refresh.gif)

Dopo 30 minuti o quando la scheda del browser diventa inattiva, l&#39;interruttore **[!UICONTROL Aggiornamento in tempo reale]** viene disattivato automaticamente e gli aggiornamenti in tempo reale vengono interrotti.

Non appena l&#39;opzione di aggiornamento in tempo reale è disattivata, il pannello (e tutte le visualizzazioni in ) tornano a [utilizzare i dati e le funzionalità standard di reporting di Customer Journey Analytics](real-time.md#how-it-works).
