---
title: Creare una visualizzazione dati in Customer Journey Analytics
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 44%

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

Per creare una visualizzazione dati occorre creare metriche e dimensioni dagli elementi dello schema o utilizzare componenti standard. La maggior parte degli elementi dello schema può essere una dimensione o una metrica, a seconda dei requisiti aziendali. Una volta trascinato un elemento schema in una visualizzazione dati, a destra vengono visualizzate le opzioni con cui è possibile regolare il funzionamento della dimensione o metrica in Customer Journey Analytics.

Per creare una visualizzazione dati:

1. Accedi a [Customer Journey Analytics](https://analytics.adobe.com) e passa alla scheda **[!UICONTROL Data views]**.

1. Seleziona **[!UICONTROL Create new data view]**. In alternativa, puoi selezionare una visualizzazione dati esistente dal relativo elenco per modificarla.

1. Nella scheda [!UICONTROL **Configura**], specificare un nome per la visualizzazione dati e configurarne le impostazioni di base, i componenti e le opzioni di calendario.

   Per informazioni dettagliate su ciascun campo, vedere [Configurare](/help/data-views/create-dataview.md#configure) in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).

   ![Configurare una visualizzazione dati](assets/dataview-configure.png)

1. Selezionare la scheda [!UICONTROL **Componenti**].

   Nella scheda [!UICONTROL **Componenti**] è possibile impostare i componenti di una visualizzazione dati, il che significa che è possibile creare metriche e dimensioni dagli elementi dello schema. Puoi anche utilizzare i componenti standard.

   ![Scheda Componenti](assets/dataview-components.png)

1. Dalla scheda [!UICONTROL **Componenti**], trascina gli elementi dello schema dalla barra a sinistra alla sezione [!UICONTROL **Metriche**] o alla sezione [!UICONTROL **Dimensioni**]. Gli elementi dello schema aggiunti diventano metriche o dimensioni nella visualizzazione dati.

   Per informazioni dettagliate sulle opzioni disponibili quando si aggiungono componenti a una visualizzazione dati, vedere [Componenti](/help/data-views/create-dataview.md#components) in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).

1. Selezionare la scheda [!UICONTROL **Impostazioni**]. Da qui puoi configurare i filtri da applicare all’intera visualizzazione dati e configurare il timeout e le metriche della sessione.

   Per informazioni dettagliate sulle opzioni disponibili durante la configurazione delle impostazioni per una visualizzazione dati, vedere [Impostazioni](/help/data-views/create-dataview.md#settings) in [Creare o modificare una visualizzazione dati](/help/data-views/create-dataview.md).

1. Seleziona **[!UICONTROL Save]** per salvare la configurazione per la visualizzazione dati.

1. Dopo aver specificato tutte le impostazioni desiderate, selezionare **[!UICONTROL Save and finish]**.

{{upgrade-final-step}}
