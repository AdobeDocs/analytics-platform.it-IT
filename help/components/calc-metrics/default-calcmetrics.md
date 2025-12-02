---
description: Adobe fornisce varie metriche calcolate che puoi utilizzare. In questa pagina sono elencate tali metriche e i loro utilizzi previsti.
title: Modelli di metriche calcolate
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 59%

---

# Modelli di metriche calcolate

Customer Journey Analytics fornisce i seguenti modelli di metriche calcolate per coprire i casi d’uso più comuni. Queste metriche calcolate definite da Adobe sono identificate da un piccolo logo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Per filtrare rapidamente queste metriche, selezionare ![Etichetta](/help/assets/icons/Label.svg) **[!UICONTROL Modello Adobe]** nel filtro [Componenti](/help/components/overview.md#filter).

| Nome della metrica calcolata | Descrizione<br/>Formula |
|---------|----------|
| **[!UICONTROL Frequenza di inizio sessione]** | La percentuale di tempo in cui si è verificato un elemento dimensionale nel primo evento di una sessione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Componente standard] [&#x200B; &#x200B;](/help/data-views/component-reference.md) della sessione nella [visualizzazione dati](/help/data-views/create-dataview.md).</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Inizio sessione** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessioni** **)** |
| **[!UICONTROL Tempo trascorso per persona]** | Il tempo medio trascorso da una persona per un dato elemento della dimensione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Tempo trascorso (secondi)] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md). Il segmento Escludi ultimo evento della sessione viene applicato alla metrica Persone. Il segmento esclude l’ultimo evento di ogni sessione in un set di dati. Questa esclusione può aiutarti ad analizzare il comportamento dell’utente che porta a un evento o a un’azione, ad esempio un acquisto o l’invio di un modulo, escludendo al contempo l’azione finale stessa.</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo trascorso (secondi)** ![Dividi](/help/assets/icons/Divide.svg) ![Segmentazione](/help/assets/icons/Segmentation.svg) **Escludi ultimo evento della sessione(** ![Evento](/help/assets/icons/Event.svg) **Persone )** |
| **[!UICONTROL Sessioni per persona]** | Numero medio di sessioni per persona<p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Sessioni** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Persone** **)** |
| **[!UICONTROL Tempo trascorso per sessione]** | Il tempo medio trascorso da una persona in una sessione per un dato elemento della dimensione.<p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando includi il [!UICONTROL Tempo trascorso (secondi)] [componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md). Il segmento Escludi ultimo evento della sessione viene applicato alla metrica Sessioni. Il segmento esclude l’ultimo evento di ogni sessione in un set di dati. Questa esclusione può aiutarti ad analizzare il comportamento dell’utente che porta a un evento o a un’azione, ad esempio un acquisto o l’invio di un modulo, escludendo al contempo l’azione finale stessa.</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo trascorso (secondi)** ![Dividi](/help/assets/icons/Divide.svg) ![Segmentazione](/help/assets/icons/Segmentation.svg) **Escludi ultimo evento della sessione(** ![Evento](/help/assets/icons/Event.svg) **Sessioni )** |
| **[!UICONTROL Frequenza di fine sessione]** | La percentuale di tempo in cui si è verificato un elemento dimensionale nell’ultimo evento di una sessione. <p>Questa metrica calcolata viene aggiunta automaticamente a Workspace quando si includono [!UICONTROL le fine sessione] [il componente standard](/help/data-views/component-reference.md) nella [visualizzazione dati](/help/data-views/create-dataview.md).</p>Riepilogo: **(** ![Evento](/help/assets/icons/Event.svg) **Fine sessione** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessioni** **)** |
| **[!UICONTROL Sessioni Web]** | Il numero di sessioni che si sono verificate sul sito web. |
| **[!UICONTROL Tasso di completamento sondaggio]** | Velocità con cui le persone hanno completato un sondaggio dopo averlo avviato. |
| **[!UICONTROL Frequenza sessioni multicanale]** | Il rapporto tra le sessioni che si sono verificate e che includevano più canali (ad esempio traffico web e traffico mobile) e quelle che includevano un solo canale. |
| **[!UICONTROL Percentuale di persone multicanale]** | Il rapporto tra le persone che hanno partecipato a più canali, rispetto a quelle che hanno partecipato solo a un singolo canale. |
| **[!UICONTROL Sessioni per app mobile]** | Il numero di sessioni che si sono verificate nell’app mobile. |
| **[!UICONTROL Sessioni Web+app cross-channel]** | Il numero di sessioni che si sono verificate e che includevano sia il traffico web che il traffico mobile. |
| **[!UICONTROL Costo delle chiamate]** | Il costo totale delle chiamate al call center. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Durata media chiamata]** | La durata media delle chiamate effettuate al call center. |
| **[!UICONTROL Costo medio per chiamata]** | Il costo medio delle chiamate effettuate al call center. |
| **[!UICONTROL Punteggio medio sondaggio chiamate]** | Punteggio medio del sondaggio relativo alle chiamate effettuate al call center. |

{style="table-layout:auto"}
