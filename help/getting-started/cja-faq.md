---
title: Domande frequenti sull'analisi del percorso del cliente
description: Analisi del percorso del cliente - Domande frequenti.
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Domande frequenti

| Domanda | Risposta |
|---|---|
| **Prerequisiti** |  |
| Hai bisogno di Device Graph o Device Coop per l&#39;analisi del percorso del cliente? | No, Device Graph privato o Device Coop non sono richiesti per l&#39;analisi del percorso del cliente. In realtà, non sono ancora supportati. |
| Hai bisogno di Experience Cloud ID (ECID) per l&#39;analisi del percorso del cliente? | No, Analisi del percorso cliente supporta qualsiasi ID in un set di dati, sia esso ECID o qualsiasi altro ID scelto. |
| Cosa succede se devi ETL (Estrai, Trasforma, Carica) i tuoi dati prima di Analisi del percorso cliente? | Oggi, è necessario lavorare con un partner ETL (Unifi o Informatica) per trasformare i dati prima di inserirli in AEP. Se avete bisogno di ETL dopo che i dati sono già stati acquisiti, AEP Query Services offre alcune opzioni limitate. |
| **Cucitura** |  |
| È possibile &quot;cucire&quot; l&#39;analisi del percorso del cliente tra dispositivi o tra set di dati? | No. Analisi del percorso del cliente è un sistema di analisi &quot;introiti il tuo ID&quot;. Piani per un buon approccio di cucitura sono in corso. |
| È supportata l&#39;unione da un comportamento anonimo a un comportamento autenticato? | No, non ancora. |
| **Come inserire i dati nell&#39;analisi del percorso del cliente** |  |
| Qual è la latenza prevista per l&#39;analisi del percorso del cliente sulla piattaforma? | <ul><li>Sotto carico normale: &lt; 60<br>**minutiNota:**In caso di un volume insolitamente elevato di dati che fluiscono attraverso la conduttura, potrebbero essere necessarie fino a 24 ore.</li><li>Dati di backfill (fino a 10 miliardi di eventi): &lt; 4 settimane</li></ul> |
| Come si collegano i dati online ai dati offline in Customer Journey Analytics? | Analisi percorso cliente è un sistema di analisi &quot;porta il tuo ID&quot;. Fintanto che l&#39;ID persona corrisponde tra set di dati, Analisi percorso cliente può collegare segmenti, attribuzione, flusso, abbandono, ecc. tra set di dati. |
| Come posso portare i miei dati offline in Customer Journey Analytics? | I clienti devono prima portare tutti i dati ad AEP prima di poterli utilizzare con Analisi del percorso cliente. Il team dedicato ai dati della piattaforma Experience può fornire consigli o consulenza ai clienti, se necessario. |
| Come si ottengono i dati di Analytics in Customer Journey Analytics? | I dati di Analytics possono essere collegati ad AEP tramite il Connettore dati di Analytics. La maggior parte dei campi di Analytics vengono trasferiti in formato XDM, ma altri campi non sono ancora disponibili (come le dimensioni di Marketing Channels). |
| Quanto tempo è necessario per assemblare gli elementi del dataset in una visualizzazione dati? | Poche ore per iniziare e qualche giorno per recuperare gli ultimi 13 mesi di dati. |
| È necessario inserire dati PII per stabilire connessioni tra i dati? | No, puoi utilizzare qualsiasi ID, incluso un hash di un ID cliente, che non è PII. |
| **Componenti Analytics tradizionali** |  |
| Cosa significa questo per il nostro prodotto Adobe Analytics tradizionale? | Customer Journey Analytics è il prodotto di analisi di nuova generazione. L&#39;evoluzione dai nostri prodotti attuali ad Analisi del percorso del cliente richiederà anni e molta coordinazione. Questa versione è un grande passo avanti di molti in questa direzione. |
| Posso condividere segmenti da Analisi percorso cliente ad AEP o altre soluzioni? | Non ancora. Stiamo studiando nuovi metodi innovativi per condividere in futuro segmenti da Customer Journey Analytics ad AEP che non avranno un ritardo così lungo. Detto questo, potete condividere l&#39;output di Servizi query su Profilo unificato come soluzione alternativa. |
| Cos&#39;è successo alla mia vecchia impostazione eVar? | eVar, prop ed eventi nel senso tradizionale di Adobe Analytics non esistono più in Analisi del percorso del cliente. Sono disponibili elementi dello schema illimitati (dimensioni, metriche, campi elenco). Di conseguenza, tutte le impostazioni di attribuzione applicate durante il processo di raccolta dei dati vengono ora applicate al momento della query. |
| Dove sono ora tutte le impostazioni relative alla sessione e alla persistenza variabile? | Analisi del percorso del cliente applica tutte queste impostazioni al momento del rapporto e queste ora sono live in Visualizzazioni dati. Le modifiche a queste impostazioni sono ora retroattive e puoi avere più versioni utilizzando più visualizzazioni dati! |
| Cosa succede ai segmenti/metriche calcolate esistenti? | Analisi del percorso del cliente non utilizza più eVar, prop o eventi e utilizza invece uno schema AEP. Ciò significa che nessuno dei segmenti o delle metriche di calcolo esistenti è compatibile con l&#39;analisi del percorso cliente. |
| In che modo l&#39;analisi del percorso cliente gestisce `Uniques Exceeded` i limiti? | Analisi del percorso del cliente non ha limiti di valore univoci, quindi non è necessario preoccuparsi di loro! |
| Se sono già un [!DNL Data Workbench] cliente, posso passare all&#39;analisi del percorso del cliente in questo momento? | Dipende. Se ti fidi molto del processo unificato dei clienti (UCP), dovrai aspettare fino a quando non sarà stato implementato il sistema di cuciture. Se hai già tassi di autenticazione elevati per i clienti, o se vuoi che tutti i tuoi dati vengano salvati in un&#39;unica posizione, o se desideri eliminare le eVar, Analisi del percorso cliente potrebbe essere una buona soluzione. |

