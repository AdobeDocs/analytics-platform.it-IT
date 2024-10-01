---
description: Adobe fornisce varie metriche calcolate che puoi utilizzare. In questa pagina sono elencate tali metriche e i loro utilizzi previsti.
title: Metriche calcolate predefinite
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a507417c945f827ebb8bc92f7b5f54a9c4e6faa0
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 9%

---

# Metriche calcolate predefinite

Customer Journey Analytics fornisce le metriche calcolate predefinite seguenti per coprire i casi d’uso più comuni. Le metriche calcolate predefinite definite nell&#39;Adobe sono identificate da un piccolo logo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Per filtrare rapidamente queste metriche, selezionare ![Etichetta](/help/assets/icons/Label.svg) **[!UICONTROL Adobe Template]** nel filtro [Componenti](/help/components/overview.md#filter).

| Nome metrica calcolata | Descrizione<br/>Formula |
|---------|----------|
| **[!UICONTROL Session Start Rate]** | Percentuale in cui si è verificato un elemento dimensione al primo evento di una sessione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Session Starts] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md).</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Inizio sessione** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessioni** **)** |
| **[!UICONTROL Time Spent Per Person]** | Il tempo medio trascorso da una persona per un dato elemento della dimensione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Time Spent (seconds)] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md). Il filtro Escludi ultimo evento della sessione viene applicato alla metrica Persone. Il filtro esclude l’ultimo evento di ogni sessione in un set di dati. Questa esclusione può aiutarti ad analizzare il comportamento degli utenti che porta a un evento o a un’azione, ad esempio un acquisto o un invio di moduli, escludendo al contempo l’azione finale stessa.</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo trascorso (secondi)** ![Dividi](/help/assets/icons/Divide.svg) ![Segmentazione](/help/assets/icons/Segmentation.svg) **Escludi ultimo evento della sessione(** ![Evento](/help/assets/icons/Event.svg) **Persone )** |
| **[!UICONTROL Sessions Per Person]** | Il numero medio di sessioni per persona.<p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Sessioni** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Persone** **)** |
| **[!UICONTROL Time Spent Per Session]** | Il tempo medio trascorso da una persona in una sessione per un dato elemento della dimensione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Time Spent (seconds)] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md). Il filtro Escludi ultimo evento della sessione viene applicato alla metrica Sessioni. Il filtro esclude l’ultimo evento di ogni sessione in un set di dati. Questa esclusione può aiutarti ad analizzare il comportamento degli utenti che porta a un evento o a un’azione, ad esempio un acquisto o un invio di moduli, escludendo al contempo l’azione finale stessa.</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo trascorso (secondi)** ![Dividi](/help/assets/icons/Divide.svg) ![Segmentazione](/help/assets/icons/Segmentation.svg) **Escludi ultimo evento della sessione(** ![Evento](/help/assets/icons/Event.svg) **Sessioni )** |
| **[!UICONTROL Session End Rate]** | Percentuale in cui si è verificato un elemento dimensione nell’ultimo evento di una sessione. <p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Session Ends] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md).</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Fine Sessione** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessioni** **)** |

{style="table-layout:auto"}
