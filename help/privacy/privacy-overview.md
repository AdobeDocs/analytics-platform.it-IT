---
title: Panoramica sulla privacy di Analisi del percorso del cliente
description: Descrive il funzionamento delle impostazioni di privacy in Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Panoramica sulla privacy di Analisi del percorso del cliente

In generale, tutte le impostazioni relative alla privacy in Analisi del percorso del cliente vengono ereditate da Adobe Experience Platform.

## GDPR

Customer Journey Analytics non si iscriverà direttamente al servizio centrale General Data Protection Regulation (GDPR) e erediterà invece tutte le modifiche apportate ai dataset in Experience Platform. Dipendiamo da Platform Data Lake per far rispettare le richieste di eliminazione di GDPR e inviarci una notifica al termine del processo. Ascoltiamo la pipeline e sincronizziamo tutte le modifiche apportate ai batch interessati nell&#39;analisi del percorso cliente per i set di dati dell&#39;evento. I set di dati di profilo e di ricerca interessati dalle richieste di eliminazione GDPR verranno completamente rivisitati dopo ogni richiesta di eliminazione. Possiamo garantire che le richieste di eliminazione vengano eseguite entro 7 giorni da un evento di eliminazione in Data Lake.

## CCPA

Il California Consumer Privacy Act (CCPA) migliora i diritti alla privacy e la protezione dei consumatori per i residenti in California, Stati Uniti. La legge entrerà in vigore il 1° gennaio 2020.
Il CCPA conferisce ai residenti della California nuovi diritti sulla privacy dei dati, come il diritto di accesso e cancellazione dei propri dati personali, di sapere se i propri dati personali vengono venduti o divulgati (e a chi), e di rifiutare la vendita degli stessi.
In previsione del CCPA, i servizi per la privacy supporteranno le richieste di rinuncia alla vendita di dati personali.
