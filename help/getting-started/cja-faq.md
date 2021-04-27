---
title: Domande frequenti su Customer Journey Analytics
description: Customer Journey Analytics - Domande frequenti.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: 5667e2f43873061c5350c75fdb830a95b1c9b73f
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 32%

---

# Domande frequenti

[!UICONTROL Customer Journey Analytics] (CJA) è il nostro prodotto di analisi di nuova generazione. Di seguito sono riportate le risposte alle domande frequenti su CJA. Per ulteriori informazioni, consulta [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/cja-aa.md).

## 1. Prerequisiti

| Domanda | Risposta |
| --- | --- |
| Sono necessari [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] per [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] non sono necessari per [!UICONTROL Customer Journey Analytics]. Al momento non sono ancora supportati. |
| È necessario [!UICONTROL Experience Cloud ID] (ECID) per [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supporta qualsiasi ID in un set di dati, sia esso o qualsiasi altro ID scelto.[!UICONTROL ECID] |
| In che modo si possono effettuare operazioni di ETL (Extract, Transform, Load, cioè Estrai, Trasforma, Carica) sui dati prima di inserirli in [!UICONTROL Customer Journey Analytics]? | Il Customer Journey Analytics include le funzionalità [Preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html) per trasformare i dati prima di inserirli nel data lake di Adobe Experience Platform. Se hai bisogno di ETL dopo che i dati sono già stati acquisiti, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=en#queries) offre alcune opzioni limitate, anche se potrebbero essere presenti costi aggiuntivi. |

{style=&quot;table-layout:auto&quot;}

## 2. Stitching dei dati (Cross-Channel Analytics)

| Domanda | Risposta |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] può effettuare lo stitching tra dispositivi o tra set di dati? | Sì. [!UICONTROL Customer Journey Analytics] dispone di una soluzione di unione denominata  [Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html)  (CCA). Ti consente di reimpostare l’ID persona di un set di dati, consentendo una combinazione perfetta di più set di dati. |
| È supportato lo stitching da un comportamento anonimo a un comportamento autenticato? | Sì. [Cross-Channel ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) Analytics esamina i dati utente provenienti da sessioni autenticate e non autenticate per generare un ID vincolato. |
| Come funziona &#39;replay&#39; in CCA? | CCA &quot;riproduce&quot; i dati in base a identificatori univoci appresi. La riproduzione causa l&#39;unione di nuovi dispositivi alla connessione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=en#step-1%3A-live-stitching) |
| Come funziona l’unione dei dati storici (backfill) in CCA? | Quando è attivato per la prima volta, Adobe fornisce una retrocompilazione dei dati uniti che risalgono all’inizio del mese precedente (fino a 60 giorni). Per eseguire questa operazione di recupero, l’ID transitorio deve esistere nei dati non uniti che risalgono al tempo precedente. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=en#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3. Come inserire dati in [!UICONTROL Customer Journey Analytics]

| # | Domanda | Risposta |
| --- | --- | --- |
| È possibile combinare i dati di diverse sandbox [!UICONTROL Adobe Experience Platform] in una connessione [!UICONTROL Customer Journey Analytics]? | No, non è possibile accedere ai dati di sandbox diverse. È possibile combinare solo i set di dati che si trovano all’interno della stessa sandbox. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Qual è la latenza prevista per [!UICONTROL Customer Journey Analytics] in [!UICONTROL Adobe Experience Platform]? | <ul><li>In condizioni di carico normale: &lt; 60 minuti <br>**Nota:** in caso di volume insolitamente elevato del flusso di dati che attraversa la pipeline, potrebbero essere necessarie fino a 24 ore.</li><li>In caso di recupero dei dati (fino a 13 mesi di dati, indipendentemente dalle dimensioni): &lt; 4 settimane</li></ul> |
| Come si collegano i dati online ai dati offline in [!UICONTROL Customer Journey Analytics]? | Se l’ID della persona corrisponde tra i set di dati, [!UICONTROL Customer Journey Analytics] può collegare filtri, attribuzione, flusso, fallout, ecc. tra i vari set di dati. |
| Come posso inserire i dati offline in [!UICONTROL Customer Journey Analytics]? | Il diritto al Customer Journey Analytics ti consente di inserire i dati in Experience Platform. Puoi quindi creare connessioni a tali visualizzazioni dati e dati in [!UICONTROL Customer Journey Analytics], per la generazione di rapporti in Analysis Workspace. Se necessario, il team di Experience Platform che si occupa dell’onboarding dei dati ti può fornire consigli o consulenza. |
| Come posso ottenere i dati [!UICONTROL Adobe Analytics] in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] i dati possono essere collegati ad Experience Platform tramite  [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/it-IT/experience-platform/sources/connectors/adobe-applications/analytics.html). La maggior parte dei campi [!UICONTROL Adobe Analytics] viene portata avanti in formato XDM, ma altri campi non sono ancora disponibili (come le dimensioni [!UICONTROL Marketing Channels]). |
| Quanto tempo è necessario per assemblare gli elementi dei set di dati in una visualizzazione dati? | Poche ore per iniziare e qualche giorno per recuperare gli ultimi 13 mesi di dati. |
| È necessario inserire dati PII per stabilire connessioni tra i dati? | No, puoi utilizzare qualsiasi ID, incluso un hash di un ID cliente, che non è un dato PII. |

{style=&quot;table-layout:auto&quot;}

## 4. Componenti tradizionali [!UICONTROL Adobe Analytics]

| Domanda | Risposta |
| --- | --- |
| Posso condividere/pubblicare filtri (segmenti) da profilo unificato di Customer Journey Analytics ad Experience Platform o altre applicazioni di Experience Cloud? | Non ancora, ma stiamo lavorando attivamente per fornire questa funzionalità. |
| Cos’è successo alla mia vecchia impostazione eVar? | eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in [!UICONTROL Customer Journey Analytics]. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query. |
| Dove sono ora tutte le impostazioni di persistenza relative alla sessione e alle variabili? | [!UICONTROL Customer Journey Analytics] applica tutte queste impostazioni al momento di creazione del rapporto ed esse si trovano ora in Data Views (Visualizzazioni dati). Le modifiche a queste impostazioni sono ora retroattive e si possono avere più versioni utilizzando più Data Views (Visualizzazioni dati). |
| Cosa succede ai segmenti o alle metriche calcolate esistenti? | [!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi,  utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti o delle metriche calcolate esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. |
| In che modo [!UICONTROL Customer Journey Analytics] gestisce i limiti `Uniques Exceeded`? | [!UICONTROL Customer Journey Analytics] non ha limiti di valore univoci, quindi non è necessario preoccuparsene! |
| Se sono già un cliente [!DNL Data Workbench], posso passare subito a [!UICONTROL Customer Journey Analytics] | Dipende dal tuo caso d’uso: collabora con il team dell’account Adobe. I tuoi attuali casi d&#39;uso possono già essere una buona misura per il Customer Journey Analytics! |

{style=&quot;table-layout:auto&quot;}

## 5. Implicazioni dell’eliminazione dei componenti dati

Per quanto riguarda l’eliminazione dei dati, ci occupiamo di 6 tipi di componenti: sandbox, schema, set di dati, connessione, visualizzazione dati e progetto Workspace. Di seguito sono riportati alcuni possibili scenari relativi all’eliminazione di uno qualsiasi di questi componenti:

| Se tu... | Ciò si verifica... |
| --- | --- |
| Eliminare una sandbox in [!UICONTROL Adobe Experience Platform] | L’eliminazione di una sandbox interrompe il flusso di dati su qualsiasi connessione [!UICONTROL Customer Journey Analytics] ai set di dati in quella sandbox. Attualmente, le connessioni in CJA collegate alla sandbox eliminata non verranno eliminate automaticamente. |
| Elimina uno schema in [!UICONTROL Adobe Experience Platform], ma non i set di dati associati a questo schema | [!UICONTROL Adobe Experience Platform] non consente l’eliminazione di schemi a cui sono associati uno o più set di dati. Tuttavia, un amministratore con l’insieme di diritti appropriato può prima eliminare i set di dati e quindi eliminare lo schema. |
| Elimina un set di dati nel lago di dati [!UICONTROL Adobe Experience Platform] | L’eliminazione di un set di dati in AEP data lake interrompe il flusso di dati da tale set di dati a qualsiasi connessione CJA che include tale set di dati. Eventuali dati provenienti da tale set di dati non vengono eliminati automaticamente dalle connessioni CJA associate. |
| Elimina un set di dati in [!UICONTROL Customer Journey Analytics] | Al momento non è possibile eliminare un set di dati all’interno di una connessione salvata. Dovreste cancellare l&#39;intera connessione e ricominciare da capo. Tuttavia, i clienti che hanno acquistato lo SKU di CJA possono eliminare un set di dati nell’ interfaccia utente di [!UICONTROL Adobe Experience Platform] . |
| Eliminare un batch da un set di dati (in [!UICONTROL Adobe Experience Platform]) | Se un batch viene eliminato da un set di dati [!UICONTROL Adobe Experience Platform], lo stesso batch verrà rimosso da tutte le connessioni CJA che contengono tale batch specifico.  CJA riceve una notifica delle eliminazioni batch in [!UICONTROL Adobe Experience Platform]. |
| Elimina un batch **durante l&#39;acquisizione** in [!UICONTROL Customer Journey Analytics] | Se nel set di dati è presente un solo batch, nessun dato o dato parziale da quel batch verrà visualizzato in [!UICONTROL Customer Journey Analytics]. L&#39;ingestione verrà rimandata. Se, ad esempio, nel set di dati sono presenti 5 batch e 3 di essi sono già stati acquisiti al momento dell’eliminazione del set di dati, i dati di tali 3 batch saranno visualizzati in [!UICONTROL Customer Journey Analytics]. |
| Elimina una connessione in [!UICONTROL Customer Journey Analytics] | Un messaggio di errore indica che:<ul><li>Tutte le visualizzazioni dati create per la connessione eliminata non funzioneranno più.</li><li> Analogamente, tutti i progetti Workspace che dipendono dalle visualizzazioni dati nella connessione eliminata cesseranno di funzionare.</li></ul> |
| Eliminare una visualizzazione dati in [!UICONTROL Customer Journey Analytics] | Un messaggio di errore indica che tutti i progetti Workspace dipendenti da questa visualizzazione dati eliminata cesseranno di funzionare. |
