---
description: Spiega i fattori che influenzano la coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-time Customer Data Platform (Real-Time CDP) e Customer Journey Analytics.
title: Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-Time CDP e Customer Journey Analytics
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '609'
ht-degree: 100%

---


# Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-Time CDP e Adobe Customer Journey Analytics

In scenari reali, non è possibile garantire la coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-time Customer Data Platform (Real-Time CDP) e Customer Journey Analytics. Questo documento spiega perché.

Quando si confrontano i conteggi di appartenenza a un pubblico tra Real-Time CDP e Customer Journey Analytics, è importante tenere presente le diverse finalità di questi due strumenti. Real-Time CDP utilizza i dati del profilo cliente per indirizzare le esperienze digitali ai singoli consumatori, Customer Journey Analytics invece è progettato per aiutare gli utenti a comprendere eventuali pattern nei segmenti e nelle metriche aziendali chiave. La pubblicazione di tipi di pubblico da Customer Journey Analytics a Real-Time CDP consente a chi usa questi strumenti di “attivare” facilmente e in modalità nativa un approfondimento, sfruttando le informazioni ottenute in Customer Journey Analytics; tuttavia questi due strumenti servono a scopi fondamentalmente diversi.

## Differenze nelle configurazioni di identità

Real-Time CDP e Customer Journey Analytics attualmente non condividono la stessa definizione di persona. Real-Time CDP si basa interamente sulle informazioni contenute nel [grafo delle identità](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=it) per generare un profilo unito.

Customer Journey Analytics può essere configurato per utilizzare l’[Unione](../stitching/overview.md), che estrae gli identificatori dai set di dati nel data lake e applica una logica personalizzata per collegarli tra di loro.

In futuro, Customer Journey Analytics sarà in grado di utilizzare il grafo identità.

## Differenze nella configurazione dei set di dati

Puoi scegliere di inserire alcuni dati in Real-Time CDP e alcuni in Customer Journey Analytics; spesso, i clienti scelgono di inserire in Customer Journey Analytics più dati storici, meno rilevanti per Real-Time CDP. Altri set di dati potrebbero invece essere più rilevanti per Real-Time CDP che per Customer Journey Analytics.

## Differenze nella configurazione di elaborazione

Customer Journey Analytics consente di applicare modifiche estese ai dati in fase di query, ad esempio combinando dei campi, suddividendoli in più parti ed effettuando altre manipolazioni, per esempio con inclusioni/esclusioni, sottostringhe, deduplicazione dei valori, sessionizzazione e filtro a livello di riga.

Real-Time CDP offre un diverso set di strumenti di manipolazione dei dati. Applica i [criteri di unione](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=it) per determinare quali dati avranno priorità e quali saranno combinati per creare una vista unificata di una persona.

## Differenze in TTL (Time to Live) e acquisizione dei dati

Anche se i set di dati sono gli stessi in Real-Time CDP e Customer Journey Analytics, Real-Time CDP può conservare solo una finestra di dati storici molto limitata. Al contrario, Customer Journey Analytics probabilmente avrà dati riferiti a diversi anni. Inoltre:

* I clienti Customer Journey Analytics e Real-Time CDP possono impostare per i dati finestre di conservazione personalizzate e indipendenti tra loro.

* Real-Time CDP e Customer Journey Analytics hanno una logica diversa per l’acquisizione dei dati. Customer Journey Analytics ignora i record privi di un ID persona o di una marca temporale e impone limiti rigidi al numero di record che un singolo profilo o una singola persona può avere.

* I clienti Real-Time CDP hanno accesso a 7 giorni di dati nel data lake, principalmente per facilitare l’onboarding dei dati nel profilo e per query ad-hoc.

* Per i clienti Customer Journey Analytics non esistono TTL (Time to Live) per i dati presenti nel data lake. Gli utenti Customer Journey Analytics possono tuttavia impostare una finestra di conservazione personalizzata al momento della creazione di una connessione.

* L’archivio profili in Real-Time CDP consente ldi utilizzare TTL configurabili dal cliente. I clienti possono modificare il TTL in base alle esigenze, entro i propri diritti di licenza.

## Differenze nella latenza di acquisizione dei dati

Il reporting di Customer Journey Analytics, che non dispone ancora delle funzionalità in tempo reale di Real-Time CDP; è soggetto a una certa latenza prima di poter utilizzare i dati per la creazione di un rapporto o di un pubblico. Real-Time CDP elabora i dati attraverso diversi sistemi, ciascuno con propri valori di latenza.
