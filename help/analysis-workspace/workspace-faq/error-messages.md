---
description: Scopri i messaggi di errore in Adobe Analysis Workspace e i relativi componenti
title: Messaggi di errore comuni in Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: fe089afb2022d8c4b50346bb81d6ba4ad6404014
workflow-type: ht
source-wordcount: '310'
ht-degree: 100%

---

# Messaggi di errore comuni

È possibile che, durante l’interazione con Analysis Workspace, si verifichino errori che influiscono anche sulle prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni possibili.

| Messaggio di errore | Perché si verifica? | Ottimizzazione |
| --- | --- | --- |
| [!UICONTROL The data view is experiencing unusually heavy reporting. Please try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una visualizzazione di dati specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di reporting. | Distribuisci le richieste e le pianificazioni per la visualizzazione di dati in modo più uniforme durante l’intera giornata.<p>Gli amministratori possono utilizzare il [Reporting Activity Manager per identificare e annullare le richieste](/help/reporting-activity-manager/reporting-activity-overview.md) che utilizzano la capacità di reporting.</p> |
| [!UICONTROL This report is too complex. Please review best practices for building Analysis Workspace reports.] | La richiesta di reporting è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla complessità della richiesta. | Facilità la richiesta abbreviando l’intervallo di date, semplificando i criteri di filtro o rimuovendo alcune colonne o righe nella tabella. In alternativa, puoi suddividere la tabella in più richieste separate. |
| [!UICONTROL The data view is currently exceeding its reporting capacity. Please simplify the request or try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una visualizzazione di dati specifica. Questo errore è causato da richieste API, progetti pianificati e utenti simultanei che eseguono richieste di reporting. | Distribuisci le richieste e le pianificazioni per la visualizzazione di dati in modo più uniforme durante l’intera giornata. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all’Assistenza clienti. |
| [!UICONTROL Error 500: Failed to load page] | I problemi relativi alla rete locale, come le [impostazioni del firewall](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=it) aziendale, contribuiscono a questo errore. Inoltre, è possibile che Adobe stia affrontando un problema che necessita di essere risolto. | Prova a eseguire di nuovo l’accesso dopo alcuni minuti. Se il problema persiste, invia il codice ID istanza EIM all’Assistenza clienti. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | La tabella contiene troppe celle a forma libera (righe * colonne). | Rimuovi alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |
