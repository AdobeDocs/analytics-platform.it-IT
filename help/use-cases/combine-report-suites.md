---
title: Combinare suite di rapporti con schemi diversi
description: Scopri come utilizzare Preparazione dati per combinare suite di rapporti con schemi diversi
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '1335'
ht-degree: 3%

---

# Combinare suite di rapporti con schemi diversi

La [Connettore sorgente di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) porta i dati della suite di rapporti da Adobe Analytics in Adobe Experience Platform (AEP) per l’utilizzo da parte di applicazioni AEP, come Real-time Customer Data Platform e Customer Journey Analytics (CJA). Ogni suite di rapporti portata in AEP è configurata come flusso di dati di connessione sorgente individuale e ogni flusso di dati arriva come un set di dati all’interno del lago di dati AEP. Il connettore origine Analytics crea un set di dati per suite di rapporti.

I clienti CJA utilizzano [connessioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it) per integrare i set di dati da AEP data lake nell’Analysis Workspace di CJA. Tuttavia, quando si combinano suite di rapporti all’interno di una connessione, è necessario risolvere le differenze di schema tra suite di rapporti utilizzando AEP [Preparazione dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) funzionalità. Lo scopo è garantire che le variabili di Adobe Analytics come prop ed eVar abbiano un significato coerente in CJA.

## Le differenze di schema tra le suite di rapporti sono problematiche

Supponiamo che la tua azienda voglia inserire in AEP i dati provenienti da due suite di rapporti diverse e utilizzarli da CJA, e che gli schemi per le due suite di rapporti presentino differenze:

| Suite di rapporti A | Suite di rapporti B |
| --- | --- |
| eVar1 = termine di ricerca | eVar1 = Business Unit |
| eVar2 = categoria cliente | eVar2 = termine di ricerca |

Per semplicità, supponiamo che queste siano le uniche eVar definite per entrambe le suite di rapporti.

Supponiamo inoltre di eseguire le seguenti azioni:

- Creare una connessione sorgente di Analytics (senza l’uso di data prep) che acquisisce **Suite di rapporti A** in AEP data lake come **Set di dati A**.
- Creare una connessione sorgente di Analytics (senza l’uso di data prep) che acquisisce **Suite di rapporti B** in AEP data lake come **Set di dati B**.
- Crea un [Connessione CJA](/help/connections/create-connection.md) chiamato **Tutte le suite di rapporti** che combina il set di dati A e il set di dati B.
- Crea un [Visualizzazione dati CJA](/help/data-views/create-dataview.md) chiamato **Visualizzazione globale** in base alla connessione Tutte le suite di rapporti.

Senza l’utilizzo di Data Prep per risolvere le differenze di schema tra il set di dati A e il set di dati B, le eVar nella visualizzazione dati Visualizzazione globale conterranno una combinazione di valori:

| Visualizzazione dati globale in CJA |
| --- |
| eVar1 => un mix di termini di ricerca e business unit |
| eVar2 => un mix di categorie di clienti e termini di ricerca |

Questa situazione si traduce in relazioni insignificanti per eVar1 e eVar2:

- I campi di eVar contengono una miscela di valori con significati semantici diversi.
- I termini di ricerca sono distribuiti tra eVar1 e eVar2.
- Non è possibile utilizzare modelli di attribuzione diversi per ciascun termine di ricerca, business unit e categorie di clienti.

## Utilizzare la preparazione dati AEP per risolvere le differenze di schema tra le suite di rapporti

La funzionalità Preparazione dei dati di Experience Platform è integrata con il connettore origine di Analytics e può essere utilizzata per risolvere le differenze di schema descritte nello scenario precedente. Questo si traduce in eVar con significati coerenti nella visualizzazione dati di CJA. Le convenzioni di denominazione utilizzate di seguito possono essere personalizzate in base alle tue esigenze.

1. Prima di creare i flussi di dati della connessione sorgente per Report Suite A e Report Suite B, [Creare un nuovo schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) in AEP (lo chiameremo **Schema unificato** nel nostro esempio). Aggiungi quanto segue allo schema:

   | &quot;Schema unificato&quot; |
   | --- |
   | **ExperienceEvent XDM** Classe |
   | **Modello di Adobe Analytics ExperienceEvent** gruppo di campi |

1. Aggiungi un altro gruppo di campi allo schema o [creare un gruppo di campi personalizzato](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) e aggiungerlo allo schema. Creeremo un nuovo gruppo di campi e lo chiameremo **Campi unificati**. Quindi aggiungeremo i seguenti campi al nuovo gruppo di campi:

   | Gruppo di campi personalizzati &quot;Campi unificati&quot;  |
   | --- |
   | Termine di ricerca |
   | Business Unit |
   | Categoria cliente |

1. Crea il flusso di dati della connessione sorgente per **Suite di rapporti A**, selezionando **Schema unificato** da utilizzare nel flusso di dati. Aggiungi mappature personalizzate al flusso di dati come segue:

   | Suite di rapporti Un campo sorgente | Campo di destinazione dal gruppo di campi Campi unificati |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >Il percorso XDM per i campi di destinazione dipenderà dalla struttura del gruppo di campi personalizzato.

1. Crea il flusso di dati della connessione sorgente per **Suite di rapporti B**, selezionando nuovamente **Schema unificato** da utilizzare nel flusso di dati. Il flusso di lavoro mostrerà che due campi hanno un conflitto di nome del descrittore. Questo perché i descrittori per eVar1 e eVar2 sono diversi nella suite di rapporti B rispetto alla suite di rapporti A. Ma lo sappiamo già, così possiamo tranquillamente ignorare il conflitto e utilizzare mappature personalizzate come segue:

   | Campo di origine della suite di rapporti B | Campo di destinazione dal gruppo di campi Campi unificati |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_ Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Ora crea un **Tutte le suite di rapporti** connessione per CJA, che combina il set di dati A e il set di dati B.

1. Crea un **Vista globale** visualizzazione dati in CJA. Ignorare i campi di eVar originali e includere solo i campi del gruppo di campi Campi unificati.

   **Visualizzazione globale** visualizzazione dati in CJA:

   | Campo di origine | Includi nella visualizzazione dati? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\&lt;path>_.Search_term | Sì |
   | _\&lt;path>_.Customer_category  | Sì |
   | _\&lt;path>_ Business_unit | Sì |

Ora hai mappato eVar1 e eVar2 dalle suite di rapporti di origine a tre nuovi campi. Un altro vantaggio dell’utilizzo delle mappature Preparazione dati è che i campi di destinazione ora si basano su nomi significativi dal punto di vista semantico (termine di ricerca, Business Unit, categoria Cliente) invece dei nomi eVar meno significativi (eVar1, eVar2).

>[!NOTE]
>
>Il gruppo di campi personalizzati Campi unificati e le mappature dei campi associati possono essere aggiunte ai flussi di dati e ai set di dati esistenti del connettore di origine di Analytics in qualsiasi momento. Tuttavia, questo influisce solo sui dati in futuro.

## Più che semplici suite di rapporti

Le funzionalità di Preparazione dei dati per combinare i set di dati con schemi diversi vanno oltre le suite di rapporti di Analytics. Supponiamo di disporre di due set di dati contenenti i dati seguenti:

| Set di dati A = suite di rapporti di Analytics tramite Connettore origine Analytics |
| --- |
| `eVar1` => Categoria cliente |

| Set di dati B = dati del call center |
| --- |
| Some_field => Categoria cliente |

Utilizzando Preparazione dati, puoi combinare la categoria cliente in eVar 1 nei dati di Analytics con la categoria cliente in Some_field nei dati del call center. Ecco un modo in cui potresti farlo. Anche in questo caso, la convenzione di denominazione può essere modificata in base alle tue esigenze.

1. Crea uno schema in AEP. Aggiungi quanto segue allo schema:

   | &quot;Schema esteso&quot; |
   | --- | 
   | **Evento esperienza XDM** Classe |
   | **Modello evento di Adobe Analytics Experience** gruppo di campi |

1. Crea un nuovo gruppo di campi e aggiungilo allo schema. Aggiungi campi al gruppo di campi:

   | Gruppo di campi personalizzati &quot;Informazioni cliente&quot;  |
   | --- |
   | Categoria_cliente |

1. Crea il flusso di dati per **Set di dati A**, selezionando **Schema esteso** come schema. Aggiungi mappature personalizzate al flusso di dati come segue:

   | Set di dati Un campo di origine | Campo di destinazione dal gruppo di campi Informazioni cliente |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Crea il flusso di dati per **Set di dati B**, selezionando nuovamente **Schema esteso** come schema. Aggiungi mappature personalizzate al flusso di dati come segue:

   | Campo origine del set di dati B | Campo di destinazione dal gruppo di campi Informazioni cliente |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. Crea una connessione CJA che combina il set di dati A e il set di dati B.

1. Crea una visualizzazione dati in CJA, utilizzando la connessione CJA appena creata. Ignorare i campi di eVar originali e includere solo i campi del gruppo di campi Informazioni cliente.

   Visualizzazione dati in CJA:

   | Campo di origine | Includi nella visualizzazione dati? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\&lt;path>_.Customer_category | Sì |

## Preparazione dei dati e ID componente

Come descritto in precedenza, Data Prep ti consente di mappare diversi campi tra loro in più suite di rapporti di Adobe Analytics. Questa funzione è utile in CJA quando desideri combinare dati provenienti da più set di dati in un’unica connessione CJA. Tuttavia, se desideri mantenere le suite di rapporti in connessioni CJA separate ma desideri utilizzare un set di rapporti tra tali connessioni e visualizzazioni dati, la modifica dell’ID componente sottostante in CJA consente di rendere i rapporti compatibili anche se gli schemi sono diversi. Vedi [Impostazioni dei componenti](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) per ulteriori informazioni.

La modifica dell’ID componente è una funzione solo CJA e non influisce sui dati provenienti dal connettore origine di Analytics che viene inviato a Profilo cliente in tempo reale e RTCDP.
