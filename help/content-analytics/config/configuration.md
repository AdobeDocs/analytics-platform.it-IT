---
title: Configurare l’analisi dei contenuti
description: Panoramica sulla configurazione di Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: cea253d3b1da080e6735989d59cc6eda44afc203
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 1%

---

# Configurare l’analisi dei contenuti

>[!WARNING]
>
>Questo articolo è una bozza preliminare non ufficiale di una versione finale di prossima pubblicazione e fa parte della documentazione di Content Analytics. Tutti i contenuti sono soggetti a modifiche e nessun obbligo legale può essere derivato dalla versione corrente di questo articolo.
>

{{release-limited-testing}}


Per configurare Content Analytics per la tua organizzazione, utilizza la [configurazione guidata](guided.md) di Content Analytics. La procedura guidata di configurazione ti guida attraverso tutti i passaggi necessari per impostare i prerequisiti per una configurazione automatica di Content Analytics.

## Prerequisiti

Prima di configurare Content Analytics, accertati di soddisfare i seguenti prerequisiti:

* Hai inserito nell’elenco Consentiti l’agente utente e l’indirizzo IP per il servizio di funzionalità utilizzato in Content Analytics. La stringa dell&#39;agente utente è `AdobeFeaturization/1.0`.
* Hai il ruolo Amministratore di prodotto Customer Journey Analytics, con le autorizzazioni aggiuntive per gestire le connessioni e le raccolte di dati. Le autorizzazioni Experience Platform richieste sono:

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

   * Il tuo sito è adatto per la generazione di rapporti sull&#39;esperienza? Una corretta generazione di rapporti sulle esperienze è possibile solo quando sono soddisfatte le seguenti condizioni:
      * Il contenuto del sito è gestito solo dagli URL.
      * Le pagine del sito sono riproducibili utilizzando l’URL della pagina e comprendi quali parametri URL facoltativi guidano le esperienze.
   * Hai una chiara comprensione delle pagine che desideri acquisire analisi e approfondimenti sul coinvolgimento dei contenuti.
   * Hai una chiara comprensione di quale (tipo di) risorsa desideri acquisire analisi e approfondimenti sul coinvolgimento dei contenuti.


>>
[!MORELIKETHIS]
>>
* [Controllo dell&#39;accesso](/help/technotes/access-control.md)
>


