---
title: Customer Journey Analytics e governance dei dati
description: Descrive il funzionamento della governance dei dati nel Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 2f74c10f821aed421e31ee8e14b854f2a73c11f1
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 75%

---

# Customer Journey Analytics e governance dei dati

In generale, tutte le impostazioni relative alla governance dei dati nel Customer Journey Analytics vengono ereditate da Adobe Experience Platform.

## Governance dei dati

CJA supporta le etichette e i criteri per la governance dei dati configurati in Adobe Experience Platform. Per ulteriori informazioni, consulta [Supporto di CJA per la governance dei dati di Adobe Experience Platform](/help/data-views/data-governance.md).

## RGPD

Customer Journey Analytics non aderirà direttamente al servizio centrale del regolamento generale sulla protezione dei dati (RGPD) ed erediterà invece tutte le modifiche ai dataset effettuate in Experience Platform. Ci affidiamo a Platform Data Lake perché faccia rispettare le richieste di eliminazione relative al RGPD e ci invii una notifica quando il processo viene completato sulla pipeline. Controlliamo la pipeline e sincronizziamo tutte le modifiche apportate ai batch interessati in Customer Journey Analytics per i dataset di eventi. I dataset di profilo e di ricerca interessati da richieste di eliminazione relative al RGPD verranno completamente riacquisiti dopo ogni richiesta di eliminazione. Possiamo garantire che le richieste di eliminazione siano eseguite entro 7 giorni da un evento di eliminazione in Data Lake.

## CCPA

Il California Consumer Privacy Act (CCPA) migliora i diritti alla privacy e la protezione dei consumatori per i residenti in California, Stati Uniti. La legge entrerà in vigore il 1° gennaio 2020.
Il CCPA conferisce ai residenti della California nuovi diritti sulla privacy dei dati, come il diritto di accesso e cancellazione dei propri dati personali, di sapere se i propri dati personali vengono venduti o divulgati (e a chi) e di rifiutare la vendita degli stessi.
In previsione del CCPA, Privacy Service supporterà le richieste di rinuncia alla vendita di dati personali.
