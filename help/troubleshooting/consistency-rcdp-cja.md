---
description: Spiega quali fattori influenzano la coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-time Customer Data Platform (Real-time CDP) e Customer Journey Analytics.
title: Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-time CDP e Customer Journey Analytics
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 23%

---


# Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-time CDP e Adobe Customer Journey Analytics

In scenari reali, non è possibile garantire la coerenza di metriche e conteggi di appartenenza a un pubblico in Real-time Customer Data Platform (Real-time CDP) e nel Customer Journey Analytics. Questo documento spiega perché.

Quando si confrontano i conteggi di appartenenza a un pubblico tra Real-Time CDP e Customer Journey Analytics, è importante tenere presente le diverse finalità di questi due strumenti. Real-Time CDP utilizza i dati del profilo del cliente per indirizzare le esperienze digitali ai singoli consumatori, mentre il Customer Journey Analytics è progettato per aiutare gli utenti a comprendere i pattern nei segmenti e nelle metriche aziendali chiave. La pubblicazione di tipi di pubblico da Customer Journey Analytics a Real-time CDP consente a un utente di questi strumenti di &quot;attivare&quot; facilmente e in modalità nativa un approfondimento, sfruttando le informazioni ottenute nel Customer Journey Analytics. Tuttavia, questi strumenti servono a scopi fondamentalmente diversi.

## Differenze nelle configurazioni di identità

Real-Time CDP e Customer Journey Analytics oggi non condividono la stessa definizione di persona. Real-Time CDP si basa interamente sulle informazioni contenute nel [grafo delle identità](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html) per generare un profilo unito.

Il Customer Journey Analytics può essere configurato per l&#39;utilizzo [Stitching](../stitching/overview.md) che estrae gli identificatori dai set di dati nel data lake e applica una logica personalizzata per collegarli tra loro.

In futuro, il Customer Journey Analytics sarà in grado di utilizzare il grafico delle identità.

## Differenze nella configurazione dei set di dati

Puoi scegliere di inserire alcuni dati in Real-time CDP e alcuni in Customer Journey Analytics; spesso, i clienti scelgono di inserire nel Customer Journey Analytics più dati storici di quelli rilevanti per Real-time CDP. Altri set di dati potrebbero essere più rilevanti per Real-time CDP che per Customer Journey Analytics.

## Differenze nella configurazione di elaborazione

Il Customer Journey Analytics consente di apportare modifiche estese ai dati in fase di query, ad esempio combinando i campi, suddividendoli in più parti ed effettuando altre manipolazioni quali inclusioni/esclusioni, sottostringhe, deduplicazione dei valori, sessionizzazione e filtro a livello di riga.

Real-Time CDP offre un diverso set di strumenti di manipolazione dei dati. Applica i [criteri di unione](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html) per determinare quali dati avranno priorità e quali saranno combinati per creare una vista unificata di una persona.

## Differenze in TTL (Time to Live) e acquisizione dei dati

Anche se i set di dati in Real-time CDP e Customer Journey Analytics sono gli stessi, Real-time CDP può mantenere solo una finestra di cronologia molto limitata. Al contrario, il Customer Journey Analytics probabilmente ha dati riferiti a diversi anni. Inoltre:

* I clienti Customer Journey Analytics e Real-time CDP possono impostare finestre di conservazione dei dati personalizzate e indipendenti tra loro.

* Real-Time CDP e Customer Journey Analytics hanno una logica diversa per l’acquisizione dei dati. Il Customer Journey Analytics ignora i record privi di un ID persona o di una marca temporale e prevede limiti rigidi al numero di record che un singolo profilo o una singola persona può avere.

* I clienti Real-Time CDP hanno accesso a 7 giorni di dati nel data lake, principalmente per facilitare l’onboarding dei dati nel profilo e per query ad-hoc.

* Non ci sono TTL per i dati nel data lake per i clienti di Customer Journey Analytics. Gli utenti del Customer Journey Analytics possono tuttavia impostare una finestra di conservazione personalizzata nel Customer Journey Analytics durante la creazione di una connessione.

* L’archivio profili in Real-Time CDP consente ldi utilizzare TTL configurabili dal cliente. I clienti possono modificare il TTL in base alle esigenze, entro i propri diritti di licenza.

## Differenze nella latenza di acquisizione dei dati

Il Customer Journey Analytics non dispone ancora delle funzionalità in tempo reale di Real-time CDP e, di conseguenza, il reporting del Customer Journey Analytics include una certa latenza prima che i dati siano disponibili per il reporting o la creazione di tipi di pubblico. Real-Time CDP elabora i dati attraverso diversi sistemi, ciascuno con propri valori di latenza.
