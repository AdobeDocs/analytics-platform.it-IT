---
title: Customer Journey Analytics e governance dei dati
description: Descrive il funzionamento della governance dei dati nel Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 68%

---

# Adobe Customer Journey Analytics e governance dei dati

In generale, Customer Journey Analytics eredita tutte le impostazioni relative alla privacy da Adobe Experience Platform.

## Governance dei dati

L’integrazione tra Adobe Customer Journey Analytics e [Governance dei dati Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=it) consente l’etichettatura dei dati sensibili del Customer Journey Analytics e l’applicazione delle politiche sulla privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di Customer Journey Analytics. Queste etichette interrompono o avvertono gli utenti che creano metriche e/o dimensioni da campi sensibili.

Inoltre, quando i dati vengono esportati dal Customer Journey Analytics (tramite reporting, esportazione, API, ecc.), vengono aggiunti avvisi o etichette per avvisare gli utenti che un rapporto contiene informazioni sensibili che devono essere trattate in un modo specifico.

Questa integrazione consente di gestire più facilmente la conformità. Gli amministratori di dati della tua organizzazione possono impostare criteri per limitare l’utilizzo. Di conseguenza, gli utenti del Customer Journey Analytics possono utilizzare i dati in modo più affidabile, sapendo che sono conformi alle policy definite dagli amministratori dei dati.

[Ulteriori informazioni](/help/data-views/data-governance.md)

## RGPD

Customer Journey Analytics non aderirà direttamente al servizio centrale del regolamento generale sulla protezione dei dati (RGPD) ed erediterà invece tutte le modifiche ai dataset effettuate in Experience Platform. Utilizziamo Platform Data Lake per rispettare le richieste di eliminazione relative al RGPD e per ricevere una notifica quando il processo viene completato nella pipeline. Controlliamo la pipeline e sincronizziamo tutte le modifiche apportate ai batch interessati in Customer Journey Analytics per i dataset di eventi. I dataset di profilo e di ricerca interessati da richieste di eliminazione relative al RGPD verranno completamente riacquisiti dopo ogni richiesta di eliminazione. Possiamo garantire che le richieste di eliminazione siano eseguite entro 7 giorni da un evento di eliminazione in Data Lake.

## CCPA

Il California Consumer Privacy Act (CCPA) migliora i diritti alla privacy e la protezione dei consumatori per i residenti in California, Stati Uniti. La legge è entrata in vigore il 1° gennaio 2020.
Il CCPA conferisce ai residenti della California nuovi diritti sulla privacy dei dati, come il diritto di accesso e cancellazione dei propri dati personali, di sapere se i propri dati personali vengono venduti o divulgati (e a chi) e di rifiutare la vendita degli stessi.
In conformità al CCPA, Privacy Service supporta le richieste di rinuncia alla vendita di dati personali.
