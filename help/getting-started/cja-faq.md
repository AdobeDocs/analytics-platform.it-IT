---
title: Domande frequenti su Customer Journey Analytics
description: Customer Journey Analytics - Domande frequenti.
translation-type: ht
source-git-commit: 297ed03ff59cc8d719a6bf0984e82597e8d33392
workflow-type: ht
source-wordcount: '771'
ht-degree: 100%

---


# Domande frequenti

| Domanda | Risposta |
| --- | --- |
| **Prerequisiti** |  |
| Sono necessari Device Graph o Device Coop per utilizzare [!UICONTROL Customer Journey Analytics]? | No, per utilizzare [!UICONTROL Customer Journey Analytics] non sono necessari Private Device Graph o Device Coop. Al momento non sono ancora supportati. |
| È necessario Experience Cloud ID (ECID) per utilizzare [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supporta qualsiasi ID in un set di dati, sia esso ECID o qualsiasi altro ID scelto. |
| In che modo si possono effettuare operazioni di ETL (Extract, Transform, Load, cioè Estrai, Trasforma, Carica) sui dati prima di inserirli in Customer Journey Analytics? | Al momento, è necessario lavorare con un partner ETL (Unifi o Informatica) per trasformare i dati prima di inserirli in AEP. Se hai bisogno di effettuare operazioni di ETL dopo che i dati sono già stati acquisiti, AEP Query Services offre alcune opzioni limitate. |
| **Stitching** |  |
| [!UICONTROL Customer Journey Analytics] può effettuare lo stitching tra dispositivi o tra set di dati? | No. [!UICONTROL Customer Journey Analytics] è un sistema di analisi che richiede un proprio ID. La realizzazione di un approccio efficace di stitching è in corso di progettazione. |
| È supportato lo stitching da un comportamento anonimo a un comportamento autenticato? | No, non ancora. |
| **Come inserire dati in [!UICONTROL Customer Journey Analytics]** |  |
| È possibile combinare i dati di diverse sandbox Experience Platform in una connessione CJA? | No, non è possibile accedere ai dati di sandbox diverse. È possibile combinare solo i set di dati che si trovano all’interno della stessa sandbox. [Ulteriori informazioni...](https://docs.adobe.com/content/help/it-IT/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Qual è la latenza prevista per [!UICONTROL Customer Journey Analytics] in [!UICONTROL Experience Platform]? | <ul><li>In condizioni di carico normale: &lt; 60 minuti <br>**Nota:** in caso di volume insolitamente elevato del flusso di dati che attraversa la pipeline, potrebbero essere necessarie fino a 24 ore.</li><li>Dati di backfill (fino a 10 miliardi di eventi): &lt; 4 settimane.</li></ul> |
| Come si collegano i dati online ai dati offline in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] è un sistema di analisi che richiede un proprio ID. Se l’ID della persona corrisponde nei diversi set di dati, [!UICONTROL Customer Journey Analytics] può collegare segmenti, attribuzione, flusso, fallout e così via tra i vari set di dati. |
| Come posso inserire i miei dati offline in Customer Journey Analytics? | Devi inserire tutti i dati in Experience Platform prima di poterli utilizzare con Customer Journey Analytics. Se necessario, il team di Experience Platform che si occupa dell’onboarding dei dati ti può fornire consigli o consulenza. |
| Come posso inserire i dati di Analytics in Customer Journey Analytics? | I dati di Analytics possono essere collegati a Experience Platform tramite [Analytics Data Connector](https://docs.adobe.com/content/help/it-IT/experience-platform/sources/connectors/adobe-applications/analytics.html). La maggior parte dei campi di Analytics vengono trasferiti in formato XDM, ma altri campi non sono ancora disponibili (come le dimensioni dei canali di marketing). |
| Quanto tempo è necessario per assemblare gli elementi dei set di dati in una visualizzazione dati? | Poche ore per iniziare e qualche giorno per recuperare gli ultimi 13 mesi di dati. |
| È necessario inserire dati PII per stabilire connessioni tra i dati? | No, puoi utilizzare qualsiasi ID, incluso un hash di un ID cliente, che non è un dato PII. |
| **Componenti tradizionali di Analytics** |  |
| Cosa implica questo per il prodotto Adobe Analytics tradizionale? | Customer Journey Analytics è il nostro prodotto di analisi di prossima generazione. L’evoluzione dai nostri prodotti attuali a Customer Journey Analytics richiederà anni e molta coordinazione. |
| Posso condividere segmenti da Customer Journey Analytics verso AEP o altre soluzioni? | Non ancora. Stiamo studiando nuovi metodi innovativi per condividere in futuro segmenti da Customer Journey Analytics verso AEP che non comportino un ritardo così lungo. Detto questo, è possibile condividere l’output di Query Services sul profilo unificato come soluzione alternativa. |
| Cos’è successo alla mia vecchia impostazione eVar? | eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in Customer Journey Analytics. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query. |
| Dove sono ora tutte le impostazioni di persistenza relative alla sessione e alle variabili? | Customer Journey Analytics applica tutte queste impostazioni al momento di creazione del rapporto ed esse si trovano ora in Data Views (Visualizzazioni dati). Le modifiche a queste impostazioni sono ora retroattive e si possono avere più versioni utilizzando più Data Views (Visualizzazioni dati). |
| Cosa succede ai segmenti o alle metriche calcolate esistenti? | Al posto di eVar, prop o eventi, Customer Journey Analytics utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti o delle metriche calcolate esistenti è compatibile con Customer Journey Analytics. |
| In che modo Customer Journey Analytics gestisce i limiti `Uniques Exceeded`? | Customer Journey Analytics non ha limiti di valore univoci, quindi non è necessario preoccuparsene. |
| Se sono già un cliente [!DNL Data Workbench], posso passare subito a Customer Journey Analytics? | Dipende. Se fai un grande utilizzo del processo unificato dei clienti (UCP), ti consigliamo di aspettare fino a quando non sarà stato implementato il sistema di stitching. Se hai già tassi elevati di autenticazione dei clienti, se vuoi che tutti i tuoi dati vengano salvati in un’unica posizione o se desideri eliminare le eVar, Customer Journey Analytics potrebbe essere una buona soluzione. |

