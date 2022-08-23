---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e7ff0bfae0f7d041a8131cecbf362cf71aca9740
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 65%

---

# Note sulla versione del Customer Journey Analytics corrente (CJA) (agosto 2022)

**Ultimo aggiornamento**: 23 agosto 2022

## Funzioni chiave

| Funzione | Descrizione | [Data definita](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Pannello Visualizzatori simultanei di contenuti multimediali** | Scopri dove si verificano picchi di concorrenza o abbandoni. Ottieni informazioni approfondite sulla qualità dei contenuti e sul livello di coinvolgimento dell’utente, utili anche per risolvere problemi o pianificare volumi e scala. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=it) | 9 agosto 2022 |
| **Pannello Tempo trascorso su contenuti multimediali** | La funzione Tempo trascorso su contenuti multimediali fornisce insight utili sul coinvolgimento degli utenti. Consente alle organizzazioni di media di ottenere informazioni più approfondite e dettagliate sul coinvolgimento degli utenti minuto per minuto attraverso un’analisi avanzata del tempo trascorso con funzionalità di ripartizione giornaliera. È possibile osservare il tempo impiegato per visualizzare i flussi multimediali in un determinato momento. Puoi suddividere la durata della riproduzione in base a diverse granularità, tra cui nuove granularità di 5, 15 e 30 minuti.  [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=it) | 9 agosto 2022 |
| **Pubblicazione di tipi di pubblico su Real-time Customer Profile** | Consente di pubblicare i tipi di pubblico rilevati in CJA su Adobe Experience Platform/Profilo cliente in tempo reale per il targeting e la personalizzazione del cliente. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=it) | 17 agosto 2022 |
| **Supporto di CJA per etichette e criteri per la governance dei dati** | Automatizza l’integrazione tra le etichette e i criteri di privacy di CJA e Adobe Experience Platform. Le etichette dati create sui set di dati utilizzati da Platform vengono visualizzate nelle visualizzazioni dati di CJA per interrompere o avvisare gli utenti che creano metriche e/o dimensioni dai campi sensibili. Inoltre, quando i dati vengono esportati da CJA (tramite Workspace o reporting per Report Builder, esportazione, API, ecc.) verranno aggiunti avvisi o etichette aggiuntivi per avvisare gli utenti che un report contiene informazioni sensibili che devono essere trattate in un modo specifico. [Ulteriori informazioni](/help/data-views/data-governance.md) | 17 agosto 2022 |
| **Supporto del campo data in CJA** | Consente a CJA di creare rapporti sui campi data e ora. [Ulteriori informazioni](/help/data-views/data-views-usecases.md#date) | 17 agosto 2022 |
| **Supporto tra aree geografiche per il connettore origine di Analytics** | È ora possibile acquisire suite di rapporti da qualsiasi regione (Stati Uniti, Regno Unito o Singapore). Tuttavia, queste suite di rapporti devono essere mappate nella stessa organizzazione dell’istanza Sandbox di Experience Platform in cui viene creata la connessione sorgente. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) | 24 agosto 2022 |
| **Rapporti sulla sessione nuovi e ripetuti** | Ora puoi scoprire se una particolare sessione è stata la prima di un utente in assoluto. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) | 24 agosto 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni

AN-297141

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Mappatura IP-geolocalizzazione migliorata** | 11 luglio 2022 | Il fornitore di Adobe per le ricerche IP, Digital Element, sta effettuando l’aggiornamento a un nuovo set di dati migliorato (NetAcuity Pulse) per la mappatura IP-geolocalizzazione. Adobe Analytics adotterà questo nuovo set di dati nel **Ottobre 2022** scadenzario. Il nuovo database sarà più accurato delle versioni precedenti. Alcune mappature IP-geolocalizzazione cambieranno/miglioreranno quando verrà adottato il nuovo database.<p> Anche i dati CJA forniti tramite il connettore origine di Analytics sfrutteranno automaticamente le nuove mappature. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics - Aggiornamenti della documentazione](/help/release-notes/doc-changes.md)
