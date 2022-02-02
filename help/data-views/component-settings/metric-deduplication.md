---
title: Impostazioni dei componenti di deduplicazione delle metriche
description: Conta solo la prima occorrenza di una metrica nei rapporti.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 6%

---

# Impostazioni dei componenti di deduplicazione delle metriche

La deduplicazione delle metriche consente di configurare una metrica in modo da contare solo i valori in modo non ripetitivo.

| Impostazione | Descrizione |
| --- | --- |
| Deduplicazione delle metriche | Una casella di controllo che consente di abilitare la deduplicazione delle metriche. Disabilitata per impostazione predefinita. |
| Ambito di deduplicazione | Consente di determinare la distanza indietro del controllo univoco.<br>**Sessione**: Viene conteggiata solo la prima occorrenza metrica della sessione.<br>**Persona**: Viene conteggiata solo la prima occorrenza metrica nell’intervallo di reporting. |
| ID deduplicazione | Invece di applicare la deduplicazione sulla metrica stessa, puoi applicare la deduplicazione metrica in base a una dimensione. È utile per dimensioni come ID acquisto per applicare la deduplicazione. |
