---
title: Controllo degli accessi a CJA
description: Scopri i requisiti di controllo degli accessi per la creazione di connessioni, l’aggiunta di set di dati, la creazione di visualizzazioni dati, ecc.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: e5ae592c6765638e26ee5252f458e82af9d24e44
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Controllo degli accessi a CJA

Per accedere ed eseguire attività in Customer Journey Analytics, devi essere aggiunto come Amministratore al **Profilo prodotto Customer Journey Analytics** in [Admin Console](https://adminconsole.adobe.com/enterprise/). Gli amministratori di prodotto dispongono delle seguenti autorizzazioni:

* Creare/aggiornare/eliminare connessioni o visualizzazioni dati
* Aggiornare o eliminare progetti, filtri, metriche calcolate o filtri creati da altri utenti
* Condividere progetti Workspace con tutti gli utenti

## Autorizzazioni Adobe Experience Platform richieste

Per poter creare, aggiornare o eliminare una connessione, non è sufficiente diventare amministratore di prodotto in Customer Journey Analytics. Per creare una connessione a un set di dati di Experience Platform, è necessario disporre anche di autorizzazioni Experience Platform. In particolare, devi far parte di un **profilo di prodotto Experience Platform** che ti fornisca le seguenti autorizzazioni:

* Visualizzare gli schemi
* Gestire gli schemi
* Visualizzare gli spazi dei nomi delle identità
* Visualizzare i set di dati

Per ulteriori informazioni sulle autorizzazioni di Experience Platform, consulta [Controllo degli accessi in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=it).

## Consentire l’accesso a singole metriche o dimensioni

Non puoi concedere o negare autorizzazioni sulle singole metriche o dimensioni in Customer Journey Analytics, come invece puoi fare in Adobe Analytics. Le metriche e le dimensioni possono essere modificate nelle [visualizzazioni dati](/help/data-views/data-views.md) e sono quindi soggette a modifiche in CJA, con conseguenti modifiche retroattive nella generazione di rapporti.

## Accesso utente

Gli utenti di Customer Journey Analytics che non sono amministratori di prodotto non possono vedere le visualizzazioni di dati o le connessioni, ma possono creare filtri, progetti e metriche calcolate.

## Cura dei progetti Workspace

Per ulteriori informazioni su come limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) a livello di progetto, consulta [Cura progetti](/help/analysis-workspace/curate-share/curate.md).



