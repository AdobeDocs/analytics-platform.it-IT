---
description: Scopri i messaggi di errore e come risolvere i problemi in Adobe Analysis Workspace
title: Errori comuni e risoluzione dei problemi in Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: ec32b7bca6fd4fc4b2652d1265048ec788f19718
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 70%

---

# Errori e risoluzione problemi

È possibile che, durante l’interazione con Analysis Workspace, si verifichino errori che possono influenzarne le funzionalità o le prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni possibili.

## Messaggi di errore

Alcuni messaggi di errore comuni che potrebbero verificarsi quando si utilizza Analysis Workspace:

| Messaggio di errore | Perché si verifica l’errore? | Ottimizzazione |
| --- | --- | --- |
| [!UICONTROL The data view is experiencing unusually heavy reporting. Please try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una visualizzazione di dati specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di reporting. | Distribuisci le richieste e le pianificazioni per la visualizzazione di dati in modo più uniforme durante l’intera giornata.<p>Gli amministratori possono utilizzare il [Reporting Activity Manager per identificare e annullare le richieste](/help/reporting-activity-manager/reporting-activity-overview.md) che utilizzano la capacità di reporting.</p> |
| [!UICONTROL This report is too complex. Please review best practices for building Analysis Workspace reports.] | La richiesta di reporting è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla complessità della richiesta. | Semplifica la tua richiesta. Ad esempio, riduci l’intervallo di date, semplifica i criteri di filtro o rimuovi alcune colonne o righe nella tabella. Puoi anche considerare di suddividere la tabella in richieste separate. |
| [!UICONTROL The data view is currently exceeding its reporting capacity. Please simplify the request or try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una visualizzazione di dati specifica. Questo errore è causato da richieste API, progetti pianificati e utenti simultanei che eseguono richieste di reporting. | Distribuisci le richieste e le pianificazioni per la visualizzazione di dati in modo più uniforme durante l’intera giornata. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all’Assistenza clienti. |
| [!UICONTROL Error 500: Failed to load page] | I problemi relativi alla rete locale, come le [impostazioni del firewall](https://experienceleague.adobe.com/en/docs/analytics/technotes/ip-addresses) aziendale, contribuiscono a questo errore. Inoltre, è possibile che Adobe stia affrontando un problema che necessita di essere risolto. | Prova a eseguire di nuovo l’accesso dopo alcuni minuti. Se il problema persiste, invia il codice ID istanza EIM all’Assistenza clienti. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | La tabella contiene troppe celle a forma libera (righe * colonne). | Rimuovi alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |


## Risoluzione dei problemi

Quando si utilizza Analysis Workspace, è possibile utilizzare le informazioni riportate di seguito per risolvere alcuni problemi comuni.

| Problema | Come risolvere i problemi |
|---|---|
| Quando trascino una metrica, visualizzo *Dati non validi*. | Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Posiziona invece le metriche una accanto all’altra. |
| Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri. | Se crei correttamente un report Workspace, ma non sono presenti dati, puoi controllare alcuni elementi:<ul><li>Se hai applicato un filtro nel report, i criteri di filtro potrebbero non corrispondere ad alcun dato. Prova a rimuovere il filtro o a regolare la definizione del filtro.</li><li>Controlla l’intervallo di date nell’angolo in alto a destra e accertati che sia impostato sul valore previsto.</li><li>Vai al tuo sito web e utilizza il [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it) per convalidare i dati raccolti.</li></ul> |
