---
title: Progettare e uno schema da utilizzare con Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 26%

---

# Progettare e uno schema da utilizzare con Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Progettare uno schema"
>abstract="Discuti all’interno della tua organizzazione i requisiti di raccolta dei dati e determina come creare uno schema da utilizzare in Adobe Experience Platform. Questo passaggio viene visualizzato perché desideri utilizzare il processo di utilizzo consigliato di uno schema personalizzato per la tua organizzazione. È fondamentale eseguire correttamente questo passaggio, in quanto uno schema su cui allineare tutti i team all’interno della tua organizzazione semplifica notevolmente l’acquisizione dei dati.<br><br>Il tempo stimato per riunire tutte le parti rilevanti della tua organizzazione e allinearle su uno schema unificato è di 1-2 mesi. Questo intervallo di tempo dipende maggiormente dal numero di team necessari da coordinare e dal numero di dimensioni + metriche da allineare."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe consiglia di creare uno schema XDM (Experience Data Model) personalizzato da utilizzare con il Web SDK durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics. In alternativa, puoi utilizzare lo schema Adobe Analytics predefinito, che utilizza il gruppo di campi Adobe Analytics ExperienceEvent.

Uno schema XDM personalizzato consente uno schema semplificato personalizzato in base alle esigenze della tua organizzazione e alle specifiche applicazioni Platform utilizzate. A differenza dello schema Adobe Analytics predefinito che utilizza il gruppo di campi Adobe Analytics ExperienceEvent, quando sono necessarie modifiche a uno schema XDM personalizzato, non è necessario esaminare migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.

Per ulteriori informazioni su queste opzioni di schema, vedere [Scegliere lo schema per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Esamina le sezioni seguenti quando inizi a progettare lo schema XDM.

## Evitare le restrizioni di Adobe Analytics nello schema XDM

L’architettura di base di Customer Journey Analytics offre molta più flessibilità rispetto ad Adobe Analytics. La creazione di un nuovo schema XDM è un modo chiave per liberare tale flessibilità. Quando esegui l’aggiornamento a Customer Journey Analytics, accertati di evitare di portare avanti nello schema restrizioni Adobe Analytics non necessarie.

>[!NOTE]
>
>Le seguenti informazioni non sono ancora complete. Sarà completato nel prossimo futuro.

| Architettura dei dati di Adobe Analytics | Architettura dello schema XDM |
|---------|----------|
| Le singole metriche vengono aggiunte all’architettura dei dati di Analytics.<br/>In Adobe Analytics, ad esempio, si dispone di un eVar diverso per ogni evento. | Crea singole metriche nella visualizzazione dati anziché nello schema XDM. Questa operazione offre maggiore flessibilità in se è necessario apportare modifiche in un secondo momento.<br/>In Customer Journey Analytics, ad esempio, si dispone di un singolo evento nello schema e si utilizzano gli eventi di creazione nella visualizzazione dati. |
| Per creare variabili personalizzate sono necessarie proprietà ed eVar. |  |

## Identificare il team di dati e altre parti interessate in tutta l’organizzazione

>[!NOTE]
>
>Queste informazioni non sono ancora disponibili. Sarà disponibile a breve.

## Considera altre applicazioni Adobe Experience Platform utilizzate nell’organizzazione

>[!NOTE]
>
>Queste informazioni non sono ancora disponibili. Sarà disponibile a breve.
