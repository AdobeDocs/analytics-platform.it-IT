---
title: Customer Journey Analytics e governance dei dati
description: Descrive il funzionamento della governance dei dati nel Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 40706e3118cbaf7582d8625d307358b16f1836ac
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 100%

---

# Adobe Customer Journey Analytics e governance dei dati

In generale, Customer Journey Analytics eredita tutte le impostazioni relative alla governance dei dati da Adobe Experience Platform.

## Governance dei dati

L’integrazione tra Adobe Customer Journey Analytics e [governance dei dati di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=it) consente l’etichettatura dei dati Customer Journey Analytics sensibili e l’applicazione dei criteri di privacy.

Le etichette e i criteri di privacy creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle visualizzazioni dati di Customer Journey Analytics. Queste etichette interrompono o avvertono gli utenti che creano metriche e/o dimensioni da campi sensibili.

Inoltre, quando i dati vengono esportati da Customer Journey Analytics (tramite reporting, esportazione, API ecc.), vengono aggiunti avvisi o etichette per avvisare gli utenti che un report contiene informazioni sensibili che devono essere trattate in un modo specifico.

Questa integrazione consente di gestire più facilmente la conformità. Gli amministratori di dati della tua organizzazione possono impostare criteri per limitare l’utilizzo. Di conseguenza, gli utenti di Customer Journey Analytics possono utilizzare i dati in modo più affidabile, sapendo che sono conformi ai criteri definiti dagli amministratori dei dati.

[Ulteriori informazioni](/help/data-views/data-governance.md)

## Richieste di privacy

Adobe gestisce le richieste di privacy in conformità alle leggi locali e internazionali applicabili.

Poiché Customer Journey Analytics utilizza i dati disponibili in Adobe Experience Platform, Adobe offre [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) per inviare richieste di accesso ed eliminazione dei dati. Le richieste si applicano sia ai set di dati originali che a quelli reimpostati.

## GDPR

Customer Journey Analytics non aderirà direttamente al servizio centrale del regolamento generale sulla protezione dei dati (GDPR) ed erediterà invece tutte le modifiche ai dataset effettuate in Experience Platform. Customer Journey Analytics dipende dal data lake di Platform per l’applicazione delle richieste di eliminazione GDPR e per la notifica a Customer Journey Analytics quando le richieste sono completate. Tutte le modifiche ai batch interessati in Customer Journey Analytics per i set di dati evento sono sincronizzate con i dati di Platform. I set di dati di profilo e di ricerca interessati da richieste di eliminazione GDPR sono completamente riacquisiti dopo ogni richiesta di eliminazione. Le richieste di eliminazione vengono generalmente completate entro 7 giorni da un evento di eliminazione nel data lake.

## CCPA

Il California Consumer Privacy Act (CCPA) migliora i diritti alla privacy e la protezione dei consumatori per i residenti in California, Stati Uniti. La legge è entrata in vigore il 1° gennaio 2020.
Il CCPA conferisce ai residenti della California nuovi diritti sulla privacy dei dati, come il diritto di accesso e cancellazione dei propri dati personali, di sapere se i propri dati personali vengono venduti o divulgati (e a chi) e di rifiutare la vendita degli stessi.
In conformità al CCPA, Privacy Service supporta le richieste di rinuncia alla vendita di dati personali.

>[!MORELIKETHIS]
>
>* [Blog: Come mantenere una governance efficace in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4?profile.language=it)
