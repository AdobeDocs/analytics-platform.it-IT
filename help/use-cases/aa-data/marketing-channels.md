---
title: Utilizzare le dimensioni del canale di marketing in Adobe Experience Platform
description: Utilizza il connettore di origine di Analytics per inserire regole di elaborazione del canale di marketing in Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 96%

---

# Utilizzare le dimensioni del canale di marketing in Adobe Experience Platform

Se la tua organizzazione utilizza il [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it) per inserire in CJA i dati della suite di rapporti, puoi configurare una connessione in CJA per ottenere rapporti sulle dimensioni del canale di marketing.

## Prerequisiti

* I dati della suite di rapporti devono essere già importati in Adobe Experience Platform mediante il [connettore di origine di Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=it). Non sono supportate altre origini di dati, poiché i canali di marketing si basano sulle regole di elaborazione di una suite di rapporti di Analytics.
* Le regole di elaborazione del canale di marketing devono già essere configurate. Vedi [Regole di elaborazione per i canali di marketing](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=it), nella guida dei componenti tradizionali di Analytics.

## Elementi schema del canale di marketing

Una volta stabilito il connettore di origine di Analytics per la suite di rapporti desiderata, viene creato uno schema XDM. Tale schema contiene tutte le dimensioni e le metriche di Analytics come dati non elaborati, che non contengono attribuzione né persistenza. Piuttosto, ogni evento viene eseguito tramite le regole di elaborazione del canale di marketing e registra la prima regola corrispondente. Dovrai specificare attribuzione e persistenza quando crei una visualizzazione dati in CJA.

1. [Crea una connessione](/help/connections/create-connection.md) che includa un set di dati basato sul connettore di origine di Analytics.
2. [Crea una visualizzazione dati](/help/data-views/create-dataview.md) che includa le dimensioni seguenti:
   * **`channel.typeAtSource`**: equivalente alla dimensione [Canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=it).
   * **`channel._id`**: equivalente ai [dettagli del canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html?lang=it)
3. Assegna a ciascuna dimensione il modello di attribuzione e la persistenza desiderati. Se desideri entrambe le dimensioni Primo contatto e Ultimo contatto, trascina più volte ciascuna dimensione del canale di marketing nell’area dei componenti. Assegna a ciascuna dimensione il modello di attribuzione e la persistenza desiderati. Adobe consiglia inoltre di assegnare a ogni dimensione un nome visualizzato che permetta di identificarla facilmente in Workspace.
4. Crea la visualizzazione dati.

Le dimensioni del canale di marketing sono ora disponibili per l’uso in Analysis Workspace.

>[!NOTE]
>
> Il connettore di origine di Analytics richiede che entrambi `channel.typeAtSource` (Canale di marketing) e `channel._id` (Dettagli canale di marketing) siano compilati; in caso contrario, nessuno dei due sarà trasferito a ExperienceEvent XDM. Se il campo Dettagli canale di marketing è vuoto nella suite di rapporti di origine, viene visualizzato un valore `channel._id` vuoto e anche il connettore di origine di Analytics lascerà vuoto il valore `channel.typeAtSource`. Questo può causare discrepanze nei rapporti di Adobe Analytics e Customer Journey Analytics.

## Differenze a livello di elaborazione e architettura

>[!IMPORTANT]
>
>Esistono diverse differenze fondamentali tra i dati della suite di rapporti e quelli di Platform. Adobe consiglia vivamente di modificare le regole di elaborazione del canali di marketing della suite di rapporti per agevolare la corretta raccolta dei dati in Platform.

>[!NOTE]
>
>Per massimizzare l’efficacia dei canali di marketing per Attribution IQ e Customer Journey Analytics, abbiamo pubblicato alcune [best practice](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=it).

Le impostazioni del canale di marketing operano in modo diverso per i dati di Platform e quelli della suite di rapporti. Quando imposti i canali di marketing per CJA, considera le seguenti differenze:

* **Is First Page of Visit** (È la prima pagina della visita): questo criterio delle regole è comune a diverse definizioni predefinite del canale di marketing. Le regole di elaborazione contenenti questo criterio vengono ignorate in Platform (altri criteri nella stessa regola vengono comunque applicati). Platform non può utilizzare questo specifico criterio di regola perché le sessioni vengono determinate al momento della query dei dati e non al momento della raccolta dei dati. Adobe consiglia di rivalutare eventuali regole di elaborazione del canale di marketing contenenti i criteri “Is First Page of Visit” (È la prima pagina della visita), e di adottare eventuali approcci alternativi in base agli obiettivi che desideri conseguire.

   ![Prima pagina della visita](../assets/first-page-of-visit.png)

* **Override Last-Touch Channel** (Ignora canale ultimo contatto): questa impostazione in Marketing Channel Manager in genere impedisce ad alcuni canali di ottenere il merito del canale di ultimo contatto. Platform ignora questa impostazione, consentendo a canali ampi come “Direct” (Diretto) o “Internal” (Interno) di attribuire metriche in modo potenzialmente indesiderato. Adobe consiglia di rimuovere i canali in cui l’opzione “Override Last-Touch Channel” (Ignora canale ultimo contatto) è deselezionata.
   * Puoi eliminare il canale di marketing Diretto in Marketing Channel Manager, quindi utilizzare per tale canale l’elemento di dimensione “No value” (Nessun valore) di CJA. Puoi anche rinominare questo elemento di dimensione “Direct” (Diretto) o escludere completamente l’elemento di dimensione dalla configurazione di una visualizzazione dati.
   * In alternativa, puoi creare una classificazione del canale di marketing, classificando ciascun valore su se stesso, a eccezione dei canali da escludere in CJA. Quindi puoi utilizzare questa dimensione di classificazione quando crei una visualizzazione dati, al posto di `channel.typeAtSource`.

   ![Ignora canale ultimo contatto](../assets/override-last-touch-channel.png)

* **Scadenza canale di marketing**: questa impostazione del periodo di coinvolgimento determina quanto tempo di inattività deve trascorrere prima che una persona possa ottenere un nuovo canale di primo contatto nei dati della suite di rapporti. Platform utilizza impostazioni di attribuzione proprie; pertanto questa impostazione viene ignorata completamente in CJA.

   ![Scadenza canale di marketing](../assets/marketing-channel-expiration.png)

## Confronto dei dati tra CJA e Analytics tradizionale

Poiché l’architettura di Adobe Experience Platform è diversa dalle suite di rapporti tradizionali di Analytics, i risultati potrebbero non corrispondere. Tuttavia, ecco alcuni suggerimenti per semplificare il confronto:

* Verifica che le differenze di architettura elencate qui sopra non influiscano sul confronto. Ad esempio, rimuovi i canali per i quali non è possibile ignorare il canale di ultimo contatto, nonché i criteri di regole di tipo “primo hit di una visita” (sessione).
* Controlla che la connessione utilizzi la stessa suite di rapporti di Analytics tradizionale. Se la connessione CJA contiene più suite di rapporti con proprie regole di elaborazione del canale di marketing, non è possibile eseguire un confronto con la versione tradizionale di Analytics. In questo caso, per confrontare i dati, puoi creare una connessione separata per ogni suite di rapporti.
* Assicurati di confrontare gli stessi intervalli di date e verifica che l’impostazione del fuso orario nella visualizzazione dati sia identico a quello della suite di rapporti.
* Utilizza un modello di attribuzione personalizzato quando visualizzi i dati della suite di rapporti. Ad esempio, utilizza la dimensione [Canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=it) con metriche che utilizzano un modello di attribuzione non predefinito. Adobe consiglia di non confrontare le dimensioni predefinite [First touch channel](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html?lang=it) o [Last touch channel](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html?lang=it) (Canale di primo contatto, Canale di ultimo contatto), poiché si basano sull’attribuzione raccolta nella suite di rapporti. CJA non si basa sui dati di attribuzione di una suite di rapporti; vengono invece calcolati nel momento in cui viene eseguito un rapporto CJA.
* A causa delle differenze al livello di architettura tra i dati della suite di rapporti e quelli di Platform, per alcune metriche non esistono metriche paragonabili. Alcuni esempi includono visite/sessioni, persone/persone e occorrenze/eventi.
