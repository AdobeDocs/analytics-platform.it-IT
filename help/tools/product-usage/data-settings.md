---
title: Impostazioni dei dati di utilizzo del prodotto
description: Abilita, disabilita o configura le impostazioni di utilizzo del prodotto.
hide: true
hidefromtoc: true
source-git-commit: b3d33561cc29aa1d37efa9f943bc145c16be814c
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 15%

---

# Impostazioni dei dati di utilizzo del prodotto {#product-usage-data-settings}

{{release-limited-testing}}

La pagina _Impostazioni dati_ gestisce la configurazione di utilizzo del prodotto. Puoi utilizzare questa pagina per abilitare o disabilitare l’utilizzo dei prodotti per la tua organizzazione. Puoi anche configurare in quale sandbox di Adobe Experience Platform viene creato il set di dati e, se necessario, ignorare la finestra di conservazione dei dati. È visibile solo agli amministratori di prodotto.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Data settings]**

>[!IMPORTANT]
>Quando si attiva questa funzione, è necessario accettare i termini e le condizioni prima di utilizzarla. Quando si accettano questi termini e condizioni, lo si fa per conto dell&#39;intera organizzazione.

In questa pagina sono disponibili le seguenti impostazioni:

* **[!UICONTROL Enable product usage]**: attiva/disattiva la raccolta dati sull&#39;utilizzo del prodotto. Se abiliti l’utilizzo del prodotto e poi lo disabiliti in futuro, il set di dati, la connessione e la visualizzazione dati non vengono eliminati. Quando viene disattivato, il tracciamento viene disattivato a livello globale per la tua organizzazione.
* **[!UICONTROL Sandbox]**: determina la sandbox di Adobe Experience Platform in cui vengono creati lo schema e il set di dati. La sandbox scelta non influisce sulla raccolta dei dati di utilizzo del prodotto. Se modifichi questa impostazione sandbox, tutti i dati esistenti vengono eliminati. Nella sandbox selezionata vengono creati un nuovo set di dati, una nuova connessione e una nuova visualizzazione dati.
* **[!UICONTROL Override data retention window]**: ogni set di dati ha una finestra di conservazione dei dati predefinita. Se questa impostazione è disabilitata, l’utilizzo del prodotto segue tale periodo di tempo predefinito. È possibile abilitare questa impostazione se si desidera ridurre il tempo di conservazione dei dati. Abbreviare la finestra di conservazione dei dati, ridurre i costi e rispettare le linee guida sulla privacy specifiche dei dipendenti. Non è possibile estendere la conservazione dei dati oltre la finestra di conservazione dei dati predefinita del set di dati.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Sandbox di Adobe Experience Platform"
>abstract="Determina la sandbox di Adobe Experience Platform in cui vengono creati lo schema e il set di dati."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Sostituisci finestra di conservazione dei dati"
>abstract="Riduci la disponibilità dei dati di utilizzo del prodotto per aiutare a ridurre i costi o rispettare le linee guida sulla privacy."
