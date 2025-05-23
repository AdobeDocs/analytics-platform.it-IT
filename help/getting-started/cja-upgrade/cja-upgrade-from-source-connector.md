---
title: Transizione dal connettore di origine di Analytics a Web SDK per Customer Journey Analytics
description: Scopri come passare al Web SDK dal connettore di origine di Analytics durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '527'
ht-degree: 100%

---

# Transizione dal connettore di origine di Analytics a Web SDK per Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Imlementazione del connettore di origine di Analytics"
>abstract="Il connettore di origine di Analytics consente di ottenere facilmente valore da Customer Journey Analytics, ma richiede il pagamento sia per Adobe Analytics che per Customer Journey Analytics. Questa guida consente di passare a un’implementazione indipendente di Web SDK."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="Eliminare il connettore di origine di Analytics esistente"
>abstract="Il connettore di origine di Analytics di cui disponi attualmente non è compatibile con lo schema personalizzato della tua organizzazione. Tuttavia, i dati esistono ancora nella suite di rapporti di Analytics. Questo passaggio rimuove il connettore di origine di Analytics corrente in modo da poterlo ricreare utilizzando lo schema corretto in un passaggio successivo.<br><br>Prima di eliminare il connettore di origine, puoi coordinarti con altri utenti dell’organizzazione per assicurarti che tale rimozione non influisca sul reporting all’interno della tua organizzazione. Questo coordinamento potrebbe richiedere diverse settimane per essere completato."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

L’utilizzo del connettore di origine di Analytics come unica implementazione per Customer Journey Analytics presenta alcuni svantaggi impliciti.

Se la tua organizzazione ha già effettuato l’aggiornamento a Customer Journey Analytics utilizzando solo l’implementazione del connettore di origine di Analytics, Adobe consiglia di passare a una nuova implementazione di Web SDK per la raccolta dati continua e di utilizzare il connettore di origine di Analytics solo per i dati storici.

## Comprendere vantaggi e svantaggi dell’utilizzo esclusivo del connettore di origine di Analytics

Per informazioni sui vantaggi e gli svantaggi dell’utilizzo del connettore di origine Analytics, consulta [Utilizzare il connettore di origine Analytics esclusivamente per l’aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

## Transizione dal connettore di origine di Analytics al Web SDK

Di seguito è riportato il processo di alto livello per la transizione dall’utilizzo esclusivo del connettore di origine Analytics a un’implementazione composta sia dal connettore di origine Analytics che da un’implementazione Web SDK:

1. Crea un’implementazione di Web SDK, come descritto in [Passaggi dettagliati consigliati per l’aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) nell’articolo [Aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Dopo aver configurato l’implementazione di Web SDK, continua con i passaggi seguenti.

1. [Crea uno schema XDM per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Mappa ogni dimensione di Adobe Analytics dal connettore di origine di Analytics alla dimensione nello schema di Web SDK.

   1. &#x200B;
      <!-- how do you get here -->

   1. Nella sezione **[!UICONTROL Map standard fields]**, seleziona la scheda **[!UICONTROL Custom]**.

   1. Seleziona **[!UICONTROL Add new mapping]**.

      ![mappa campi schema](assets/schema-mapping.png)

   1. Nel **[!UICONTROL Source field]**, seleziona un campo Adobe Analytics dal gruppo di campi del modello Adobe Analytics ExperienceEvent. Quindi, nel **[!UICONTROL Target field]**, seleziona il campo XDM a cui desideri mapparlo.

   1. Ripeti questa procedura per ogni campo del gruppo di campi Modello di Adobe Analytics ExperienceEvent che utilizzi per raccogliere dati in Adobe Analytics.

1. Aggiungi il set di dati creato automaticamente con il connettore di origine Analytics originale alla connessione Customer Journey Analytics.

   Per ulteriori informazioni, consulta [Aggiungere il set di dati dal connettore di origine Analytics corrente alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condizionale) Se utilizzi i set di dati di ricerca, devi creare il set di dati di ricerca e aggiungerlo alla connessione. Per ulteriori informazioni, consulta [Creare set di dati di ricerca per classificare i dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Elimina il connettore di origine originale di Analytics. <!-- need to add steps somewhere about how to do this -->

1. [Creare un nuovo connettore di origine di Analytics e mappare i campi](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

{{upgrade-final-step}}
