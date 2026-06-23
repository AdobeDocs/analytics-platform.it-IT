---
description: Gli amministratori sono responsabili del monitoraggio dell’integrità del dizionario dei dati. Ciò include verificare se i componenti raccolgono dati, sono approvati, contengono descrizioni e sono privi di duplicati.
title: Monitorare l’integrità del dizionario dei dati
feature: Components
role: Admin
exl-id: 8bc89ac7-078d-469d-8627-3905823d4100
TQID: https://experienceleague.adobe.com/RKh01bcmVkoZ2wkHDvBM-oX9rRagVaOqK4fn2A-IpaI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: b7493ad9283b5830c36b8e3ac942bf9295b693f8
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 88%

---

# Monitorare l’integrità del dizionario dei dati {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="Dizionario dei dati"
>abstract="Quando questa opzione è selezionata, il componente primario viene condiviso con tutti coloro che hanno accesso ai componenti duplicati (sia i proprietari che gli utenti con cui i componenti sono stati condivisi). Tali utenti potranno quindi selezionare il componente principale dall’elenco dei componenti per i progetti futuri. Tuttavia, non potranno modificare il componente, anche se erano i proprietari di un componente duplicato che è stato consolidato. <br/>Questa opzione è disponibile solo quando il componente primario è un segmento, una metrica calcolata o un intervallo di date. Le metriche e le dimensioni sono sempre disponibili per tutti gli utenti."
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_share_primary"
>title="Condividi componente primario"
>abstract="Quando questa opzione è selezionata, il componente primario viene condiviso con tutti coloro che hanno accesso ai componenti duplicati (sia i proprietari che gli utenti con cui i componenti sono stati condivisi). Tali utenti potranno quindi selezionare il componente principale dall’elenco dei componenti per i progetti futuri. Tuttavia, non potranno modificare il componente, anche se erano i proprietari di un componente duplicato che è stato consolidato. <br/>Questa opzione è disponibile solo quando il componente primario è un segmento, una metrica calcolata o un intervallo di date. Le metriche e le dimensioni sono sempre disponibili per tutti gli utenti."
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_delete_duplicates"
>title="Elimina duplicati sostituiti"
>abstract="Quando questa opzione è selezionata, i duplicati consolidati non saranno più disponibili per l’uso. Deseleziona questa opzione se desideri mantenere i duplicati ancora disponibili."

<!-- markdownlint-enable MD034 -->

Gli amministratori di Customer Journey Analytics sono responsabili della gestione di un dizionario dati integro.

## Caratteristiche di un dizionario dei dati integro

Un dizionario dei dati integro è un dizionario in cui tutti i componenti:

* Sono in uso e stanno raccogliendo dati

* Contengono descrizioni utili che consentono agli utenti di utilizzarle al meglio

* Sono privi di duplicati non necessari

* Sono approvati dall’amministratore

## Verificare l’integrità del dizionario dei dati

Per identificare i problemi di integrità nel dizionario dei dati:

1. Apri un progetto di Analysis Workspace.

1. Seleziona l’icona Dizionario dei dati a sinistra di Analysis Workspace. I modi alternativi per accedere al dizionario dati sono descritti in “Accedere al dizionario dei dati” in [Panoramica del dizionario dei dati](/help/components/data-dictionary/data-dictionary-overview.md).

   Viene visualizzata la finestra Dizionario dei dati.

   ![Visualizzazione dell&#39;amministratore del dizionario dati che mostra l&#39;integrità del dizionario](assets/data-dictionary-admin.png)

1. Verifica che nel menu a discesa sia selezionata la visualizzazione dati corretta.

1. Nella scheda [!UICONTROL **Integrità del dizionario**], seleziona [!UICONTROL **Visualizza**] accanto a una delle seguenti opzioni:

   * [!UICONTROL **mancano descrizioni dei componenti**]

   * [!UICONTROL **i componenti hanno duplicati**]

   * [!UICONTROL **ai componenti non sono collegati dati**]

   A seconda di ciò che selezioni, il segmento appropriato viene applicato al dizionario dati e vengono visualizzati solo i componenti rilevanti.

1. Modifica i componenti per migliorare lo stato del dizionario dei dati. Per informazioni su come modificare un componente nel dizionario dei dati, vedi [Modificare le voci dei componenti nel dizionario dei dati](/help/components/data-dictionary/edit-entries-data-dictionary.md).
