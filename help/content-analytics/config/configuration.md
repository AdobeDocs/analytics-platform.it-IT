---
title: Configurare l’analisi dei contenuti
description: Panoramica sulla configurazione di Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# Configurare l’analisi dei contenuti

>[!WARNING]
>
>Questo articolo è una bozza preliminare non ufficiale di una versione finale di prossima pubblicazione e fa parte della documentazione di Content Analytics. Tutti i contenuti sono soggetti a modifiche e nessun obbligo legale può essere derivato dalla versione corrente di questo articolo.
>

{{release-limited-testing}}

La configurazione di Content Analytics prevede i seguenti passaggi:

![Configurazione di Content Analytics](../assets/aca-configuration.svg)

1. Utilizza la procedura guidata [configurazione guidata](guided.md) di Content Analytics per eseguire tutti i passaggi necessari per impostare i prerequisiti per una configurazione di Content Analytics. Puoi salvare le configurazioni e tornare in un secondo momento.
1. Una volta acquisiti i valori di configurazione, puoi implementare la configurazione. Questa implementazione crea tutti gli artefatti richiesti, in base a ciò che hai configurato nella procedura guidata. Vengono creati, aggiornati o selezionati i seguenti artefatti:
   * Customer Journey Analytics
      * [visualizzazione dati](/help/data-views/data-views.md) selezionata.
      * È selezionata una [connessione](/help/connections/overview.md), derivata automaticamente dalla visualizzazione dati selezionata.
   * Experience Platform
      * Viene selezionata la sandbox, derivata automaticamente dalla connessione. I flussi di lavoro e i servizi necessari sono abilitati nella sandbox.
      * Gli schemi Content Analytics sono selezionati nella sandbox. Se non disponibile, vengono creati gli schemi necessari.
      * I set di dati di Content Analytics sono selezionati nella sandbox. Se non disponibile, vengono creati i set di dati necessari.
   * Raccolta dati
      * All’interno del flusso di dati viene creato un flusso di dati e viene configurato un servizio Experience Platform per inviare dati al set di dati dell’evento esperienza di Content Analytics.
      * Viene creata una proprietà Tags con l’estensione Adobe Content Analytics configurata per la sandbox, lo stream di dati e altre opzioni di configurazione corrette della procedura guidata.
1. Solo quando [pubblichi manualmente](manual.md) la proprietà Tags, la configurazione Content Analytics verrà effettivamente distribuita e attivata.

1. È possibile apportare solo alcune modifiche minori a una configurazione implementata utilizzando la [configurazione guidata](guided.md). Ad esempio, modificare la [visualizzazione dati](/help/data-views/data-views.md).
1. Puoi apportare altre modifiche a una configurazione implementata. Utilizza l&#39;estensione [Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) nella proprietà Tags associata.
1. Solo quando [ripubblichi manualmente](manual.md) la proprietà Tags, le modifiche alla configurazione dei passaggi 4 e 5 vengono distribuite e attivate in modo efficace.


## Prerequisiti

Prima di configurare Content Analytics, verifica che siano soddisfatti i seguenti prerequisiti:

* Hai inserito nell’elenco Consentiti l’agente utente e l’indirizzo IP per il servizio di funzionalità utilizzato in Content Analytics. La stringa dell&#39;agente utente da configurare è: <code>AdobeFeature/1.0</code>.
* Hai il ruolo Amministratore di prodotto Customer Journey Analytics, con le autorizzazioni aggiuntive per gestire le connessioni e le visualizzazioni dati.
* Hai le autorizzazioni Experience Platform necessarie:

  | Categoria | Autorizzazione | Descrizione |
  |---|---|---|
  | [!UICONTROL Data Collection] | Visualizzare gli stream di dati | Accesso in sola lettura agli stream di dati. |
  | [!UICONTROL Data Collection] | Gestire gli stream di dati | Accesso per leggere, creare, modificare ed eliminare gli stream di dati. |
  | [!UICONTROL Data Modeling] | [!UICONTROL View Schemas] | Accesso in sola lettura agli schemi e alle risorse correlate. |
  | [!UICONTROL Data Modeling] | [!UICONTROL Manage Schemas] | Accesso per leggere, creare, modificare ed eliminare schemi e risorse correlate. |
  | [!UICONTROL Data Management] | [!UICONTROL View Datasets] | Accesso in sola lettura per set di dati e schemi. |
  | [!UICONTROL Data Management] | [!UICONTROL Manage Datasets] | Accesso per leggere, creare, modificare ed eliminare i set di dati. Accesso in sola lettura per gli schemi. |
  | [!UICONTROL Data Ingestion] | [!UICONTROL Manage Sources] | Accesso per leggere, creare, modificare e disabilitare le origini. |
  | [!UICONTROL Identity Management] | [!UICONTROL View Identity Namespaces] | Accesso in sola lettura per gli spazi dei nomi di identità. |

* Hai considerato attentamente le seguenti importanti opzioni di configurazione:

   * Il tuo sito è adatto per la generazione di rapporti sull’esperienza. La generazione di rapporti sull’esperienza corretta è possibile solo quando vengono soddisfatte le seguenti condizioni:
      * Puoi accedere al contenuto del sito solo tramite URL rivolti al pubblico. L’accesso al sito non richiede token personalizzati, cookie o altri meccanismi non disponibili tramite l’URL.
      * Le pagine del sito sono riproducibili utilizzando l’URL della pagina e comprendi quali parametri URL facoltativi guidano le esperienze.
   * Hai una chiara comprensione delle pagine che desideri acquisire analisi e approfondimenti sul coinvolgimento dei contenuti.
   * Hai una chiara comprensione di quale (tipo di) risorsa desideri acquisire analisi e approfondimenti sul coinvolgimento dei contenuti.


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
>* [Controllo dell&#39;accesso](/help/technotes/access-control.md)
>
