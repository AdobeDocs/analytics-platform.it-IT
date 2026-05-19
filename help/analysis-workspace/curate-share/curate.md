---
description: Scopri come curare i progetti in Analysis Workspace. La cura limita l’accesso ai componenti prima della condivisione di un progetto.
keywords: Cura di Analysis Workspace
title: Curare progetti
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
TQID: https://experienceleague.adobe.com/FX7KMzyOtrWzD-RUT-iEQZvJslmaes8dej76Jbj79OA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 517
ht-degree: 75%

---

# Curare progetti

La cura ti consente di limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) prima di condividere un progetto. Quando un destinatario apre il progetto, visualizza un set limitato di componenti che hai curato appositamente. La cura è un passaggio facoltativo ma consigliato prima di condividere un progetto.

>[!NOTE]
> I profili di prodotto sono il meccanismo principale per determinare quali componenti può vedere un utente. Sono gestite tramite [CX Enterprise Admin Console](https://experienceleague.adobe.com/it/docs/core-services/interface/administration/admin-tool-experience-cloud). La cura è un segmento secondario.

## Applicare la cura del progetto

1. Seleziona **[!UICONTROL Condividi]** > **[!UICONTROL Cura dati progetto]**.
I componenti utilizzati nel progetto vengono aggiunti automaticamente.
Se un progetto ha più visualizzazioni dati, al suo interno viene visualizzato un target di rilascio curato per ognuna di esse.
1. Per aggiungere altri componenti, trascina i componenti da condividere dal pannello di sinistra alla zona di rilascio **[!UICONTROL Cura componenti]** per la visualizzazione dati (facoltativo).
1. Seleziona **[!UICONTROL Fine]**.

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![La finestra Componenti curati che mostra i componenti in uso nel progetto.](assets/curation-field.png)

Quando un destinatario apre un progetto curato, visualizza solo il set curato di componenti che hai definito:


## Rimuovere la cura del progetto

Per rimuovere la cura del progetto e ripristinare l’intero set di componenti nel pannello a sinistra:

1. Seleziona **[!UICONTROL Condividi]** > **[!UICONTROL Cura dati progetto]**.
1. Seleziona **[!UICONTROL Rimuovi cura]**.
1. Seleziona **[!UICONTROL Fine]**.

## Opzioni di cura del componente

In un progetto curato, al destinatario viene offerta l&#39;opzione **[!UICONTROL Mostra tutti]** i componenti nel pannello a sinistra. [!UICONTROL Mostra tutto] rivela diversi set di componenti, a seconda di:

* Livello di autorizzazione dell’utente (amministratore o non amministratore)
* Ruolo di progetto (proprietario/editor o meno)
* Tipo di cura applicata (a livello di progetto)

| Tipo di cura | L’amministratore può visualizzare | Il proprietario del progetto non amministratore (o il ruolo di modifica) può visualizzare | Il ruolo duplicato non amministratore può visualizzare |
| --- | --- | --- | --- |
| **Componenti *nascosti* da una visualizzazione dati** | Tutti i componenti della visualizzazione dati sono disponibili per il reporting (i componenti nascosti richiedono la selezione di **[!UICONTROL Mostra tutto]**) | Non disponibile per il reporting | Non disponibile per il reporting |
| **Componenti aggiunti o rimossi da una visualizzazione dati** | Solo i componenti aggiunti alla visualizzazione dati (nascosti o non nascosti). Gli amministratori non possono creare rapporti su campi o componenti non definiti nella visualizzazione dati. | Solo i componenti aggiunti alla visualizzazione dati o i componenti di proprietà o condivisi con l’utente. I componenti nascosti non sono disponibili (come la cura delle suite di rapporti virtuali). | Solo i componenti aggiunti alla visualizzazione dati non sono nascosti e sono inclusi nella cura del progetto. |
| **Componenti curati in un progetto** | Tutti i componenti della visualizzazione dati disponibili per il reporting (i componenti nascosti richiedono la selezione di **[!UICONTROL Mostra tutto]**) | Tutti i componenti della visualizzazione dati non nascosti (è necessario fare clic su “mostra tutto”) | Solo i componenti curati e tutti i componenti di proprietà o condivisi con l’utente |
| **Progetto curato utilizzando una visualizzazione dati con componenti nascosti** | Tutti i componenti dati disponibili per il reporting (i componenti nascosti e non curati richiedono la selezione di **[!UICONTROL Mostra tutto]**) | Tutti i componenti di progetto non curati, tutti i componenti di visualizzazione dati non nascosti e tutti i componenti di proprietà o condivisi con l’utente | Solo i componenti curati e tutti i componenti di proprietà o condivisi con l’utente |
