---
title: Creazione di uno schema per il Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Creare set di dati di ricerca per classificare i dati nel Customer Journey Analytics

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), oppure puoi seguire i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Analogamente ai dati delle classificazioni in Adobe Analytics, i set di dati di ricerca sono il metodo per classificare i dati in Customer Journey Analytics.

Quando si utilizza il connettore di origine di Analytics, alcuni set di dati di ricerca standard vengono applicati automaticamente al momento del rapporto. Per ulteriori informazioni, consulta [Aggiungere ricerche standard ai set di dati](/help/connections/standard-lookups.md).

Per classificare i dati con una nuova implementazione di Experience Platform Web SDK, è necessario creare un set di dati di ricerca per ogni dimensione che contiene i dati da classificare.

Per creare set di dati di ricerca da utilizzare nel Customer Journey Analytics:

1. In AEP, crea un nuovo schema. Questo è un nuovo schema specifico per i set di dati di ricerca. Non è possibile utilizzare uno schema esistente.

1. Devi creare una nuova classe di schema per le ricerche.

1. Crea un set di dati di ricerca da questo.

1. Continua seguendo i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i [passaggi di aggiornamento generati dinamicamente](https://gigazelle.github.io/cja-ttv/).
