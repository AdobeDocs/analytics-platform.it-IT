---
title: Libreria JavaScript di Content Analytics
description: Scopri come configurare Content Analytics senza utilizzare i tag di raccolta dati di Experience Platform e utilizzare invece la libreria JavaScript di Content Analytics.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
autotag-review: '2026-05-19T06:56:34.440Z'
TQID: 'https://experienceleague.adobe.com/GUYf0ZoTlAkoIIPWzfZTm0-eMvBjN8ieYSu6goHu3GA'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 484
ht-degree: 4%

---


# Libreria JavaScript di Content Analytics

La libreria JavaScript di Adobe Content Analytics consente il tracciamento di eventi relativi ai contenuti sui siti web inviando dati sui contenuti a Adobe Experience Platform tramite Experience Platform Edge Network. Utilizza questa libreria per implementare Content Analytics senza i tag Adobe Experience Platform.

>[!NOTE]
>
>Questo articolo si applica a Content Analytics per il canale web.


>[!PREREQUISITES]
>
>* È necessario inizializzare Adobe Experience Platform Web SDK (Alloy) nella pagina prima di chiamare `initializeContentLibrary`.
>* Completa la configurazione guidata di Content Analytics per conoscere tutti i passaggi necessari per impostare i prerequisiti per una configurazione di Content Analytics.
>* Al termine della configurazione guidata, le impostazioni JavaScript sono disponibili per l’uso.


## Installazione

È possibile installare la libreria in due modi:

### pacchetto npm

Utilizza `npm` per installare la libreria.

1. Nella riga di comando, utilizza:

   ```bash
   npm install @adobe/content-analytics
   ```

1. Importa la libreria:

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### Tag script (CDN)

Carica la libreria direttamente dal CDN.

1. Inizializza la [libreria Web SDK JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library) e carica il bundle Content Analytics:

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   dove
   * `alloy/2.x.x` fa riferimento alla versione che si desidera utilizzare della [libreria Web SDK JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library).
   * `content-analytics/1.x.x` fa riferimento alla versione che si desidera utilizzare della libreria SDK di Content Analytics.

2. La compilazione autonoma espone `window.contentAnalytics` come funzione di inizializzazione.


## Configurazione dello stream di dati

L&#39;opzione `datastreamId` è obbligatoria e deve fare riferimento a un datastream in cui il servizio Experience Platform è configurato con un set di dati evento esperienza Content Analytics abilitato. Assicurati che la sandbox associata allo stream di dati non sia già associata a un’altra configurazione di Content Analytics.

Puoi fornire ID dello stream di dati separati per ambiente:

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## Acquisizione e definizione dell’esperienza

Abilita il tracciamento dell’esperienza e controlla come le esperienze vengono identificate sul tuo sito web. Le esperienze sono definite combinando un&#39;**espressione regolare di dominio** con **parametri di query** facoltativi che distinguono un&#39;esperienza da un&#39;altra nelle pagine corrispondenti.

| Opzione | Tipo | Impostazione predefinita | Descrizione |
|--------|------|---------|-------------|
| `includeExperiences` | booleano | `false` | Abilita tracciamento visualizzazione pagina/esperienza |
| `experienceConfigurations` | array | - | Definire le esperienze per dominio, regex e parametri di query |

Ogni voce in `experienceConfigurations` accetta:

| Proprietà | Tipo | Descrizione |
|----------|------|-------------|
| `regEx` | string | Espressione regolare del dominio corrispondente all&#39;URL della pagina (esempio: `^(?!.*\b(store\|help\|admin)\b)`) |
| `queryParameters` | array | Nomi di parametri di query i cui valori distinguono le esperienze nelle pagine corrispondenti (esempio: `["outdoors", "patio", "kitchen"]`) |

### Esempio

Di seguito trovi un esempio di come abilitare il tracciamento dell’esperienza con i parametri regex di dominio e query.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## Filtro eventi

Controlla quali URL di pagina e URL di risorsa sono inclusi nella raccolta dati utilizzando espressioni regolari. Utilizza gli esempi di pattern riportati di seguito come punto di partenza e convalidali con un regex tester prima della distribuzione.

| Opzione | Tipo | Impostazione predefinita | Descrizione |
|--------|------|---------|-------------|
| `pageUrlQualifier` | stringa (regex) | - | Tieni traccia solo delle pagine il cui URL corrisponde a questo pattern |
| `assetUrlQualifier` | stringa (regex) | - | Tieni traccia solo delle risorse il cui URL corrisponde a questo pattern |
| `excludeURLsFromTracking` | array | `[]` | Elenco di stringhe URL da escludere dal tracciamento |

### Esempio

Di seguito è riportato un esempio di come escludere le pagine della documentazione da Content Analytics e considerare solo le immagini dei prodotti per Content Analytics.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```
