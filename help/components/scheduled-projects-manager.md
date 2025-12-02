---
description: Scopri come gestire i progetti pianificati.
title: Progetti pianificati
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 35%

---

# Progetti pianificati

I progetti Analysis Workspace pianificati possono essere gestiti in Customer Journey Analytics utilizzando **[!UICONTROL Componenti]** > **[!UICONTROL Progetti pianificati]**.

In **[!UICONTROL Progetti pianificati]**, puoi modificare ed eliminare pianificazioni ricorrenti di progetti.  L&#39;[elenco progetti pianificato](#scheduled-project-list) mostra gli elementi creati da un utente specifico. Se l’account utente è disabilitato nell’applicazione, tutte le consegne pianificate si interrompono.

![Interfaccia progetti pianificati](assets/scheduled-projects.png)

## Elenco progetti programmati

Nell&#39;elenco Progetti pianificati ➊ sono visualizzate le colonne per:

| Colonna | Descrizione |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Quando sono selezionati uno o più progetti programmati, nella parte inferiore dell’interfaccia Progetti programmati viene visualizzata una barra blu delle azioni. Per ulteriori dettagli, consulta [Azioni](#actions). |
| ![Stella](/help/assets/icons/Star.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un progetto pianificato. |
| **[!UICONTROL ID pianificazione]** | Un ID utilizzato principalmente a scopo di debug. |
| **[!UICONTROL Nome]** | Nome del progetto.<br/>Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare ulteriori dettagli sul progetto pianificato.<br/>Selezionare ![Altro](/help/assets/icons/More.svg) per aprire un menu di scelta rapida. Da questo menu puoi:<ul><li>![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina]** un progetto pianificato.</li><li>![Etichette](/help/assets/icons/Labels.svg) **[!UICONTROL Contrassegna]** un progetto pianificato.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approva]** un progetto pianificato.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Esporta CSV]**: esporta un progetto pianificato in un file CSV.</li></ul> |
| **[!UICONTROL Proprietario]** | La persona che ha creato ed è proprietaria del progetto. |
| **[!UICONTROL Tag]** | (facoltativo) Assegnare tag è un modo efficace per organizzare progetti. Tutti gli utenti possono creare tag e applicarne uno o più a un progetto. Tuttavia, puoi visualizzare solo i tag dei progetti di tua proprietà o che sono stati condivisi con te. |
| **[!UICONTROL Consegnato a]** | Destinatari del progetto pianificato. |
| **[!UICONTROL Data di scadenza]** | Puoi impostare la data di scadenza massima fino a un anno, indipendentemente dalla frequenza di pianificazione. |
| **[!UICONTROL Frequenza]** | Con quale frequenza desideri che questo progetto di pianificazione venga inviato a uno o più destinatari. |
| **[!UICONTROL Tempo di esecuzione]** | A che ora del giorno viene inviato questo progetto programmato. |
| **[!UICONTROL Numero di query]** | Il numero di query su questo progetto. |
| **[!UICONTROL Intervallo di date più lungo]** | L’intervallo di date più lungo definito per il progetto pianificato. Questo valore potrebbe essere rilevante per analizzare i problemi di prestazioni. Per ulteriori informazioni, vedere [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md). |
| **[!UICONTROL Numero di query]** | Numero di query eseguite per il progetto pianificato. Questo valore potrebbe essere rilevante per analizzare i problemi di prestazioni. Per ulteriori informazioni, vedere [Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md). |


È possibile utilizzare ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per configurare le colonne da visualizzare.

Cerca un progetto pianificato utilizzando ![Ricerca](/help/assets/icons/Search.svg). Puoi anche vedere se sono stati applicati filtri dal pannello Filtri. Per rimuovere un filtro, selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per un filtro. Per rimuovere tutti i filtri, selezionare **[!UICONTROL Cancella tutto]**.

Per modificare un progetto pianificato, seleziona il titolo del progetto. Utilizza la finestra di dialogo **[!UICONTROL Modifica progetto pianificato]** per aggiornare i dettagli della pianificazione. Vedi [Invia file ad altri](../analysis-workspace/export/t-schedule-report.md) per ulteriori dettagli.

![Modifica progetto pianificato](assets/edit-scheduled-project.png)

Seleziona **[!UICONTROL Aggiorna]** per aggiornare la pianificazione.




## Azioni

Di seguito sono riportate le azioni comuni di Gestione progetti programmati: Puoi selezionare le azioni dal menu di scelta rapida o dalla barra blu delle azioni quando selezioni uno o più progetti pianificati.

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![Chiudi](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selezionato]** | Seleziona per deselezionare i progetti pianificati selezionati. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Elimina]** | Elimina i progetti pianificati selezionati per il progetto; i progetti non vengono eliminati.  <p>Per informazioni sull&#39;eliminazione di un progetto, vedere [Panoramica progetti](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> |
| ![Etichette](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Assegna tag ai progetti pianificati selezionati. In **[!UICONTROL Assegna tag ai progetti pianificati]** seleziona i tag e seleziona **[!UICONTROL Salva]** per salvare. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approva]** | Approva i progetti programmati selezionati. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Esporta in CSV]** | Esporta i progetti pianificati selezionati in un file denominato `Export Scheduled Projects List.csv`. |


## Filtro

Puoi filtrare i progetti pianificati [Elenco progetti pianificati](#scheduled-project-list) utilizzando il pannello dei filtri ➌. Per mostrare o nascondere il pannello dei filtri, utilizza l’icona ![Filtro](/help/assets/icons/Filter.svg).

Il pannello dei filtri è costituito dalle sezioni seguenti.

### Tag

| Tag | Descrizione |
|---|---|
| ![Tag](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | La sezione **[!UICONTROL Tag]** consente di filtrare i tag. <ul><li>Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) **[!UICONTROL Ricerca tag]** per cercare i tag in base ai quali applicare il filtro.</li><li>Puoi selezionare più di un tag. I tag disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>7︎⃣: numero di progetti pianificati associati al tag specifico.</li></ul></li></ul> |


### Proprietari

| Proprietario | Descrizione |
|---|---|
| ![Proprietari](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | La sezione **[!UICONTROL Proprietario]** consente di filtrare in base ai proprietari. <ul><li>Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) *Ricerca proprietari* per cercare i proprietari da utilizzare per filtrare.</li><li>Puoi selezionare più di un proprietario. I proprietari disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>4︎⃣: numero di progetti pianificati associati al proprietario specifico.</li></ul></li></ul> |


### Altri filtri

| Altri filtri | Descrizione |
|---|---|
| ![Altri filtri](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | La sezione **[!UICONTROL Altri filtri]** ti consente di filtrare in base ad un altro filtro predefinito.<ul><li>È possibile scegliere una o più delle opzioni seguenti:<ul><li> **[!UICONTROL Scaduto]**: applica il filtro ai progetti pianificati scaduti.</li><li>**[!UICONTROL Non riuscito]**: filtrare i progetti pianificati per i quali la pianificazione non è riuscita.</li></ul>Ciò che puoi selezionare dipende dal tuo ruolo e dalle autorizzazioni.</li><li>Puoi selezionare più di un altro filtro. Gli altri filtri disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>4︎⃣: numero di progetti pianificati associati all’altro filtro specifico.</li></ul></li></ul> |
