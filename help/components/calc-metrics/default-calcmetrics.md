---
description: Adobe fornisce varie metriche calcolate che puoi utilizzare. In questa pagina sono elencate tali metriche e i loro utilizzi previsti.
title: Modelli di metriche calcolate
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d13f980d1fbae3f608bf64587f59dc22c3fac9ce
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 6%

---

# Modelli di metriche calcolate

Customer Journey Analytics fornisce i seguenti modelli di metriche calcolate per coprire i casi d’uso più comuni. Queste metriche calcolate definite da Adobe sono identificate da un piccolo logo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Per filtrare rapidamente queste metriche, selezionare ![Etichetta](/help/assets/icons/Label.svg) **[!UICONTROL Adobe Template]** nel filtro [Componenti](/help/components/overview.md#filter).

| Nome metrica calcolata | Descrizione<br/>Formula |
|---------|----------|
| **[!UICONTROL Session start rate]** | Percentuale in cui si è verificato un elemento dimensione al primo evento di una sessione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Session Starts] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md).</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Inizio sessione** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessioni** **)** |
| **[!UICONTROL Time spent per person]** | Il tempo medio trascorso da una persona per un dato elemento della dimensione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Time Spent (seconds)] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md). Il filtro Escludi ultimo evento della sessione viene applicato alla metrica Persone. Il filtro esclude l’ultimo evento di ogni sessione in un set di dati. Questa esclusione può aiutarti ad analizzare il comportamento degli utenti che porta a un evento o a un’azione, ad esempio un acquisto o un invio di moduli, escludendo al contempo l’azione finale stessa.</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo trascorso (secondi)** ![Dividi](/help/assets/icons/Divide.svg) ![Segmentazione](/help/assets/icons/Segmentation.svg) **Escludi ultimo evento della sessione(** ![Evento](/help/assets/icons/Event.svg) **Persone )** |
| **[!UICONTROL Sessions per person]** | Il numero medio di sessioni per persona.<p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Sessioni** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Persone** **)** |
| **[!UICONTROL Time spent per session]** | Il tempo medio trascorso da una persona in una sessione per un dato elemento della dimensione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Time Spent (seconds)] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md). Il filtro Escludi ultimo evento della sessione viene applicato alla metrica Sessioni. Il filtro esclude l’ultimo evento di ogni sessione in un set di dati. Questa esclusione può aiutarti ad analizzare il comportamento degli utenti che porta a un evento o a un’azione, ad esempio un acquisto o un invio di moduli, escludendo al contempo l’azione finale stessa.</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo trascorso (secondi)** ![Dividi](/help/assets/icons/Divide.svg) ![Segmentazione](/help/assets/icons/Segmentation.svg) **Escludi ultimo evento della sessione(** ![Evento](/help/assets/icons/Event.svg) **Sessioni )** |
| **[!UICONTROL Session end rate]** | Percentuale in cui si è verificato un elemento dimensione nell’ultimo evento di una sessione. <p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Session Ends] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md).</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Fine sessione** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessioni** **)** |
| **[!UICONTROL Web sessions]** | Il numero di sessioni che si sono verificate sul sito web. |
| **[!UICONTROL Survey completion rate]** | Frequenza con cui le persone hanno completato un sondaggio dopo averlo avviato. |
| **[!UICONTROL Multi-channel session rate]** | Il rapporto tra le sessioni che si sono verificate e che includevano più canali (ad esempio traffico web e traffico mobile) e quelle che includevano un solo canale. |
| **[!UICONTROL Multi-channel person rate]** | Il rapporto tra le persone che hanno partecipato a più canali, rispetto a quelle che hanno partecipato solo a un singolo canale. |
| **[!UICONTROL Mobile app sessions]** | Il numero di sessioni che si sono verificate nell’app mobile. |
| **[!UICONTROL Web+app cross-channel sessions]** | Il numero di sessioni che si sono verificate e che includevano sia il traffico web che il traffico mobile. |
| **[!UICONTROL Cost of calls]** | Il costo totale delle chiamate al call center. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Average call duration]** | La durata media delle chiamate effettuate al call center. |
| **[!UICONTROL Average cost per call]** | Il costo medio delle chiamate effettuate al call center. |
| **[!UICONTROL Average call survey score]** | Punteggio medio del sondaggio relativo alle chiamate effettuate al call center. |

{style="table-layout:auto"}
