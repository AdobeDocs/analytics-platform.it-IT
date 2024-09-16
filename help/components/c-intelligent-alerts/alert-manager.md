---
description: Crea, modifica o elimina gli avvisi.
title: Gestione avvisi (Analysis Workspace)
feature: Workspace Basics
role: User, Admin
source-git-commit: 640624ab017d8fc0e7b942c2f00c71cf255c4296
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 5%

---

# Gestire gli avvisi

È possibile gestire gli avvisi esistenti nella Gestione avvisi. È possibile eseguire varie attività di gestione sugli avvisi, ad esempio assegnare tag, rinominare, eliminare e altro ancora.

La gestione avvisi è strutturata in modo analogo alla [gestione filtri](/help/components/filters/manage-filters.md) e alla [gestione metriche calcolate](/help/components/calc-metrics/cm-workflow/cm-manager.md).

## Creare avvisi

Per creare avvisi da Gestione avvisi:

1. Selezionare **[!UICONTROL Components]** > **[!UICONTROL Alerts]** per accedere alla Gestione avvisi nel Customer Journey Analytics.

   ![](assets/alert-manager.png)

1. Seleziona [!UICONTROL **Aggiungi**] (o [!UICONTROL **Crea nuovo avviso**] se non hai avvisi esistenti).

1. Continuare con [Crea avvisi](/help/components/c-intelligent-alerts/alert-builder.md) per ulteriori dettagli sulla creazione di avvisi.

## Gestire gli avvisi esistenti

Per gestire gli avvisi esistenti in Gestione avvisi:

1. Selezionare **[!UICONTROL Components]** > **[!UICONTROL Alerts]** per accedere alla Gestione avvisi nel Customer Journey Analytics.

   ![](assets/alert-manager.png)

1. Seleziona uno o più avvisi da gestire.

   ![](assets/alert-manager-tasks.png)

1. Nella barra delle azioni, seleziona una delle opzioni seguenti:

   | Azione | Funzione |
   |---------|----------|
   | [!UICONTROL **Tag**] | Applicare un tag a un avviso. In questo modo è possibile organizzare gli avvisi in modo semplice e intuitivo. |
   | [!UICONTROL **Elimina**] | Elimina l’avviso. |
   | [!UICONTROL **Rinomina**] | Rinomina l&#39;avviso. |
   | [!UICONTROL **Approva**] | Contrassegna l&#39;avviso come Approvato. |
   | [!UICONTROL **Copia**] | Crea una copia (duplicata) dell&#39;avviso. |
   | [!UICONTROL **Disattiva**] | Disattiva un avviso attualmente abilitato. |
   | [!UICONTROL **Abilita**] | Abilita un avviso attualmente disabilitato. |
   | [!UICONTROL **Rinnova**] | Rinnova la data di scadenza dell’avviso. Questa funzione sposta la data di scadenza a 1 anno dal giorno in cui hai selezionato questa opzione, indipendentemente dalla data di scadenza originale. |
   | [!UICONTROL **Esporta in CSV**] | Esporta l&#39;avviso in un file CSV. |

## Modificare un avviso

Per modificare un avviso esistente:

1. Selezionare **[!UICONTROL Components]** > **[!UICONTROL Alerts]** per accedere alla Gestione avvisi in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Selezionare il nome dell&#39;avviso nella colonna [!UICONTROL **Titolo e descrizione**].

1. Modificare l&#39;avviso come desiderato.

   Di seguito sono riportate alcune delle operazioni che è possibile eseguire durante la modifica di un avviso:

   * Aggiungere avvisi ad altre suite di rapporti
   * Cambia il proprietario
   * Aggiornare i filtri
   * Aggiornare la data di scadenza

1. Modifica l&#39;avviso, quindi seleziona [!UICONTROL **Salva**].

## Configurare le colonne

È possibile configurare le informazioni visualizzate per ogni avviso in Gestione avvisi configurando le colonne visualizzate.

Per configurare le colonne visibili in Gestione avvisi:

1. In Adobe Analytics, selezionare la scheda **[!UICONTROL Components]**, quindi selezionare **[!UICONTROL Alerts]**.

1. In Gestione avvisi, selezionare l&#39;icona **Personalizza colonne** ![Personalizza colonne icona](assets/customize-columns-icon.png), quindi selezionare le colonne che si desidera visualizzare in Gestione avvisi.

   Sono disponibili le seguenti colonne:

   | Titolo colonna | Descrizione |
   |---|---|
   | Titolo e descrizione | Questi valori vengono forniti nel generatore di avvisi. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo per aprire il generatore di avvisi. |
   | Preferiti | Visualizza icone a forma di stella accanto a ogni avviso, che consentono di contrassegnare gli avvisi come preferiti. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Tipo | Mostra se l’avviso è un avviso di dati di Analytics o un avviso di utilizzo di chiamate al server. |
   | Abilitata | Indica se l&#39;avviso è attualmente abilitato o disabilitato. |
   | Suite di rapporti | Indica in quale suite di rapporti è stato salvato l’ultimo avviso. |
   | Proprietario | Indica il proprietario dell&#39;avviso. In qualità di non amministratore, puoi visualizzare solo gli avvisi di tua proprietà o quelli che sono stati condivisi con te. |
   | Tag | Mostra i tag applicati all&#39;avviso, da te o da altri utenti che lo hanno condiviso con te. |
   | Data di scadenza | Mostra la data e l’ora in cui l’avviso è impostato per scadere. |
   | Data di modifica | Indica la data dell’ultima modifica apportata all’avviso. |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

## Risolvere i problemi relativi a un avviso

Durante la risoluzione di un problema relativo a un avviso, specifica il numero JID (Job Instance ID) per il supporto Adobe. Il numero JID si trova in fondo alla notifica e-mail di avviso ricevuta.

![E-mail avviso](assets/alerts-email.PNG)