---
description: Spiega come creare una metrica che mostra quali canali di marketing supportano gli ordini.
title: Creare Una Metrica Calcolata Più Complessa
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 0%

---

# Creare una metrica calcolata più complessa

Questo articolo spiega un esempio più complesso di metrica calcolata. Queste metriche calcolate mostrano quali canali di marketing forniscono assistenza per la gestione degli ordini. Questo tipo di metrica calcolata può essere adattata a qualsiasi dimensione o evento di successo.

1. Inizia a generare una metrica calcolata, come descritto in [Metriche di compilazione](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

1. Nel generatore di metriche calcolate, assegnare un nome alla metrica `Assisted Online Orders` o a un nome simile.

1. Seleziona la metrica **[!UICONTROL Ordini in linea]** dai componenti **[!UICONTROL Metriche]** e trascina la metrica nell&#39;area **[!UICONTROL Definizione]**.

   1. Selezionare ![Impostazione](/help/assets/icons/Setting.svg) per la metrica.
   1. Selezionare **[!UICONTROL Usa modello di attribuzione non predefinito]**.
   1. Regola il modello di attribuzione nel **[!UICONTROL modello di attribuzione colonna]**.
      1. Seleziona **[!UICONTROL Personalizzato]** per **[!UICONTROL Modello]**. Imposta **[!UICONTROL Starter]** su `0`, **[!UICONTROL Player]** su `100` e **[!UICONTROL Closer]** su `0`.
      1. Seleziona **[!UICONTROL Visitatore]** per **[!UICONTROL Contenitore]**.
      1. Seleziona **[!UICONTROL 30 giorni]** per **[!UICONTROL Intervallo di lookback]**.

      1. Seleziona **[!UICONTROL Applica]**.

      ![Modello di attribuzione colonna](assets/complex-calculated-metric.png)

1. Seleziona **[!UICONTROL Salva]** per salvare la metrica calcolata.

Per utilizzare la metrica calcolata:

1. In Analysis Workspace, crea una tabella a forma libera con la dimensione **[!UICONTROL Canale di marketing]**, **[!UICONTROL Ordini online]** e la nuova metrica **[!UICONTROL Ordini online con assistenza]**.

   ![Ordini online con assistenza per il canale di marketing](assets/marketing-channel-assists.png)

1. (Facoltativo) Condividi la metrica con altri utenti dell&#39;organizzazione, come descritto in [Condividi metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-sharing.md).

Questo è un modo semplice per capire quali canali di marketing hanno assistito negli ordini. In alternativa, da una tabella a forma libera, puoi selezionare qualsiasi metrica e dal menu di scelta rapida regolare il modello di attribuzione direttamente dalla tabella.
