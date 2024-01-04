---
title: Aggiungere ricerche globali ai set di dati
description: Utilizza le ricerche standard per migliorare i rapporti con dimensioni utili nel Customer Journey Analytics.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 73%

---

# Aggiungere ricerche globali ai set di dati

>[!IMPORTANT]
>Le ricerche standard sono disponibili solo per le origini dati del connettore di origine di Analytics nel Customer Journey Analytics. Puoi utilizzarli con le implementazioni standard di Adobe Analytics, [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) o le API di raccolta dati di Experience Platform.

Le ricerche standard (anche note come ricerche fornite da Adobe) migliorano la capacità del Customer Journey Analytics di generare rapporti su alcune dimensioni/attributi che non sono utili da sole ma sono utili quando sono collegate con altri dati. Alcuni esempi includono attributi di dispositivi mobili e attributi delle dimensioni del sistema operativo e del browser, come i numeri di versione del browser. Una ricerca standard è simile a un set di dati di ricerca. Le ricerche standard sono applicabili a tutte le organizzazioni Experience Cloud. Vengono applicati automaticamente a tutti i set di dati evento che contengono alcuni campi dello schema XDM (vedi di seguito per i campi specifici). Esiste un set di dati di ricerca standard per ogni posizione dello schema classificata da Adobe.

In Adobe Analytics tradizionale, queste dimensioni vengono visualizzate autonomamente, mentre in Customer Journey Analytics, devi includere attivamente queste dimensioni quando crei le visualizzazioni dati. Nel flusso di lavoro Connessioni, seleziona un set di dati contrassegnato come un insieme di chiavi per la ricerca standard. L’interfaccia utente Visualizzazioni dati sa includere automaticamente tutte le dimensioni di ricerca standard disponibili per il reporting. I file di ricerca vengono aggiornati e sono disponibili automaticamente, in tutte le aree geografiche e per tutti gli account. Sono memorizzate in organizzazioni specifiche per l’area geografica associate al cliente.

## Utilizzare le ricerche standard con i set di dati del connettore di origine di Analytics

I set di dati di ricerca standard vengono applicati automaticamente al momento del rapporto. Se utilizzi il connettore di origine di Analytics e inserisci una dimensione per la quale Adobe fornisce una ricerca standard, questa ricerca standard verrà applicata automaticamente. Se un set di dati evento contiene campi XDM, possiamo applicarvi le ricerche standard.

<!--
### Specific IDs that need to be populated

The following IDs need to be populated in the specific XDM mixins for this functionality to work:

* Environment Details Mixin – device/typeID value populated - Must match Device Atlas IDs and will populate device data.
* Adobe Analytics ExperienceEvent Template Mixin or Adobe Analytics ExperienceEvent Full Extension Mixin with analytics/environment/browserIDStr and analytics/environment/operatingSystemIDStr. Both must match the Adobe IDs and  populate browser and OS data, respectively.

You need these mixins with the three IDs populated (device/typeID, environment/browserIDStr, and environment/operatingSystemIDStr). The lookup dimensions will then be pulled automatically by Customer Journey Analytics and will be available in the Data View.

The catch here is that they can only populate those IDs today if they have a direct relationship with Device Atlas. They are Device Atlas IDs, and they provide an API to allow a customer to look them up. This is a significant hurdle, and we may just want to take the reference to this capability out of the product documentation until we have a productized way to expose the Device Atlas ID lookup functionality.
-->

### Campi di ricerca standard disponibili

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
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

## Rapporto sulle dimensioni di ricerca standard

Per creare rapporti sulle dimensioni di ricerca standard, devi aggiungerle quando crei una visualizzazione dati in Customer Journey Analytics:

![Creare una visualizzazione dati che mostri l’elenco Aggiungi componenti](assets/global-lookup.png)

Puoi quindi visualizzare i dati di ricerca in Workspace:

![Tabella a forma libera con i dati](assets/gl-reporting.png)
