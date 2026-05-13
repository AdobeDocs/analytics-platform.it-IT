---
title: Impostazioni di rinuncia all’utilizzo del prodotto
description: Gestisci le impostazioni di rinuncia per i singoli utenti all’interno della tua organizzazione.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
TQID: https://experienceleague.adobe.com/Z0CR6bB6k0-bR3q2OPs11FcHHDy948UuYIqbX-kwdcg
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
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
