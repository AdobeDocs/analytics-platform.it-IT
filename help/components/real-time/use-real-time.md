---
description: Scopri come utilizzare il reporting in tempo reale in Analysis Workspace.
title: Usa reporting in tempo reale
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
TQID: https://experienceleague.adobe.com/tQgkfejYepjtgY4eN6cmT4K49I8VUb6les1abWXGGa0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 239
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

Viene visualizzato un messaggio con la marca temporale dell’aggiornamento più recente dei dati. Ad esempio: [!UICONTROL  *Ultimo aggiornamento alle 17:02:00*].:55

Dal menu a discesa, seleziona il periodo in tempo reale su cui desideri creare un rapporto. Le opzioni disponibili sono:

* [!UICONTROL Ultimi 15 minuti]
* [!UICONTROL Ultimi 30 minuti]
* [!UICONTROL Ultima ora]
* [!UICONTROL Ultime 8 ore]
* [!UICONTROL Ultime 24 ore]

Tutte le visualizzazioni nel pannello ora vengono aggiornate ogni minuto per un massimo di 30 minuti mentre è attiva la scheda del browser con il pannello con aggiornamento in tempo reale abilitato.

Ad esempio, di seguito trovi un&#39;istantanea di un **[!UICONTROL pannello di reporting in tempo reale]** che aggiorna la visualizzazione a barre **[!UICONTROL Ricavi totali/Ora]** e la tabella a forma libera **[!UICONTROL Ricavi totali/Ora]** con lo spostamento dell&#39;ora da **[!UICONTROL *06:26pm*]** a **[!UICONTROL *06:27 pm *]**.

![Aggiornamento in tempo reale](assets/real-time-refresh.gif)

Dopo 30 minuti o quando la scheda del browser diventa inattiva, l&#39;interruttore **[!UICONTROL Aggiornamento in tempo reale]** viene disattivato automaticamente e gli aggiornamenti in tempo reale vengono interrotti.

Non appena l&#39;opzione di aggiornamento in tempo reale è disattivata, il pannello (e tutte le visualizzazioni in ) tornano a [utilizzare i dati e le funzionalità standard di reporting di Customer Journey Analytics](real-time.md#how-it-works).
