---
title: Adobe Context-Aware Sessions
description: Impostazioni in una visualizzazione dati da utilizzare per definire sessioni in base al contesto.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 92511d2bedf322097b4d70ccede5ac6e0df7b0c6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 1%

---


# Adobe Context-Aware Sessions

Le sessioni in base al contesto nelle visualizzazioni dati modificano il modo in cui il Customer Journey Analytics calcola le sessioni dai dati presenti nella connessione.

All&#39;interno del [!UICONTROL Settings] di Visualizzazioni dati, puoi definire una sessione in qualsiasi modo per far corrispondere il modo in cui le persone interagiscono con le tue esperienze digitali. Le definizioni delle sessioni in base al contesto non sono distruttive e non alterano i dati sottostanti. Puoi impostare più visualizzazioni dati ciascuna con la rispettiva definizione di sessione in base al contesto, da usare come base per i progetti Workspace.

Per definire il contesto di una sessione per una visualizzazione dati:

1. Seleziona **[!UICONTROL Data views]** nell’interfaccia utente del Customer Journey Analytics.

1. Crea una nuova visualizzazione dati o modificane una esistente. Consulta [Creare o modificare una visualizzazione dati](create-dataview.md) per ulteriori informazioni.

1. Seleziona la **[!UICONTROL Settings]** scheda. Sotto [!UICONTROL Session settings]:

   1. Immetti un valore per **[!UICONTROL Session timeout]** in [!UICONTROL minute(s)], [!UICONTROL hour(s)], [!UICONTROL day(s)], o [!UICONTROL week(s)]. Il timeout della sessione determina per quanto tempo una sessione può rimanere inattiva (non si verificano eventi) prima di avviare una nuova sessione.

   2. Seleziona una metrica da **[!UICONTROL Drop a metric here]** elenco sotto [!UICONTROL Start new session with a metric]. In alternativa, puoi trascinare e rilasciare una metrica dal riquadro di sinistra sulla **[!UICONTROL Drop a metric field]**. La metrica selezionata definisce l’inizio di una nuova sessione. Puoi definire più di una metrica.

1. Seleziona **[!UICONTROL Save]** o **[!UICONTROL Save and finish]** per salvare la definizione della sessione in base al contesto.

