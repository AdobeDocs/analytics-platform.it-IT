---
description: Scopri le diverse opzioni di salvataggio, tra cui salvataggio automatico, con nome o come modello e apertura delle versioni precedenti.
title: Salvare i progetti
feature: Workspace Basics
role: User
exl-id: d751057e-6a5f-4605-abc1-9259a1f95a28
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 93%

---

# Salvare i progetti

I progetti in Analysis Workspace vengono salvati automaticamente ogni 2 minuti.

Puoi anche salvare i progetti manualmente. Quando salvi manualmente un progetto sono disponibili opzioni aggiuntive, ad esempio l’aggiunta di tag o note.

## Opzioni di salvataggio dei progetti {#Save}

Quando salvi manualmente un progetto in Analysis Workspace sono disponibili varie opzioni.

Per salvare manualmente un progetto:

1. Con il progetto aperto in Analysis Workspace, seleziona **[!UICONTROL Project]** (Progetto), quindi scegli tra le seguenti opzioni:

   | Azione | Descrizione |
   |---|---| 
   | **[!UICONTROL Save]** | Salva le modifiche apportate al progetto. Se il progetto è condiviso, i destinatari del progetto visualizzeranno anche le modifiche. Quando salvi il progetto per la prima volta, ti viene richiesto di assegnare al progetto un nome, una descrizione (facoltativa) e di aggiungere tag (facoltativi). |
   | **[!UICONTROL Save with notes]** | Prima di salvare il progetto, aggiungi note sulle modifiche apportate al progetto. Le note sono memorizzate con la versione del progetto e sono disponibili per tutti gli editor in [!UICONTROL Project] (Progetto) > [!UICONTROL Open previous version] (Apri versione precedente). |
   | **[!UICONTROL Save as]** | Crea un duplicato del progetto. Il progetto originale non subirà modifiche. |
   | **[!UICONTROL Save as template]** | Salva il progetto come [modello personalizzato](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it) che diventa disponibile per la tua organizzazione in **[!UICONTROL Project > New]** |

## Salvataggio automatico {#Autosave}

Tutti i progetti in Analysis Workspace vengono salvati automaticamente ogni 2 minuti nel computer locale. Sono inclusi i progetti appena creati che non sono ancora stati salvati manualmente.

* **Nuovi progetti:** anche se i nuovi progetti vengono salvati automaticamente, è necessario salvarli manualmente la prima volta. Analysis Workspace richiede di salvare manualmente nuovi progetti quando si passa a un altro progetto, si chiude la scheda del browser e così via.

  Se per qualsiasi motivo perdi inaspettatamente l’accesso a un nuovo progetto creato prima di salvarlo manualmente, viene salvata una versione di ripristino del progetto nella pagina di destinazione di Analysis Workspace in una cartella denominata `Recovered Projects (Last 7 Days)` (Ultimi 7 giorni). È necessario ripristinare il progetto recuperato e salvarlo manualmente nella posizione desiderata.

  Per ripristinare un progetto recuperato:

   1. Vai alla cartella [!UICONTROL **Recovered Projects**] (Progetti recuperati) nella pagina di destinazione di Analysis Workspace.

      ![L’elenco delle cartelle che evidenziano la cartella Progetto recuperato.](assets/recovered-folder.png)

   1. Apri il progetto e salvalo nella posizione desiderata.


* **Progetti esistenti:** se per qualsiasi motivo esci da un progetto con modifiche non ancora salvate automaticamente, Analysis Workspace richiede di salvare le modifiche o mostra un messaggio di avviso.

  Di seguito sono riportati alcuni scenari comuni:

### Aprire un altro progetto

Se apri un progetto aggiuntivo mentre lavori a un progetto contenente modifiche non ancora salvate automaticamente, Analysis Workspace richiede di salvare il progetto in corso prima di uscire.

Sono disponibili le seguenti opzioni:

* **Save (Salva):** sostituisce la copia locale più recente del progetto salvata automaticamente con le ultime modifiche.
* **Save as (Salva con nome):** salva le modifiche più recenti come nuovo progetto. Il progetto originale viene salvato solo con le ultime modifiche salvate automaticamente.
* **Discard Changes (Elimina modifiche):** elimina le modifiche più recenti. Il progetto conserva le modifiche salvate automaticamente più recenti.

![Fai clic su Salva per salvare le modifiche apportate a un progetto.](assets/existing-save.png)

### Uscire o chiudere una scheda

In caso di uscita o chiusura della scheda del browser durante la visualizzazione di un progetto con modifiche non ancora salvate automaticamente, il browser avverte che le modifiche non salvate andranno perse. È possibile scegliere di uscire o annullare.

![Fai clic su Lascia per uscire dal sito o su Annulla per spostarti senza salvare le modifiche. ](assets/browser-image.png)

### Arresto anomalo del browser o timeout della sessione

Se il browser si blocca o se la sessione si interrompe, al prossimo accesso ad Analysis Workspace viene richiesto di ripristinare eventuali modifiche al progetto che non sono ancora state salvate automaticamente.

Di seguito è riportata la finestra di dialogo Project Recovery (Recupero progetto) che compare al primo accesso ad Analysis Workspace dopo un arresto anomalo o un timeout.

Seleziona **Yes** (Sì) per ripristinare il progetto dalla copia salvata automaticamente più recente.

Seleziona **No** per eliminare la copia salvata automaticamente e aprire l’ultima versione del progetto salvata dall’utente.

![Finestra di dialogo Ripristino del progetto.](assets/project-recovery.png)

Per i **nuovi** progetti che non sono mai stati salvati, non è possibile recuperare le modifiche non salvate.

## Aprire la versione precedente {#previous-version}

Per aprire una versione precedente di un progetto:

1. Vai a **[!UICONTROL Project]** > **[!UICONTROL Open previous version]**

   ![Nell’elenco Versioni del progetto salvate in precedenza sono elencate le opzioni che consentono di visualizzare Tutte le versioni o Solo le versioni con note.](assets/previous-versions.png)

1. Rivedi l’elenco delle versioni precedenti disponibili.
   Vengono visualizzati [!UICONTROL Timestamp] e [!UICONTROL Editor], oltre a [!UICONTROL Notes] se sono state aggiunte al momento del salvataggio dell’[!UICONTROL Editor]. Le versioni senza note sono conservate per 90 giorni; le versioni con note sono memorizzate per 1 anno.
1. Seleziona una versione precedente e fai clic su **[!UICONTROL Load]** (Carica).
La versione precedente viene quindi caricata con una notifica. La versione precedente diventa la versione salvata corrente del progetto solo dopo aver fatto clic su **[!UICONTROL Save]**. Se ti sposti dalla versione caricata, quando torni viene visualizzata l’ultima versione salvata del progetto.
