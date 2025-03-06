---
title: Transizione dal connettore di origine di Analytics a Web SDK per Customer Journey Analytics
description: Scopri come passare al Web SDK dal connettore di origine di Analytics durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 773c03dfec99abcabdc667c549cce0dc1b1aabc4
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 13%

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
>title="Elimina il connettore di origine Analytics esistente"
>abstract="Il connettore di origine di Analytics di cui disponi non è compatibile con lo schema personalizzato della tua organizzazione. Tuttavia, i dati esistono ancora nella suite di rapporti di Analytics. Questo passaggio rimuove il connettore di origine Analytics corrente in modo da poterlo ricreare utilizzando lo schema corretto in un passaggio successivo.<br><br>Prima di eliminare il connettore di origine, è possibile coordinarsi con altri utenti dell&#39;organizzazione per assicurarsi che la rimozione del connettore di origine non influisca sulla creazione di rapporti all&#39;interno dell&#39;organizzazione. Questo coordinamento potrebbe richiedere diverse settimane per essere completato."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

L’utilizzo del connettore di origine di Analytics come unica implementazione per Customer Journey Analytics presenta alcuni svantaggi intrinseci.

Se la tua organizzazione ha già effettuato l’aggiornamento a Customer Journey Analytics utilizzando solo l’implementazione del connettore di origine di Analytics, Adobe consiglia di passare a una nuova implementazione del SDK web per la raccolta dati continua e di utilizzare il connettore di origine di Analytics solo per i dati storici.

## Comprendere vantaggi e svantaggi dell’utilizzo esclusivo del connettore di origine di Analytics

Per informazioni sui vantaggi e gli svantaggi dell&#39;utilizzo del connettore di origine Analytics, vedere [Utilizzare il connettore di origine Analytics esclusivamente per l&#39;aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

## Transizione dal connettore di origine di Analytics al Web SDK

Di seguito è riportato il processo di alto livello per la transizione dall’utilizzo esclusivo del connettore di origine Analytics a un’implementazione composta sia dal connettore di origine Analytics che da un’implementazione Web SDK:

1. Creare un&#39;implementazione di Web SDK, come descritto in [Passaggi dettagliati consigliati per l&#39;aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) nell&#39;articolo [Aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   Dopo aver configurato l’implementazione di Web SDK, continua con i passaggi seguenti.

1. [Creare uno schema XDM per il connettore di origine di Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Mappa ogni dimensione di Adobe Analytics dal connettore di origine di Analytics alla dimensione nello schema di Web SDK.

   1. 
      <!-- how do you get here -->

   1. Nella sezione **[!UICONTROL Map standard fields]** selezionare la scheda **[!UICONTROL Custom]**.

   1. Seleziona **[!UICONTROL Add new mapping]**.

      ![mappa campi schema](assets/schema-mapping.png)

   1. In **[!UICONTROL Source field]**, selezionare un campo Adobe Analytics dal gruppo di campi Modello Adobe Analytics ExperienceEvent. Quindi, in **[!UICONTROL Target field]**, seleziona il campo XDM a cui vuoi mappare.

   1. Ripeti questa procedura per ogni campo del gruppo di campi Modello Adobe Analytics ExperienceEvent che utilizzi per raccogliere dati in Adobe Analytics.

1. Aggiungi il set di dati creato automaticamente con il connettore di origine Analytics originale alla connessione Customer Journey Analytics.

   Per ulteriori informazioni, consulta [Aggiungere il set di dati dal connettore di origine Analytics corrente alla connessione](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Condizionale) Se utilizzi i set di dati di ricerca, devi creare il set di dati di ricerca e aggiungerlo alla connessione. Per ulteriori informazioni, vedere [Creare set di dati di ricerca per classificare i dati in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Elimina il connettore di origine originale di Analytics. <!-- need to add steps somewhere about how to do this -->

1. [Crea un nuovo connettore di origine Analytics e mappa i campi](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
