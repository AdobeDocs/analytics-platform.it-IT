---
title: Aggiungere ricerche globali ai set di dati
description: Utilizza le ricerche globali per migliorare il reporting con dimensioni utili nel Customer Journey Analytics.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
translation-type: tm+mt
source-git-commit: 8224fd2fde787f0d3cf0cb983641efc588c316b0
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---

# Aggiungere ricerche globali ai set di dati

Le ricerche globali migliorano la capacità del Customer Journey Analytics di generare rapporti su alcune dimensioni/attributi che non sono utili da solo ma sono utili quando vengono unite ad altri dati. Alcuni esempi includono attributi di dispositivi mobili e attributi delle dimensioni del sistema operativo e del browser, come i numeri di versione del browser. Una &quot;Ricerca globale&quot; è molto simile a un set di dati di ricerca (noto come classificazioni in Adobe Analytics tradizionale). Tuttavia, le ricerche globali sono applicabili a tutte le organizzazioni di Experience Cloud. Le ricerche globali vengono applicate automaticamente a tutti i set di dati evento che contengono determinati campi dello schema XDM (vedi di seguito per i campi specifici).
Per ogni posizione dello schema classificata da Adobe, esiste un set di dati di ricerca globale. Puoi utilizzare i set di dati di ricerca globali con Analytics Source Connector o con altri set di dati personalizzati che possono accettarli.

In Adobe Analytics tradizionale, queste dimensioni vengono visualizzate autonomamente, mentre in CJA, devi includere attivamente queste dimensioni quando crei visualizzazioni dati. Quando un utente, nel flusso di lavoro Connessioni, seleziona un set di dati contrassegnato come un insieme con una chiave per le ricerche globali, l’interfaccia utente delle visualizzazioni dati sa includere tutte le dimensioni delle dimensioni di ricerca globale disponibili per il reporting. Il flusso di lavoro delle visualizzazioni dati sa di includere queste dimensioni di ricerca globale come disponibili per la visualizzazione dati. I file di ricerca vengono aggiornati e disponibili automaticamente, in tutte le aree geografiche e per tutti gli account. Sono memorizzate in organizzazioni specifiche per l&#39;area geografica associate al cliente.

## Utilizzare le ricerche globali con i set di dati del connettore dati di Adobe

I set di dati di ricerca globali vengono applicati automaticamente al momento del rapporto. Se utilizzi il [Connettore dati di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#connectors) e inserisci una dimensione per la quale Adobe fornisce una ricerca globale, questa ricerca globale viene applicata automaticamente. Se un set di dati evento contiene campi [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en), possiamo applicarvi le ricerche globali.

## Campi di ricerca globali disponibili

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`,  `group_id`,  `id`
* `os_group`
   * `os_group`,  `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## Report sulle dimensioni di ricerca globale

Per creare rapporti sulle dimensioni di ricerca globale, devi aggiungerle quando crei una visualizzazione dati in un Customer Journey Analytics:

![](assets/global-lookup.png)

Puoi quindi visualizzare i dati di ricerca in Workspace:

![](assets/gl-reporting.png)
