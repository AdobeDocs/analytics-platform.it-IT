---
description: La cura ti permette di limitare i componenti prima di condividere un progetto.
keywords: Cura di Analysis Workspace
title: Curare progetti
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '471'
ht-degree: 100%

---

# Curare progetti

La cura ti consente di limitare i componenti (dimensioni, metriche, filtri, intervalli di date) prima di condividere un progetto. Quando un destinatario apre il progetto, vedrà un set limitato di componenti che hai curato per lui. La cura è un passaggio facoltativo ma consigliato prima di condividere un progetto.

>[!NOTE]
> I profili di prodotto sono il meccanismo principale per determinare quali componenti può vedere un utente. Vengono gestiti tramite [Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it). La cura è un filtro secondario.

## Applicare la cura del progetto

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
I componenti utilizzati nel progetto verranno aggiunti automaticamente.
1. Per aggiungere altri componenti, trascina i componenti da condividere dalla barra a sinistra al campo [!UICONTROL Curate Components] (facoltativo).
1. Fai clic su **[!UICONTROL Done]**.

È inoltre possibile applicare la cura dal menu [!UICONTROL Share] facendo clic su **[!UICONTROL Curate and Share]**. Questa opzione cura automaticamente il progetto con i componenti in uso nel progetto. Puoi aggiungere altri componenti seguendo la procedura descritta sopra.

![](assets/curation-field.png)

## Vista del progetto curato

Quando un destinatario apre un progetto curato, vedrà solo il set curato di componenti che hai definito:

![](assets/curate-project.png)

## Rimuovere la cura del progetto

Per rimuovere la cura del progetto e ripristinare l’intero set di componenti nella barra a sinistra:

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Fai clic su **[!UICONTROL Remove Curation]**.
1. Fai clic su **[!UICONTROL Done]**.

## Opzioni di cura del componente

In un progetto curato, al destinatario verrà offerta l’opzione **[!UICONTROL Show All]** per mostrare tutti i componenti nella barra a sinistra. [!UICONTROL Show All] mostra diversi set di componenti in base a:

* Livello di autorizzazione dell’utente (amministratore o non amministratore)
* Ruolo di progetto (proprietario/editor o meno)
* Tipo di cura applicata (a livello di progetto)

| Tipo di cura | L’amministratore può visualizzare | Il proprietario del progetto non amministratore (o il ruolo di modifica) può visualizzare | Il ruolo duplicato non amministratore può visualizzare |
| --- | --- | --- | --- |
| **Componenti “nascosti” da una visualizzazione dati** | Tutti i componenti della visualizzazione dati disponibili per il reporting (i componenti nascosti richiedono di fare clic su “Mostra tutto”) | Non disponibile per il reporting | Non disponibile per il reporting |
| **Componenti aggiunti o rimossi da una visualizzazione dati** | Solo i componenti aggiunti alla visualizzazione dati (nascosti o non nascosti). Gli amministratori non possono creare rapporti su campi o componenti non definiti dalla visualizzazione dati. | Solo i componenti aggiunti alla visualizzazione dati o i componenti di proprietà o condivisi con l’utente. I componenti nascosti non sono disponibili (come la cura delle VRS). | Solo i componenti aggiunti al DV non sono nascosti e sono stati inclusi nella cura del progetto. |
| **Componenti curati in un progetto** | Tutti i componenti della visualizzazione dati disponibili per il reporting (i componenti nascosti richiedono di fare clic su “Mostra tutto”) | Tutti i componenti della visualizzazione dati non nascosti (è necessario fare clic su “mostra tutto”) | Solo i componenti curati e tutti i componenti di proprietà o condivisi con l’utente |
| **Progetto curato utilizzando una visualizzazione dati con componenti nascosti** | Tutti i componenti dati disponibili per il reporting (i componenti nascosti e non curati richiedono di fare clic su “Mostra tutto”) | Tutti i componenti di progetto non curati, tutti i componenti di visualizzazione dati non nascosti e tutti i componenti di proprietà o condivisi con l’utente | Solo i componenti curati e tutti i componenti di proprietà o condivisi con l’utente |
