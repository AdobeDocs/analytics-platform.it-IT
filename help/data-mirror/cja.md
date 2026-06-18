---
title: Configurare Customer Journey Analytics
description: Come configurare connessioni Customer Journey Analytics, visualizzazioni dati e progetti per Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
TQID: https://experienceleague.adobe.com/1LArX1cyRWpEY8O9xMwTcgwc0aUTjMrniFiDXtpkCNY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 2%

---

# Configurare Customer Journey Analytics

{{relational-model-based}}

Per utilizzare la funzione Data Mirror di Experience Platform per Customer Journey Analytics, è necessario creare o aggiornare connessioni, visualizzazioni dati e progetti Workspace per utilizzare i dati relazionali.

## Connessioni

Nella connessione, aggiungi i set di dati relazionali che rappresentano i dati delle soluzioni native di data warehouse. Questi set di dati hanno il tipo Relazionale.

Quando aggiungi un set di dati relazionali contenente dati con mirroring da una soluzione nativa di data warehouse, tali dati sono in genere dati evento. Assicurati di selezionare le impostazioni corrette per il set di dati. Ad esempio, seleziona il tipo di set di dati, il campo per l’identità e il campo per la marca temporale corretti.


## Visualizzazioni dati

Definisci i campi dello schema relazionale come componenti (metriche e dimensioni) nella visualizzazione dati. I campi con mirroring dei dati sono disponibili nella sottocartella **[!UICONTROL Campi ad hoc e relazionali]** della cartella **[!UICONTROL Set di dati evento]**. Utilizza funzionalità, come [campi derivati](/help/data-views/derived-fields/derived-fields.md) o [impostazioni componente](/help/data-views/component-settings/overview.md), per modificare i componenti basati su campi relazionali.


## Progetti Workspace

Imposta i progetti Workspace che utilizzano metriche e dimensioni dai dati relazionali. Componenti che si basano in ultima analisi sui dati nella soluzione nativa del data warehouse. e vengono aggiornati in base alla funzionalità di mirroring dei dati configurata.

>[!MORELIKETHIS]
>
>[Guida rapida di Data Mirror: mirroring e utilizzo dei dati relazionali](relational.md)
>
