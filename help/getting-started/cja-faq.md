---
title: Domande frequenti su Customer Journey Analytics
description: Customer Journey Analytics - Domande frequenti.
translation-type: tm+mt
source-git-commit: 3b3d0b0858d559e94f1bed6a31a63b018ed32a23
workflow-type: tm+mt
source-wordcount: '1142'
ht-degree: 47%

---


# Domande frequenti

## Prerequisiti

| Domanda | Risposta |
| --- | --- |
| Ho bisogno di [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] non sono richiesti per [!UICONTROL Customer Journey Analytics]. Al momento non sono ancora supportati. |
| Ho bisogno di [!UICONTROL Experience Cloud ID] (ECID) per [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supporta qualsiasi ID in un set di dati, sia esso o qualsiasi altro ID scelto.[!UICONTROL ECID] |
| In che modo si possono effettuare operazioni di ETL (Extract, Transform, Load, cioè Estrai, Trasforma, Carica) sui dati prima di inserirli in [!UICONTROL Customer Journey Analytics]? | Al momento, è necessario lavorare con un partner ETL (Unifi o Informatica) per trasformare i dati prima di inserirli in AEP. Se è necessario ETL dopo l’assimilazione dei dati, [!UICONTROL Adobe Experience Platform Query Services] fornisce alcune opzioni limitate. |

## Fissaggio dei dati

| Domanda | Risposta |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] può effettuare lo stitching tra dispositivi o tra set di dati? | Sì. [!UICONTROL Customer Journey Analytics] è un sistema di analisi che richiede un proprio ID. Abbiamo rilasciato una soluzione cucitrice nel novembre del 2020. Ulteriori informazioni. |
| È supportato lo stitching da un comportamento anonimo a un comportamento autenticato? | No, non ancora. |

## Inserire dati in [!UICONTROL Customer Journey Analytics]

| Domanda | Risposta |
| --- | --- |
| È possibile combinare i dati di diversi [!UICONTROL Adobe Experience Platform] sandbox in un [!UICONTROL Customer Journey Analytics] connection? | No, non è possibile accedere ai dati di sandbox diverse. È possibile combinare solo i set di dati che si trovano all’interno della stessa sandbox. [Ulteriori informazioni...](https://docs.adobe.com/content/help/it-IT/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Qual è la latenza prevista per [!UICONTROL Customer Journey Analytics] in [!UICONTROL Adobe Experience Platform]? | <ul><li>In condizioni di carico normale: &lt; 60 minuti <br>**Nota:** in caso di volume insolitamente elevato del flusso di dati che attraversa la pipeline, potrebbero essere necessarie fino a 24 ore.</li><li>In caso di recupero dei dati (fino a 13 mesi di dati, indipendentemente dalle dimensioni): &lt; 4 settimane</li></ul> |
| Come si collegano i dati online ai dati offline in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] è un sistema di analisi che richiede un proprio ID. Se l’ID della persona corrisponde nei diversi set di dati, [!UICONTROL Customer Journey Analytics] può collegare segmenti, attribuzione, flusso, fallout e così via tra i vari set di dati. |
| Come si inseriscono i dati offline [!UICONTROL Customer Journey Analytics]? | Devi inserire tutti i dati in Experience Platform prima di poterli utilizzare con [!UICONTROL Customer Journey Analytics]. Se necessario, il team di Experience Platform che si occupa dell’onboarding dei dati ti può fornire consigli o consulenza. |
| Come si ottiene [!UICONTROL Adobe Analytics] data in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] i dati possono essere collegati a  Experience Platform tramite [ Adobe Analytics Source Connector](https://docs.adobe.com/content/help/it-IT/experience-platform/sources/connectors/adobe-applications/analytics.html). Most [!UICONTROL Adobe Analytics] i campi vengono trasferiti in formato XDM, ma altri campi non sono ancora disponibili (come [!UICONTROL Marketing Channels] quote). |
| Quanto tempo è necessario per assemblare gli elementi dei set di dati in una visualizzazione dati? | Poche ore per iniziare e qualche giorno per recuperare gli ultimi 13 mesi di dati. |
| È necessario inserire dati PII per stabilire connessioni tra i dati? | No, puoi utilizzare qualsiasi ID, incluso un hash di un ID cliente, che non è un dato PII. |

## Tradizionale [!UICONTROL Adobe Analytics] components

| Domanda | Risposta |
| --- | --- |
| Cosa significa questo per la nostra tradizione [!UICONTROL Adobe Analytics] product? | [!UICONTROL Customer Journey Analytics] è il nostro prodotto di analisi di nuova generazione. Evoluzione dai nostri prodotti attuali a [!UICONTROL Customer Journey Analytics] Ci vorranno anni e molto coordinamento. Per ulteriori informazioni, consulta [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| Posso condividere segmenti da [!UICONTROL Customer Journey Analytics] AEP o altre soluzioni? | Non ancora. Stiamo studiando nuovi metodi innovativi per condividere segmenti da [!UICONTROL Customer Journey Analytics] per AEP in futuro che non ha un ritardo così lungo. Detto questo, è possibile condividere l’output di Query Services sul profilo unificato come soluzione alternativa. |
| Cos’è successo alla mia vecchia impostazione eVar? | eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in [!UICONTROL Customer Journey Analytics]. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query. |
| Dove sono ora tutte le impostazioni di persistenza relative alla sessione e alle variabili? | [!UICONTROL Customer Journey Analytics] applica tutte queste impostazioni al momento di creazione del rapporto ed esse si trovano ora in Data Views (Visualizzazioni dati). Le modifiche a queste impostazioni sono ora retroattive e si possono avere più versioni utilizzando più Data Views (Visualizzazioni dati). |
| Cosa succede ai segmenti o alle metriche calcolate esistenti? | [!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi,  utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti o delle metriche calcolate esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. |
| Procedura [!UICONTROL Customer Journey Analytics] handle `Uniques Exceeded` limitazioni? | [!UICONTROL Customer Journey Analytics] non ha limiti di valore unici, quindi non c&#39;è bisogno di preoccuparsi per loro! |
| Se sono già un cliente [!DNL Data Workbench], posso passare subito a [!UICONTROL Customer Journey Analytics] | Dipende. Se fai un grande utilizzo del processo unificato dei clienti (UCP), ti consigliamo di aspettare fino a quando non sarà stato implementato il sistema di stitching. Se hai già tassi elevati di autenticazione dei clienti, se vuoi che tutti i tuoi dati vengano salvati in un’unica posizione o se desideri eliminare le eVar, Customer Journey Analytics potrebbe essere una buona soluzione. |

## Implicazioni dell&#39;eliminazione dei componenti dati

Per quanto riguarda la cancellazione, ci occupiamo di 6 componenti: progetti sandbox, schema, set di dati, connessione, visualizzazione dati e Workspace. Di seguito sono riportati alcuni possibili scenari per l’eliminazione di uno dei seguenti componenti:

| E se io... | Ciò si verifica... |
| --- | --- |
| Eliminare una sandbox in [!UICONTROL Adobe Experience Platform]? | L&#39;eliminazione di una sandbox interrompe qualsiasi [!UICONTROL Customer Journey Analytics] connessioni ai dataset in quella sandbox. Tuttavia, i set di dati nella CJA non verranno attualmente eliminati. |
| Elimina uno schema in [!UICONTROL Adobe Experience Platform], ma non il/i set di dati associati a questo schema? | [!UICONTROL Adobe Experience Platform] non consente l&#39;eliminazione di schemi a cui sono associati uno o più set di dati. Tuttavia, un amministratore con l&#39;insieme di diritti appropriato può eliminare prima i set di dati e quindi lo schema. |
| Elimina un set di dati in [!UICONTROL Adobe Experience Platform]? | Nessuna notifica in [!UICONTROL Customer Journey Analytics]; tuttavia, se i dati di streaming sono attivati, dopo l&#39;eliminazione dei set di dati non saranno più disponibili nuovi dati.<br>In altre parole, se l&#39;impostazione **[!UICONTROL Automatically import all new datasets in this connection, beginning today]** quando la connessione è abilitata, non saranno più disponibili nuovi dati dopo l&#39;eliminazione dei set di dati. |
| Elimina un set di dati in [!UICONTROL Customer Journey Analytics]? | Al momento non è possibile eliminare un dataset all&#39;interno di una connessione salvata. Dovreste eliminare l&#39;intera connessione e ricominciare da capo. Tuttavia, è possibile eliminare un set di dati in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch da un set di dati (in [!UICONTROL Adobe Experience Platform])? | Se il batch è già stato assimilato in [!UICONTROL Customer Journey Analytics], [!UICONTROL Customer Journey Analytics] al momento non è a conoscenza del fatto che il batch è stato eliminato. Se il batch non è stato ingerito, ovviamente non può essere ingerito una volta eliminato in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch **durante l&#39;assimilazione** in [!UICONTROL Customer Journey Analytics]? | Se nel set di dati è presente un solo batch, non verranno visualizzati dati o dati parziali da tale batch [!UICONTROL Customer Journey Analytics]. L&#39;assimilazione verrà ripristinata. Se, ad esempio, nel set di dati sono presenti 5 batch e 3 di essi sono già stati acquisiti al momento dell&#39;eliminazione del set di dati, i dati provenienti da questi 3 batch verranno visualizzati in [!UICONTROL Customer Journey Analytics]. |
| Elimina una connessione in [!UICONTROL Customer Journey Analytics]? | Un messaggio di errore indica che:<ul><li>Tutte le visualizzazioni dati create per la connessione eliminata non funzioneranno più.</li><li> Allo stesso modo, tutti i progetti Workspace che dipendono dalla visualizzazione dei dati nella connessione eliminata cesseranno di funzionare.</li></ul> |
| Eliminare una visualizzazione dati in [!UICONTROL Customer Journey Analytics]? | Un messaggio di errore indica che tutti i progetti Workspace dipendenti da questa visualizzazione dati eliminata cesseranno di funzionare. |
| Eliminare un progetto Workspace in [!UICONTROL Customer Journey Analytics]? | Potete ricreare il progetto oppure utilizzare una soluzione alternativa per recuperare il progetto. Vai a [!UICONTROL Admin > Logs > Usage and Access Log], trova il progetto eliminato e copia il relativo ID. Quindi apri qualsiasi progetto Workspace e aggiorna l’ID nell’URL con quello copiato. Salvate quindi il progetto. |
