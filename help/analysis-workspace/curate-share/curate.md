---
description: Scopri come curare i progetti in Analysis Workspace. La cura limita l’accesso ai componenti prima della condivisione di un progetto.
keywords: Cura di Analysis Workspace
title: Curare progetti
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: ht
source-wordcount: '476'
ht-degree: 100%

---

# Curare progetti

La cura ti consente di limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) prima di condividere un progetto. Quando un destinatario apre il progetto, visualizza un set limitato di componenti che hai curato appositamente. La cura è un passaggio facoltativo ma consigliato prima di condividere un progetto.

>[!NOTE]
> I profili di prodotto sono il meccanismo principale per determinare quali componenti può vedere un utente. Vengono gestiti tramite [Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/it/docs/core-services/interface/administration/admin-tool-experience-cloud). La cura è un segmento secondario.

## Applicare la cura del progetto

1. Seleziona **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
I componenti utilizzati nel progetto vengono aggiunti automaticamente.
Se un progetto ha più visualizzazioni dati, al suo interno viene visualizzato un target di rilascio curato per ognuna di esse.
1. (Facoltativo) Per aggiungere altri componenti, trascina quelli che desideri condividere dal pannello a sinistra all’area di rilascio **[!UICONTROL Curate components]** per la visualizzazione dati.
1. Seleziona **[!UICONTROL Done]**.

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![La finestra Componenti curati che mostra i componenti in uso nel progetto.](assets/curation-field.png)

Quando un destinatario apre un progetto curato, visualizza solo il set curato di componenti che hai definito:


## Rimuovere la cura del progetto

Per rimuovere la cura del progetto e ripristinare l’intero set di componenti nel pannello a sinistra:

1. Seleziona **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Seleziona **[!UICONTROL Remove Curation]** (Aggiungi set di dati).
1. Seleziona **[!UICONTROL Done]** (Salva).

## Opzioni di cura del componente

In un progetto curato, al destinatario viene offerta l’opzione **[!UICONTROL Show All]** i componenti nel pannello a sinistra. [!UICONTROL Show All] mostra diversi set di componenti in base a:

* Livello di autorizzazione dell’utente (amministratore o non amministratore)
* Ruolo di progetto (proprietario/editor o meno)
* Tipo di cura applicata (a livello di progetto)

| Tipo di cura | L’amministratore può visualizzare | Il proprietario del progetto non amministratore (o il ruolo di modifica) può visualizzare | Il ruolo duplicato non amministratore può visualizzare |
| --- | --- | --- | --- |
| **Componenti *nascosti* da una visualizzazione dati** | Tutti i componenti della visualizzazione dati disponibili per il reporting (per i componenti nascosti è necessario selezionare **[!UICONTROL Show all]**) | Non disponibile per il reporting | Non disponibile per il reporting |
| **Componenti aggiunti o rimossi da una visualizzazione dati** | Solo i componenti aggiunti alla visualizzazione dati (nascosti o non nascosti). Gli amministratori non possono creare rapporti su campi o componenti non definiti nella visualizzazione dati. | Solo i componenti aggiunti alla visualizzazione dati o i componenti di proprietà o condivisi con l’utente. I componenti nascosti non sono disponibili (come la cura delle suite di rapporti virtuali). | Solo i componenti aggiunti alla visualizzazione dati non sono nascosti e sono inclusi nella cura del progetto. |
| **Componenti curati in un progetto** | Tutti i componenti della visualizzazione dati disponibili per il reporting (per i componenti nascosti è necessario selezionare **[!UICONTROL Show all]**) | Tutti i componenti della visualizzazione dati non nascosti (è necessario fare clic su “mostra tutto”) | Solo i componenti curati e tutti i componenti di proprietà o condivisi con l’utente |
| **Progetto curato utilizzando una visualizzazione dati con componenti nascosti** | Tutti i componenti dati disponibili per il reporting (per i componenti nascosti e non curati è necessario selezionare **[!UICONTROL Show all]**) | Tutti i componenti di progetto non curati, tutti i componenti di visualizzazione dati non nascosti e tutti i componenti di proprietà o condivisi con l’utente | Solo i componenti curati e tutti i componenti di proprietà o condivisi con l’utente |
