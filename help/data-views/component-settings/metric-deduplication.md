---
title: Impostazioni dei componenti di deduplicazione delle metriche
description: Conteggia solo la prima occorrenza di una metrica nei rapporti.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 9a31b1dcba4015f00dd7ae8c43b317e1c5679a2c
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# Impostazioni dei componenti di deduplicazione delle metriche

La deduplicazione delle metriche consente di configurare una metrica in modo da conteggiare unicamente i valori in modo non ripetitivo.

| Impostazione | Descrizione |
| --- | --- |
| [!UICONTROL Metric deduplication] | Una casella di controllo che consente di abilitare la deduplicazione delle metriche. Disabilitata per impostazione predefinita. |
| [!UICONTROL Deduplication scope] | Consente di determinare quanto indietro nel tempo deve effettuarsi la verifica univoca.<br>**Sessione**: viene conteggiata solo la prima occorrenza metrica della sessione.<br>**Persona**: viene conteggiata solo la prima occorrenza metrica nell’intervallo di reporting. |
| [!UICONTROL Deduplication ID] | Invece di applicare la deduplicazione sulla metrica stessa, puoi applicare la deduplicazione metrica in base a una dimensione. Impostazione molto utile per dimensioni quali l&#39;ID acquisto. |
| [!UICONTROL Value to keep] | <ul><li>**Mantieni prima istanza**: utilizza questa opzione nelle situazioni in cui l’istanza iniziale della metrica è quella valida. Ad esempio, per una conferma di acquisto: se l’utente ricarica inavvertitamente la pagina e questo genera un’altra istanza di conferma dell’acquisto, l’evento valido resta comunque quello iniziale.</li><li>**Mantieni ultima istanza**: utilizza questa opzione in situazioni in cui conviene raccogliere l’ultima istanza. Esempio: l’utente aggiorna il suo profilo online. In questo caso sarà necessario contare solo uno di tali aggiornamenti per sessione. Tuttavia, l’utente può aggiornare il profilo più volte durante una sessione. Se si mantenesse la prima istanza, alcune attività potrebbero non essere associate all’evento. In casi simili, conviene mantenere l’ultima istanza.</li></ul> |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>La deduplica a livello di una _persona_ viene valutata in base a mesi completi nel fuso orario UTC. Se l’intervallo di reporting non comprende mesi completi, potrebbero essere escluse le prime o ultime istanze che si sono verificate entro il mese completo, ma oltre le date di reporting.
