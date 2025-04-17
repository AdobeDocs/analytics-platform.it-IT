---
title: Impostazioni di rinuncia all’utilizzo del prodotto
description: Gestisci le impostazioni di rinuncia per i singoli utenti all’interno della tua organizzazione.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: ht
source-wordcount: '204'
ht-degree: 100%

---

# Impostazioni di rinuncia all’utilizzo del prodotto {#product-usage-opt-out-settings}

La pagina delle _impostazioni di rinuncia_ ti consente di escludere o includere nuovamente gli utenti all’interno della tua organizzazione nel tracciamento dell’utilizzo del prodotto. È visibile solo agli amministratori di prodotto.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]** > **[!UICONTROL Opt-out settings]**

Le seguenti impostazioni sono disponibili in questa pagina:

* **[!UICONTROL Opt-out user]**: elenco a discesa contenente tutti gli utenti Customer Journey Analytics della tua organizzazione. Seleziona un utente da questo elenco a discesa e seleziona **[!UICONTROL Opt-out]** per escluderlo dal tracciamento dell’utilizzo del prodotto. L’utente è aggiunto alla tabella [!UICONTROL Opt-out user list] seguente.
* **[!UICONTROL Opt-out user list]**: tabella che mostra tutti gli utenti attualmente esclusi dal tracciamento dell’utilizzo del prodotto. Per fornire nuovamente il consenso a un utente per il monitoraggio dell’utilizzo del prodotto, seleziona la casella di controllo accanto a un determinato utente, quindi seleziona il pulsante **[!UICONTROL Opt-in]**.

Adobe utilizza una combinazione di tracciamento lato client e lato server per raccogliere i dati di utilizzo del prodotto per la tua organizzazione. Quando un utente viene inizialmente escluso, potrebbe comunque visualizzare i dati di tracciamento lato client nel debugger fino a quando non si disconnette e torna a Customer Journey Analytics. La convalida lato server di Adobe garantisce che i dati di tracciamento lato client vengano eliminati per gli utenti esclusi.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Escludere utenti"
>abstract="Escludi utenti dal tracciamento dell’utilizzo del prodotto."

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="Escludere utenti"
>abstract="Escludi utenti dal tracciamento dell’utilizzo del prodotto."
