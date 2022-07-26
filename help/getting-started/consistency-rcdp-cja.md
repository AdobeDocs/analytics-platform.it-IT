---
description: Spiega quali fattori influenzano la coerenza delle metriche e i conteggi di appartenenza al pubblico tra Real-time Customer Data Platform (Real-time CDP) e CJA.
title: Coerenza delle metriche e dei conteggi di iscrizione al pubblico tra Real-time CDP e CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 769eef205df32865874753859ce79e573db40641
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# Coerenza delle metriche e dei conteggi di iscrizione al pubblico tra Real-time CDP e CJA

In scenari reali, non è possibile garantire la coerenza delle metriche e i conteggi di iscrizione al pubblico in Real-time Customer Data Platform (Real-time CDP) e Customer Journey Analytics (CJA). Questo documento spiega perché.

Quando si confrontano i conteggi di appartenenza al pubblico tra Real-time CDP e CJA, è importante tenere presente le diverse finalità di questi due strumenti. Real-time CDP utilizza i dati del profilo del cliente per indirizzare le esperienze digitali ai singoli consumatori, mentre CJA è progettato per aiutare gli utenti a comprendere i pattern nelle metriche e nei segmenti aziendali chiave. Mentre la pubblicazione del pubblico da CJA a Real-time CDP consente all’utente di questi strumenti di &quot;attivare&quot; facilmente e in modo nativo un’informazione, sfruttando gli insegnamenti ottenuti in CJA, questi strumenti servono tuttavia a scopi fondamentalmente diversi.

## Differenze nelle configurazioni di identità

CDP e CJA in tempo reale non condividono la stessa definizione di persona oggi. Real-time CDP si basa interamente sulle informazioni contenute nel [Grafico di identità](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) per creare un profilo unito.

CJA può essere configurato per l’utilizzo [Analisi cross-channel](/help/connections/cca/overview.md) che estrae gli identificatori dai set di dati nel data lake e applica una logica personalizzata per collegarli.

In futuro, CJA sarà in grado di utilizzare Identity Graph.

## Differenze nella configurazione del set di dati

Puoi scegliere di inserire alcuni dati in Real-time CDP e alcuni in CJA; spesso, i clienti scelgono di inserire in CJA più dati storici rispetto a quelli relativi a Real-time CDP. Altri set di dati potrebbero essere più rilevanti per Real-time CDP che per CJA.

## Differenze nella configurazione di elaborazione

CJA consente di modificare i dati in modo esteso in fase di query, ad esempio combinando campi, suddividendo i campi in più parti e altre manipolazioni come include/esclude, sottostringhe, deduplicazione dei valori, sessionizzazione e filtro a livello di riga.

Real-time CDP offre un diverso set di strumenti di manipolazione dei dati. Si applica [criteri di unione](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) per determinare quali dati avranno priorità e quali saranno combinati per creare una visualizzazione unificata di una persona.

## Differenze in TTL (Time to Live) e inserimento dati

Anche se i set di dati in Real-time CDP e CJA sono gli stessi, Real-time CDP può solo tenere una finestra molto limitata della storia. Al contrario, CJA probabilmente vanta dati per anni. Inoltre:

* I clienti CJA e Real-time CDP possono impostare finestre di conservazione personalizzate per i dati, indipendentemente l’uno dall’altro.

* CDP e CJA in tempo reale hanno una logica diversa per l’acquisizione dei dati. CJA ignora i record privi di un ID persona o di una marca temporale e ha limiti rigidi al numero di record che un singolo profilo/persona può avere.

* I clienti Real-time CDP ottengono 7 giorni di accesso ai dati nel lago, principalmente per facilitare l’onboarding dei dati nel profilo e per query ad-hoc.

* Non esistono TTL per i dati presenti nel lago per i clienti CJA. Tuttavia, gli utenti CJA possono impostare una finestra di conservazione personalizzata in CJA al momento della creazione di una connessione.

* L’archivio profili in Real-time CDP consente l’utilizzo di TTL configurabili dal cliente. I clienti possono cambiare questo TTL in qualsiasi cosa debbano rimanere entro i propri diritti di licenza.

## Differenze nella latenza di acquisizione dei dati

CJa non dispone ancora delle funzionalità in tempo reale di Real-time CDP e, di conseguenza, il reporting di CJA include una certa latenza prima che i dati siano disponibili per il reporting o la creazione di audience. Real-time CDP elabora i dati attraverso diversi sistemi con latenza diversa.
