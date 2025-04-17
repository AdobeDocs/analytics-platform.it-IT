---
title: Impostazioni dei dati di utilizzo del prodotto
description: Abilita, disabilita o configura le impostazioni di utilizzo del prodotto.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: ht
source-wordcount: '340'
ht-degree: 100%

---

# Impostazioni dei dati di utilizzo del prodotto {#product-usage-data-settings}

La pagina _Impostazioni dati_ gestisce la configurazione di utilizzo del prodotto. Puoi utilizzare questa pagina per abilitare o disabilitare l’utilizzo del prodotto per la tua organizzazione. Puoi anche configurare in quale sandbox di Adobe Experience Platform viene creato il set di dati e, se lo desideri, ignorare la finestra di conservazione dei dati. È visibile solo agli amministratori di prodotto.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Data settings]**

>[!IMPORTANT]
>Quando attivi questa funzione, devi accettare i termini e le condizioni prima di utilizzarla. Quando accetti questi termini e condizioni, lo fai per conto dell’intera organizzazione.

Le seguenti impostazioni sono disponibili in questa pagina:

* **[!UICONTROL Enable product usage]**: attiva/disattiva la disponibilità di raccolta dati sull’utilizzo del prodotto. Se abiliti l’utilizzo del prodotto e poi lo disabiliti in futuro, il set di dati, la connessione e la visualizzazione dei dati non vengono eliminati. Se viene disattivato, il tracciamento è disattivato a livello globale per la tua organizzazione.
* **[!UICONTROL Sandbox]**: determina la sandbox di Adobe Experience Platform in cui vengono creati lo schema e il set di dati. La sandbox scelta non influisce sulla raccolta dei dati di utilizzo del prodotto. Se modifichi questa impostazione della sandbox, tutti i dati esistenti vengono eliminati. Nella sandbox selezionata vengono creati un nuovo set di dati, una nuova connessione e una nuova visualizzazione dati.
* **[!UICONTROL Override data retention window]**: ogni set di dati ha una finestra di conservazione dei dati predefinita. Se questa impostazione è disabilitata, l’utilizzo del prodotto segue tale periodo di tempo predefinito. Puoi abilitare questa impostazione, se desideri ridurre il tempo di conservazione dei dati. Abbreviando la finestra di conservazione dei dati, aiuta a ridurre i costi e consente di rispettare le linee guida sulla privacy specifiche dei dipendenti. Non puoi estendere la conservazione dei dati oltre la finestra di conservazione dei dati predefinita del set di dati.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Sandbox di Adobe Experience Platform"
>abstract="Determina la sandbox di Adobe Experience Platform in cui vengono creati lo schema e il set di dati."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Sostituisci finestra di conservazione dei dati"
>abstract="Riduci la disponibilità dei dati di utilizzo del prodotto per aiutare a ridurre i costi o rispettare le linee guida sulla privacy."

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Sandbox di Adobe Experience Platform"
>abstract="Determina la sandbox di Adobe Experience Platform in cui vengono creati lo schema e il set di dati."

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="Sostituisci finestra di conservazione dei dati"
>abstract="Riduci la disponibilità dei dati di utilizzo del prodotto per aiutare a ridurre i costi o rispettare le linee guida sulla privacy."
