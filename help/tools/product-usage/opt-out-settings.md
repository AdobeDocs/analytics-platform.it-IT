---
title: Impostazioni di rinuncia all’utilizzo del prodotto
description: Gestisci le impostazioni di rinuncia per i singoli utenti all’interno della tua organizzazione.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 57%

---

# Impostazioni di rinuncia all’utilizzo del prodotto {#product-usage-opt-out-settings}

La pagina delle _impostazioni di rinuncia_ ti consente di escludere o includere nuovamente gli utenti all’interno della tua organizzazione nel tracciamento dell’utilizzo del prodotto. È visibile solo agli amministratori di prodotto.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Strumenti]** > **[!UICONTROL Utilizzo prodotto]** > **[!UICONTROL Impostazioni di rinuncia]**

Le seguenti impostazioni sono disponibili in questa pagina:

* **[!UICONTROL Utente rinuncia]**: un menu a discesa contenente tutti gli utenti di Customer Journey Analytics dell&#39;organizzazione. Seleziona un utente da questo menu a discesa e seleziona **[!UICONTROL Rinuncia]** per escluderlo dal tracciamento dell&#39;utilizzo del prodotto. L&#39;utente è stato aggiunto alla tabella seguente [!UICONTROL Elenco utenti rinuncia].
* **[!UICONTROL Elenco utenti esclusi]**: tabella che mostra tutti gli utenti attualmente esclusi dal tracciamento dell&#39;utilizzo del prodotto. Per consentire a un utente di accedere nuovamente al monitoraggio dell&#39;utilizzo del prodotto, selezionare la casella di controllo accanto a un utente specifico, quindi selezionare il pulsante **[!UICONTROL Opt-in]**.

Adobe utilizza una combinazione di tracciamento lato client e lato server per raccogliere i dati di utilizzo del prodotto per la tua organizzazione. Quando un utente viene inizialmente escluso, potrebbe comunque visualizzare i dati di tracciamento lato client nel debugger fino a quando non si disconnette e torna a Customer Journey Analytics. La convalida lato server di Adobe garantisce che i dati di tracciamento lato client vengano eliminati per gli utenti esclusi.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Escludere utenti"
>abstract="Escludi utenti dal tracciamento dell’utilizzo del prodotto."

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="Escludere utenti"
>abstract="Escludi utenti dal tracciamento dell’utilizzo del prodotto."
