---
title: Confrontare i dati AA con i dati CJA
description: Scopri come confrontare i dati di Adobe Analytics con quelli del Customer Journey Analytics
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: bbeceb076e7f249f2c2b8f997bdf37f3dc839db8
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 95%

---

# Confrontare i dati di Adobe Analytics con i dati CJA

Quando l’organizzazione adotta CJA, potresti notare alcune differenze nei dati tra Adobe Analytics e CJA. Questo è normale e può verificarsi per diversi motivi. CJA è progettato per consentirti di migliorare alcune delle limitazioni ai dati in AA. Tuttavia, possono verificarsi discrepanze inaspettate/non previste. Questo articolo è progettato per aiutarti a diagnosticare e risolvere tali differenze in modo che tu e il tuo team possiate usare CJA senza problemi per l’integrità dei dati.

Supponiamo che tu abbia acquisito i dati di Adobe Analytics in AEP tramite il [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en), quindi ha creato una connessione CJA utilizzando questo set di dati.

![Flusso dei dati](assets/compare.png)

Successivamente, hai creato una visualizzazione dati e hai notato delle discrepanze con i risultati dei rapporti in Adobe Analytics, quando effettui rapporti su questi dati su CJA.

Di seguito sono riportati alcuni passaggi per confrontare i dati Adobe Analytics originali con quelli di Adobe Analytics attualmente in Customer Journey Analytics.

## Prerequisiti

* Assicurati che il set di dati di Analytics in AEP contenga dati per l’intervallo di date che stai esaminando.

* Assicurati che la suite di rapporti selezionata in Analytics corrisponda alla suite di rapporti che è stata acquisita in Adobe Experience Platform.

## Passaggio 1: eseguire la metrica Occorrenze in Adobe Analytics

La metrica [Occorrenze](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=it) mostra il numero di hit in cui una determinata dimensione è stata impostata o persistita.

1. In Analytics > [!UICONTROL Workspace], trascina l’intervallo di date su cui desideri creare un rapporto come dimensione in una [!UICONTROL Freeform] tabella.

1. La metrica [!UICONTROL Occurrences] viene applicata automaticamente a tale intervallo di date.

1. Salva questo progetto in modo da poterlo utilizzare nel confronto.

## Passaggio 2: confrontare i risultati con [!UICONTROL Total records by timestamps] in CJA

Ora confronta le [!UICONTROL Occurrences] in Analytics con i record totali per marca temporale in Customer Journey Analytics.

I record totali per marca temporale devono corrispondere alle occorrenze, purché nessun record sia stato rilasciato dal connettore di origine di Analytics - vedi la sezione seguente.

>[!NOTE]
>
>Questo funziona solo per i set di dati con valori medi regolari, non per i set di dati con unione (tramite [Cross-Channel Analytics](/help/connections/cca/overview.md)). Tieni presente che la contabilizzazione dell’ID persona utilizzato in CJA è fondamentale per il corretto funzionamento del confronto. Potrebbe non essere sempre facile replicarlo in AA, specialmente se Cross-Channel Analytics è stato attivato.

1. Da [Servizi di query](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=it) di Adobe Experience Platform, esegui la seguente [!UICONTROL Total Records by timestamps] query:

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. In [Feed dati di Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it), identifica se alcune righe potrebbero essere state eliminate dal connettore di origine di Analytics.

   Il [Connettore origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) potrebbe rilasciare righe durante la trasformazione in schema XDM. Ci possono essere diversi motivi per cui l’intera riga è inadatta alla trasformazione. Se uno dei seguenti campi di Analytics contiene questi valori, l’intera riga verrà eliminata.

   | Campo Analytics | Valori che ne causano l’eliminazione |
   | --- | --- |
   | Opt_out | `y, Y` |
   | In_data_only | Not 0 |
   | Exclude_hit | No 0 |
   | Bot_id | No 0 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 53,63 |

1. Se il connettore ha rilasciato delle righe, sottrarle dalla metrica [!UICONTROL Occurrences]. Il numero risultante deve corrispondere al numero di eventi nei set di dati Adobe Experience Platform.

## Perché i record potrebbero essere ignorati o saltati durante l’acquisizione da AEP

CJA [Connessioni](/help/connections/create-connection.md) ti consente di unire più set di dati in base a un ID persona comune nei set di dati. Sul back-end, si applica la deduplicazione: join esterno completo o unione su set di dati evento basati su marche temporali, quindi join interno su un set di dati di profilo e di ricerca, in base all’ID persona.

Ecco alcuni dei motivi per cui i record potrebbero essere ignorati durante l’acquisizione di dati da AEP.

* **Marca temporale mancante** - Se le marche temporali non sono presenti nei set di dati dell’evento, questi verranno completamente ignorati o saltati durante l’acquisizione.

* **ID persona mancanti** - Gli ID persona mancanti (dal set di dati degli eventi e/o dal set di dati profilo/ricerca) fanno sì che tali record vengano ignorati o saltati. Il motivo è che non esistono ID comuni o chiavi corrispondenti per unire i record.

* **ID persona non validi o grandi** - Con ID non validi, il sistema non può trovare un ID comune valido tra i set di dati da unire. In alcuni casi, la colonna ID persona presenta ID persona non validi, ad esempio “non definito” o “00000000”. Un ID persona (con qualsiasi combinazione di numeri e lettere) visualizzato in un evento più di 1 milione di volte al mese non può essere attribuito a un utente o a una persona specifica. Verrà classificato come non valido. Tali record non possono essere acquisiti nel sistema e causare l’inserimento e la generazione di rapporti soggetti a errori.