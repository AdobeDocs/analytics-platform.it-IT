---
title: Combinare suite di rapporti con schemi diversi
description: Scopri come utilizzare la preparazione dati per combinare suite di rapporti con schemi diversi
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 57%

---

# Combinare suite di rapporti con schemi diversi

Il [Connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it) inserisce i dati della suite di rapporti di Adobe Analytics in Adobe Experience Platform per l’utilizzo da parte di applicazioni Adobe Experience Platform, come Real-time Customer Data Platform e Customer Journey Analytics (Customer Journey Analytics). Ogni suite di rapporti introdotta in Adobe Experience Platform è configurata come flusso di dati di connessione di origine individuale e ogni flusso di dati arriva come un set di dati all’interno del data lake di Adobe Experience Platform. Il connettore di origine di Analytics crea un set di dati per suite di rapporti.

Customer Journey Analytics utilizzato dai clienti [connessioni](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it) integrare i set di dati dal data lake di Adobe Experience Platform in Customer Journey Analytics Analysis Workspace. Tuttavia, quando si combinano suite di rapporti all’interno di una connessione, è necessario risolvere le differenze di schema tra suite di rapporti utilizzando Adobe Experience Platform [Preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it) funzionalità. Lo scopo è garantire che le variabili di Adobe Analytics come prop ed eVar abbiano un significato coerente nel Customer Journey Analytics.

## Le differenze di schema tra le suite di rapporti sono problematiche

Supponiamo che la tua azienda desideri inserire in Adobe Experience Platform i dati provenienti da due suite di rapporti diverse per l’utilizzo per Customer Journey Analytics e che gli schemi delle due suite di rapporti presentino delle differenze:

| Suite di rapporti A | Suite di rapporti B |
| --- | --- |
| eVar1 = termine di ricerca | eVar1 = business unit |
| eVar2 = categoria di clienti | eVar2 = termine di ricerca |

Per semplicità, supponiamo che queste siano le uniche eVar definite per entrambe le suite di rapporti.

Supponiamo inoltre di eseguire le seguenti azioni:

- Creare una connessione di origine di Analytics (senza l’utilizzo della preparazione dati) che acquisisce **Suite di rapporti A** nel data lake di Adobe Experience Platform come **Set di dati A**.
- Creare una connessione di origine di Analytics (senza l’utilizzo della preparazione dati) che acquisisce **Suite di rapporti B** nel data lake di Adobe Experience Platform come **Set di dati B**.
- Creare un [Connessione Customer Journey Analytics](/help/connections/create-connection.md) ha chiamato **Tutte le suite di rapporti** che combina il Set di dati A e il Set di dati B.
- Creare un [Visualizzazione dati Customer Journey Analytics](/help/data-views/create-dataview.md) ha chiamato **Vista globale** basato sulla connessione Tutte le suite di rapporti.

Senza l’utilizzo della preparazione dati per risolvere le differenze di schema tra il Set di dati A e il Set di dati B, le eVar nella visualizzazione dati denominata Visualizzazione globale conterranno una combinazione di valori:

| Visualizzazione globale nel Customer Journey Analytics |
| --- |
| eVar1 => una combinazione di termini di ricerca e business unit |
| eVar2 => una combinazione di categorie di clienti e termini di ricerca |

Questa situazione comporta rapporti privi di significato per eVar1 e eVar2:

- I campi eVar contengono una combinazione di valori con significati semantici diversi.
- I termini di ricerca sono distribuiti tra eVar1 e eVar2.
- Non è possibile utilizzare modelli di attribuzione diversi per ciascun termine di ricerca, business unit e categoria di clienti.

## Utilizzare la preparazione dati di Adobe Experience Platform per risolvere le differenze di schema tra le suite di rapporti

La funzionalità di preparazione dati di Experience Platform è integrata con il connettore di origine di Analytics e può essere utilizzata per risolvere le differenze di schema descritte nello scenario precedente. Questo determina eVar con significati coerenti nella visualizzazione dati del Customer Journey Analytics. Le convenzioni di denominazione utilizzate di seguito possono essere personalizzate in base alle esigenze.

1. Prima di creare i flussi di dati della connessione di origine per le suite di rapporti A e B, [Crea un nuovo schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it) in Adobe Experience Platform (lo chiameremo **Schema unificato** nel nostro esempio.) Aggiungi quanto segue allo schema:

   | “Schema unificato” |
   | --- |
   | Classe **XDM ExperienceEvent** |
   | Gruppo di campi **Modello Adobe Analytics ExperienceEvent** |

1. Aggiungi un altro gruppo di campi allo schema o [creare un gruppo di campi personalizzato](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) e aggiungilo allo schema. Creeremo un nuovo gruppo di campi e lo chiameremo **Campi unificati**, quindi aggiungeremo i seguenti campi al nuovo gruppo di campi:

   | Gruppo di campi personalizzato “Campi unificati”  |
   | --- |
   | Termine di ricerca |
   | Business unit |
   | Categoria di clienti |

1. Crea il flusso di dati della connessione di origine per la **Suite di rapporti A**, selezionando lo **Schema unificato** da utilizzare nel flusso di dati. Aggiungi mappature personalizzate al flusso di dati come segue:

   | Campo di origine Suite di rapporti A | Campo di destinazione dal gruppo di campi Campi unificati |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >Il percorso XDM per i campi di destinazione dipenderà dalla struttura del gruppo di campi personalizzato.

1. Crea il flusso di dati della connessione di origine per la **Suite di rapporti B**, selezionando nuovamente lo **Schema unificato** da utilizzare nel flusso di dati. Il flusso di lavoro mostrerà che due campi hanno un conflitto relativo al nome del descrittore. Ciò accade perché i descrittori di eVar1 e eVar2 sono diversi nella suite di rapporti B rispetto alla suite di rapporti A. Tuttavia lo sappiamo già, quindi possiamo tranquillamente ignorare il conflitto e utilizzare mappature personalizzate come segue:

   | Campo di origine Suite di rapporti B | Campo di destinazione dal gruppo di campi Campi unificati |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Ora crea un’ **Tutte le suite di rapporti** per il Customer Journey Analytics, combinando il Set di dati A e il Set di dati B.

1. Creare un **Vista globale** visualizzazione dati nel Customer Journey Analytics. Ignora i campi eVar originali e includi solo i campi del gruppo Campi unificati.

   **Vista globale** visualizzazione dati nel Customer Journey Analytics:

   | Campo di origine | Includere nella visualizzazione dati? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\&lt;path>_.Search_term | Sì |
   | _\&lt;path>_.Customer_category  | Sì |
   | _\&lt;path>_.Business_unit | Sì |

Ora hai mappato eVar1 e eVar2 delle suite di rapporti di origine su tre nuovi campi. Un altro vantaggio dell’utilizzo delle mappature della preparazione dati è che i campi di destinazione si basano ora su nomi significativi dal punto di vista semantico (termine di ricerca, business unit, categoria di clienti) invece dei meno significativi nomi eVar (eVar1, eVar2).

>[!NOTE]
>
>Il gruppo di campi personalizzato Campi unificati e le mappature dei campi associate possono essere aggiunti ai flussi di dati e ai set di dati del connettore di origine di Analytics esistenti in qualsiasi momento. Tuttavia, questo influisce solo sui dati futuri.

## Più di semplici suite di rapporti

Le funzionalità della preparazione dati per la combinazione di set di dati con schemi diversi vanno oltre le suite di rapporti di Analytics. Supponiamo di disporre di due set di dati contenenti i dati seguenti:

| Set di dati A = suite di rapporti di Analytics tramite il connettore di origine di Analytics |
| --- |
| `eVar1` => categoria di clienti |

| Set di dati B = dati del call center |
| --- |
| Some_field => categoria di clienti |

Utilizzando la preparazione dati, puoi combinare la categoria di clienti in eVar 1 nei dati di Analytics con la categoria di clienti in Some_field nei dati del call center. Di seguito è riportato un modo in cui potresti farlo. Anche in questo caso, la convenzione di denominazione può essere modificata in base alle tue esigenze.

1. Crea uno schema in Adobe Experience Platform. Aggiungi quanto segue allo schema:

   | “Schema esteso” |
   | --- | 
   | Classe **XDM Experience Event** |
   | Gruppo di campi **Modello Adobe Analytics Experience Event** |

1. Crea un nuovo gruppo di campi e aggiungilo allo schema. Aggiungi dei campi al gruppo di campi:

   | Gruppo di campi personalizzato “Informazioni cliente”  |
   | --- |
   | Customer_category |

1. Crea il flusso di dati per il **Set di dati A**, selezionando **Schema esteso** come schema. Aggiungi mappature personalizzate al flusso di dati come segue:

   | Campo di origine del Set di dati A | Campo di destinazione dal gruppo di campi Informazioni cliente |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Crea il flusso di dati per il **Set di dati B**, selezionando nuovamente **Schema esteso** come schema. Aggiungi mappature personalizzate al flusso di dati come segue:

   | Campo origine del Set di dati B | Campo di destinazione dal gruppo di campi Informazioni cliente |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. Creare una connessione di Customer Journey Analytics che combina il Set di dati A e il Set di dati B.

1. Creare una visualizzazione dati in Customer Journey Analytics utilizzando la connessione di Customer Journey Analytics appena creata. Ignora i campi eVar originali e includi solo i campi del gruppo Informazioni cliente.

   Visualizzazione dati nel Customer Journey Analytics:

   | Campo di origine | Includere nella visualizzazione dati? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\&lt;path>_.Customer_category | Sì |

## Preparazione dati e ID componente

Come descritto in precedenza, la preparazione dati ti consente di mappare diversi campi tra loro in più suite di rapporti di Adobe Analytics. Questa funzione è utile in Customer Journey Analytics quando desideri combinare dati provenienti da più set di dati in una singola connessione di Customer Journey Analytics. Tuttavia, se desideri mantenere le suite di rapporti in connessioni di Customer Journey Analytics separate, ma desideri utilizzare un set di rapporti su tali connessioni e visualizzazioni dati, la modifica dell’ID componente sottostante nel Customer Journey Analytics consente di rendere i rapporti compatibili anche se gli schemi sono diversi. Consulta [Component Settings](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html) (Impostazioni dei componenti) per ulteriori informazioni.

La modifica dell’ID componente è una funzione esclusiva del Customer Journey Analytics e non influisce sui dati provenienti dal connettore di origine di Analytics che vengono inviati a Real-time Customer Profile e RTCDP.
