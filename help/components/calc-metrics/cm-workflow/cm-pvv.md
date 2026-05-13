---
description: Scopri come creare una semplice metrica calcolata.
title: Creare Una Metrica Calcolata Semplice
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
TQID: https://experienceleague.adobe.com/hbiAmMoSUMm2Ggf5Vkxm484SzYETtgRRZAuaWvlS884
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 0%

---

# Creare una metrica calcolata semplice

Le informazioni seguenti spiegano come creare una semplice metrica *Visualizzazioni pagina per visite*.

1. Inizia a generare una metrica, come descritto in [Metriche di compilazione](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Denomina la metrica `Page Views per Session` o qualcosa di simile.
1. Assegna alla metrica una **[!UICONTROL Descrizione]** intuitiva per mostrare a cosa serve la metrica.
1. Seleziona il **[!UICONTROL Formato]** destro. Per questo esempio, scegli **[!UICONTROL Decimal]**.
1. Decidi quante cifre decimali visualizzare nel rapporto.
1. Nel menu a discesa **[!UICONTROL Mostra tendenza verso l&#39;alto come]**, selezionare ▲ **[!UICONTROL Buono (Verde)]**.
1. Aggiungi un **[!UICONTROL Tag]** per organizzare le metriche.
1. Per questa metrica calcolata, trascina prima **[!UICONTROL Visualizzazioni pagina]** dai componenti **[!UICONTROL Metriche]** nella sezione **[!UICONTROL Definizione]** dell&#39;area di lavoro.
1. Trascina quindi **[!UICONTROL Sessioni]** dai componenti **[!UICONTROL Metriche]** e rilascia la metrica sotto **[!UICONTROL Visualizzazioni pagina]** (attendi che venga visualizzata la linea blu prima di rilasciare la metrica).
1. Selezionare l&#39;operatore ![Dividi](/help/assets/icons/Divide.svg). (Dividi è l&#39;operatore predefinito).
1. È possibile visualizzare una **[!UICONTROL Anteprima]** della metrica durante la creazione della metrica.
1. **[!UICONTROL Compatibilità del prodotto]** indica se la metrica calcolata è compatibile ovunque in Customer Journey Analytics (esclusa la sperimentazione).

   ![Metrica semplice calcolata](assets/simple-calculated-metric.png)
1. Seleziona **[!UICONTROL Salva]**.

   La formula **[!UICONTROL Riepilogo]** viene aggiornata ogni volta che si apporta una modifica alla definizione della metrica.

1. (Facoltativo) Per condividere, approvare, (ri)assegnare tag, rinominare o eliminare una metrica, puoi passare al [Gestore metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-manager.md).

