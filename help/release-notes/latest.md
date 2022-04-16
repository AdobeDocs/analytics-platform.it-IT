---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 56f62d8af96e64a6867e38a9701219bcefc62a6a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 15%

---

# Note sulla versione del Customer Journey Analytics corrente (CJA) (aprile 2022)

>[!NOTE]
>
>Questa pagina contiene informazioni precedenti al rilascio soggette a modifiche.

**Ultimo aggiornamento**: 13 aprile 2022

## Funzioni chiave

| Funzione | Descrizione | [Data definita](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Dimension sottostringhe | Fornisce più metodi per estrarre la parte desiderata di una stringa da utilizzare come elementi dimensionali. Questa funzione consente inoltre di trattare una dimensione stringa come una matrice se la stringa contiene valori delimitati. [Ulteriori informazioni](../data-views/component-settings/substring.md) | 20 aprile 2022 |
| Preparazione dei dati per il connettore origine di Analytics | La [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) è ora integrato con [Preparazione dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) funzionalità fornite da Adobe Experience Platform. I clienti Adobe Real-time Customer Data Platform (RTCDP), CJA e Adobe Journey Optimizer (AJO) ora possono estendere il gruppo di campi di Analytics con gruppi di campi aggiuntivi. Possono inoltre sfruttare più di 100 operatori di preparazione dati per arricchire i dati di Analytics durante l’acquisizione in Adobe Experience Platform (AEP). I clienti RTCDP possono ora abilitare più suite di rapporti abilitate per la preparazione dei dati per il profilo.<p>I clienti CJA che acquisiscono più suite di rapporti tramite il connettore origine di Analytics ora dispongono di un mezzo per decomporre le differenze di colonna tra le suite di rapporti. Ad esempio, se &quot;Termine di ricerca&quot; è memorizzato in `eVar1` in una suite di rapporti e `eVar2` in un’altra suite di rapporti, utilizzando Preparazione dati puoi estendere il gruppo di campi di Analytics con una nuova colonna che unisce i valori dei due eVar. | 25 aprile 2022 |

{style=“table-layout:auto”}

>[!MORELIKETHIS]
>[Customer Journey Analytics - Aggiornamenti della documentazione](/help/release-notes/doc-changes.md)
