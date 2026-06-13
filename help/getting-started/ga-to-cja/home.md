---
title: Transizione da Google Analytics 4 a Customer Journey Analytics
description: Scopri i concetti chiave per ottenere rapporti in Customer Journey Analytics rivolti agli analisti che hanno familiarità con Google Analytics 4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# Transizione da Google Analytics 4 a Customer Journey Analytics

Questa guida aiuta gli analisti che hanno familiarità con Google Analytics 4 ad apprendere i concetti e i rapporti equivalenti in Adobe Customer Journey Analytics. Se sei responsabile dell&#39;implementazione tecnica anziché del reporting, consulta [Aggiornamento da una soluzione di analisi di terze parti a Customer Journey Analytics](../cja-upgrade/cja-upgrade-third-party-solution.md) per informazioni sulla configurazione di Web SDK e sull&#39;acquisizione dei dati. Se la tua organizzazione deve ancora eseguire la migrazione dei dati esistenti di Google Analytics in Adobe Experience Platform, consulta [Eseguire la migrazione dei dati da Google Analytics](/help/use-cases/third-party/ga/overview.md).

## Differenze chiave tra GA4 e Customer Journey Analytics

GA4 e Customer Journey Analytics condividono la stessa filosofia di base: ogni interazione dell’utente è un evento e l’analisi viene eseguita in uno strumento a area vuota in cui puoi trascinare dimensioni e metriche per creare viste personalizzate. Se conosci GA4 Explore, è probabile che Analysis Workspace sia immediatamente riconoscibile.

Le differenze più significative sono quelle in cui Customer Journey Analytics si estende oltre la GA4:

* **Dati cross-channel**: Customer Journey Analytics può combinare analisi web con origini dati offline (come record di call center, attività CRM, programmi fedeltà o coinvolgimento e-mail) nella stessa analisi. GA4 è limitato alle interazioni digitali raccolte attraverso il suo SDK.
* **Elaborazione al momento del reporting**: Customer Journey Analytics applica una logica come modelli di attribuzione, definizioni di sessione e regole di segmento al momento della query, non al momento della raccolta. Le modifiche apportate alle definizioni di sessione o ai modelli di attribuzione vengono applicate retroattivamente a tutti i dati storici senza essere rielaborati.
* **Definizioni di sessione flessibili**: la durata del timeout della sessione, gli eventi di avvio della sessione e gli eventi di fine sessione sono tutti configurabili in base alla visualizzazione dati in Customer Journey Analytics. Il timeout della sessione di GA4 è regolabile (impostazione predefinita di 30 minuti, fino a 7 ore e 55 minuti) ma si applica a livello di proprietà e il suo comportamento di avvio e fine sessione è fisso.
* **Unione identità**: la funzionalità di unione di Customer Journey Analytics può collegare interazioni tra dispositivi e canali diversi alla stessa persona, producendo conteggi di persone più precisi rispetto al modello di identità misto di GA4.

## Struttura dei conti e dei dati

GA4 e Customer Journey Analytics organizzano i dati in modo diverso a livello di piattaforma.

| GA4 | Customer Journey Analytics |
|---|---|
| Account Google | Organizzazione Adobe IMS |
| Proprietà | Connessione + visualizzazione dati |
| Flusso dati | [!UICONTROL Set di dati evento] in Platform |
| Filtri dati | Filtri dei componenti della visualizzazione dati |
| Sottoproprietà | Visualizzazione dati separata con filtri applicati |
| Proprietà rollup | Connessione che combina più set di dati |

La differenza strutturale più importante è che una proprietà GA4 gestisce sia il cablaggio dei dati che il reporting come un singolo oggetto. Customer Journey Analytics separa questi concetti in due livelli distinti:

* Una **connessione** collega uno o più set di dati di Adobe Experience Platform a Customer Journey Analytics. Questo passaggio acquisisce i dati in Customer Journey Analytics in un formato ottimizzato per il reporting.
* Una **visualizzazione dati** è basata su una connessione e definisce quali dimensioni, metriche e impostazioni sono disponibili per il reporting. È il livello di configurazione del reporting.

Entrambi devono esistere prima di poter analizzare i dati in Customer Journey Analytics. Non sono presenti suite di rapporti in Customer Journey Analytics.

## Guida introduttiva ad Analysis Workspace

GA4 Explore e Analysis Workspace sono strumenti di analisi in bianco e trascinamento. Il modello di interazione è lo stesso; la terminologia è leggermente diversa.

| Esplora GA4 | Analysis Workspace |
|---|---|
| Area di lavoro di esplorazione | Pannello |
| Tipo di grafico o visualizzazione | Visualizzazione |
| Dimensione | Dimensione |
| Metrica | Metrica |
| Segmento o filtro | Segmento |
| Conteggio eventi | [!UICONTROL Eventi] |
| Utenti | [!UICONTROL Persone] |
| Sessioni | [!UICONTROL Sessioni] |

>[!TIP]
>
>I contenitori di segmenti GA4 sono denominati Utenti, Sessioni ed Eventi. In Customer Journey Analytics, i contenitori equivalenti sono **[!UICONTROL Persona]**, **[!UICONTROL Sessione]** e **[!UICONTROL Evento]**. La logica di ambito è la stessa.

>[!MORELIKETHIS]
>
>* [Esegui migrazione dati da Google Analytics](/help/use-cases/third-party/ga/overview.md)
