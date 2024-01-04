---
title: Impostazioni di sessione
description: Impostazioni in una visualizzazione dati da utilizzare per definire la durata di una sessione e il trigger per avviare una nuova sessione
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---

# Impostazioni di sessione

Le impostazioni di sessione nelle visualizzazioni dati cambiano il modo in cui il Customer Journey Analytics calcola le sessioni dai dati presenti nella connessione.

All&#39;interno del **[!UICONTROL Settings]** di Visualizzazioni dati, puoi definire una sessione in qualsiasi modo per far corrispondere il modo in cui le persone interagiscono con le tue esperienze digitali. Le definizioni delle impostazioni di sessione non sono distruttive e non alterano i dati sottostanti. Puoi impostare più visualizzazioni dati (ciascuna con la propria definizione di impostazioni di sessione specifiche) come base per i progetti Workspace.

Per definire il contesto di una sessione per una visualizzazione dati:

1. Seleziona **[!UICONTROL Data views]** nell’interfaccia utente del Customer Journey Analytics.

2. Crea una nuova visualizzazione dati o modificane una esistente. Consulta [Creare o modificare una visualizzazione dati](create-dataview.md) per ulteriori informazioni.

3. Seleziona la **[!UICONTROL Settings]** scheda. Sotto [!UICONTROL Session settings]:

   1. Immetti un valore per **[!UICONTROL Session timeout]** in [!UICONTROL minute(s)], [!UICONTROL hour(s)], [!UICONTROL day(s)], o [!UICONTROL week(s)]. Il timeout della sessione determina per quanto tempo una sessione può rimanere inattiva (non si verificano eventi) prima di avviare una nuova sessione.

      Se sei interessato ad analizzare principalmente le interazioni online, utilizza un breve timeout di sessione (ad esempio, 30 minuti). Ad esempio, analizzando se i profili che visitano le pagine di prodotti del negozio online aggiungono prodotti al carrello o addirittura acquistano online.

      Utilizza un timeout di sessione lungo (ad esempio 3 mesi) se stai combinando dati online e offline e desideri analizzare se i clienti che hanno acquistato uno o più prodotti hanno chiamato il tuo contact center entro i primi tre mesi dopo l’acquisto.


   2. Seleziona una metrica da **[!UICONTROL Drop a metric here]** elenco sotto **[!UICONTROL Start new session with a metric]**. In alternativa, puoi trascinare e rilasciare una metrica dal riquadro di sinistra sulla **[!UICONTROL Drop a metric field]**. La metrica selezionata definisce l’inizio di una nuova sessione. Puoi definire più di una metrica.

      Puoi utilizzare qualsiasi tipo di metrica per definire una nuova sessione. Ad esempio, immagina di voler definire una nuova sessione ogni volta che un profilo avvia la tua app mobile. In entrata **[!UICONTROL Data view]** > **[!UICONTROL Components]**, puoi definire un componente di tipo metrica, denominato **[!UICONTROL Launches]**, in base a un **[!UICONTROL appInteraction]** **[!UICONTROL Name]** campo schema. È inoltre possibile specificare **[!UICONTROL Launches]** componente metrica per contare solo il valore quando il valore corrisponde a `launch`.

      ![Avvii dei componenti della metrica di interazione app](assets/component-launches.png)

      Quindi trascina e rilascia, oppure seleziona la **[!UICONTROL Launches]** come metrica per definire una nuova sessione.

      ![Avvii impostazioni sessione](assets/session-settings-launches-metric.png)



4. Seleziona **[!UICONTROL Save]** o **[!UICONTROL Save and finish]** per salvare la definizione delle impostazioni di sessione.
