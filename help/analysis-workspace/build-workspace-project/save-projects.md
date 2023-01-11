---
description: Scopri le diverse opzioni di salvataggio, tra cui salvataggio automatico, con nome o come modello e apertura delle versioni precedenti.
title: Salvare i progetti
feature: CJA Workspace Basics
role: User, Admin
exl-id: d751057e-6a5f-4605-abc1-9259a1f95a28
source-git-commit: 8845d3e7142c5eb0f9007d7f9b5cd9e52017f31e
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 37%

---

# Salvare i progetti

I progetti in Analysis Workspace vengono salvati automaticamente ogni 2 minuti.

Puoi anche salvare manualmente i progetti. Quando salvi manualmente un progetto sono disponibili opzioni aggiuntive, ad esempio l’aggiunta di tag o note.

## Opzioni di salvataggio dei progetti {#Save}

Sono disponibili varie opzioni quando salvi manualmente un progetto in Analysis Workspace.

Per salvare manualmente un progetto:

1. Con il progetto aperto in Analysis Workspace, seleziona **[!UICONTROL Project]**, quindi scegli tra le seguenti opzioni:

   | Azione | Descrizione |
   |---|---| 
   | **[!UICONTROL Save]** | Salva le modifiche apportate al progetto. Se il progetto è condiviso, i destinatari del progetto visualizzeranno anche le modifiche. Quando salvi il progetto per la prima volta, ti viene richiesto di assegnare al progetto un nome, una descrizione (facoltativa) e di aggiungere tag (facoltativi). |
   | **[!UICONTROL Save with notes]** | Prima di salvare il progetto, aggiungi note sulle modifiche apportate al progetto. Le note sono memorizzate con la versione del progetto e sono disponibili per tutti gli editor in [!UICONTROL Project] (Progetto) > [!UICONTROL Open previous version] (Apri versione precedente). |
   | **[!UICONTROL Save as]** | Crea un duplicato del progetto. Il progetto originale non subirà modifiche. |
   | **[!UICONTROL Save as template]** | Salva il progetto come [modello personalizzato](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it) che diventa disponibile per la tua organizzazione in **[!UICONTROL Project > New]** |

## Salvataggio automatico {#Autosave}

Tutti i progetti in Analysis Workspace vengono salvati automaticamente ogni 2 minuti nel computer locale. Sono inclusi i progetti appena creati che non vengono ancora salvati manualmente.

* **Nuovi progetti:** Anche se i nuovi progetti vengono salvati automaticamente, è necessario salvarli manualmente per la prima volta. Analysis Workspace richiede di salvare manualmente nuovi progetti quando si passa a un altro progetto, si chiude la scheda del browser e così via.

   Se per qualsiasi motivo perdi inaspettatamente l’accesso a un nuovo progetto creato prima di salvarlo manualmente, una versione di ripristino del progetto viene salvata nella pagina di destinazione di Analysis Workspace in una cartella denominata `Recovered Projects (Last 7 Days)`. È necessario ripristinare il progetto recuperato e salvarlo manualmente nella posizione desiderata.

   Per ripristinare un progetto recuperato:

   1. Vai a [!UICONTROL **Progetti recuperati**] nella pagina di destinazione di Analysis Workspace.

      ![](assets/recovered-folder.png)

   1. Apri il progetto e salvalo nella posizione desiderata.


* **Progetti esistenti:** Se per qualsiasi motivo lasci un progetto con modifiche non ancora salvate automaticamente, Analysis Workspace richiede di salvare le modifiche o fornisce un messaggio di avviso.

   Di seguito sono riportati alcuni scenari comuni:

### Apri un altro progetto

Se apri un progetto aggiuntivo mentre lavori a un progetto contenente modifiche non ancora salvate automaticamente, Analysis Workspace richiede di salvare il progetto corrente prima di uscire.

Sono disponibili le seguenti opzioni:

* **Salva:** Sostituisce la copia locale del progetto salvata automaticamente più recente con le modifiche più recenti.
* **Salva con nome:** Salva le modifiche più recenti come nuovo progetto. Il progetto originale viene salvato solo con le ultime modifiche salvate automaticamente.
* **Elimina modifiche:** Ignora le modifiche più recenti. Il progetto conserva le modifiche salvate automaticamente più recenti.

![](assets/existing-save.png)

### Spostarsi o chiudere una scheda

Se ti allontani dalla pagina o chiudi la scheda del browser durante la visualizzazione di un progetto con modifiche non ancora salvate automaticamente, il browser avverte che le modifiche non salvate andranno perse. È possibile scegliere di uscire o annullare.

![](assets/browser-image.png)

### Arresto anomalo del browser o timeout della sessione

Se il browser si blocca o se la sessione si interrompe, alla successiva accesso ad Analysis Workspace viene richiesto di recuperare eventuali modifiche al progetto che non sono ancora state salvate automaticamente.

Di seguito è riportata la finestra di dialogo Recupero progetto che visualizza la prima volta che accedi ad Analysis Workspace dopo un arresto anomalo o un timeout.

Seleziona **Sì** per ripristinare il progetto dalla copia salvata automaticamente più recente.

Seleziona **No** per eliminare la copia salvata automaticamente e aprire l’ultima versione del progetto salvata dall’utente.

![](assets/project-recovery.png)

Per i **nuovi** progetti che non sono mai stati salvati, non è possibile recuperare le modifiche non salvate.

## Aprire la versione precedente {#previous-version}

Per aprire una versione precedente di un progetto:

1. Vai a **[!UICONTROL Project]** > **[!UICONTROL Open previous version]**

   ![](assets/previous-versions.png)

1. Rivedi l’elenco delle versioni precedenti disponibili.
   Vengono visualizzati [!UICONTROL Timestamp] e [!UICONTROL Editor], oltre a [!UICONTROL Notes] se sono state aggiunte al momento del salvataggio dell’[!UICONTROL Editor]. Le versioni senza note sono conservate per 90 giorni; le versioni con note sono memorizzate per 1 anno.
1. Seleziona una versione precedente e fai clic su **[!UICONTROL Load]** (Carica).
La versione precedente viene quindi caricata con una notifica. La versione precedente diventa la versione salvata corrente del progetto solo dopo aver fatto clic su **[!UICONTROL Save]**. Se ti sposti dalla versione caricata, quando torni viene visualizzata l’ultima versione salvata del progetto.
