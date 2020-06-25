---
description: Condivisione dei progetti e ruoli dei progetti in Workspace
keywords: Analysis Workspace sharing
title: Condivisione di progetti Workspace
translation-type: tm+mt
source-git-commit: 3a2cb7ad15f1491ef4fe6fdcb3135b29675c40e8
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 5%

---


# Condivisione di progetti Workspace

>[!NOTE] Stai visualizzando la documentazione per  Analysis Workspace in Customer Journey Analytics. Il set di funzioni è leggermente diverso da [Analysis Workspace in Adobe  Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html)tradizionale. [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

La condivisione rende un progetto disponibile ad altri utenti Analysis Workspace &#39;organizzazione. Qualsiasi [cura](curate.md) applicata viene visualizzata all’apertura del progetto da parte dei destinatari.

## Ruoli del progetto {#Roles}

Puoi aggiungere i destinatari a uno dei tre ruoli di progetto. I ruoli del progetto sono legati all&#39;utente e all&#39;ID progetto specifico. I ruoli del progetto sono indipendenti dalle autorizzazioni utente gestite nella console [di amministrazione di](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html)Adobe Experience Cloud.

| Ruolo | Controllo progetto |
|---|---|
| Può modificare | I destinatari possono **[!UICONTROL Save]** modificare un progetto e fungere da co-proprietari. Questo ruolo è utile se si desidera gestire un progetto con altri colleghi; ciò include la modifica, l&#39;eliminazione e la modifica degli elenchi dei destinatari per un progetto condiviso. <br>Nota:  Analysis Workspace al momento non supporta la collaborazione in tempo reale, pertanto si consiglia di modificare un progetto solo da un utente alla volta. Se i progetti vengono salvati allo stesso tempo, l&#39;ultima versione viene mantenuta. |
| Può duplicare | I destinatari possono accedere **[!UICONTROL Save as]** e possono accedere alla barra a sinistra. Le interazioni dei progetti non sono limitate in questo ruolo. Questo ruolo è utile se desiderate condividere un progetto con utenti che conoscono i dati dell’organizzazione e come utilizzare  Analysis Workspace, ma non desiderate che il progetto venga modificato. |
| Può visualizzare | I destinatari non possono salvare con nome e non hanno accesso alla barra a sinistra. Anche le interazioni dei progetti sono limitate. Questo ruolo è utile se desiderate condividere un progetto con utenti che hanno meno familiarità con la struttura dei dati della vostra organizzazione,  Analysis Workspace o Adobe  Analytics in genere. Tuttavia, è comunque necessario che utilizzino dati e informazioni in un ambiente sicuro.<br>Scopri di più sull&#39;esperienza [](/help/analysis-workspace/curate-share/view-only-projects.md)Può visualizzare il progetto. |

>[!IMPORTANT]
> I destinatari del progetto aggiunti prima del 18 giugno 2020 sono stati trasferiti in un ruolo di progetto. Gli utenti amministratore sono passati al **[!UICONTROL Can edit]** ruolo e gli utenti non amministratori sono passati al **[!UICONTROL Can duplicate]** ruolo. Questi ruoli forniscono la stessa esperienza di progetto che avevano in precedenza. Inoltre, tutti i gruppi (incluso &quot;All&quot;) sono migrati al **[!UICONTROL Can duplicate]** ruolo.

### Nessun ruolo assegnato (destinatari del collegamento Progetto)

Se a un destinatario non viene assegnato un ruolo e riceve un collegamento al progetto (**[!UICONTROL Share]>[!UICONTROL Get project link]**), per impostazione predefinita verrà assegnato loro un ruolo. Gli amministratori ricevono **[!UICONTROL Can edit]**e i non amministratori ricevono **[!UICONTROL Can duplicate]**.

### Più ruoli assegnati

Se un destinatario viene posizionato in più ruoli, avrà sempre la massima esperienza. Ciò potrebbe verificarsi se un destinatario viene aggiunto sia come singolo che come parte di un gruppo. Ad esempio, se a un destinatario viene assegnato il **[!UICONTROL Can edit]** ruolo di individuo e il **[!UICONTROL Can view]** ruolo di membro di un gruppo, riceverà un&#39;esperienza di **[!UICONTROL Can edit]** progetto.

### Amministratori e ruoli

Gli amministratori inseriti in un ruolo **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** ruolo riceveranno tali esperienze limitate quando aprono un progetto. Se necessario, un amministratore può incrementare il proprio ruolo in **[!UICONTROL Can edit]** qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**.

## Aggiunta di destinatari al progetto condiviso {#Add}

Per aggiungere dei destinatari al progetto condiviso:

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share project]**.
In presenza di modifiche non salvate, vi verrà richiesto di salvare prima il progetto.
1. Aggiungi destinatari o gruppi di destinatari.
Fate riferimento all&#39;icona della guida nella parte superiore per le descrizioni di ciascun ruolo.
1. (Facoltativo) Condividi componenti di progetto incorporati (segmenti, metriche calcolate e intervalli di date) con tutti i destinatari.
Dopo essere stati condivisi, questi componenti verranno visualizzati nel menu a discesa Componenti dell&#39;area di lavoro del destinatario. Tenete presente che questa impostazione non persiste, ma rappresenta una singola azione al momento della condivisione.
1. (Facoltativo) Imposta questa pagina come pagina di destinazione per i destinatari.
Questa impostazione non è persistente; è una singola azione da eseguire al momento della condivisione.
1. Fai clic su Condividi.
Potete anche fare clic **[!UICONTROL Curate and Share]** per applicare automaticamente la cura del progetto. Se un progetto è già stato condiviso, questi pulsanti indicano **[!UICONTROL Update]** e **[!UICONTROL Curate & Update]**. Ulteriori informazioni sulla cura dei [progetti](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-workspace/curate-share/curate.html).

![](assets/share-proj-modal.png)

## Condivisione a gruppi di destinatari {#Groups}

Tutti gli utenti possono condividere i progetti a gruppi, che sono una raccolta di destinatari. In Adobe  Analytics, i gruppi sono definiti dai profili di prodotto nella console [di amministrazione di](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html)Adobe Experience Cloud.

* Gli amministratori possono condividere con qualsiasi gruppo, incluso &quot;All&quot;.
* I non amministratori possono condividere con i gruppi di cui sono membri, ad eccezione di &quot;All&quot;.

## Condivisione di un collegamento di progetto {#Links}

Puoi trovare un collegamento a un progetto in **[!UICONTROL Share]>[!UICONTROL Get project link]**. Quando un utente fa clic su di esso, i destinatari dovranno effettuare l&#39;accesso prima di atterrare nel progetto. Se il destinatario non è stato posizionato in un ruolo, riceverà un ruolo predefinito. Gli amministratori ricevono **[!UICONTROL Can edit]**e i non amministratori ricevono **[!UICONTROL Can duplicate]**.

## Condivisione di progetti in Project Manager {#Manager}

I progetti possono essere condivisi anche da **[!UICONTROL Components]>[!UICONTROL Projects]**. Un singolo progetto può essere condiviso seguendo gli stessi passaggi indicati sopra.  Se sono stati selezionati più progetti da condividere, i destinatari verranno aggiunti all&#39;elenco esistente di destinatari per ciascun progetto.

Ad esempio:

* Il progetto A è condiviso con i destinatari 1, 2, 3
* Il progetto B è condiviso con i destinatari 4, 5, 6

Con i progetti A e B selezionati, i destinatari 4 e 7 vengono aggiunti agli elenchi di condivisione. Il nuovo elenco di condivisione per ciascun progetto è ora:

* Progetto A: 1, 2, 3, 4, 7
* Progetto B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Domande frequenti {#FAQs}

| Domanda | Risposta |
|---|---|
| Cosa succede se due editor salvano un progetto contemporaneamente? | Le modifiche non vengono unite e l&#39;ultima versione del progetto salvata viene mantenuta.  Analysis Workspace non supporta attualmente la collaborazione in tempo reale. |
| In qualità di amministratore, quale esperienza di progetto visualizzerò? | Gli amministratori inseriti in un ruolo **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** ruolo riceveranno tali esperienze limitate quando aprono un progetto. Se necessario, un amministratore può incrementare il proprio ruolo in **[!UICONTROL Can edit]** qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Cosa succede se un destinatario viene collocato in un ruolo come singolo e in un altro ruolo come membro di un gruppo? | Se un destinatario viene posizionato in più ruoli, riceverà sempre l&#39;esperienza più alta. Ad esempio, se a un destinatario viene assegnato il **[!UICONTROL Can edit]** ruolo di individuo e il **[!UICONTROL Can view]** ruolo di membro di un gruppo, riceverà un&#39;esperienza di **[!UICONTROL Can edit]** progetto. |
| Che esperienza riceve un destinatario se apre un collegamento di progetto? | I destinatari ricevono il ruolo che li avete inseriti nella modalità di condivisione. Se a un destinatario non viene assegnato un ruolo e riceve un collegamento al progetto (**[!UICONTROL Share]>[!UICONTROL Get project link]**), per impostazione predefinita verrà assegnato loro un ruolo. Gli amministratori ricevono **[!UICONTROL Can edit]**e i non amministratori ricevono **[!UICONTROL Can duplicate]**. |
