---
title: Configurare Content Analytics
description: Panoramica sulla configurazione di Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: beb2e35354d3da1fe6d22f4221e30ff0ccde3138
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 77%

---

# Configurare Content Analytics

Questo articolo illustra, ad alto livello, come configurare Content Analytics.

Prima di configurare Content Analytics, è necessario verificare che i [prerequisiti](#prerequisites) siano soddisfatti, che di disporre del [controllo degli accessi](#access-control) richiesto e conoscendone le [limitazioni](#limitations).


Passaggi di alto livello

![Configurazione di Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Utilizza la [configurazione guidata](guided.md) di Content Analytics per eseguire tutti i passaggi necessari per impostare i prerequisiti per una configurazione di Content Analytics. Puoi salvare le configurazioni in qualsiasi momento e tornare in seguito.
1. Una volta che hai acquisito dimestichezza con i valori di configurazione, puoi procedere con l’implementazione. Questa implementazione crea tutti gli artefatti richiesti, in base a ciò che hai configurato nella procedura guidata.
1. Solo quando [pubblichi manualmente](manual.md) la proprietà Tags è la configurazione di Content Analytics distribuita in modo efficace e la raccolta dati è stata avviata.

1. Puoi apportare solo alcune modifiche minori a una configurazione implementata utilizzando la procedura guidata [configurazione guidata](guided.md). Ad esempio, puoi modificare la [visualizzazione dati](/help/data-views/data-views.md).
1. Puoi apportare altre modifiche a una configurazione implementata utilizzando l&#39;estensione Adobe Content Analytics nella proprietà Tag associata per [web](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview) o [mobile](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).
1. Le modifiche di configurazione vengono distribuite in modo efficace e la raccolta dei dati viene avviata solo quando si ripubblica manualmente la proprietà Tags.


## Prerequisiti

Prima di configurare Content Analytics, accertati che siano soddisfatti i seguenti prerequisiti:

### Web

* Hai inserito nell’elenco Consentiti l’agente utente e l’indirizzo IP per il servizio di funzionalità utilizzato in Content Analytics. La stringa dell’agente utente da configurare è: <code>AdobeFeaturization/1.0</code>.
* Se hai implementato il [Web SDK utilizzando JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library){target="_blank"} per la raccolta regolare di dati comportamentali, assicurati di utilizzare il nome predefinito <code>alloy</code> per la libreria JavaScript.
* Hai il ruolo di amministratore di prodotto Customer Journey Analytics, con le autorizzazioni aggiuntive per gestire le connessioni e le visualizzazioni dati.
* Se decidi di raccogliere esperienze Content Analytics, assicurati di impostare e aggiornare il controllo delle versioni di Content Analytics in base alle modifiche apportate alle pagine web.
* È necessario disporre di [autorizzazioni per la raccolta dati](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Autorizzazioni Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}.
   * [Autorizzazioni di Experience Platform Data Collection](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}.
* Hai considerato attentamente le seguenti importanti opzioni di configurazione:

   * Il sito è adatto per la generazione di rapporti sull’esperienza. Una corretta generazione di rapporti sull’esperienza è possibile solo quando sono soddisfatte le seguenti condizioni:
      * Le pagine del sito devono essere riproducibili utilizzando l’URL della pagina.
      * Il contenuto di testo visualizzato da un determinato utente può essere riprodotto utilizzando l’URL della pagina e non dipende da cookie o altri meccanismi di personalizzazione.
   * Hai una chiara comprensione delle pagine che desideri acquisire per l’analisi e le informazioni sul coinvolgimento dei contenuti.
   * Hai una chiara comprensione della risorsa o tipo di risorsa per la quale desideri acquisire analisi e approfondimenti sul coinvolgimento dei contenuti.

### Mobile

* Assicurati che le estensioni [Experience Platform Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) e [Experience Platform Identity per Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) siano abilitate per l&#39;app mobile.
* Hai il ruolo di amministratore di prodotto Customer Journey Analytics, con le autorizzazioni aggiuntive per gestire le connessioni e le visualizzazioni dati.
* È necessario disporre di [autorizzazioni per la raccolta dati](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Autorizzazioni Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}.
   * [Autorizzazioni di Experience Platform Data Collection](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}.



## Controllo degli accessi

>[!IMPORTANT]
>
>Non è possibile configurare alcuna autorizzazione di Content Analytics per abilitare o disabilitare l’accesso a Content Analytics per singoli utenti o gruppi di utenti.
>

Per consentire a un utente o a un gruppo di utenti l’accesso a Content Analytics, è necessario fornire l’accesso a una o più [visualizzazioni dati configurate per Content Analytics](guided.md#data-view).

Questo accesso implica:

1. La visualizzazione dati abilitata per Content Analytics è inclusa nelle autorizzazioni delle visualizzazioni dati per uno specifico profilo di prodotto Customer Journey Analytics.
1. Questo specifico profilo di prodotto Customer Journey Analytics è uno dei profili di prodotto assegnati all’utente o al gruppo di utenti.

## Limitazioni

Lo schema utilizzato per i dati dell’evento di Content Analytics è di proprietà del sistema. Non è possibile modificare uno schema di proprietà del sistema, il che implica:

* Non è possibile includere gruppi di campi per il supporto di funzionalità quali geolocalizzazione, rilevamento di bot o ricerca per dispositivi.
* Impossibile aggiungere un identificatore specifico per supportare l’[unione delle identità basata sui campi](/help/stitching/fbs.md).

>[!MORELIKETHIS]
>
>* [Configurazione guidata](guided.md)
>* [Configurazione manuale](manual.md)
>* [Controllo degli accessi](/help/technotes/access-control.md)
>
