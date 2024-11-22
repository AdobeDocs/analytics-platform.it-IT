---
title: Architettura dello schema da utilizzare con il Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 6%

---

# Architettura dello schema da utilizzare con il Customer Journey Analytics

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Adobe consiglia di creare uno schema Experience Data Model (XDM) durante l’aggiornamento al Customer Journey Analytics. Uno schema XDM consente uno schema semplificato personalizzato in base alle esigenze della tua organizzazione e alle specifiche applicazioni Platform utilizzate. Quando sono necessarie delle modifiche allo schema, non è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.

Esamina le sezioni seguenti quando inizi a progettare lo schema XDM.

## Evitare le restrizioni di Adobe Analytics nello schema XDM

L’architettura di base del Customer Journey Analytics offre molta più flessibilità rispetto ad Adobe Analytics. La creazione di un nuovo schema XDM è un modo chiave per liberare tale flessibilità. Quando esegui l’aggiornamento a Customer Journey Analytics, evita di trasferire nello schema restrizioni Adobe Analytics non necessarie.

| Architettura dei dati di Adobe Analytics | Architettura dello schema XDM |
|---------|----------|
| Le singole metriche vengono aggiunte all’architettura dei dati di Analytics.<br/>In Adobe Analytics, ad esempio, si dispone di un eVar diverso per ogni evento. | Crea singole metriche nella visualizzazione dati anziché nello schema XDM. Questa operazione offre maggiore flessibilità in se è necessario apportare modifiche in un secondo momento.<br/>In Customer Journey Analytics, ad esempio, è presente un singolo evento nello schema e si utilizzano gli eventi di creazione nella visualizzazione dati. |
| Per creare variabili personalizzate sono necessarie proprietà ed eVar. | B2 |
| A3 | B3 |

## Identificare il team di dati e altre parti interessate in tutta l’organizzazione


## Considera altre applicazioni Adobe Experience Platform utilizzate nell’organizzazione



1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).
