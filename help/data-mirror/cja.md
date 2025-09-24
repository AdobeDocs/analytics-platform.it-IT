---
title: Configurare Customer Journey Analytics
description: Come configurare connessioni Customer Journey Analytics, visualizzazioni dati e progetti per Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: b585187f112c2081a8e51bd84d9f95e75ceebdc3
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 2%

---

# Configurare Customer Journey Analytics

{{release-limited-testing}}

Per utilizzare la funzione Data Mirror di Experience Platform per Customer Journey Analytics, è necessario creare o aggiornare connessioni, visualizzazioni dati e progetti Workspace per utilizzare i dati basati su modelli.

## Connessioni

Nella connessione, aggiungi i set di dati basati su modello che rappresentano i dati delle soluzioni native di data warehouse. Questi set di dati hanno il tipo di set di dati Modello.

Quando aggiungi un set di dati basato su modello che contiene dati con mirroring da una soluzione nativa di data warehouse, tali dati sono in genere dati evento. Assicurati di selezionare le impostazioni corrette per il set di dati. Ad esempio, seleziona il tipo di set di dati, il campo per l’identità e il campo per la marca temporale corretti.


## Visualizzazioni dati

Definisci i campi dello schema basato su modello come componenti (metriche e dimensioni) nella visualizzazione dati. I campi con mirroring dei dati sono disponibili nella sottocartella **[!UICONTROL Adhoc & Model-based fields]** della cartella **[!UICONTROL Event datasets]**. Utilizza funzionalità, come [campi derivati](/help/data-views/derived-fields/derived-fields.md) o [impostazioni componente](/help/data-views/component-settings/overview.md), per modificare i componenti basati su campi basati su modelli.


## Progetti Workspace

Configura progetti Workspace che utilizzano metriche e dimensioni dai dati basati su modelli. Componenti che si basano in ultima analisi sui dati nella soluzione nativa del data warehouse. e vengono aggiornati in base alla funzionalità di mirroring dei dati configurata.

>[!MORELIKETHIS]
>
>[Guida rapida di Data Mirror: simulare e utilizzare dati basati su modelli](model-based.md)
>
