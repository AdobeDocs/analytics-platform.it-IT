---
title: Generazione rapporti di Target
description: Integrare Adobe Target con Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
TQID: https://experienceleague.adobe.com/7Q8q-e58PrmANht9DpOXuNFImYC48ELhrXPRhBG6gYQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 34593a4407e6334e9abab6034accd84fc5a70d33
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 40%

---

# Generazione rapporti di Target

La funzione di reporting di Target in Customer Journey Analytics consente di misurare e creare rapporti sulle attività di Adobe Target direttamente in Customer Journey Analytics. Questa funzionalità è paragonabile a quella eseguita in Adobe Analytics (AA) tramite Analytics for Target (A4T), ma con la connettività a Adobe Experience Platform (AEP). Dopo aver creato un’attività Target che utilizza Customer Journey Analytics come origine per la generazione di rapporti, nella sandbox corrispondente viene creato un set di dati di ricerca denominato Eventi di classificazione di Adobe Target. Questo set di dati di ricerca arricchisce i rapporti classificando gli ID attività di Target con i loro attributi facili da usare (come Nome attività e Nome esperienza).

Aggiungendo questo set di dati di ricerca a una connessione Customer Journey Analytics, gli utenti ora hanno un’esposizione corretta agli strumenti di reporting di Target, all’attribuzione degli ordini di Target e ad altre funzioni. Con solo alcune lievi preparazioni e modifiche effettuate all’interno della visualizzazione dati di Customer Journey Analytics, queste attività possono essere rese immediatamente disponibili per qualsiasi utente che desideri inviare i dati di Target direttamente in Customer Journey Analytics.

## Vantaggi principali

* I marketer possono applicare dinamicamente le metriche di successo di Customer Journey Analytics ai rapporti di attività di Target in qualsiasi momento. Non è necessario specificare tutte le impostazioni prima di eseguire l’attività.
* I marketer possono sfruttare le funzioni di Customer Journey Analytics, come il pannello Sperimentazione, per analizzare ulteriormente la personalizzazione del sito web.
* I marketer possono avere un’unica origine di reporting per Adobe Journey Optimizer e Target. Entrambi i prodotti di personalizzazione possono essere collegati a Customer Journey Analytics per una visualizzazione più olistica della personalizzazione web.

## Note e considerazioni

L&#39;attività di Target deve [utilizzare Customer Journey Analytics come origine per la generazione di rapporti](https://experienceleague.adobe.com/it/docs/target/using/integrate/cja/target-reporting-in-cja).

Dopo che il set di dati di ricerca degli eventi di classificazione di Adobe Target è stato aggiunto a una connessione, è necessario apportare alcune piccole modifiche all’interno della visualizzazione dati dopo l’aggiunta di questi componenti come dimensioni, tra cui:

* Impostare la persistenza in modo che sia simile a come viene tracciata in Target (rivolgiti a un consulente di Target o al cliente per verificare le impostazioni corrette).

* Impostando la persistenza su ALL, si consente il tracciamento simultaneo di più attività di Target e non la sovrascrittura di attività future o precedenti.

## Informazioni più dettagliate

Per ulteriori informazioni, consulta [Reporting di Target in Adobe Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/target/using/integrate/cja/target-reporting-in-cja) nella documentazione di Target.

Consulta il [pannello Sperimentazione](../analysis-workspace/c-panels/experimentation.md) per ulteriori informazioni sulle possibilità, da parte degli analisti, di confrontare diverse varianti di esperienza utente, marketing o messaggistica al fine di stabilire quale sia meglio per determinare un risultato specifico. Puoi valutare l’incremento e l’affidabilità di qualsiasi esperimento A/B da qualsiasi piattaforma di sperimentazione: online, offline, dalle soluzioni di Adobe, come Target o Journey Optimizer e persino da dati BYO (risorse disponibili).
