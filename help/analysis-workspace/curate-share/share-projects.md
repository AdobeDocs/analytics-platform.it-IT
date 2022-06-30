---
description: Condivisione e ruoli dei progetti in Workspace
keywords: Condivisione di Analysis Workspace
title: Condividere progetti
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '1023'
ht-degree: 100%

---

# Condividere progetti

La condivisione rende un progetto disponibile ad altri utenti di Analysis Workspace all’interno dell’azienda. Qualsiasi [cura](curate.md) applichi viene visualizzata all’apertura del progetto da parte dei destinatari.

## Ruoli di progetto {#Roles}

Puoi aggiungere i destinatari a uno dei tre ruoli di progetto. I ruoli di progetto sono legati all’ID dell’utente e del progetto specifico. I ruoli di progetto sono indipendenti dalle autorizzazioni utente gestite nella [Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it).

| Ruolo | Controllo progetto |
|---|---|
| Can edit | I destinatari possono **[!UICONTROL Save]** le modifiche a un progetto e fungere da co-proprietari. Questo ruolo è utile se desideri gestire un progetto con altri colleghi; ciò include la modifica e l’eliminazione degli elenchi dei destinatari per un progetto condiviso. <br>Nota: Analysis Workspace al momento non supporta la collaborazione in tempo reale, pertanto si consiglia di modificare un progetto solo un utente alla volta. Se i progetti vengono salvati contemporaneamente, viene mantenuta l’ultima versione. |
| Can duplicate | I destinatari possono **[!UICONTROL Save as]** e accedere alla barra a sinistra. Le interazioni del progetto non sono limitate in questo ruolo. Questo ruolo è utile se desideri condividere un progetto con utenti che conoscono i dati dell’organizzazione e sanno come utilizzare Analysis Workspace, ma non desideri che il progetto venga modificato. |
| Can view | I destinatari non possono salvare con nome e non hanno accesso alla barra a sinistra. Anche le interazioni del progetto sono limitate. Questo ruolo è utile se desideri condividere un progetto con utenti che hanno meno familiarità con la struttura dei dati della tua organizzazione e con Analysis Workspace o Customer Journey Analytics in genere. Tuttavia, desideri comunque che utilizzino dati e informazioni in un ambiente sicuro.<br>Scopri di più sull’[esperienza di progetto Can view](/help/analysis-workspace/curate-share/view-only-projects.md). |

>[!IMPORTANT]
> I destinatari del progetto aggiunti prima del 18 giugno 2020 sono stati trasferiti in un ruolo di progetto. Gli utenti amministratore sono passati al ruolo **[!UICONTROL Can edit]** e gli utenti non amministratori sono passati al ruolo **[!UICONTROL Can duplicate]**. Questi ruoli forniscono la stessa esperienza di progetto che avevano in precedenza. Inoltre, tutti i gruppi (incluso “All”) sono stati trasferiti al ruolo **[!UICONTROL Can duplicate]**.

### Nessun ruolo assegnato (destinatari del collegamento al progetto)

Se a un destinatario non viene assegnato un ruolo e riceve un [collegamento](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=it) al progetto (**[!UICONTROL Share]>[!UICONTROL Get project link]**), per impostazione predefinita gli verrà assegnato un ruolo. Gli amministratori ricevono **[!UICONTROL Can edit]** e i non amministratori **[!UICONTROL Can duplicate]**.

### Più ruoli assegnati

Se un destinatario viene posizionato in più ruoli, avrà sempre l’esperienza di livello più elevato. Ciò potrebbe verificarsi se un destinatario viene aggiunto sia come singolo utente che come parte di un gruppo. Ad esempio, se a un destinatario viene assegnato il ruolo **[!UICONTROL Can edit]** come singolo utente e il ruolo **[!UICONTROL Can view]** come membro di un gruppo, riceverà un’esperienza di progetto **[!UICONTROL Can edit]**.

### Amministratori e ruoli

Gli amministratori inseriti in un ruolo **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** riceveranno tali esperienze limitate quando aprono un progetto. Se necessario, un amministratore può elevare il proprio ruolo a **[!UICONTROL Can edit]** in qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**.

## Aggiungere destinatari al progetto condiviso {#Add}

Per aggiungere dei destinatari al progetto condiviso:

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share project]**.
In presenza di modifiche non salvate, ti verrà richiesto di salvare prima il progetto.
1. Aggiungi destinatari o gruppi di destinatari.
Fai riferimento all’icona della guida nella parte superiore per le descrizioni di ciascun ruolo.
1. Condividi componenti di progetto incorporati (filtri, metriche calcolate e intervalli di date) con tutti i destinatari (facoltativo).
Una volta condivisi, tali componenti sono disponibili nel menu a discesa Components nell’interfaccia Workspace del destinatario. Tieni presente che questa impostazione non è persistente, è una singola azione da eseguire al momento della condivisione.
1. Imposta questa pagina come pagina di destinazione per i destinatari (facoltativo).
Questa impostazione non è persistente; è una singola azione da eseguire al momento della condivisione.
1. Fai clic su Share.
Puoi anche fare clic su **[!UICONTROL Curate and Share]** per applicare automaticamente la cura del progetto. Se un progetto è già stato condiviso, questi pulsanti indicano **[!UICONTROL Update]** e **[!UICONTROL Curate & Update]**. Ulteriori informazioni sulla [cura dei progetti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=it).

![](assets/share-proj-modal.png)

## Condivisione con gruppi di destinatari {#Groups}

Tutti gli utenti possono condividere i progetti con gruppi, che sono una raccolta di destinatari. In Customer Journey Analytics, i gruppi sono definiti dai profili di prodotto nell’[Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it).

* Gli amministratori possono condividere con qualsiasi gruppo, incluso “All”.
* I non amministratori possono condividere con i gruppi di cui sono membri, ad eccezione di “All”.

## Condividere un collegamento al progetto {#Links}

Puoi ottenere un collegamento a un progetto in **[!UICONTROL Share]>[!UICONTROL Get project link]**. Quando fanno clic su di esso, ai destinatari viene richiesto di effettuare l’accesso prima di poter visualizzare il progetto. Se il destinatario non è stato posizionato in un ruolo, riceverà un ruolo predefinito. Gli amministratori ricevono **[!UICONTROL Can edit]** e i non amministratori **[!UICONTROL Can duplicate]**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=it) sulla creazione di collegamenti condivisibili ai progetti Workspace.

## Condivisione di progetti nel Project manager {#Manager}

I progetti possono essere condivisi anche da **[!UICONTROL Components]>[!UICONTROL Projects]**. Un singolo progetto può essere condiviso seguendo gli stessi passaggi indicati sopra.  Se sono stati selezionati più progetti da condividere, i destinatari verranno aggiunti all’elenco esistente di destinatari per ciascun progetto.

Ad esempio:

* Il progetto A è condiviso con i destinatari 1, 2, 3
* Il progetto B è condiviso con i destinatari 4, 5, 6

Con i progetti A e B selezionati, i destinatari 4 e 7 vengono aggiunti agli elenchi di condivisione. Il nuovo elenco di condivisione per ciascun progetto ora è:

* Progetto A: 1, 2, 3, 4, 7
* Progetto B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Domande frequenti {#FAQs}

| Domanda | Risposta |
|---|---|
| Cosa succede se due editor salvano un progetto contemporaneamente? | Le modifiche non vengono unite e viene mantenuta l’ultima versione del progetto salvata. Analysis Workspace non supporta attualmente la collaborazione in tempo reale. |
| In qualità di amministratore, quale esperienza di progetto visualizzerò? | Gli amministratori inseriti in un ruolo **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** riceveranno tali esperienze limitate quando aprono un progetto. Se necessario, un amministratore può elevare il proprio ruolo a **[!UICONTROL Can edit]** in qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Cosa succede se un destinatario viene collocato in un ruolo come singolo utente e in un altro ruolo come membro di un gruppo? | Se un destinatario viene posizionato in più ruoli, riceverà sempre l’esperienza di livello più elevato. Ad esempio, se a un destinatario viene assegnato il ruolo **[!UICONTROL Can edit]** come singolo utente e il ruolo **[!UICONTROL Can view]** come membro di un gruppo, riceverà un’esperienza di progetto **[!UICONTROL Can edit]**. |
| Quale esperienza riceve un destinatario se apre un collegamento al progetto? | I destinatari ricevono il ruolo in cui li hai inseriti nella modalità di condivisione. Se a un destinatario non viene assegnato un ruolo e riceve un collegamento al progetto (**[!UICONTROL Share]>[!UICONTROL Get project link]**), per impostazione predefinita gli verrà assegnato un ruolo. Gli amministratori ricevono **[!UICONTROL Can edit]** e i non amministratori **[!UICONTROL Can duplicate]**. |
