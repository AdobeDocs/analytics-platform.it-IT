---
title: Impostazioni dati di utilizzo prodotto
description: Abilita, disabilita o configura le impostazioni di utilizzo del prodotto.
hide: true
hidefromtoc: true
source-git-commit: 40b761928697d1d55e1177aa7b2b3c056739ecc9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Impostazioni dati di utilizzo prodotto {#product-usage-data-settings}

{{release-limited-testing}}

La pagina _Impostazioni dati_ gestisce la configurazione di utilizzo del prodotto. Puoi utilizzare questa pagina per abilitare o disabilitare l’utilizzo dei prodotti per la tua organizzazione. Puoi anche configurare in quale sandbox di Adobe Experience Platform viene creato il set di dati e, se necessario, ignorare la finestra di conservazione dei dati. È visibile solo agli amministratori di prodotto.

**Customer Journey Analytics** > **Strumenti** > **Utilizzo prodotto** > **Impostazioni dati**

>[!IMPORTANT]
>
>Quando si attiva questa funzione, è necessario accettare i termini e le condizioni prima di utilizzarla. Quando si accettano questi termini e condizioni, lo si fa per conto dell&#39;intera organizzazione.

In questa pagina sono disponibili le seguenti impostazioni:

* **Abilita utilizzo prodotto**: attiva la raccolta dati sull&#39;utilizzo dei prodotti. Se abiliti l’utilizzo del prodotto e lo disabiliti in futuro, il set di dati, la connessione e la visualizzazione dati non vengono eliminati. Quando viene disattivato, il tracciamento viene disattivato a livello globale per la tua organizzazione.
* **Sandbox**: determina la sandbox Adobe Experience Platform in cui vengono creati lo schema e il set di dati. La sandbox scelta non influisce sulla raccolta dei dati di utilizzo del prodotto. Se modifichi questa impostazione sandbox, tutti i dati esistenti vengono eliminati. Nella sandbox selezionata vengono creati un nuovo set di dati, una nuova connessione e una nuova visualizzazione dati.
* **Ignora finestra di conservazione dati**: ogni set di dati ha una finestra di conservazione dati predefinita. Se questa impostazione è disabilitata, l’utilizzo del prodotto segue tale periodo di tempo predefinito. È possibile abilitare questa impostazione se si desidera ridurre il tempo di conservazione dei dati. Abbreviare la finestra di conservazione dei dati, ridurre i costi e rispettare le linee guida sulla privacy specifiche dei dipendenti. Non è possibile estendere la conservazione dei dati oltre la finestra di conservazione dei dati predefinita del set di dati.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Sandbox Adobe Experience Platform"
>abstract="Determina la sandbox di Adobe Experience Platform in cui vengono creati lo schema e il set di dati."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Ignora finestra di conservazione dei dati"
>abstract="Riduci la disponibilità dei dati di utilizzo del prodotto per ridurre i costi o rispettare le linee guida sulla privacy."
