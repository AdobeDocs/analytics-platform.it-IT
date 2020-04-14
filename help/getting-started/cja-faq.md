---
title: Domande frequenti su Customer Journey Analytics
description: Customer Journey Analytics - Domande frequenti.
translation-type: tm+mt
source-git-commit: 69f9154387ec11e9b1ec6f867ebab6d556451a9a

---


# Domande frequenti

| Domanda | Risposta |
|---|---|
| **Prerequisiti** |  |
| Do you need Device Graph or Device Coop for [!UICONTROL Customer Journey Analytics]? | No, Private Device Graph or Device Coop are not required for [!UICONTROL Customer Journey Analytics]. Al momento non sono ancora supportati. |
| Do you need Experience Cloud ID (ECID) for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supports any ID in a dataset, whether that&#39;s ECID or any other ID you choose. |
| In che modo si possono effettuare operazioni di ETL (Extract, Transform, Load, cioè Estrai, Trasforma, Carica) sui dati prima di inserirli in Customer Journey Analytics? | Al momento, è necessario lavorare con un partner ETL (Unifi o Informatica) per trasformare i dati prima di inserirli in AEP. Se hai bisogno di effettuare operazioni di ETL dopo che i dati sono già stati acquisiti, AEP Query Services offre alcune opzioni limitate. |
| **Stitching** |  |
| Can [!UICONTROL Customer Journey Analytics] &quot;stitch&quot; across devices or across datasets? | No. [!UICONTROL Customer Journey Analytics] è un sistema di analisi &quot;port-your-own-ID&quot;. La realizzazione di un approccio efficace di stitching è in corso di progettazione. |
| È supportato lo stitching da un comportamento anonimo a un comportamento autenticato? | No, non ancora. |
| **Recupero dei dati[!UICONTROL Customer Journey Analytics]** |  |
| Qual è la latenza prevista per [!UICONTROL Customer Journey Analytics] on [!UICONTROL Experience Platform]? | <ul><li>In condizioni di carico normale: &lt; 60 minuti <br>**Nota:** in caso di volume insolitamente elevato del flusso di dati che attraversa la pipeline, potrebbero essere necessarie fino a 24 ore.</li><li>Dati di backfill (fino a 10 miliardi di eventi): &lt; 4 settimane</li></ul> |
| How do you connect online data to offline data in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] è un sistema di analisi &quot;porta il tuo ID&quot;. As long as the person ID matches between datasets, [!UICONTROL Customer Journey Analytics] can connect segments, attribution, flow, fallout, etc. tra dataset. |
| Come posso inserire i miei dati offline in Customer Journey Analytics? | I clienti devono innanzitutto portare qualsiasi dato a Experience Platform prima di poterlo utilizzare con Customer Journey Analytics. Se necessario, il team di Experience Platform che si occupa dell’onboarding dei dati può fornire consigli o consulenza ai clienti. |
| Come posso inserire i dati di Analytics in Customer Journey Analytics? | I dati di Analytics possono essere collegati a Experience Platform tramite il Connettore dati di Analytics. La maggior parte dei campi di Analytics vengono trasferiti in formato XDM, ma altri campi non sono ancora disponibili (come le dimensioni dei canali di marketing). |
| Quanto tempo è necessario per assemblare gli elementi di un dataset in una visualizzazione dati? | Poche ore per iniziare e qualche giorno per recuperare gli ultimi 13 mesi di dati. |
| È necessario inserire dati PII per stabilire connessioni tra i dati? | No, puoi utilizzare qualsiasi ID, incluso un hash di un ID cliente, che non è un dato PII. |
| **Componenti tradizionali di Analytics** |  |
| Cosa implica questo per il prodotto Adobe Analytics tradizionale? | Customer Journey Analytics è il nostro prodotto di analisi di prossima generazione. L’evoluzione dai nostri prodotti attuali a Customer Journey Analytics richiederà anni e molta coordinazione. Questa versione è uno di tanti grandi passi avanti in questa direzione. |
| Posso condividere segmenti da Customer Journey Analytics verso AEP o altre soluzioni? | Non ancora. Stiamo studiando nuovi metodi innovativi per condividere in futuro segmenti da Customer Journey Analytics verso AEP che non comportino un ritardo così lungo. Detto questo, è possibile condividere l’output di Query Services sul profilo unificato come soluzione alternativa. |
| Cos’è successo alla mia vecchia impostazione eVar? | eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in Customer Journey Analytics. Sono disponibili elementi schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione che si applicavano durante il processo di raccolta dei dati vengono ora applicate al momento della query. |
| Dove sono ora tutte le impostazioni di persistenza relative alla sessione e alle variabili? | Customer Journey Analytics applica tutte queste impostazioni al momento di creazione del rapporto ed esse si trovano ora in Data Views (Visualizzazioni dati). Le modifiche a queste impostazioni sono ora retroattive e si possono avere più versioni utilizzando più Data Views (Visualizzazioni dati). |
| Cosa succede ai segmenti o alle metriche calcolate esistenti? | Al posto di eVar, prop o eventi, Customer Journey Analytics utilizza qualsiasi schema AEP. Ciò significa che nessuno dei segmenti o delle metriche calcolate esistenti è compatibile con Customer Journey Analytics. |
| In che modo Customer Journey Analytics gestisce i limiti `Uniques Exceeded`? | Customer Journey Analytics non ha limiti di valore univoci, quindi non è necessario preoccuparsene. |
| Se sono già un cliente [!DNL Data Workbench], posso passare subito a Customer Journey Analytics? | Dipende. Se fai un grande utilizzo del processo unificato dei clienti (UCP), ti consigliamo di aspettare fino a quando non sarà stato implementato il sistema di stitching. Se hai già tassi elevati di autenticazione dei clienti, se vuoi che tutti i tuoi dati vengano salvati in un’unica posizione o se desideri eliminare le eVar, Customer Journey Analytics potrebbe essere una buona soluzione. |

