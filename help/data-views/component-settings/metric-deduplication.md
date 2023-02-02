---
title: Impostazioni dei componenti di deduplicazione delle metriche
description: Conteggia solo la prima occorrenza di una metrica nei rapporti.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e2ebda486eae7740351370f48bdf104c90494ae3
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 73%

---

# Impostazioni dei componenti di deduplicazione delle metriche

La deduplicazione delle metriche consente di configurare una metrica in modo da conteggiare unicamente i valori in modo non ripetitivo.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Metric deduplication] | Una casella di controllo che consente di abilitare la deduplicazione delle metriche. Disabilitata per impostazione predefinita. |
| [!UICONTROL Deduplication scope] | Consente di determinare quanto indietro nel tempo deve effettuarsi la verifica univoca.<br>**Sessione**: viene conteggiata solo la prima occorrenza metrica della sessione.<br>**Persona**: viene conteggiata solo la prima occorrenza metrica nell’intervallo di reporting. |
| [!UICONTROL Deduplication ID] | Invece di applicare la deduplicazione sulla metrica stessa, puoi applicare la deduplicazione metrica in base a una dimensione. Impostazione molto utile per dimensioni quali l&#39;ID acquisto. |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>   Deduplication a un _persona_ l&#39;ambito viene valutato in base ai mesi completi nell&#39;ora UTC. Un intervallo di reporting a mese parziale potrebbe non visualizzare tutte le prime o ultime istanze, se alcune si sono verificate entro il mese completo ma al di fuori delle date di reporting.
