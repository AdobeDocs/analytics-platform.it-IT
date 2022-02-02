---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 70%

---

# Note sulla versione del Customer Journey Analytics corrente

## Aggiornamenti chiave

|[!UICONTROL Persistence] opzioni per il binding di dimensioni e metriche di binding| Durante la creazione o la modifica di una visualizzazione dati, è possibile eseguire un binding della persistenza di una dimensione con un’altra dimensione o metrica. Questo concetto è noto come _merchandising_ in Reports &amp; Analytics ed è ora supportato in CJA. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#binding-dimension)| 19 gennaio 2022 |

## Altri aggiornamenti

| Funzione | Descrizione | Data definita |
| ----------- | ---------- | ----- |
| [!UICONTROL First Known] e [!UICONTROL Last Known] modelli di allocazione | Questi due nuovi modelli di allocazione considerano il primo o l’ultimo valore osservato come dimensione all’interno di un ambito di persistenza specificato (sessione, persona o periodo di tempo personalizzato con look-back). Quindi applicano il modello di allocazione a tutti gli eventi all’interno dell’ambito specificato. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=it#allocation-settings) | 19 gennaio 2022 |
| [!UICONTROL PersonID] e [!UICONTROL PersonID namespace] come dimensioni | Espone `personID` (o `customerID`, o qualsiasi ID utilizzato per unire i set di dati in una connessione) come dimensione nelle visualizzazioni dati. Questo miglioramento consente di includere più facilmente `personID` come dimensione nella visualizzazione dati estraendola dalla connessione. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=it#optional-standard-components) | 19 gennaio 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Aggiornamenti alla documentazione del Customer Journey Analytics](/help/doc-changes.md)
