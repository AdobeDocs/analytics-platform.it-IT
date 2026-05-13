---
title: Creare una visualizzazione dati in Customer Journey Analytics
description: Scopri il percorso consigliato durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
TQID: https://experienceleague.adobe.com/rQL8R2D1JeIabt-iQSyYGY74N5JkP3hTN-x2kj-swXU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 89%

---

# Creare una visualizzazione dati in Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Creare una visualizzazione dati in Customer Journey Analytics"
>abstract="Una visualizzazione dati è un contenitore specifico di Customer Journey Analytics che consente di determinare come interpretare i dati da una connessione.<br><br>Mentre la creazione iniziale della visualizzazione dati richiede alcuni minuti, la configurazione di ogni dimensione e metrica con le impostazioni dei componenti desiderate può richiedere alcuni giorni. La modifica di queste impostazioni viene applicata retroattivamente, in modo che l’organizzazione possa perfezionarle nel tempo."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

Per creare una visualizzazione dati occorre creare metriche e dimensioni dagli elementi dello schema o utilizzare componenti standard. Gli elementi dello schema sono prevalentemente dimensioni o metriche, a seconda dei requisiti aziendali. Una volta trascinato un elemento schema in una visualizzazione dati, a destra vengono visualizzate le opzioni con cui è possibile regolare il funzionamento della dimensione o metrica in Customer Journey Analytics.

Per creare una visualizzazione dati:

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e seleziona **[!UICONTROL Visualizzazioni dati]**, facoltativamente da **[!UICONTROL Gestione dati]**, nel menu superiore.

1. Selezionare **[!UICONTROL Crea nuova visualizzazione dati]**. In alternativa, puoi selezionare una visualizzazione dati esistente dal relativo elenco per modificarla.

1. Nella scheda [!UICONTROL **Configura**], specifica un nome per la visualizzazione dati e configurane le impostazioni di base, i componenti e le opzioni di calendario.

   Per informazioni dettagliate su ciascun campo, consulta [Configurare](/help/data-views/create-dataview.md#configure) in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).

   ![Configurare una visualizzazione dati](assets/dataview-configure.png)

1. Seleziona la scheda [!UICONTROL **Componenti**].

   La scheda [!UICONTROL **Componenti**] è quella in cui puoi impostare i componenti di una visualizzazione dati e quindi creare metriche e dimensioni dagli elementi dello schema. Puoi anche utilizzare i componenti standard.

   ![Scheda Componenti](assets/dataview-components.png)

1. Dalla scheda [!UICONTROL **Componenti**], trascina gli elementi dello schema dalla barra a sinistra alla sezione [!UICONTROL **Metriche**] o alla sezione [!UICONTROL **Dimensioni**]. Gli elementi dello schema aggiunti diventano metriche o dimensioni nella visualizzazione dati.

   Per informazioni dettagliate sulle opzioni disponibili quando si aggiungono componenti a una visualizzazione dati, consulta [Componenti](/help/data-views/create-dataview.md#components) in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).

1. Seleziona la scheda [!UICONTROL **Impostazioni**]. Da qui, puoi configurare i segmenti da applicare all’intera visualizzazione dati e configurare il timeout e le metriche della sessione.

   Per informazioni dettagliate sulle opzioni disponibili durante la configurazione delle impostazioni per una visualizzazione dati, consulta [Impostazioni](/help/data-views/create-dataview.md#settings) in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).

1. Seleziona **[!UICONTROL Salva]** per salvare la configurazione per la visualizzazione dati.

1. Dopo aver specificato tutte le impostazioni desiderate, selezionare **[!UICONTROL Salva e termina]**.

{{upgrade-final-step}}
