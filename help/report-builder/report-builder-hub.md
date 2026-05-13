---
title: Hub Report Builder
description: Scopri l’hub Report Builder.
role: User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/lXd4Z4gvGpgmdUbmtV-e0rkmt4r4NvlBHX5Np-HWEFY
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 25%

---

# Hub Report Builder

L&#39;hub Report Builder è il riquadro destro visualizzato nella cartella di lavoro di Excel quando si seleziona ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** dalla barra multifunzione di Excel.

Utilizza l’hub Report Builder per creare, aggiornare, eliminare e gestire i blocchi di dati.

L&#39;hub Report Builder contiene i pulsanti ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**, ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** e ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]**, il pannello **[!UICONTROL Commands]** e il pannello **[!UICONTROL Quick edit]**.

![Hub Report Builder](assets/hub51.png){zoomable="yes"}


Seleziona

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Crea]** per [creare nuovi blocchi di dati](create-a-data-block.md).
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** per [gestire blocchi di dati esistenti](manage-reportbuilder.md).
* ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Pianifica]** per [gestire le pianificazioni per inviare la cartella di lavoro tramite e-mail](schedule-reportbuilder.md).

## Pannello Comandi

Utilizza il pannello **[!UICONTROL Comandi]** per accedere a comandi compatibili con le celle selezionate o con un&#39;azione precedente.

| Comandi | Quando è disponibile | Finalità |
|------|------------------|--------|
| ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Modifica blocco dati]** | La cella o l’intervallo di celle selezionato fa parte di un solo blocco di dati. | Utilizza per modificare un blocco di dati. |
| ![Aggiorna](/help/assets/icons/Refresh.svg) **[!UICONTROL Aggiorna blocco dati]** | La selezione contiene almeno un blocco di dati. Il comando aggiorna solo i blocchi di dati nella selezione. | Utilizza per aggiornare uno o più blocchi di dati. |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Aggiorna tutti i blocchi di dati]** | La cartella di lavoro contiene uno o più blocchi di dati. | Utilizzare per aggiornare tutti i blocchi di dati nella cartella di lavoro |
| ![Invia](/help/assets/icons/Send.svg) **[!UICONTROL Invia cartella di lavoro]** | La cartella di lavoro contiene uno o più blocchi di dati. | Utilizza per [inviare la cartella di lavoro come file tramite e-mail](schedule-reportbuilder.md). |
| ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copia blocco di dati]** | La cella o l’intervallo di celle selezionato fa parte di uno o più blocchi di dati. | Utilizza per copiare un blocco di dati. |
| ![Taglia](/help/assets/icons/Cut.svg) **[!UICONTROL Taglia blocco dati]** | La cella o l’intervallo di celle selezionato fa parte di uno o più blocchi di dati. | Utilizza per tagliare un blocco di dati. |
| ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Elimina blocco di dati]** | La cella o l’intervallo di celle selezionato fa parte di un solo blocco di dati. | Utilizzare per eliminare un blocco di dati |

## Pannello Quick edit (Modifica rapida)

Quando selezioni uno o più blocchi di dati in un foglio di calcolo, Report Builder visualizza il pannello **[!UICONTROL Modifica rapida]**. Puoi utilizzare il pannello **[!UICONTROL Modifica rapida]** per modificare i parametri in uno o più blocchi di dati contemporaneamente.

Le modifiche apportate quando si utilizzano le sezioni **[!UICONTROL Modifica rapida]** vengono applicate a tutti i blocchi di dati selezionati.

### Visualizzazioni dati

I blocchi di dati estraggono i dati da una visualizzazione dati selezionata. Se più blocchi di dati sono selezionati in un foglio di lavoro e non estraggono dati dalla stessa visualizzazione dati, il collegamento **Visualizzazioni dati** visualizza **[!UICONTROL _Multiple_]**.

Quando modifichi la visualizzazione dati, tutti i blocchi di dati nella selezione adottano la nuova visualizzazione dati. I componenti nel blocco di dati vengono associati alla nuova visualizzazione dati in base all’ID. Se un componente non viene trovato in un blocco di dati, il componente viene rimosso e sostituito con **[!UICONTROL Valore non valido]** oppure viene visualizzato un ![AlertRed](/help/assets/icons/AlertRed.svg) per il componente specifico.

Per modificare la visualizzazione dati, selezionare una nuova visualizzazione dati dal menu a discesa **[!UICONTROL Visualizzazione dati]**.


### Intervallo date

**Intervallo date** mostra l’intervallo di date per i blocchi di dati selezionati. Se sono selezionati più blocchi di dati con più intervalli di date, il collegamento **[!UICONTROL Intervallo di date]** visualizza **[!UICONTROL _Multiplo_]**.

### Segmenti

Il collegamento **Segmenti** visualizza un elenco di riepilogo dei segmenti utilizzati dai blocchi di dati selezionati. Se sono selezionati più blocchi di dati con più segmenti applicati, il collegamento **Segmenti** visualizza **[!UICONTROL _Multipli_]**.

>[!MORELIKETHIS]
>
>[Selezionare una visualizzazione dati](select-data-view.md)
>[Selezionare un intervallo di date](select-date-range.md)
>[Utilizzare i filtri](work-with-filters.md)
>
