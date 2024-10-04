---
description: In Analysis Workspace, le metriche possono essere utilizzate in due modi.
title: Metriche
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 13%

---

# Progetti programmati

I progetti Analysis Workspace pianificati possono essere gestiti in Customer Journey Analytics utilizzando **[!UICONTROL Components]** > **[!UICONTROL Scheduled projects]**.

In **[!UICONTROL Scheduled Projects]** è possibile modificare ed eliminare pianificazioni ricorrenti dei progetti.  L&#39;[elenco progetti pianificato](#scheduled-project-list) mostra gli elementi creati da un utente specifico. Se l’account utente è disabilitato nell’applicazione, tutte le consegne pianificate si interrompono.

![Interfaccia progetti pianificati](assets/scheduled-projects.png)

## Elenco progetti programmati

Nell&#39;elenco Progetti pianificati vengono visualizzate le colonne relative a:

| Colonna | Descrizione |
| --- | --- |
| ![CasellaSelezione](/help/assets/icons/SelectBox.svg) | Quando sono selezionati uno o più progetti programmati, nella parte inferiore dell’interfaccia Progetti programmati viene visualizzata una barra blu delle azioni. Vedi [Azioni](#actions) per ulteriori dettagli. |
| ![Stella](/help/assets/icons/Star.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un progetto pianificato. |
| **[!UICONTROL Schedule ID]** | Un ID utilizzato principalmente a scopo di debug. |
| **[!UICONTROL Name]** | Nome del progetto.<br/>Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare ulteriori dettagli sul progetto pianificato.<br/>Selezionare ![Altro](/help/assets/icons/More.svg) per aprire un menu di scelta rapida. Da questo menu puoi:<ul><li>![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** un progetto pianificato.</li><li>![Etichette](/help/assets/icons/Labels.svg) **[!UICONTROL Tag]** un progetto pianificato.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** un progetto pianificato.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]**: esporta un progetto pianificato in un file CSV.</li></ul> |
| **[!UICONTROL Owner]** | La persona che ha creato ed è proprietaria del progetto. |
| **[!UICONTROL Tags]** | (facoltativo) Assegnare tag è un modo efficace per organizzare progetti. Tutti gli utenti possono creare tag e applicarne uno o più a un progetto. Tuttavia, puoi visualizzare solo i tag dei progetti di tua proprietà o che sono stati condivisi con te. |
| **[!UICONTROL Delivered to]** | Destinatari del progetto pianificato. |
| **[!UICONTROL Expiration date]** | Puoi impostare la data di scadenza fino a un anno, indipendentemente dalla frequenza di pianificazione. |
| **[!UICONTROL Frequency]** | Con quale frequenza desideri che questo progetto di pianificazione venga inviato a uno o più destinatari. |
| **[!UICONTROL Execution Time]** | A che ora del giorno viene inviato questo progetto programmato. |
| **[!UICONTROL Number of Queries]** | Il numero di query su questo progetto. |
| **[!UICONTROL Longest Date Range]** | L’intervallo di date più lungo definito per il progetto pianificato. Questo valore potrebbe essere rilevante per analizzare i problemi di prestazioni. Per ulteriori informazioni, vedere [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md). |
| **[!UICONTROL Number of queries]** | Numero di query eseguite per il progetto pianificato. Questo valore potrebbe essere rilevante per analizzare i problemi di prestazioni. Per ulteriori informazioni, vedere [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md). |


È possibile utilizzare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per configurare le colonne da visualizzare.

Cerca un progetto pianificato utilizzando ![Ricerca](/help/assets/icons/Search.svg). Puoi anche vedere se sono stati applicati filtri dal pannello Filtri. Per rimuovere un filtro, selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per un filtro. Per rimuovere tutti i filtri, selezionare **[!UICONTROL Clear all]**.

Per modificare un progetto pianificato, seleziona il titolo del progetto. Utilizza la finestra di dialogo **[!UICONTROL Edit scheduled project]** per aggiornare i dettagli della pianificazione.

![Modifica progetto pianificato](assets/edit-scheduled-project.png)

Selezionare **[!UICONTROL Update]** per aggiornare la pianificazione.




## Azioni

Di seguito sono riportate le azioni più comuni di Gestione progetti programmati. Puoi selezionare le azioni dal menu di scelta rapida o dalla barra blu delle azioni quando selezioni uno o più progetti pianificati.

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![Chiudi](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selezionato]** | Seleziona per deselezionare i progetti pianificati selezionati. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina i progetti pianificati selezionati per il progetto; i progetti non vengono eliminati. |
| ![Etichette](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Assegna tag ai progetti pianificati selezionati. In **[!UICONTROL Tag Scheduled projects]** selezionare i tag e selezionare **[!UICONTROL Save]** da salvare. |
| ![CerchioSegno di spunta](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** | Approva i progetti programmati selezionati. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Esporta i progetti pianificati selezionati in un file denominato `Export Scheduled Projects List.csv`. |


## Filtro

È possibile filtrare i progetti pianificati [Elenco progetti pianificati](#scheduled-project-list) utilizzando il pannello di filtro. Per mostrare o nascondere il pannello dei filtri, utilizza ![Filtro](/help/assets/icons/Filter.svg).

Il pannello dei filtri è costituito dalle sezioni seguenti.

### Tag

| Tag | Descrizione |
|---|---|
| ![Tag](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | La sezione **[!UICONTROL Tags]** consente di filtrare i tag. <ul><li>![Cerca](/help/assets/icons/Search.svg) **[!UICONTROL Search Tags]** per cercare i tag da utilizzare per filtrare.</li><li>È possibile selezionare più tag. I tag disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>7︎⃣: numero di progetti pianificati associati al tag specifico.</li></ul></li></ul> |


### Proprietari

| Proprietario | Descrizione |
|---|---|
| ![Proprietari](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | La sezione **[!UICONTROL Owner]** consente di filtrare in base ai proprietari. <ul><li>Puoi utilizzare ![Cerca](/help/assets/icons/Search.svg) *Cerca proprietari* per cercare i proprietari da utilizzare per filtrare.</li><li>È possibile selezionare più di un proprietario. I proprietari disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>4︎⃣: numero di progetti pianificati associati al proprietario specifico.</li></ul></li></ul> |


### Altri filtri

| Altri filtri | Descrizione |
|---|---|
| ![Altri filtri](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | La sezione **[!UICONTROL Other filters]** consente di filtrare in base ad un altro filtro predefinito.<ul><li>Puoi selezionare una o più delle seguenti opzioni:<ul><li> **[!UICONTROL Expired]**: filtro per progetti pianificati scaduti.</li><li>**[!UICONTROL Failed]**: filtro per progetti pianificati per i quali la pianificazione non è riuscita.</li></ul>Ciò che puoi selezionare dipende dal tuo ruolo e dalle autorizzazioni.</li><li>Puoi selezionare più di un altro filtro. Gli altri filtri disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>4︎⃣: numero di progetti pianificati associati all’altro filtro specifico.</li></ul></li></ul> |
