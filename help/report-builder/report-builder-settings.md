---
title: Come configurare le impostazioni per Report Builder in Customer Journey Analytics
description: Descrive come impostare la modalità offline, la lingua, la data di fine e le impostazioni per la risoluzione dei problemi.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Impostazioni Report Builder

Utilizza il riquadro **Impostazioni** per configurare le impostazioni a livello di applicazione, ad esempio la lingua visualizzata dall&#39;interfaccia utente o se utilizzare o meno la modalità offline. Le impostazioni vengono applicate immediatamente e vengono impostate per tutte le sessioni future fino a quando non vengono modificate.

Per modificare le impostazioni di Report Builder

1. Seleziona l&#39;icona **Impostazioni**.

1. Apportare modifiche a [attivazione della modalità offline](#off-line-mode), [selezione di una lingua](#language) o [attivazione della risoluzione dei problemi](#troubleshooting).

1. Seleziona **[!UICONTROL Apply]**.

   ![Riquadro dell&#39;intervallo di date di Report Builder con il pulsante Annulla e applica.](./assets/report-builder-settings.png){zoomable="yes"}

## Modalità offline

Quando crei e modifichi un blocco di dati in modalità offline, i dati non vengono recuperati. Al contrario, i dati di simulazione vengono utilizzati in modo da poter lavorare rapidamente senza attendere l’esecuzione della richiesta. Quando sei di nuovo online, seleziona ![Aggiorna](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** o ![AggiornaDocumento](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** per aggiornare i blocchi di dati con i dati effettivi.

Per attivare la modalità offline

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg).

1. Attiva **[!UICONTROL Enable off-line mode]**.

1. Immettere un numero intero positivo nel campo **[!UICONTROL Display metric data]** come.

1. Seleziona **[!UICONTROL Apply]**.


## Lingua

È possibile scegliere la lingua per l&#39;interfaccia di Report Builder. Sono disponibili tutte le lingue di Customer Journey Analytics supportate.

Per selezionare la lingua utilizzata nell&#39;interfaccia di Report Builder:

1. Selezionare una lingua dal menu a discesa **[!UICONTROL Language]**.

1. Seleziona **Applica.**

## Risoluzione dei problemi

L&#39;impostazione **[!UICONTROL Troubleshooting logs]** registra tutti i dati client/server in un file locale. Utilizza questa opzione per risolvere i ticket di supporto.

Per abilitare i registri di risoluzione dei problemi, selezionare **[!UICONTROL Log report builder request to local file]**.
