---
title: Domande frequenti su Customer Journey Analytics
description: Customer Journey Analytics - Domande frequenti.
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 51%

---


# Domande frequenti

## Prerequisiti

| Domanda | Risposta |
| --- | --- |
| È necessario [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] per [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] non sono richiesti per [!UICONTROL Customer Journey Analytics]. Al momento non sono ancora supportati. |
| È necessario [!UICONTROL Experience Cloud ID] (ECID) per [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supporta qualsiasi ID in un set di dati, sia esso o qualsiasi altro ID scelto.[!UICONTROL ECID] |
| In che modo si possono effettuare operazioni di ETL (Extract, Transform, Load, cioè Estrai, Trasforma, Carica) sui dati prima di inserirli in [!UICONTROL Customer Journey Analytics]? | Al momento, è necessario lavorare con un partner ETL (Unifi o Informatica) per trasformare i dati prima di inserirli in AEP. Se è necessario ETL dopo che i dati sono già stati acquisiti, [!UICONTROL Adobe Experience Platform Query Services] offre alcune opzioni limitate. |

## Fissaggio dei dati

| Domanda | Risposta |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] può effettuare lo stitching tra dispositivi o tra set di dati? | Sì. [!UICONTROL Customer Journey Analytics] è un sistema di analisi che richiede un proprio ID. Abbiamo rilasciato una soluzione cucitrice nel novembre del 2020. Ulteriori informazioni. |
| È supportato lo stitching da un comportamento anonimo a un comportamento autenticato? | No, non ancora. |

## Inserire dati in [!UICONTROL Customer Journey Analytics]

| Domanda | Risposta |
| --- | --- |
| È possibile combinare i dati di diverse sandbox [!UICONTROL Adobe Experience Platform] in una connessione [!UICONTROL Customer Journey Analytics]? | No, non è possibile accedere ai dati di sandbox diverse. È possibile combinare solo i set di dati che si trovano all’interno della stessa sandbox. [Ulteriori informazioni...](https://docs.adobe.com/content/help/it-IT/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Qual è la latenza prevista per [!UICONTROL Customer Journey Analytics] in [!UICONTROL Adobe Experience Platform]? | <ul><li>In condizioni di carico normale: &lt; 60 minuti <br>**Nota:** in caso di volume insolitamente elevato del flusso di dati che attraversa la pipeline, potrebbero essere necessarie fino a 24 ore.</li><li>In caso di recupero dei dati (fino a 13 mesi di dati, indipendentemente dalle dimensioni): &lt; 4 settimane</li></ul> |
| Come si collegano i dati online ai dati offline in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] è un sistema di analisi che richiede un proprio ID. Se l’ID della persona corrisponde nei diversi set di dati, [!UICONTROL Customer Journey Analytics] può collegare segmenti, attribuzione, flusso, fallout e così via tra i vari set di dati. |
| Come posso portare i miei dati offline in [!UICONTROL Customer Journey Analytics]? | Devi inserire tutti i dati in Experience Platform prima di poterli utilizzare con [!UICONTROL Customer Journey Analytics]. Se necessario, il team di Experience Platform che si occupa dell’onboarding dei dati ti può fornire consigli o consulenza. |
| Come si ottengono i dati [!UICONTROL Adobe Analytics] in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] i dati possono essere collegati  Experience Platform tramite il  [ connettore](https://docs.adobe.com/content/help/it-IT/experience-platform/sources/connectors/adobe-applications/analytics.html) di origine Adobe Analytics. La maggior parte dei campi [!UICONTROL Adobe Analytics] vengono trasferiti in formato XDM, ma altri campi non sono ancora disponibili (come [!UICONTROL Marketing Channels] dimensioni). |
| Quanto tempo è necessario per assemblare gli elementi dei set di dati in una visualizzazione dati? | Poche ore per iniziare e qualche giorno per recuperare gli ultimi 13 mesi di dati. |
| È necessario inserire dati PII per stabilire connessioni tra i dati? | No, puoi utilizzare qualsiasi ID, incluso un hash di un ID cliente, che non è un dato PII. |

## Componenti tradizionali [!UICONTROL Adobe Analytics]

| Domanda | Risposta |
| --- | --- |
| Cosa significa questo per il nostro prodotto [!UICONTROL Adobe Analytics] tradizionale? | [!UICONTROL Customer Journey Analytics] è il nostro prodotto di analisi di nuova generazione. Evolvere dai nostri prodotti attuali a [!UICONTROL Customer Journey Analytics] richiederà anni e molta coordinazione. Per ulteriori informazioni, consulta [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| Posso condividere segmenti da [!UICONTROL Customer Journey Analytics] ad AEP o altre soluzioni? | Non ancora. Stiamo studiando nuovi metodi innovativi per condividere in futuro segmenti da [!UICONTROL Customer Journey Analytics] ad AEP che non avranno un ritardo così lungo. Detto questo, è possibile condividere l’output di Query Services sul profilo unificato come soluzione alternativa. |
| Cos’è successo alla mia vecchia impostazione eVar? | eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in [!UICONTROL Customer Journey Analytics]. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query. |
| Dove sono ora tutte le impostazioni di persistenza relative alla sessione e alle variabili? | [!UICONTROL Customer Journey Analytics] applica tutte queste impostazioni al momento di creazione del rapporto ed esse si trovano ora in Data Views (Visualizzazioni dati). Le modifiche a queste impostazioni sono ora retroattive e si possono avere più versioni utilizzando più Data Views (Visualizzazioni dati). |
| Cosa succede ai segmenti o alle metriche calcolate esistenti? | [!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi,  utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti o delle metriche calcolate esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. |
| In che modo [!UICONTROL Customer Journey Analytics] gestisce le limitazioni `Uniques Exceeded`? | [!UICONTROL Customer Journey Analytics] non ha limiti di valore unici, quindi non c&#39;è bisogno di preoccuparsi per loro! |
| Se sono già un cliente [!DNL Data Workbench], posso passare subito a [!UICONTROL Customer Journey Analytics] | Dipende. Se fai un grande utilizzo del processo unificato dei clienti (UCP), ti consigliamo di aspettare fino a quando non sarà stato implementato il sistema di stitching. Se hai già tassi elevati di autenticazione dei clienti, se vuoi che tutti i tuoi dati vengano salvati in un’unica posizione o se desideri eliminare le eVar, Customer Journey Analytics potrebbe essere una buona soluzione. |

## Implicazioni dell&#39;eliminazione dei componenti dati

Per quanto riguarda la cancellazione, ci occupiamo di 6 componenti: progetti sandbox, schema, set di dati, connessione, visualizzazione dati e Workspace. Di seguito sono riportati alcuni possibili scenari per l’eliminazione di uno dei seguenti componenti:

| E se io... | Ciò si verifica... |
| --- | --- |
| Eliminare una sandbox in [!UICONTROL Adobe Experience Platform]? | L&#39;eliminazione di una sandbox interrompe il flusso di dati su qualsiasi connessione [!UICONTROL Customer Journey Analytics] ai dataset in quella sandbox. Attualmente, le connessioni nel CJA legate a quella sandbox non verranno eliminate automaticamente. |
| Eliminare uno schema in [!UICONTROL Adobe Experience Platform], ma non il/i dataset/i associato/i a questo schema? | [!UICONTROL Adobe Experience Platform] non consente l&#39;eliminazione di schemi a cui sono associati uno o più set di dati. Tuttavia, un amministratore con l&#39;insieme di diritti appropriato può eliminare prima i set di dati e quindi lo schema. |
| Eliminare un set di dati in [!UICONTROL Adobe Experience Platform]? | L&#39;eliminazione di un set di dati in AEP interrompe il flusso di dati da tale set di dati a tutte le connessioni che lo includono. Eventuali dati provenienti da tale dataset non vengono eliminati automaticamente dalle connessioni CJA associate. |
| Eliminare un set di dati in [!UICONTROL Customer Journey Analytics]? | Al momento non è possibile eliminare un dataset all&#39;interno di una connessione salvata. Dovreste eliminare l&#39;intera connessione e ricominciare da capo. Tuttavia, è possibile eliminare un set di dati in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch da un set di dati (in [!UICONTROL Adobe Experience Platform])? | Se un batch viene eliminato da un set di dati [!UICONTROL Adobe Experience Platform], lo stesso batch verrà rimosso da tutte le connessioni CJA che contengono tale batch specifico.  La CJA riceve una notifica di eliminazione batch in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch **durante l&#39;assimilazione di** in [!UICONTROL Customer Journey Analytics]? | Se nel set di dati è presente un solo batch, nessun dato o dato parziale proveniente da tale batch verrà visualizzato in [!UICONTROL Customer Journey Analytics]. L&#39;assimilazione verrà ripristinata. Se, ad esempio, nel set di dati sono presenti 5 batch e 3 di essi sono già stati acquisiti al momento dell&#39;eliminazione del set di dati, i dati provenienti da questi 3 batch saranno visualizzati in [!UICONTROL Customer Journey Analytics]. |
| Eliminare una connessione in [!UICONTROL Customer Journey Analytics]? | Un messaggio di errore indica che:<ul><li>Tutte le visualizzazioni dati create per la connessione eliminata non funzioneranno più.</li><li> Allo stesso modo, tutti i progetti Workspace che dipendono dalla visualizzazione dei dati nella connessione eliminata cesseranno di funzionare.</li></ul> |
| Eliminare una visualizzazione dati in [!UICONTROL Customer Journey Analytics]? | Un messaggio di errore indica che tutti i progetti Workspace dipendenti da questa visualizzazione dati eliminata cesseranno di funzionare. |
