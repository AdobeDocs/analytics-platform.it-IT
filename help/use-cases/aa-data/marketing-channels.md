---
title: Usa dimensioni canale di marketing
description: Scopri come utilizzare il connettore di origine di Analytics per inserire regole di elaborazione del canale di marketing in Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 49%

---

# Utilizzare le dimensioni del canale di marketing

Se la tua organizzazione utilizza il [connettore di origine Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics) per inserire in Customer Journey Analytics i dati della suite di rapporti, puoi configurare una connessione in Customer Journey Analytics per ottenere rapporti sulle dimensioni del canale di marketing.

>[!IMPORTANT]
>
>Per informazioni sulle dimensioni del canale di marketing, consulta i [Campi derivati - Modello canali di marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) per la funzionalità nativa del prodotto.
>


## Prerequisiti

* I dati della suite di rapporti devono essere già importati in Adobe Experience Platform utilizzando il [connettore di origine Analytics](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics). Non sono supportate altre origini di dati, poiché i canali di marketing si basano sulle regole di elaborazione di una suite di rapporti di Analytics.
* Le regole di elaborazione del canale di marketing devono già essere configurate. Vedi [Regole di elaborazione per i canali di marketing](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules) nella guida dei componenti di Adobe Analytics.

## Elementi schema del canale di marketing

Una volta stabilito il connettore di origine di Analytics per la suite di rapporti desiderata, viene creato uno schema XDM. Tale schema contiene tutte le dimensioni e le metriche di Analytics come dati non elaborati, che non contengono attribuzione né persistenza. Piuttosto, ogni evento viene eseguito tramite le regole di elaborazione del canale di marketing e registra la prima regola corrispondente. Puoi specificare attribuzione e persistenza durante la creazione di una visualizzazione dati in Customer Journey Analytics.

1. [Crea una connessione](/help/connections/create-connection.md) che includa un set di dati basato sul connettore di origine di Analytics.
2. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) che includa le dimensioni seguenti:
   * **`channel.typeAtSource`**: equivalente alla dimensione [Canale di marketing](https://experienceleague.adobe.com/it/docs/analytics/components/dimensions/marketing-channel).
   * **`channel._id`**: equivalente ai [dettagli del canale di marketing](https://experienceleague.adobe.com/it/docs/analytics/components/dimensions/marketing-detail)
3. Assegna a ciascuna dimensione il modello di attribuzione e la persistenza desiderati. Se desideri entrambe le dimensioni Primo contatto e Ultimo contatto, trascina più volte ciascuna dimensione del canale di marketing nell’area dei componenti. Assegna a ciascuna dimensione il modello di attribuzione e la persistenza desiderati. Adobe consiglia inoltre di assegnare a ogni dimensione un nome visualizzato che permetta di identificarla facilmente in Workspace.
4. Crea la visualizzazione dati.

Le dimensioni del canale di marketing sono ora disponibili per l’uso in Analysis Workspace.

>[!NOTE]
>
> Il connettore di origine di Analytics richiede che siano compilati sia `channel.typeAtSource` (canale di marketing) che `channel._id` (dettagli canale di marketing). In caso contrario, nessuno dei due sarà trasferito a ExperienceEvent XDM. Se nella suite di rapporti di origine è presente un dettaglio del canale di marketing vuoto, verrà visualizzato `channel._id` vuoto e anche il connettore di origine di Analytics lascerà vuoto `channel.typeAtSource`. Questi spazi vuoti possono causare differenze di reporting tra Adobe Analytics e Customer Journey Analytics.

## Differenze a livello di elaborazione e architettura

>[!IMPORTANT]
>
>Esistono diverse differenze fondamentali tra i dati della suite di rapporti e quelli di Platform. Adobe consiglia vivamente di regolare le regole di elaborazione del canale di marketing della suite di rapporti per facilitare la corretta raccolta dei dati in Experience Platform.

>[!NOTE]
>
>Per massimizzare l&#39;efficacia dei canali di marketing per l&#39;attribuzione e Customer Journey Analytics, sono disponibili alcune [best practice riviste](https://experienceleague.adobe.com/it/docs/analytics/components/marketing-channels/mchannel-best-practices).

Le impostazioni del canale di marketing operano in modo diverso per i dati di Platform e quelli della suite di rapporti. Quando imposti i canali di marketing per Customer Journey Analytics, considera le seguenti differenze:

* **Is First Page of Visit** (È la prima pagina della visita): questo criterio delle regole è comune a diverse definizioni predefinite del canale di marketing. Le regole di elaborazione contenenti questo criterio vengono ignorate in Platform (altri criteri nella stessa regola vengono comunque applicati). Platform non può utilizzare questo specifico criterio di regola perché le sessioni vengono determinate al momento della query dei dati e non al momento della raccolta dei dati. Adobe consiglia di rivalutare eventuali regole di elaborazione del canale di marketing contenenti i criteri “Is First Page of Visit” (È la prima pagina della visita), e di adottare eventuali approcci alternativi in base agli obiettivi che desideri conseguire.

  ![Prima pagina della visita](../assets/first-page-of-visit.png)

* **Override Last-Touch Channel** (Ignora canale ultimo contatto): questa impostazione in Marketing Channel Manager in genere impedisce ad alcuni canali di ottenere il merito del canale di ultimo contatto. Platform ignora questa impostazione, consentendo a canali ampi come “Direct” (Diretto) o “Internal” (Interno) di attribuire metriche in modo potenzialmente indesiderato. Adobe consiglia di rimuovere i canali in cui l’opzione “Override Last-Touch Channel” (Ignora canale ultimo contatto) è deselezionata.
   * Puoi eliminare il canale di marketing &quot;Direct&quot; in Marketing Channel Manager, quindi utilizzare l’elemento di dimensione &quot;No value&quot; (Nessun valore) di Customer Journey Analytics per tale canale. Puoi anche rinominare questo elemento di dimensione “Direct” (Diretto) o escludere completamente l’elemento di dimensione dalla configurazione di una visualizzazione dati.
   * In alternativa, puoi creare una classificazione del canale di marketing, classificando ciascun valore su se stesso, a eccezione dei canali da escludere in Customer Journey Analytics. Quindi puoi utilizzare questa dimensione di classificazione quando crei una visualizzazione dati, al posto di `channel.typeAtSource`.

  ![Ignora canale ultimo contatto](../assets/override-last-touch-channel.png)

* **Scadenza canale di marketing**: questa impostazione del periodo di coinvolgimento determina quanto tempo di inattività deve trascorrere prima che una persona possa ottenere un nuovo canale di primo contatto nei dati della suite di rapporti. Platform utilizza impostazioni di attribuzione proprie; pertanto questa impostazione viene ignorata completamente in Customer Journey Analytics.

  ![Scadenza canale di marketing](../assets/marketing-channel-expiration.png)

## Confronto dei dati tra Customer Journey Analytics e Adobe Analytics

Poiché l’architettura di Adobe Experience Platform è diversa da quella di una suite di rapporti di Adobe Analytics, i risultati potrebbero non corrispondere. Tuttavia, ecco alcuni suggerimenti per semplificare il confronto:

* Verifica che le differenze di architettura elencate qui sopra non influiscano sul confronto. Queste differenze includono la rimozione dei canali che non ignorano il canale di ultimo contatto e la rimozione dei criteri delle regole che sono il primo hit di una visita (sessione).
* Verifica che la connessione utilizzi la stessa suite di rapporti di Adobe Analytics. Se la connessione Customer Journey Analytics contiene più suite di rapporti con proprie regole di elaborazione del canale di marketing, non è possibile eseguire un confronto con Adobe Analytics. In questo caso, per confrontare i dati, puoi creare una connessione separata per ogni suite di rapporti.
* Assicurati di confrontare gli stessi intervalli di date e verifica che l’impostazione del fuso orario nella visualizzazione dati sia identico a quello della suite di rapporti.
* Utilizza un modello di attribuzione personalizzato quando visualizzi i dati della suite di rapporti. Ad esempio, utilizza la dimensione [Canale di marketing](https://experienceleague.adobe.com/it/docs/analytics/components/dimensions/marketing-channel) con metriche che utilizzano un modello di attribuzione non predefinito. Adobe consiglia di non confrontare le dimensioni predefinite [First touch channel](https://experienceleague.adobe.com/it/docs/analytics/components/dimensions/first-touch-channel) o [Last touch channel](https://experienceleague.adobe.com/it/docs/analytics/components/dimensions/last-touch-channel) (Canale di primo contatto, Canale di ultimo contatto), poiché si basano sull’attribuzione raccolta nella suite di rapporti. Customer Journey Analytics non si basa sui dati di attribuzione di una suite di rapporti, ma viene calcolato quando viene eseguito un rapporto di Customer Journey Analytics.
* A causa delle differenze al livello di architettura tra i dati della suite di rapporti e quelli di Platform, per alcune metriche non esistono metriche paragonabili. Alcuni esempi includono visite/sessioni, persone/persone e occorrenze/eventi.
