---
title: Impostazioni di sessione
description: Impostazioni in una visualizzazione dati da utilizzare per definire la lunghezza di una sessione e il trigger per avviare una nuova sessione
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
source-git-commit: 8a56f6182b0679d64b9e4ad82402f414eeb88055
workflow-type: ht
source-wordcount: '370'
ht-degree: 100%

---

# Impostazioni di sessione

In Customer Journey Analytics puoi definire una sessione in qualsiasi modo per far corrispondere il modo in cui le persone interagiscono con le tue esperienze digitali. Puoi configurare le impostazioni della sessione all’interno di una visualizzazione dati.

Le definizioni delle impostazioni di sessione sono non distruttive e non alterano i dati sottostanti. Puoi impostare visualizzazioni dati multiple (ciascuna con la propria definizione di impostazioni di sessione specifica) come base per i progetti Workspace.

Per definire il contesto di una sessione per una visualizzazione dati:

1. Seleziona **[!UICONTROL Data views]** nell’interfaccia utente di Customer Journey Analytics.

2. Crea una nuova visualizzazione dati o modificane una esistente. Per ulteriori informazioni, consulta [Creare o modificare una visualizzazione dati](create-dataview.md).

3. Seleziona la scheda **[!UICONTROL Settings]**. In [!UICONTROL Session settings]:

   1. Immetti un valore per **[!UICONTROL Session timeout]** in [!UICONTROL minute(s)], [!UICONTROL hour(s)], [!UICONTROL day(s)] o [!UICONTROL week(s)]. Il timeout della sessione determina per quanto tempo una sessione può rimanere inattiva (non si verificano eventi) prima di avviarne una nuova.

      Se ti interessa analizzare principalmente le interazioni online, utilizza un breve timeout di sessione (ad esempio, 30 minuti). Ad esempio, analizzando se i profili che visitano le pagine di prodotti del negozio online aggiungono prodotti al carrello o acquistano anche online.

      Utilizza un timeout di sessione lungo (ad esempio 3 mesi) se stai combinando dati online e offline e desideri analizzare se chi ha acquistato uno o più prodotti ha chiamato il tuo centro assistenza nei primi tre mesi successivi all’acquisto.


   2. Seleziona una metrica dall’elenco **[!UICONTROL Drop a metric here]** in **[!UICONTROL Start new session with a metric]**. In alternativa, puoi trascinare una metrica dal riquadro a sinistra sul **[!UICONTROL Drop a metric field]**. La metrica selezionata definisce l’inizio di una nuova sessione. Puoi definire più di una metrica.

      Puoi utilizzare qualsiasi tipo di metrica per definire una nuova sessione. Ad esempio, immagina di voler definire una nuova sessione ogni volta che un profilo avvia la tua app mobile. In **[!UICONTROL Data view]** > **[!UICONTROL Components]**, definisci un componente di tipo metrica, denominato **[!UICONTROL Launches]**, in base a un campo schema **[!UICONTROL appInteraction]** **[!UICONTROL Name]**. È possibile inoltre specificare il componente metrica **[!UICONTROL Launches]** per conteggiare solo il valore quando il valore corrisponde a `launch`.

      ![Avvii componente metrica di interazione app](assets/component-launches.png)

      Quindi trascina o seleziona la metrica **[!UICONTROL Launches]** come metrica per definire una nuova sessione.

      ![Avvii impostazioni di sessione](assets/session-settings-launches-metric.png)



4. Seleziona **[!UICONTROL Save]** o **[!UICONTROL Save and finish]** per salvare la definizione delle impostazioni di sessione.
