---
title: Dati di riepilogo
description: Dettagli e informazioni su come utilizzare e configurare i dati di riepilogo in una visualizzazione dati.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 9517d698acf41a25fa972ced32faa75de540a080
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 4%

---


# Dati di riepilogo

{{release-limited-testing}}

I dati di riepilogo sono dati di serie temporali che non sono legati a un singolo ID persona. I dati di riepilogo rappresentano i dati aggregati a un diverso livello di aggregazione, ad esempio le campagne. Puoi utilizzare questi dati in Customer Journey Analytics per supportare vari casi d’uso. Ad esempio, dati contenenti una data e un singolo valore di metrica, oppure dati contenenti più dimensioni e metriche.

Questi dati di riepilogo possono quindi essere utilizzati per presentare indicatori di prestazioni di alto livello o eseguire analisi. Esempi di dati di riepilogo possono essere impression pubblicitarie, aperture di e-mail, spese pubblicitarie, costo del bene venduto, indici S&amp;P e altro ancora. Puoi anche utilizzare i dati di riepilogo per caricare target o obiettivi su base oraria o giornaliera.

>[!NOTE]
>
>I dati di riepilogo sono dati di serie temporali provenienti da un set di dati di riepilogo. Tale set di dati di riepilogo è basato su uno schema che utilizza la classe Metriche di riepilogo XDM come classe base.
>Sono supportati solo i dati di serie temporali basati su ore o su giorni.

>[!TIP]
>
>Puoi configurare una connessione, una visualizzazione dati e successivamente generare un rapporto sui **soli** dati di riepilogo. Non è necessario disporre di dati di evento, profilo o ricerca aggiuntivi come parte della configurazione.


## Esempio

Un esempio di utilizzo dei dati di riepilogo è la combinazione dei dati riepilogati delle campagne pubblicitarie con i dati clickstream nel sito per la generazione di rapporti.

### Dati di riepilogo

I dati di riepilogo contengono i seguenti dati della campagna pubblicitaria.

| Codice campagna | Impressioni | Costo |
|---|---:|---:|
| abc123 | 1.250 | $ 1.500 |
| def456 | 775 | $ 650 |
| ghi789 | 500 | $ 500 |


### Dati evento

I dati clickstream nel sito contengono i seguenti eventi.

| Codice di tracciamento | Click-through | Ricavi |
|---|---:|---:|
| abc123 | 1.250 | $ 7.200 |
| def456 | 775 | $ 1.250 |
| ghi789 | 500 | $ 750 |

### Dati combinati

Come spiegato in [Set di dati evento combinato](/help/connections/combined-dataset.md), durante la definizione di una connessione, Customer Journey Analytics crea un set di dati evento combinato complessivo. Quando configuri la visualizzazione dati per le dimensioni provenienti da un set di dati di riepilogo, sono disponibili opzioni per raggruppare e nascondere le dimensioni in preparazione al reporting in Workspace. In particolare per i dati di riepilogo, i dati di riepilogo vengono combinati con i dati evento, in base alla configurazione del [componente gruppo di dati di riepilogo](component-settings/summary-data-group.md).

| Codice di tracciamento | Codice campagna | Impressioni | Costo | Click-through | Ricavi |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1.250 | $ 1.500 | 1.250 | $ 7.200 |
| def456 | def123 | 775 | $ 650 | 775 | $ 1.250 |
| ghi789 | ghi789 | 500 | $ 500 | 500 | $ 750 |



### Reporting

La combinazione dei dati riepilogati dell’evento e dei dati clickstream nel sito consente di generare rapporti in Workspace sul ritorno sulla spesa pubblicitaria (ROAS, return on ad spend).

| Codice di tracciamento | Impressioni | Costo | Click-through | Ricavi | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1.250 | $ 1.500 | 1.250 | $ 7.200 | 4,80 |
| def456 | 775 | $ 650 | 775 | $ 1.250 | 1,92 |
| ghi789 | 500 | $ 500 | 500 | $ 750 | 1,50 |


Consulta il caso d&#39;uso [Acquisire e generare rapporti sui dati di riepilogo](/help/use-cases/data-views/summary-data.md) per un articolo dettagliato su come utilizzare, creare rapporti e analizzare i dati di riepilogo nel Customer Journey Analytics.


## Prerequisiti

Per utilizzare correttamente i dati di riepilogo nei rapporti e nelle analisi, è necessario soddisfare una serie di prerequisiti. Nelle sezioni seguenti vengono descritti in dettaglio questi prerequisiti.

### Granularità e fuso orario

Quando configuri il set di dati contenente i dati di riepilogo in Customer Journey Analytics, noti che la granularità viene derivata automaticamente dai dati. Le selezioni per l&#39;elenco a discesa **[!UICONTROL Timestamp]** e **[!UICONTROL Timezone]** sono disabilitate in quanto derivano entrambe dalla definizione dello schema.

#### Granularità

Non è possibile combinare e abbinare la granularità oraria e giornaliera dei dati di riepilogo in un unico set di dati (o con set di dati diversi), utilizzando uno schema di dati di riepilogo. Ad esempio, se disponi di dati di riepilogo granulari giornalieri e orari per i dati della campagna pubblicitaria, sono necessari due schemi: uno per i dati di riepilogo giornalieri e uno per quelli orari. Quindi carica i dati granulari rilevanti nei set di dati associati allo schema appropriato (ad esempio, carica dati orari in un set di dati associato allo schema di dati di riepilogo orari).

#### Fuso orario

Il fuso orario dei dati di riepilogo è definito a livello di schema di riepilogo in Experience Platform. Il fuso orario si applica solo ai dati granulari orari.

- Per la granularità giornaliera, l’Experience Platform assume valori UTC, a meno che la marca temporale non includa uno scostamento di fuso orario. Quando si aggiunge il set di dati di riepilogo contenente i dati di riepilogo giornalieri, Customer Journey Analytics ignora la definizione del fuso orario impostata nello schema e rispetta il giorno associato alla marca temporale dai dati nel set di dati.
- Per la granularità oraria, il Customer Journey Analytics rispetta il fuso orario configurato nello schema dei dati di riepilogo nell’Experience Platform durante l’interpretazione della marca temporale. La tabella seguente fornisce alcuni esempi di tale interpretazione.

  | Timestamp <br/> dati di origine | Schema fuso orario <br/> | Timestamp<br/>Experience<br/>Platform | Dati<br/> fuso orario<br/>visualizzazione | Timestamp<br/>Cliente<br/>Percorso<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *GMT predefinito* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *GMT predefinito* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT predefinito* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *GMT predefinito* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 02/08/2024 | *GMT predefinito* | 02/08/2024 T00:00:00 | IST | 02/08/2024 T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  Per i fusi orari con uno scostamento di 30 minuti (ad esempio IST, Ora standard dell’India), lo scostamento di 30 minuti viene eliminato durante la generazione di rapporti sui dati di riepilogo. Ad esempio: 12:30 è indicato come 12:00.


Per garantire che venga utilizzato il fuso orario corretto per i dati di riepilogo granulari orari, è necessario assicurarsi che nello schema utilizzato per i dati di riepilogo sia configurato il fuso orario corretto.

Per configurare la granularità e il fuso orario per lo schema dei dati di riepilogo, è necessario utilizzare la seguente chiamata API in quanto non è disponibile un’interfaccia utente equivalente.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| Variabile | Valore |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Per ulteriori informazioni su come specificare i valori per queste variabili, vedere [Autenticare e accedere alle API Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication). |
| `$SCHEMA_ID` | Puoi trovare l’ID dello schema nell’interfaccia utente di Experience Platform. Seleziona lo schema di riepilogo dall&#39;elenco degli schemi e individua **[!UICONTROL API Usage]** > **[!UICONTROL Schema ID]** nel pannello di destra. Utilizza tale ID come valore. |
| `$GRANULARITY` | Specificare `hour` o `day` come valore. |
| `$TIMEZONE` | Specificare il valore dell&#39;identificatore del fuso orario corretto dalla colonna dell&#39;identificatore TZ nell&#39;[Elenco dei fusi orari del database TZ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Esempio: `America/Los_Angeles`. |

## Impostazioni del componente

Assicurati che le impostazioni dei componenti per un gruppo di dati di riepilogo siano le stesse. Per ulteriori dettagli, vedere [Impostazioni dei componenti del gruppo di dati di riepilogo](component-settings/summary-data-group.md#same-component-settings).

>[!MORELIKETHIS]
>
>Consulta l&#39;articolo [Acquisire e utilizzare dati di riepilogo](/help/use-cases/data-views/summary-data.md) per un esempio dettagliato di caso d&#39;uso su come utilizzare i dati di riepilogo e generare rapporti su di essi.