---
title: Visualizza le note sulla versione del Customer Journey Analytics corrente
description: Note sulla versione più recente di CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b2a6225d6f94b158e217df4963611cb6d55580e
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 89%

---

# Note sulla versione corrente di Customer Journey Analytics (CJA) (maggio 2022)

**Ultimo aggiornamento**: 28 luglio 2022

## Funzioni chiave

| Funzione | Descrizione | [Data definita](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Supporto di campi numerici come chiavi e valori di ricerca | Utile se desideri classificare i valori stringa con un campo numerico come i costi delle vendite o il margine su una SKU di prodotto. Consentire le metriche dalle ricerche ti aiuta a ottenere questi punti dati nel reporting. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it#numeric) | 20 luglio 2022 |
| Rapporti sulla sessione nuovi e ripetuti | Ora puoi scoprire se una particolare sessione è stata la prima di un utente in assoluto. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=it#new-repeat) | 17 agosto 2022 |
| Pannello Visualizzatori simultanei contenuti multimediali | Scopri dove si verificano picchi di concorrenza o abbandoni. Ottieni informazioni approfondite sulla qualità dei contenuti e sul livello di coinvolgimento dell’utente, utili anche per risolvere problemi o pianificare volumi e scala. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 31 agosto 2022 |
| Pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) | La funzione Tempo trascorso su contenuti multimediali di Media fornisce insight utili sul coinvolgimento degli utenti. Consente alle organizzazioni di media di ottenere informazioni più approfondite e dettagliate sul coinvolgimento degli utenti minuto per minuto attraverso un’analisi avanzata del tempo trascorso con funzionalità di ripartizione giornaliera. È possibile osservare il tempo impiegato per visualizzare i flussi multimediali in un determinato momento. Puoi suddividere la durata della riproduzione in base a diverse granularità, tra cui nuove granularità di 5, 15 e 30 minuti.  [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 31 agosto 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni

AN-288455; AN-288828; AN-289323

## Avvisi importanti per amministratori CJA

| Avviso | Avviso aggiunto o aggiornato | Descrizione |
| --- | --- | --- |
| **Mappatura IP-geolocalizzazione migliorata** | 11 luglio 2022 | Il fornitore di Adobe per le ricerche IP, Digital Element, sta effettuando l’aggiornamento a un nuovo set di dati migliorato (NetAcuity Pulse) per la mappatura IP-geolocalizzazione. Adobe Analytics adotterà questo nuovo set di dati nel **Ottobre 2022**, scadenzario. Il nuovo database sarà più accurato delle versioni precedenti. Alcune mappature IP-geolocalizzazione cambieranno/miglioreranno quando verrà adottato il nuovo database.<p> Anche i dati CJA forniti tramite il connettore origine di Analytics sfrutteranno automaticamente le nuove mappature. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics - Aggiornamenti della documentazione](/help/release-notes/doc-changes.md)
