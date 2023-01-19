---
description: Spiega i fattori che influenzano la coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-time Customer Data Platform (Real-Time CDP) e CJA.
title: Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-Time CDP e CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: ht
source-wordcount: '577'
ht-degree: 100%

---


# Coerenza di metriche e conteggi di appartenenza a un pubblico tra Real-Time CDP e CJA

In scenari reali, non è possibile garantire la coerenza di metriche e conteggi di appartenenza a un pubblico in Real-time Customer Data Platform (Real-Time CDP) e Customer Journey Analytics (CJA). Questo documento spiega perché.

Quando si confrontano i conteggi di appartenenza a un pubblico tra Real-Time CDP e CJA, è importante tenere presente le diverse finalità di questi due strumenti. Real-Time CDP utilizza i dati del profilo del cliente per indirizzare le esperienze digitali ai singoli consumatori: CJA, invece, è progettato per aiutare gli utenti a comprendere eventualii pattern nei segmenti e nelle metriche aziendali chiave. La pubblicazione di tipi di pubblico da CJA a Real-Time CDP consente a chi usa questi strumenti di “attivare” facilmente e in modalità nativa un approfondimento, sfruttando le informazioni ottenute in CJA; tuttavia questi due strumenti servono a scopi fondamentalmente diversi.

## Differenze nelle configurazioni di identità

Real-Time CDP e CJA attualmente non condividono la stessa definizione di persona. Real-Time CDP si basa interamente sulle informazioni contenute nel [grafo delle identità](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=it) per generare un profilo unito.

CJA può essere configurato per l’utilizzo di [Cross-Channel Analytics](/help/cca/overview.md), che estrae gli identificatori dai set di dati nel data lake e applica una logica personalizzata per collegarli tra di loro.

In futuro, CJA sarà in grado di utilizzare il grafo delle identità.

## Differenze nella configurazione dei set di dati

Puoi scegliere di inserire alcuni dati in Real-Time CDP e alcuni in CJA; spesso, i clienti scelgono di inserire in CJA più dati storici, meno rilevanti per Real-Time CDP. Altri set di dati potrebbero invece essere più rilevanti per Real-Time CDP che per CJA.

## Differenze nella configurazione di elaborazione

CJA consente di applicare modifiche estese ai dati in fase di query, ad esempio combinando dei campi, suddividendoli in più parti ed effettuando altre manipolazioni, per esempio con inclusioni/esclusioni, sottostringhe, deduplicazione dei valori, sessionizzazione e filtro a livello di riga.

Real-Time CDP offre un diverso set di strumenti di manipolazione dei dati. Applica i [criteri di unione](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=it) per determinare quali dati avranno priorità e quali saranno combinati per creare una vista unificata di una persona.

## Differenze in TTL (Time to Live) e acquisizione dei dati

Anche se i set di dati sono gli stessi, Real-Time CDP può conservare solo una finestra di dati storici molto limitata rispetto a CJA. Al contrario, CJA probabilmente avrà dati riferiti a diversi anni. Inoltre:

* I clienti CJA e Real-Time CDP possono impostare per i dati finestre di conservazione personalizzate e indipendenti tra loro.

* Real-Time CDP e CJA hanno una logica diversa per l’acquisizione dei dati. CJA ignora i record privi di un ID persona o di una marca temporale e impone limiti rigidi al numero di record che un singolo profilo o una singola persona può avere.

* I clienti Real-Time CDP hanno accesso a 7 giorni di dati nel data lake, principalmente per facilitare l’onboarding dei dati nel profilo e per query ad-hoc.

* Per i clienti CJA non esistono TTL (Time to Live) per i dati presenti nel data lake. Gli utenti CJA, invece, possono impostare una finestra di conservazione personalizzata in CJA al momento della creazione di una connessione.

* L’archivio profili in Real-Time CDP consente ldi utilizzare TTL configurabili dal cliente. I clienti possono modificare il TTL in base alle esigenze, entro i propri diritti di licenza.

## Differenze nella latenza di acquisizione dei dati

CJA non dispone ancora delle funzionalità in tempo reale di Real-Time CDP; pertanto, il reporting di CJA è soggetto a una certa latenza prima che i dati siano disponibili per la creazione di un rapporto o di un pubblico. Real-Time CDP elabora i dati attraverso diversi sistemi, ciascuno con propri valori di latenza.
