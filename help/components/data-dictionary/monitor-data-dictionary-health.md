---
description: Gli amministratori sono responsabili del monitoraggio dell’integrità del dizionario dati. Ciò include se i componenti raccolgono dati, sono approvati, contengono descrizioni e sono privi di duplicati.
title: Monitorare l’integrità del dizionario dati
feature: Components
role: Admin
source-git-commit: 5929d56bef8f756967926482f80014db0d43d3e3
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Monitorare l’integrità del dizionario dati

{{release-limited-testing}}

Gli amministratori di Customer Journey Analytics sono responsabili della gestione di un dizionario dati integro.

## Caratteristiche di un dizionario dati integro

Un dizionario dati integro è un dizionario in cui tutti i componenti:

* È in uso e sta raccogliendo dati

* Contengono descrizioni utili che consentono agli utenti di utilizzarle al meglio

* Sono privi di duplicati non necessari

* Sono approvate dall’amministratore

## Verificare lo stato del dizionario dati

Per identificare i problemi di integrità nel dizionario dati:

1. Apri un progetto Analysis Workspace.

1. Seleziona l’icona Dizionario dati a sinistra di Analysis Workspace. (I modi alternativi per accedere al dizionario dati sono descritti in &quot;Accedere al dizionario dati&quot; in [Panoramica del dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md).)

   Viene visualizzata la finestra Dizionario dati.

   ![Visualizzazione amministrazione dizionario dati](assets/data-dictionary-admin.png)

1. Assicurati che nel menu a discesa sia selezionata la suite di rapporti corretta.

1. Il giorno [!UICONTROL **Integrità del dizionario**] , seleziona [!UICONTROL **Visualizza**] accanto a una delle seguenti opzioni:

   * [!UICONTROL **mancano descrizioni dei componenti**]

   * [!UICONTROL **i componenti hanno duplicati**]

   * [!UICONTROL **ai componenti non sono collegati dati**]

   A seconda di ciò che selezioni, il filtro appropriato viene applicato al dizionario dati e vengono visualizzati solo i componenti rilevanti.

1. Modifica uno dei componenti per migliorare lo stato del dizionario dati. Per informazioni su come modificare un componente nel dizionario dati, vedi [Modificare le voci dei componenti nel dizionario dati](/help/components/data-dictionary/edit-entries-data-dictionary.md).