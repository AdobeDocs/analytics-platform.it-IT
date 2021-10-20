---
title: Domande frequenti su Customer Journey Analytics
description: Customer Journey Analytics - Domande frequenti.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
source-git-commit: d88502218cd94fbb430a0fc5a3af994e7edaa73c
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 92%

---

# Domande frequenti

[!UICONTROL Customer Journey Analytics] (CJA) è il nostro prodotto di analisi di nuova generazione. Di seguito sono riportate le risposte alle domande più frequenti su CJA. Per ulteriori informazioni, consulta [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/cja-aa.md).

## 1. Prerequisiti

| Domanda | Risposta |
| --- | --- |
| Sono necessari [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] per [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] non sono necessari per [!UICONTROL Customer Journey Analytics]. Al momento non sono ancora supportati. |
| È necessario [!UICONTROL Experience Cloud ID] (ECID) per [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supporta qualsiasi ID in un set di dati, sia esso o qualsiasi altro ID scelto.[!UICONTROL ECID] |
| In che modo si possono effettuare operazioni di ETL (Extract, Transform, Load, cioè Estrai, Trasforma, Carica) sui dati prima di inserirli in [!UICONTROL Customer Journey Analytics]? | Customer Journey Analytics include funzionalità di [Preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=it) per trasformare i dati prima di inserirli nel data lake di Adobe Experience Platform. Se hai bisogno di ETL dopo che i dati sono già stati acquisiti, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=it#queries) offre alcune opzioni limitate; tieni presente che potrebbe comportare costi aggiuntivi. |

{style=&quot;table-layout:auto&quot;}

## 2. Unione dei dati (Cross-Channel Analytics)

| Domanda | Risposta |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] può effettuare lo stitching tra dispositivi o tra set di dati? | Sì. [!UICONTROL Customer Journey Analytics] dispone di una soluzione di unione denominata [Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=it) (CCA). Consente di reimpostare l’ID persona in un set di dati, e offre la possibilità di combinare direttamente più set di dati. |
| È supportato lo stitching da un comportamento anonimo a un comportamento autenticato? | Sì. [Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) esamina i dati utente provenienti da sessioni autenticate e non autenticate per generare un ID unico. |
| Come funziona la “riproduzione” in CCA? | CCA “riproduce” i dati in base a identificatori univoci appresi. In seguito a tale riproduzione, vengono uniti nuovi dispositivi usati per la connessione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=it#step-1%3A-live-stitching) |
| Come funziona l’unione dei dati storici (retrocompilazione) in CCA? | Quando CCA è attivato per la prima volta, Adobe fornisce la retrocompilazione dei dati uniti che risalgono all’inizio del mese precedente (fino a 60 giorni). Per eseguire questa operazione di recupero, l’ID transitorio deve esistere nei dati non uniti che risalgono al periodo precedente. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=it#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3. Inserire dati in [!UICONTROL Customer Journey Analytics]

| Domanda | Risposta |
| --- | --- |
| È possibile combinare i dati di diverse sandbox di [!UICONTROL Adobe Experience Platform] in una connessione [!UICONTROL Customer Journey Analytics]? | No, non è possibile accedere ai dati di sandbox diverse. È possibile combinare solo i set di dati che si trovano all’interno della stessa sandbox. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it#select-sandbox-and-datasets) |
| Come si collegano i dati online ai dati offline in [!UICONTROL Customer Journey Analytics]? | Se l’ID della persona corrisponde nei diversi set di dati, [!UICONTROL Customer Journey Analytics] può collegare filtri, attribuzione, flusso, abbandono e così via. tra i vari set di dati. |
| Come posso inserire dati offline in [!UICONTROL Customer Journey Analytics]? | La licenza di Customer Journey Analytics consente di acquisire i dati in Experience Platform. Puoi quindi creare connessioni a tali dati e visualizzazioni di dati in [!UICONTROL Customer Journey Analytics], da utilizzare per la generazione di rapporti in Analysis Workspace. Se necessario, il team di Experience Platform che si occupa dell’onboarding dei dati ti può fornire consigli o consulenza. |
| Come posso inserire i dati di [!UICONTROL Adobe Analytics] in [!UICONTROL Customer Journey Analytics]? | I dati di [!UICONTROL Adobe Analytics] possono essere collegati a Experience Platform tramite [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). La maggior parte dei campi [!UICONTROL Adobe Analytics] vengono trasferiti in formato XDM, ma alcuni campi non sono ancora disponibili. |
| Quanto tempo è necessario per assemblare gli elementi dei set di dati in una visualizzazione dati? | Poche ore per iniziare e qualche giorno per recuperare gli ultimi 13 mesi di dati. |
| È necessario inserire dati PII per stabilire connessioni tra i dati? | No, puoi utilizzare qualsiasi ID, incluso un hash di un ID cliente, che non è un dato PII. |
| Quali sono i limiti per l’acquisizione di date/marche temporali passate o future nei set di dati evento CJA? | <ul><li>Per quanto riguarda le date/marche temporali passate: Dati evento fino a 10 anni.</li><li>Per quanto riguarda le date/marche temporali future: Dati evento (predittivi) fino a un mese nel futuro.</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 4. Considerazioni sulla latenza

>[!NOTE]
>Non esiste una dimensione fissa dei dati in CJA e pertanto Adobe non può eseguire il commit a un tempo di acquisizione standard. Stiamo lavorando attivamente per ridurre queste latenze attraverso nuovi aggiornamenti e l’ottimizzazione dell’acquisizione.

| Domanda | Risposta |
| --- | --- |
| Qual è la latenza prevista per [!UICONTROL Customer Journey Analytics] in [!UICONTROL Adobe Experience Platform]? | <ul><li>Dati o eventi live: Elaborati e acquisiti entro 90 minuti, una volta che i dati sono disponibili in AEP.</li><li>Dimensione batch > 50 milioni di righe: più di 90 minuti.</li><li>Piccoli backfill - Ad esempio, un set di dati di ricerca di 10 milioni di righe: entro 24 ore<li>Backfill di grandi dimensioni - Ad esempio, 500 miliardi di righe: 30 giorni</li></ul> |


## 5. Componenti tradizionali di [!UICONTROL Adobe Analytics]

| Domanda | Risposta |
| --- | --- |
| Posso condividere/pubblicare filtri (segmenti) da Customer Journey Analytics a Experience Platform Unified Profile o altre applicazioni Experience Cloud? | Non ancora, ma stiamo mettendo a punto questa funzionalità. |
| Cos’è successo alla mia vecchia impostazione eVar? | eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in [!UICONTROL Customer Journey Analytics]. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query. |
| Dove sono ora tutte le impostazioni di persistenza relative alla sessione e alle variabili? | [!UICONTROL Customer Journey Analytics] applica tutte queste impostazioni al momento di creazione del rapporto ed esse si trovano ora in Data Views (Visualizzazioni dati). Le modifiche a queste impostazioni sono ora retroattive e si possono avere più versioni utilizzando più Data Views (Visualizzazioni dati). |
| Cosa succede ai segmenti o alle metriche calcolate esistenti? | [!UICONTROL Customer Journey Analytics]Al posto di eVar, prop o eventi, utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti o delle metriche calcolate esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. |
| In che modo [!UICONTROL Customer Journey Analytics] gestisce i limiti di `Uniques Exceeded`? | [!UICONTROL Customer Journey Analytics] non ha limiti di valore univoci, quindi non è necessario preoccuparsene. |
| Se sono già un cliente [!DNL Data Workbench], posso passare subito a [!UICONTROL Customer Journey Analytics] | Dipende dal tuo caso d’uso: collabora con il team del tuo account Adobe. I tuoi casi d’uso attuali potrebbero già essere gestiti con Customer Journey Analytics! |

{style=&quot;table-layout:auto&quot;}

## 6. Implicazioni dell’eliminazione di componenti dati

Per quanto riguarda l’eliminazione dei dati, ci occupiamo di 6 tipi di componenti: sandbox, schema, set di dati, connessione, visualizzazione dati e progetto Workspace. Di seguito sono riportati alcuni possibili scenari relativi all’eliminazione di uno di questi componenti:

| Azione | Ciò si verifica... |
| --- | --- |
| Eliminare una sandbox in [!UICONTROL Adobe Experience Platform] | L’eliminazione di una sandbox interrompe il flusso di dati a qualsiasi connessione [!UICONTROL Customer Journey Analytics] per il set di dati in tale sandbox. Attualmente, le connessioni in CJA associate alla sandbox eliminata non verranno eliminate automaticamente. |
| Eliminare uno schema in [!UICONTROL Adobe Experience Platform], ma non i set di dati associati a tale schema | [!UICONTROL Adobe Experience Platform] non consente di eliminare gli schemi a cui sono associati uno o più set di dati. Tuttavia, un amministratore che dispone delle autorizzazioni appropriate può prima eliminare i set di dati, e quindi eliminare lo schema. |
| Eliminare un set di dati nel data lake di [!UICONTROL Adobe Experience Platform] | L’eliminazione di un set di dati nel data lake di AEP interrompe il flusso di dati da tale set di dati a qualsiasi connessione CJA che include tale set di dati. Eventuali dati provenienti da tale set di dati non vengono eliminati automaticamente dalle connessioni CJA associate. |
| Eliminare un set di dati in [!UICONTROL Customer Journey Analytics] | Al momento non è possibile eliminare un set di dati all’interno di una connessione salvata. Occorre cancellare l’intera connessione e ricominciare da capo. (Tuttavia, i clienti che hanno acquistato lo SKU di CJA possono eliminare un set di dati nell’interfaccia utente di [!UICONTROL Adobe Experience Platform]). |
| Eliminare un batch da un set di dati (in [!UICONTROL Adobe Experience Platform]) | Se un batch viene eliminato da un set di dati [!UICONTROL Adobe Experience Platform], lo stesso batch verrà rimosso da tutte le connessioni CJA che contengono tale batch specifico.  CJA riceve una notifica dell’eliminazione del batch in [!UICONTROL Adobe Experience Platform]. |
| Eliminare un batch **durante la sua acquisizione** in [!UICONTROL Customer Journey Analytics] | Se nel set di dati è presente un solo batch, in [!UICONTROL Customer Journey Analytics] non verranno visualizzati dati o dati parziale da tale batch. L’acquisizione verrà annullata e verrà ripristinato lo stato precedente. Se, ad esempio, nel set di dati sono presenti 5 batch e 3 di essi sono già stati acquisiti al momento dell’eliminazione del set di dati, i dati di tali 3 batch saranno visualizzati in [!UICONTROL Customer Journey Analytics]. |
| Eliminare una connessione in [!UICONTROL Customer Journey Analytics] | Un messaggio di errore indica che:<ul><li>Tutte le visualizzazioni dati create per la connessione eliminata non funzioneranno più.</li><li> Analogamente, tutti i progetti Workspace che dipendono dalle visualizzazioni dati nella connessione eliminata cesseranno di funzionare.</li></ul> |
| Eliminare una visualizzazione di dati in [!UICONTROL Customer Journey Analytics] | Un messaggio di errore indica che tutti i progetti Workspace dipendenti dalla visualizzazione di dati eliminata cesseranno di funzionare. |

## 7. Considerazioni durante l’unione delle suite di rapporti in CJA

Se prevedi di acquisire dati Adobe Analytics tramite il [connettore di origine Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it), considera queste ramificazioni quando unisci 2 o più suite di rapporti Adobe Analytics.

| Problema | Considerazione |
| --- | --- |
| Variabili | Le variabili come [!UICONTROL eVars] potrebbero non essere allineate tra le diverse suite di rapporti. Ad esempio, eVar1 nella suite di rapporti 1 può fare riferimento a **[!UICONTROL Page]**. Nella suite di rapporti 2, eVar1 può invece fare riferimento a **[!UICONTROL Internal Campaign]**. In tal caso verranno generati rapporti con valori misti e imprecisi. |
| Conteggi di [!UICONTROL Sessions] e [!UICONTROL People] | Vengono deduplicati in tutte le suite di rapporti. Di conseguenza, i conteggi potrebbero non corrispondere. |
| Deduplicazione delle metriche | Deduplica le istanze di una metrica (ad esempio, [!UICONTROL Orders]) se più righe hanno lo stesso ID transazione (ad esempio, [!UICONTROL Purchase ID]). Questo impedisce che il conteggio delle metriche chiave risulti superiore ai dati effettivi. Di conseguenza, le metriche come [!UICONTROL Orders] potrebbero non corrispondere tra suite di rapporti diverse. |
| Valuta | La conversione della valuta non è ancora supportata in CJA. Se le suite di rapporti che stai tentando di unire utilizzano valute di base diverse, potrebbero verificarsi dei problemi. |
| [!UICONTROL Persistence] | La [persistenza ](../data-views/component-settings/persistence.md) si estende alle varie suite di rapporti, il che ha un impatto su [!UICONTROL filters], [!UICONTROL attribution] e così via. È possibile che i numeri non corrispondano correttamente. |
| [!UICONTROL Classifications] | I dati di [!UICONTROL Classifications] non vvengono deduplicati automaticamente durante l’unione di suite di rapporti. Quando si combinano più file di classificazione in un singolo set di dati [!UICONTROL lookup], si potrebbero riscontrare dei problemi. |