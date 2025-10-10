---
title: Generazione rapporti di Target
description: Integrare Adobe Target con Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: 979564d0249abadd454ce43aba9aeae2c78a44f0
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 41%

---

# Generazione rapporti di Target

La funzione di reporting di Target in Customer Journey Analytics consente di misurare e creare rapporti sulle attività di Adobe Target direttamente in Customer Journey Analytics. Questa funzionalità è paragonabile a quella eseguita in Adobe Analytics (AA) tramite Analytics for Target (A4T), ma con la connettività a Adobe Experience Platform (AEP).

Aggiungendo il set di dati di ricerca di Classificazione di Target (disponibile per impostazione predefinita in Experience Platform) in una connessione Customer Journey Analytics, gli utenti ora dispongono della corretta esposizione agli strumenti di reporting di Target, all’attribuzione dell’ordine di Target e ad altre funzioni. Con solo alcune lievi preparazioni e modifiche effettuate all’interno della visualizzazione dati di Customer Journey Analytics, queste attività possono essere rese immediatamente disponibili per qualsiasi utente che desideri inviare i dati di Target direttamente in CJA.

## Vantaggi principali

* I marketer possono applicare dinamicamente le metriche di successo di Customer Journey Analytics ai rapporti di attività di Target in qualsiasi momento. Non è necessario specificare tutte le impostazioni prima di eseguire l’attività.
* I marketer possono sfruttare le funzioni di Customer Journey Analytics, come il pannello Sperimentazione, per analizzare ulteriormente la personalizzazione del sito web.
* I marketer possono avere un’unica origine di reporting per Adobe Journey Optimizer e Target. Entrambi i prodotti di personalizzazione possono essere collegati a Customer Journey Analytics per una visualizzazione più olistica della personalizzazione web.

## Note e considerazioni

Una volta aggiunto il set di dati dell’evento di classificazione di Target a una connessione CJA, è necessario apportare alcune modifiche minori alla visualizzazione dati di CJA dopo l’aggiunta di questi componenti come dimensioni, tra cui:

* Impostare la persistenza in modo che sia simile a come viene tracciata in Target (rivolgiti a un consulente di Target o al cliente per verificare le impostazioni corrette).

* Impostando la persistenza su ALL, si consente il tracciamento simultaneo di più attività di Target e non la sovrascrittura di attività future o precedenti.

## Informazioni più dettagliate

Per ulteriori informazioni, consulta [Reporting di Target in Adobe Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/target/using/integrate/cja/target-reporting-in-cja) nella documentazione di Target.

Consulta il [pannello Sperimentazione](../analysis-workspace/c-panels/experimentation.md) per ulteriori informazioni sulle possibilità, da parte degli analisti, di confrontare diverse varianti di esperienza utente, marketing o messaggistica al fine di stabilire quale sia meglio per determinare un risultato specifico. Puoi valutare l’incremento e l’affidabilità di qualsiasi esperimento A/B da qualsiasi piattaforma di sperimentazione: online, offline, dalle soluzioni di Adobe, come Target o Journey Optimizer e persino da dati BYO (risorse disponibili).
