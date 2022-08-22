---
title: Impostazioni dei componenti di deduplicazione delle metriche
description: Conteggia solo la prima occorrenza di una metrica nei rapporti.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: ht
source-wordcount: '108'
ht-degree: 100%

---

# Impostazioni dei componenti di deduplicazione delle metriche

La deduplicazione delle metriche consente di configurare una metrica in modo da conteggiare unicamente i valori in modo non ripetitivo.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Metric deduplication] | Una casella di controllo che consente di abilitare la deduplicazione delle metriche. Disabilitata per impostazione predefinita. |
| [!UICONTROL Deduplication scope] | Consente di determinare quanto indietro nel tempo deve effettuarsi la verifica univoca.<br>**Sessione**: viene conteggiata solo la prima occorrenza metrica della sessione.<br>**Persona**: viene conteggiata solo la prima occorrenza metrica nell’intervallo di reporting. |
| [!UICONTROL Deduplication ID] | Invece di applicare la deduplicazione sulla metrica stessa, puoi applicare la deduplicazione metrica in base a una dimensione. Impostazione molto utile per dimensioni quali l&#39;ID acquisto. |

{style=&quot;table-layout:auto&quot;}
