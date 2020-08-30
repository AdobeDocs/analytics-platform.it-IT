---
title: Panoramica sulla privacy di Customer Journey Analytics
description: Descrive il funzionamento delle impostazioni di privacy in Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---


# Panoramica sulla privacy di Customer Journey Analytics

In generale, Customer Journey Analytics eredita tutte le impostazioni relative alla privacy da Adobe Experience Platform.

## RGPD

Customer Journey Analytics non aderirà direttamente al servizio centrale del regolamento generale sulla protezione dei dati (RGPD) ed erediterà invece tutte le modifiche ai dataset effettuate in Experience Platform. Ci affidiamo a Platform Data Lake perché faccia rispettare le richieste di eliminazione relative al RGPD e ci invii una notifica quando il processo viene completato sulla pipeline. Controlliamo la pipeline e sincronizziamo tutte le modifiche apportate ai batch interessati in Customer Journey Analytics per i dataset di eventi. I dataset di profilo e di ricerca interessati da richieste di eliminazione relative al RGPD verranno completamente riacquisiti dopo ogni richiesta di eliminazione. Possiamo garantire che le richieste di eliminazione siano eseguite entro 7 giorni da un evento di eliminazione in Data Lake.

## CCPA

Il California Consumer Privacy Act (CCPA) migliora i diritti alla privacy e la protezione dei consumatori per i residenti in California, Stati Uniti. La legge entrerà in vigore il 1° gennaio 2020.
Il CCPA conferisce ai residenti della California nuovi diritti sulla privacy dei dati, come il diritto di accesso e cancellazione dei propri dati personali, di sapere se i propri dati personali vengono venduti o divulgati (e a chi) e di rifiutare la vendita degli stessi.
In previsione del CCPA, Privacy Service supporterà le richieste di rinuncia alla vendita di dati personali.
