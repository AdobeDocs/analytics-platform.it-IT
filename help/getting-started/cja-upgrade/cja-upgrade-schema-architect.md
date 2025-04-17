---
title: Progettare uno schema da utilizzare con Customer Journey Analytics
description: Scopri il percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 91%

---

# Progettare uno schema da utilizzare con Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Progettare uno schema"
>abstract="Discuti all’interno della tua organizzazione i requisiti di raccolta dei dati e determina come creare uno schema da utilizzare in Adobe Experience Platform. Questo passaggio viene visualizzato perché desideri utilizzare il processo di utilizzo consigliato di uno schema personalizzato per la tua organizzazione. È fondamentale eseguire correttamente questo passaggio, in quanto uno schema su cui allineare tutti i team all’interno della tua organizzazione semplifica notevolmente l’acquisizione dei dati.<br><br>Il tempo stimato per riunire tutte le parti rilevanti della tua organizzazione e allinearle su uno schema unificato è di 1-2 mesi. Questo intervallo di tempo dipende maggiormente dal numero di team necessari da coordinare e dal numero di dimensioni + metriche da allineare."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe consiglia di creare uno schema XDM (Experience Data Model) personalizzato da utilizzare con Web SDK durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics. In alternativa, puoi utilizzare lo schema Adobe Analytics predefinito, che utilizza il gruppo di campi Adobe Analytics ExperienceEvent.

Uno schema XDM personalizzato consente uno schema semplificato adattato alle esigenze dell’organizzazione e alle specifiche applicazioni di Platform che utilizzi. A differenza dello schema Adobe Analytics predefinito che utilizza il gruppo di campi Adobe Analytics ExperienceEvent, quando sono necessarie modifiche a uno schema XDM personalizzato, non devi esaminare minuziosamente migliaia di campi inutilizzati per trovare quello che richiede l’aggiornamento.

Per ulteriori informazioni su queste opzioni di schema, consulta [Scegliere lo schema per Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Esamina le sezioni seguenti quando inizi a progettare lo schema XDM.

## Evitare le restrizioni di Adobe Analytics nello schema XDM

L’architettura di base di Customer Journey Analytics offre molta più flessibilità rispetto ad Adobe Analytics. La creazione di un nuovo schema XDM è un modo chiave per sbloccare tale flessibilità. Quando esegui l’aggiornamento a Customer Journey Analytics, accertati di evitare di trasportare nello schema restrizioni Adobe Analytics non necessarie.

>[!NOTE]
>
>Le seguenti informazioni non sono ancora complete. Sarà completato nel prossimo futuro.

| Architettura dati di Adobe Analytics | Architettura dello schema XDM |
|---------|----------|
| Le singole metriche vengono aggiunte all’architettura dei dati di Analytics.<br/>In Adobe Analytics, ad esempio, si dispone di una eVar diversa per ogni evento. | Crea singole metriche nella visualizzazione dati anziché nello schema XDM. Questa operazione offre maggiore flessibilità in caso tu debba apportare modifiche in un secondo momento.<br/>In Customer Journey Analytics, ad esempio, disponi di un singolo evento nello schema e utilizzi gli eventi di creazione nella visualizzazione dati. |
| Per creare variabili personalizzate sono necessarie Prop ed eVar. |  |

## Identificare il team di dati e altri stakeholder in tutta l’organizzazione

>[!NOTE]
>
>Queste informazioni non sono ancora disponibili. Sarà disponibile a breve.

## Valutare le altre applicazioni Adobe Experience Platform utilizzate nell’organizzazione

>[!NOTE]
>
>Queste informazioni non sono ancora disponibili. Sarà disponibile a breve.
