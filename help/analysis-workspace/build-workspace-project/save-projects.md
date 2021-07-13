---
description: Scopri le diverse opzioni di salvataggio, tra cui salvataggio automatico, con nome o come modello e apertura delle versioni precedenti.
title: Salvare i progetti
feature: Concetti di base di Workspace
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
source-git-commit: 734f1fe702398034090e25c251b5ff193db8381e
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 100%

---

# Salvare i progetti

Per salvare le modifiche apportate a un progetto, vai al menu **[!UICONTROL Project]** di Workspace. In alcuni casi Workspace salva automaticamente anche i progetti.

## Opzioni di salvataggio dei progetti {#Save}

È possibile effettuare diverse azioni di salvataggio nel menu **[!UICONTROL Project]**, a seconda di come desideri accedere all’analisi in futuro.

| Azione | Descrizione |
|---|---| 
| **[!UICONTROL Save]** | Salva le modifiche apportate al progetto. Se il progetto è condiviso, i destinatari del progetto visualizzeranno anche le modifiche. Quando salvi il progetto per la prima volta, ti viene richiesto di assegnare al progetto un nome, una descrizione (facoltativa) e di aggiungere tag (facoltativi). |
| **[!UICONTROL Save with notes]** | Prima di salvare il progetto, aggiungi note sulle modifiche apportate al progetto. Le note sono memorizzate con la versione del progetto e sono disponibili per tutti gli editor in [!UICONTROL Project] (Progetto) > [!UICONTROL Open previous version] (Apri versione precedente). |
| **[!UICONTROL Save as]** | Crea un duplicato del progetto. Il progetto originale non subirà modifiche. |
| **[!UICONTROL Save as template]** | Salva il progetto come [modello personalizzato](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it) che diventa disponibile per la tua organizzazione in **[!UICONTROL Project > New]** |

![](assets/save-project.png)

## Salvataggio automatico {#Autosave}

I progetti esistenti, ovvero quelli salvati almeno una volta, vengono salvati automaticamente ogni due minuti nel dispositivo locale. I nuovi progetti che non sono mai stati salvati non vengono attualmente salvati automaticamente.

Esistono alcune situazioni che possono allontanarti dalle modifiche non salvate apportate a un progetto, risultando in diverse azioni disponibili.

### Aprire un nuovo progetto Workspace

Adobe fornisce l’opzione di salvare prima di uscire dalla pagina. Dopo aver abbandonato un progetto esistente, la copia locale salvata automaticamente viene eliminata.

![](assets/existing-save.png)

### Spostarsi o chiudere una scheda

Il browser avverte che le modifiche non salvate andranno perse. È possibile scegliere di uscire o annullare.

![](assets/browser-image.png)

### Arresto anomalo del browser o timeout della sessione

Per i progetti **esistenti**, una volta tornato in Workspace viene visualizzata una finestra di dialogo modale per il **recupero del progetto**. Se si seleziona “Sì”, il progetto viene ripristinato dalla copia locale salvata automaticamente. Selezionando “No” la copia locale salvata automaticamente viene eliminata e viene aperta l’ultima versione del progetto salvata dall’utente.

![](assets/project-recovery.png)

Per i **nuovi** progetti che non sono mai stati salvati, non è possibile recuperare le modifiche non salvate.

## Aprire la versione precedente {#previous-version}

>[!NOTE]
>
>Le versioni precedenti dei progetti sono attualmente in versione limitata.

Per aprire una versione precedente di un progetto:

1. Vai a **[!UICONTROL Project]** > **[!UICONTROL Open previous version]**

   ![](assets/previous-versions.png)

1. Rivedi l’elenco delle versioni precedenti disponibili.
   Vengono visualizzati [!UICONTROL Timestamp] e [!UICONTROL Editor], oltre a [!UICONTROL Notes] se sono state aggiunte al momento del salvataggio dell’[!UICONTROL Editor]. Le versioni senza note sono conservate per 90 giorni; le versioni con note sono memorizzate per 1 anno.
1. Seleziona una versione precedente e fai clic su **[!UICONTROL Load]** (Carica).
La versione precedente viene quindi caricata con una notifica. La versione precedente diventa la versione salvata corrente del progetto solo dopo aver fatto clic su **[!UICONTROL Save]**. Se ti sposti dalla versione caricata, quando torni viene visualizzata l’ultima versione salvata del progetto.
