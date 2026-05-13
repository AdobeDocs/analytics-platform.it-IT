---
title: Creare un campo derivato da un canale di marketing per Customer Journey Analytics
description: Scopri come creare un campo derivato da un canale di marketing per Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
TQID: https://experienceleague.adobe.com/nwxJ3KEss3SlZxpGB-CW4qDW9QpQqXL1kN-VslhuAVE
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 291
ht-degree: 86%

---

# Creare un campo derivato da un canale di marketing per Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Creare un campo derivato dal canale di marketing"
>abstract="I campi derivati vengono creati all’interno di una visualizzazione dati.<br><br>L’utilizzo di una configurazione predefinita per il canale di marketing richiede solo alcuni minuti, mentre la creazione di una configurazione altamente personalizzata potrebbe richiedere alcune ore."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Utilizzando il connettore di origine di Analytics, i dati dei canali di marketing fluiscono in Customer Journey Analytics attraverso tale connettore. Le regole del canale di marketing vengono configurate nella versione tradizionale di Adobe Analytics e alcune regole non sono supportate. Per ulteriori informazioni, consulta [Utilizzare le dimensioni del canale di marketing](/help/use-cases/aa-data/marketing-channels.md).

Per utilizzare i canali di marketing in Customer Journey Analytics quando si utilizza Experience Platform Web SDK, è possibile utilizzare campi derivati in una visualizzazione dati per ricreare gli stessi canali di marketing e le stesse regole di elaborazione per Customer Journey Analytics.

1. In Customer Journey Analytics, seleziona la visualizzazione dati in cui desideri aggiungere canali di marketing.

1. Nella visualizzazione dati, selezionare la scheda **[!UICONTROL Componenti]**.

1. Seleziona **[!UICONTROL Crea campo derivato]** nella barra a sinistra.

1. Nella finestra di dialogo **[!UICONTROL Crea campo derivato]**, seleziona **[!UICONTROL Modelli di funzione]** dal menu a discesa.

   ![Creare modelli di funzione campo derivato](assets/derived-field-create.png)

1. Trascina il modello **[!UICONTROL Canali di marketing]** nell&#39;area di lavoro vuota.

1. Personalizza la logica per ciascun canale di marketing, per assicurarti che corrisponda alla logica utilizzata per identificare ogni canale nell’ambiente Adobe Analytics.

   Puoi modificare i nomi dei canali di output o aggiungere una logica per identificare canali aggiuntivi specifici dell’organizzazione.

1. Nella colonna di destra, specifica un nome e una descrizione per il canale di marketing.

1. Seleziona **[!UICONTROL Salva]**.

   Il nuovo campo derivato viene aggiunto ai Campi derivati > contenitore, come parte dei campi Schema nella barra a sinistra della visualizzazione Dati.

{{upgrade-final-step}}
