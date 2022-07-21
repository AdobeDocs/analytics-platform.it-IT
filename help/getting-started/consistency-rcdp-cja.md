---
description: Spiega quali fattori influenzano la coerenza delle metriche tra Real-time Customer Data Platform (Real-time CDP) e CJA.
title: Coerenza delle metriche tra Real-time CDP e CJA
role: Admin
feature: CJA Basics
source-git-commit: 2318b303c981ad556dc61a3419af4cce9fbbf92b
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 2%

---


# Coerenza delle metriche tra Real-time CDP e CJA

In scenari reali, non è possibile garantire la coerenza delle metriche in Real-time Customer Data Platform (Real-time CDP) e Customer Journey Analytics (CJA). Questo documento spiega perché.

## CJA non utilizza ancora Identity Graph

Attualmente CDP e CJA non condividono la stessa definizione di persona. CJA non utilizza ancora [Grafico di identità](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it) informare la sua definizione di persona. Per creare un profilo unito, la piattaforma CDP in tempo reale si basa interamente sulle informazioni contenute in Identity Graph.

CJA utilizza un metodo chiamato [Unione basata sui campi](/help/connections/cca/overview.md) che estrae gli identificatori dai set di dati nel data lake e applica una logica personalizzata per collegarli. Nel futuro intermedio, CJA dovrebbe iniziare a utilizzare [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) esportazioni verso il data lake, consentendo una nozione condivisa di identità tra Real-time CDP e CJA.

>[!IMPORTANT]
>
>L’impostazione del servizio Adobe Experience Platform Identity come origine di verità per tutte le applicazioni Adobe Experience Platform non rende automaticamente le metriche coerenti tra le applicazioni. Continua a leggere per scoprire il perché.

## Flessibilità dei dati dell&#39;applicazione

L’Experience Platform non applica un’applicazione rigorosa per mantenere i dati tra Profilo cliente in tempo reale e Data Lake uguali. Alcuni casi d&#39;uso utilizzano dati in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) (attivazione), mentre altri lavorano fuori dalla [lago dati](https://business.adobe.com/blog/basics/data-lake) (servizio di reporting e query).

I clienti Real-time CDP in genere non hanno il 100% dei dati nel data lake di Adobe Experience Platform che vanno in Profile (Profilo). Questo è di progettazione - i clienti dovrebbero abilitare i dati in particolare nel lago per Profilo. CJA consente agli analisti di dati di selezionare liberamente quali dati desiderano inserire per l’analisi dal data lake, indipendentemente da ciò che è abilitato per Real-time CDP.

## Modificatori specifici per l’applicazione

CJA consente di apportare modifiche estese ai dati in fase di query, ad esempio combinando campi, suddividendo i campi in più parti e altre manipolazioni come conversioni di valuta, deduplicazione dei valori, sessionizzazione e filtro a livello di riga. Queste funzionalità non sono disponibili per CDP.

Analogamente, si applica Real-time CDP [criteri di unione](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) per determinare quali dati avranno priorità e quali saranno combinati per creare una visualizzazione unificata di una persona. Queste configurazioni si collocano saldamente nella logica di ogni applicazione e non sono condivise.

## Comportamento in tempo di lettura e di scrittura

CDP in tempo reale richiede la combinazione di profili point-in-time utilizzando il grafico ID più recente.

* Real-time CDP è progettato per assemblare le informazioni di profilo in tempo reale per l&#39;attivazione.

* Può contenere in tempo reale tutte le modifiche agli identificatori impostati per un determinato utente.

* L’intervallo di lookback è controllato dalla definizione del segmento.

CJA richiede che i dati vengano uniti in fase di scrittura utilizzando le esportazioni di ID Graph.

* CJA applica passaggi di pre-elaborazione complessi come l’indicizzazione, la condivisione e il raggruppamento prima che i dati siano pronti per l’analisi.

* L&#39;identificativo della persona per un determinato utente è un input fondamentale per le fasi di pre-elaborazione; la successiva modifica dell&#39;identificatore della persona comporta un costo significativo di rielaborazione.

* L’intervallo di lookback è controllato a livello di applicazione.

## Differenze in TTL (Time to Live) e inserimento dati

Anche se i set di dati in Real-time CDP e CJA sono gli stessi, Real-time CDP può solo tenere una finestra molto limitata della storia. Al contrario, CJA probabilmente vanta dati per anni. Inoltre:

* I clienti CJA e Real-time CDP possono impostare finestre di conservazione personalizzate per i dati, indipendentemente l’uno dall’altro.

* CDP e CJA in tempo reale hanno una logica diversa per l’acquisizione dei dati. CJA ignora i record privi di un ID persona o di una marca temporale e ha limiti rigidi al numero di record che un singolo profilo/persona può avere.

* I clienti Real-time CDP ottengono 7 giorni di accesso ai dati nel lago, principalmente per facilitare l’onboarding dei dati nel profilo e per query ad-hoc.

* Non esistono TTL per i dati presenti nel lago per i clienti CJA. Tuttavia, gli utenti CJA possono impostare una finestra di conservazione personalizzata in CJA al momento della creazione di una connessione.

* L’archivio profili in Real-time CDP consente l’utilizzo di TTL configurabili dal cliente. I clienti possono cambiare questo TTL in qualsiasi cosa debbano rimanere entro i propri diritti di licenza.

## Differenze nell’elaborazione del RGPD (Regolamento generale sulla protezione dei dati)

La logica di elaborazione dei dati per il RGPD e l’igiene dei dati in Real-time CDP e data lake è molto diversa. Stiamo lavorando per un approccio unico.

## Differenze nella latenza di acquisizione dei dati

Il reporting di CJA include una certa latenza prima che i dati siano disponibili per il reporting o la creazione di un pubblico. Real-time CDP elabora i dati attraverso diversi sistemi con latenza diversa.