---
description: Scopri gli errori e la risoluzione dei problemi di Analysis Workspace.
title: Errori e risoluzione dei problemi
feature: Workspace Basics
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
TQID: https://experienceleague.adobe.com/sRztp43YkOt8oCDqPJH17s5jc9ukMa1NJsl9ZpOY-MQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 588
ht-degree: 85%

---

# Errori e risoluzione dei problemi

È possibile che, durante l’interazione con Analysis Workspace, si verifichino errori che possono influire sulla funzionalità e sulle prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni possibili.

## Messaggi di errore

Alcuni messaggi di errore comuni che potrebbero verificarsi durante l’utilizzo di Analysis Workspace:

| Messaggio di errore | Perché si verifica l’errore? | Ottimizzazione |
| --- | --- | --- |
| [!UICONTROL La visualizzazione dati presenta un numero di report insolitamente elevato. Riprova più tardi.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una visualizzazione di dati specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di reporting. | Distribuisci le richieste e le pianificazioni per la visualizzazione di dati in modo più uniforme durante l’intera giornata.<p>Gli amministratori possono utilizzare il [Reporting Activity Manager per identificare e annullare le richieste](/help/reporting-activity-manager/reporting-activity-overview.md) che utilizzano la capacità di reporting.</p> |
| [!UICONTROL Il report è troppo complesso. Rivedi le best practice per la creazione di rapporti di Analysis Workspace.] | La richiesta di reporting è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla complessità della richiesta. | Semplifica la richiesta. Ad esempio, riduci l’intervallo di date, semplifica i criteri di segmentazione o rimuovi alcune colonne o righe nella tabella. In alternativa, potresti anche suddividere la tabella in richieste separate. |
| [!UICONTROL La visualizzazione dati sta attualmente superando la capacità di reporting. Semplificare la richiesta o riprovare più tardi.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una visualizzazione di dati specifica. Questo errore è causato da richieste API, progetti pianificati e utenti simultanei che eseguono richieste di reporting. | Distribuisci le richieste e le pianificazioni per la visualizzazione di dati in modo più uniforme durante l’intera giornata. |
| [!UICONTROL Si è verificato un errore di sistema. Registra una richiesta dell&#39;Assistenza clienti in **[!UICONTROL Guida > Invia ticket assistenza]** e includi il codice di errore.] | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all’Assistenza clienti. |
| [!UICONTROL Errore 500: impossibile caricare la pagina] | I problemi relativi alla rete locale, come le [impostazioni del firewall](/help/technotes/ip-addresses.md) aziendale, contribuiscono a questo errore. Inoltre, è possibile che Adobe stia affrontando un problema che necessita di essere risolto. | Prova a eseguire di nuovo l’accesso dopo alcuni minuti. Se il problema persiste, invia il codice ID istanza EIM all’Assistenza clienti. |
| [!UICONTROL La richiesta non è riuscita a causa di un numero eccessivo di colonne o righe preconfigurate.] | La tabella contiene troppe celle a forma libera (righe * colonne). | Rimuovi alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |


## Risoluzione dei problemi

Quando utilizzi Analysis Workspace, puoi usare le informazioni riportate di seguito per risolvere alcuni problemi comuni.

| Problema | Come risolverlo |
|---|---|
| Quando trascino una metrica, un messaggio indica *Dati non validi*. | Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Posiziona invece le metriche una accanto all’altra. |
| Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri. | Se crei correttamente un report Workspace, ma non sono presenti dati, puoi controllare alcuni elementi:<ul><li>Se hai applicato un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.</li><li>Controlla l’intervallo di date in alto a destra e accertati che sia impostato sul valore desiderato.</li><li>Vai al tuo sito web e utilizza il [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it) per convalidare i dati raccolti.</li></ul> |
