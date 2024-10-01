---
title: Impostazioni di rinuncia all’utilizzo del prodotto
description: Gestisci le impostazioni di rinuncia per i singoli utenti all’interno della tua organizzazione.
hide: true
hidefromtoc: true
source-git-commit: 8f2a340f59d8cdf97a5309ec20dc36f49b8f1129
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# Impostazioni di rinuncia all’utilizzo del prodotto {#product-usage-opt-out-settings}

{{release-limited-testing}}

La pagina delle _impostazioni di rinuncia_ ti consente di escludere o includere nuovamente gli utenti all&#39;interno della tua organizzazione dal monitoraggio dell&#39;utilizzo dei prodotti. È visibile solo agli amministratori di prodotto.

**Customer Journey Analytics** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Opt-out settings]**

In questa pagina sono disponibili le seguenti impostazioni:

* **[!UICONTROL Opt-out user]**: elenco a discesa contenente tutti gli utenti del Customer Journey Analytics dell&#39;organizzazione. Selezionare un utente da questo elenco a discesa e selezionare **[!UICONTROL Opt-out]** per escluderlo dal monitoraggio dell&#39;utilizzo del prodotto. L&#39;utente è stato aggiunto alla tabella [!UICONTROL Opt-out user list] seguente.
* **[!UICONTROL Opt-out user list]**: tabella che mostra tutti gli utenti attualmente esclusi dal monitoraggio dell&#39;utilizzo dei prodotti. Per fornire nuovamente il consenso a un utente per il monitoraggio dell&#39;utilizzo del prodotto, selezionare la casella di controllo accanto a un determinato utente, quindi selezionare il pulsante **[!UICONTROL Opt-in]**.

Adobe utilizza una combinazione di tracciamento lato client e lato server per raccogliere i dati di utilizzo del prodotto per la tua organizzazione. Quando un utente viene inizialmente escluso, potrebbe comunque visualizzare i dati di tracciamento lato client nel debugger fino a quando non si disconnette e torna al Customer Journey Analytics. La convalida lato server di Adobe garantisce che i dati di tracciamento lato client vengano eliminati per gli utenti esclusi.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Utenti esclusi"
>abstract="Escludi utenti dal tracciamento dell’utilizzo del prodotto."
