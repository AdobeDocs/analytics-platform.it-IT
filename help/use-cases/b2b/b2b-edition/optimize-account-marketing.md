---
title: Ottimizzare il marketing dell’account
description: Scopri come ottimizzare il marketing degli account utilizzando Customer Journey Analytics B2B edition.
solution: Customer Journey Analytics
feature: Use Cases
role: User
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: d5e44546-ea82-42eb-98df-19d51c71e9be
source-git-commit: f66df039c56fc1df3fb0e102745f500a3782d26d
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 1%

---

# Ottimizzare il marketing dell’account

{{draft-b2b}}

Un marketing efficace basato sull’account richiede una profonda comprensione del percorso di acquisto a livello di account. Quindi, puoi determinare le attività di marketing di maggior impatto da concludere.

Per comprendere questo aspetto, è necessario analizzare ed esplorare i seguenti aspetti:

* Impatto sul marketing:

   * Tra campagne, canali e contenuti.
   * Per gruppi di acquisto all’interno di account,

* Progressione della pipeline di vendita.
* Opportunità di upselling e cross-selling.
* Integrità dell’account del cliente.


Customer Journey Analytics B2B edition può aiutarti nell’ottimizzazione del marketing per gli account. Per alcuni esempi, consulta le sezioni seguenti.


## Coinvolgimento di marketing basato sull’account

Desideri identificare quali esperienze, sia online che offline, sono più incisive nella creazione di opportunità chiuse.

Utilizza la visualizzazione [area di lavoro Percorsi](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) per mappare ogni interazione tra account, opportunità, gruppi di acquisto, campagne e canali per ottenere informazioni approfondite su ciò che funziona nel marketing del tuo account e su dove puoi migliorare.

Una visualizzazione dell’area di lavoro del percorso consente di:

* Guarda la storia completa. Ad esempio, puoi visualizzare un percorso dettagliato di un account o gruppo di acquisto *specifico* che include tutte le interazioni note online e offline.
* Contestualizzare i momenti chiave che precedono o seguono tappe fondamentali critiche (ad esempio: un trigger di lead qualificato per il marketing o la creazione di opportunità).
* Supporta il personale di vendita attraverso la cronologia delle interazioni della visualizzazione su account specifici. Tale visualizzazione consente conversazioni rilevanti.

### Esempio

Si desidera visualizzare il percorso da modulo lead a vincitore chiuso.

1. [Crea e configura una visualizzazione area di lavoro del Percorso](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
1. Configura **[!UICONTROL Account]** come **[!UICONTROL Primary metric]**.
1. Assicurarsi di selezionare **[!UICONTROL Account]** come **[!UICONTROL Journey canvas container]**.

   ![Caso di utilizzo B2B - ottimizzare il marketing dell&#39;account - area di lavoro del percorso - configurazione](assets/b2b-uc-optimize-marketing-journey-canvas-config.png)

1. Seleziona **[!UICONTROL Build]**.
1. Trascina e rilascia i nodi nell’area di lavoro e connetti i nodi per illustrare il percorso di account. Ad esempio: da **[!UICONTROL Lead Form: Step 1]** modulo a **[!UICONTROL Opp. Created]**.

   ![Caso di utilizzo B2B - ottimizzare il marketing dell&#39;account - area di lavoro percorso](assets/b2b-uc-optimize-marketing-journey-canvas.png)


## Segmentazione per coorte

Vuoi identificare il gruppo chiave di acquirenti in modo da attivare questi gruppi di acquirenti per altri canali, come media a pagamento, e-mail, social.

Utilizza la visualizzazione [Tabella coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) per raggruppare entità B2B (account, opportunità, gruppi di acquisto) in base a un punto di partenza condiviso (come una data di lead time di qualificazione del mercato (MQL)). E tenere traccia dell&#39;avanzamento di ciascuna di queste entità nel tempo nelle fasi o nei milestone successivi.

Una visualizzazione con tabella coorte consente di:

* Analizza la rapidità con cui le coorti di account o opportunità raggiungono le tappe fondamentali (ad esempio: da un lead qualificato per il marketing a un lead qualificato per le vendite) nell’arco di settimane o mesi.
* Identifica se alcune coorti (per segmento, origine della campagna, tipo di gruppo di acquisto) progrediscono più rapidamente nel ciclo di vendita rispetto ad altre coorti.
* Valuta se le iniziative strategiche (ad esempio: campagne di marketing) sono correlate a tempistiche di progressione più brevi per le coorti successive.

### Esempio

Volete vedere coorti mensili di opportunità chiuse.

1. [Crea e configura una visualizzazione Tabella coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
1. Utilizza **[!UICONTROL Opportunity Created]** come metrica **[!UICONTROL Inclusion criteria]**. Selezionare **[!UICONTROL >=]** come operatore e immettere il valore `1`.
1. Utilizza **[!UICONTROL Closed-Won]** come metrica **[!UICONTROL Return criteria]**. Selezionare **[!UICONTROL >=]** come operatore e immettere il valore `1`.
1. Seleziona **[!UICONTROL Opportunity]** come contenitore.

   ![Caso di utilizzo B2B - segmentazione coorte - tabella coorte - config](assets/b2b-uc-optimize-marketing-cohort-table-config.png)

1. Seleziona **[!UICONTROL Build]**. Di seguito è riportato un esempio di tabella coorte.

   ![Caso di utilizzo B2B - segmentazione per coorte - tabella coorte](assets/b2b-uc-optimize-marketing-cohort-table.png)


## Eventi di persona

Desideri creare rapporti sull’account coinvolto e visualizzare l’attività in più eventi di persona. In questo modo, puoi analizzare e ottimizzare l’impatto della partecipazione diretta agli eventi.

Una visualizzazione del [flusso](/help/analysis-workspace/visualizations/c-flow/flow.md) consente di visualizzare i percorsi seguiti dagli utenti, ma ora anche dagli account o dai gruppi di acquisto, da seguire tra le interazioni o le fasi nel tempo.

Una visualizzazione del flusso consente di:

* Identifica le sequenze più frequenti di punti di contatto attraversati da entità B2B (ad esempio: da *Visita sito* a *Download white paper* a *Richiesta demo*).
* Visualizzare la modalità di navigazione non lineare degli account o dei gruppi di acquisto (ad esempio: eseguire un ciclo indietro, saltare fasi o seguire percorsi imprevisti).
* Concentrati sul flusso prima o dopo un’interazione critica (ad esempio: una richiesta demo) per capire a quali fattori contribuisce o quali azioni seguono dopo l’interazione.

### Esempio

Desideri visualizzare l’influenza sulla generazione di MQL (lead qualificati per il marketing).

1. [Crea e configura una visualizzazione Flusso](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
1. Selezionare **[!UICONTROL MQL Qualified]** per **[!UICONTROL End with]**.
1. Selezionare **[!UICONTROL Content Type]** per **[!UICONTROL Pathing dimension]**.
1. Seleziona **[!UICONTROL Show advanced settings]**.
1. Immettere `5` per **[!UICONTROL Number of columns]**.
1. Selezionare **[!UICONTROL Account]** per **[!UICONTROL Flow container]**.

   ![Caso di utilizzo B2B - eventi di persona - configurazione flusso](assets/b2b-uc-optimize-marketing-flow-config.png)

1. Seleziona **[!UICONTROL Build]**.

   ![Caso di utilizzo B2B - eventi di persona - configurazione flusso](assets/b2b-uc-optimize-marketing-flow.png)
