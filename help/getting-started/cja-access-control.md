---
title: Controllo dell’accesso a CJA
description: Scopri i requisiti di controllo degli accessi per la creazione di connessioni, l’aggiunta di set di dati, la creazione di visualizzazioni dati, ecc.
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# Controllo dell’accesso a CJA

Per creare connessioni, aggiungere set di dati e così via è necessario disporre delle seguenti autorizzazioni in [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Per accedere a Customer Journey Analytics o effettuare una connessione, l’utente deve essere aggiunto come Amministratore al **prodotto Customer Journey Analytics** da [Admin Console](https://adminconsole.adobe.com/enterprise/). Gli amministratori di prodotto dispongono delle seguenti autorizzazioni:
   * Creare/aggiornare/eliminare connessioni o visualizzazioni dati
   * Aggiornare o eliminare progetti, filtri, metriche calcolate o filtri creati da altri utenti
   * Condividere un progetto Workspace con tutti gli utenti
* Per poter creare, aggiornare o eliminare una connessione, non è sufficiente diventare amministratore di prodotto in Customer Journey Analytics. Per creare una connessione a un set di dati di Experience Platform, è necessario disporre anche di autorizzazioni Experience Platform. In particolare, devi far parte di un **profilo di prodotto Experience Platform** che ti fornisca le seguenti autorizzazioni:
   * Visualizzare gli schemi
   * Gestire gli schemi
   * Visualizzare gli spazi dei nomi delle identità
   * Visualizzare i set di dati

Per ulteriori informazioni sulle autorizzazioni di Experience Platform, consulta [Controllo degli accessi in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it).

>[!NOTE]
>
>Non puoi concedere o negare autorizzazioni sulle singole metriche o dimensioni in Customer Journey Analytics, come invece puoi fare in Adobe Analytics. Le metriche e le dimensioni possono essere modificate nelle [visualizzazioni dati](/help/data-views/data-views.md) e sono quindi soggette a modifiche in CJA, con conseguenti modifiche retroattive nella generazione di rapporti.

## Accesso utente

Gli utenti di Customer Journey Analytics che non sono amministratori di prodotto non possono visualizzare le visualizzazioni di dati o le connessioni, ma possono creare filtri, progetti e metriche calcolate.