---
description: Scopri i messaggi di errore in Adobe Analysis Workspace e i relativi componenti
title: Messaggi di errore comuni in Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: 51a20b0a1f003d2e6ce8baf4d7cec16bfa2fe5b3
workflow-type: ht
source-wordcount: '251'
ht-degree: 100%

---

# Messaggi di errore comuni

È possibile che, durante l’interazione con Analysis Workspace, si verifichino errori che influiscono anche sulle prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni possibili.

| Messaggio di errore | Perché si verifica? | Ottimizzazione |
| --- | --- | --- |
| [!UICONTROL The data view is currently exceeding its reporting capacity. Please simplify the request or try again later.] | La richiesta di generazione di rapporti è troppo complessa e deve essere semplificata. | Restringi i criteri del rapporto e prova a inviare di nuovo la richiesta. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all’Assistenza clienti. |
| [!UICONTROL Error 500: Failed to load page] | I problemi relativi alla rete locale, come le [impostazioni del firewall](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=it) aziendale, contribuiscono a questo errore. Inoltre, è possibile che Adobe stia affrontando un problema che necessita di essere risolto. | Prova a eseguire di nuovo l’accesso dopo alcuni minuti. Se il problema persiste, invia il codice ID istanza EIM all’Assistenza clienti. |
| [!UICONTROL One of the filters or the search in this visualization contains a text search that returned too many results.] | Il criterio del filtro o il filtro del rapporto è troppo ampio. | Restringi i criteri di ricerca e prova a inviare di nuovo la richiesta. |
| [!UICONTROL The request is too complex.] | La richiesta di generazione rapporti è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla dimensione della richiesta, troppi elementi associati in un filtro o un filtro di ricerca, inclusione di troppe metriche, combinazioni di dimensioni e metriche incompatibili, ecc. | Semplifica la richiesta rimuovendo alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | La tabella contiene troppe celle a forma libera (righe * colonne). | Rimuovi alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |
