---
description: In Analysis Workspace, le metriche possono essere utilizzate in due modi.
title: Metriche
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 22%

---

# Progetti programmati

I progetti Analysis Workspace pianificati possono essere gestiti in Customer Journey Analytics utilizzando **[!UICONTROL Components]** > **[!UICONTROL Scheduled projects]**.

In **[!UICONTROL  Scheduled Projects]** è possibile modificare ed eliminare pianificazioni ricorrenti dei progetti. Cerca una pianificazione utilizzando ![Cerca](/help/assets/icons/Search.svg) nel campo di ricerca. In alternativa, utilizza le opzioni filtro ![Filtro](/help/assets/icons/Filter.svg) nel pannello a sinistra. È possibile filtrare per **[!UICONTROL Tag]**, **[!UICONTROL Owners]** e **[!UICONTROL Other filters]**.

Nell&#39;elenco Progetti pianificati sono visualizzate le colonne relative a:

| Campo | Descrizione |
| --- | --- |
| ![Stella](/help/assets/icons/Star.svg) | Selezionando ![Stella](/help/assets/icons/Star.svg) questa pianificazione diventa la preferita. |
| **[!UICONTROL Schedule ID]** | Un ID utilizzato principalmente a scopo di debug. |
| [!UICONTROL Name] | Nome del progetto.<br/>Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare ulteriori dettagli sul progetto pianificato.<br/>Selezionare ![Altro](/help/assets/icons/More.svg) per aprire un menu di scelta rapida. Da questo menu puoi:<ul><li>![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** un progetto pianificato.</li><li>![Etichette](/help/assets/icons/Labels.svg) **[!UICONTROL Tag]** un progetto pianificato.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** un progetto pianificato.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export CSV]**: esporta un progetto pianificato in un file CSV.</li></ul> |
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

Progetti programmati mostra gli elementi creati da un utente specifico. Se l’account utente è disabilitato nell’applicazione, tutte le consegne pianificate si interrompono.



## Azioni

Di seguito sono riportate le azioni più comuni di Gestione progetti programmati. Quando selezioni più di un progetto pianificato, puoi selezionare le azioni dal menu di scelta rapida o dalla barra blu delle azioni.

| Azione | Descrizione |
|---|---|
| **[!UICONTROL Approve]** | Approva il progetto pianificato. |
| **[!UICONTROL Edit]** | Fai clic sul titolo della pianificazione per aggiornare le impostazioni di consegna. |
| **[!UICONTROL Delete]** | Elimina la pianificazione selezionata per il progetto; il progetto stesso non viene eliminato. |
| **[!UICONTROL Tag]** | Assegna tag al progetto pianificato in modo che i progetti siano più facili da trovare. |

Utilizzando il filtro ![Filtro](/help/assets/icons/Filter.svg), è inoltre possibile eseguire le azioni seguenti:

| Azione | Descrizione |
|---|---|
| **[!UICONTROL View failed schedules]** | Passare a **[!UICONTROL Other filters]** e selezionare **[!UICONTROL Failed]** per visualizzare le pianificazioni non riuscite. |
| **[!UICONTROL View expired schedules]** | Passare a **[!UICONTROL Other filters]** e selezionare **[!UICONTROL Expired]** per visualizzare le pianificazioni scadute. Fai clic sul titolo della pianificazione per impostare una nuova pianificazione di consegna. |

