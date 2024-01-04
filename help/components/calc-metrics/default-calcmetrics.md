---
description: Adobe fornisce varie metriche calcolate che puoi utilizzare. In questa pagina sono elencate tali metriche e i loro utilizzi previsti.
title: Metriche calcolate predefinite
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 25%

---

# Metriche calcolate predefinite

Customer Journey Analytics fornisce le seguenti metriche calcolate per coprire i casi d’uso più comuni:

| Nome metrica calcolata | Descrizione | Formula |
|---------|----------|---------|
| Session Start Rate (Frequenza di inizio sessione) | Percentuale in cui si è verificato un elemento dimensione al primo evento di una sessione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il `[Session Starts]` [componente standard](/help/data-views/component-reference.md) nel tuo [visualizzazione dati](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| Tempo trascorso per persona | Il tempo medio trascorso da una persona per un dato elemento della dimensione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il `[Time Spent (seconds)]` [componente standard](/help/data-views/component-reference.md) nel tuo [visualizzazione dati](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| Sessions Per Person (Sessioni per persona) | Il numero medio di sessioni per persona. | `[Sessions] / [Users]` |
| Time Spent Per Session (Tempo trascorso per sessione) | Il tempo medio trascorso da una persona in una sessione per un dato elemento della dimensione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il `[Time Spent (seconds)]` [componente standard](/help/data-views/component-reference.md) nel tuo [visualizzazione dati](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| Session End Rate (Frequenza di fine sessione) | Percentuale in cui si è verificato un elemento dimensione nell’ultimo evento di una sessione. <p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il `[Session Ends]` [componente standard](/help/data-views/component-reference.md) nel tuo [visualizzazione dati](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
