---
title: Configurare Content Analytics
description: Panoramica sulla configurazione di Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 19%

---

# Configurare Content Analytics

La configurazione di Content Analytics prevede i seguenti passaggi:

![Configurazione di Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Utilizza la procedura guidata [configurazione guidata](guided.md) di Content Analytics per eseguire tutti i passaggi necessari per impostare i prerequisiti per una configurazione di Content Analytics. Puoi salvare le configurazioni in qualsiasi momento e tornare in un secondo momento.
1. Una volta acquisiti i valori di configurazione, puoi implementare la configurazione. Questa implementazione crea tutti gli artefatti richiesti, in base a ciò che hai configurato nella procedura guidata.
1. Solo quando [pubblichi manualmente](manual.md) la proprietà Tags, la configurazione di Content Analytics viene distribuita in modo efficace e la raccolta dati viene avviata.

1. È possibile apportare solo alcune modifiche minori a una configurazione implementata utilizzando la [configurazione guidata](guided.md). Ad esempio, modificare la [visualizzazione dati](/help/data-views/data-views.md).
1. Puoi apportare altre modifiche a una configurazione implementata utilizzando l&#39;estensione [Adobe Content Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/content-analytics/overview) nella proprietà Tags associata.
1. Solo quando [ripubblichi manualmente](manual.md) la proprietà Tags, le modifiche alla configurazione vengono effettivamente distribuite e la raccolta dati, in base alle modifiche, viene avviata.


## Prerequisiti

Prima di configurare Content Analytics, verifica che siano soddisfatti i seguenti prerequisiti:

* Hai inserito nell’elenco Consentiti l’agente utente e l’indirizzo IP per il servizio di funzionalità utilizzato in Content Analytics. La stringa dell&#39;agente utente da configurare è: <code>AdobeFeature/1.0</code>.
* Se hai implementato il [Web SDK utilizzando JavaScript](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/install/library){target="_blank"} per la regolare raccolta di dati comportamentali, assicurati di utilizzare il nome predefinito <code>alloy</code> per la libreria JavaScript.
* Hai il ruolo Amministratore di prodotto Customer Journey Analytics, con le autorizzazioni aggiuntive per gestire le connessioni e le visualizzazioni dati.
* Se pensi di raccogliere esperienze Content Analytics, assicurati di impostare e aggiornare [il controllo delle versioni di Content Analytics](manual.md#versioning) in base alle modifiche apportate alle pagine Web.
* È necessario disporre di [autorizzazioni per la raccolta dati](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Autorizzazioni di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Autorizzazioni di Experience Platform Data Collection](https://experienceleague.adobe.com/it/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* Hai considerato attentamente le seguenti importanti opzioni di configurazione:

   * Il tuo sito è adatto per la generazione di rapporti sull’esperienza. La generazione di rapporti sull’esperienza corretta è possibile solo quando vengono soddisfatte le seguenti condizioni:
      * Le pagine del sito devono essere riproducibili utilizzando l’URL della pagina.
      * Il contenuto di testo visualizzato da un utente può essere riprodotto utilizzando l’URL della pagina e non dipende da cookie o altri meccanismi di personalizzazione.
   * Hai una chiara comprensione delle pagine per le quali desideri acquisire analisi e approfondimenti sul coinvolgimento dei contenuti.
   * Hai una chiara comprensione della risorsa o tipo di risorsa per la quale desideri acquisire analisi e approfondimenti sul coinvolgimento dei contenuti.


## Controllo degli accessi

>[!IMPORTANT]
>
>Non è possibile configurare alcuna autorizzazione di Content Analytics per abilitare o disabilitare l&#39;accesso a Content Analytics per singoli utenti o gruppi di utenti.
>

Per consentire a un utente o a un gruppo di utenti l&#39;accesso a Content Analytics, è necessario fornire all&#39;utente o al gruppo di utenti l&#39;accesso a una o più [visualizzazioni dati configurate per Content Analytics](guided.md#data-view).

Questo accesso implica:

1. La visualizzazione dati abilitata per Content Analytics è inclusa nelle autorizzazioni Visualizzazione dati per un profilo di prodotto Customer Journey Analytics specifico.
1. Quello specifico profilo di prodotto Customer Journey Analytics è uno dei profili di prodotto assegnati all’utente o al gruppo di utenti.

>[!MORELIKETHIS]
>
>* [Configurazione guidata](guided.md)
>* [Configurazione manuale](manual.md)
>* [Controllo degli accessi](/help/technotes/access-control.md)
>
