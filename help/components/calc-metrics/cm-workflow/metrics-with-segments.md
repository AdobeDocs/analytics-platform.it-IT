---
description: Il filtro per singole metriche consente di effettuare confronti di metriche all’interno dello stesso rapporto.
title: Metriche filtrate
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 1%

---

# Metriche filtrate

Nel [Generatore di metriche calcolate](cm-build-metrics.md#definition-builder), puoi applicare filtri all&#39;interno della definizione della metrica. L’applicazione dei filtri è utile se desideri utilizzare nell’analisi le metriche per un sottoinsieme di dati.

>[!NOTE]
>
>Le definizioni dei filtri vengono aggiornate tramite il [Generatore di filtri](/help/components/filters/filter-builder.md). Se apporti una modifica a un filtro, questo viene aggiornato automaticamente ovunque venga utilizzato il filtro, anche se il filtro fa parte di una definizione di metrica calcolata.
>

Vuoi confrontare le metriche per i tedeschi che interagiscono con il tuo marchio con quelle di persone al di fuori della Germania. Quindi puoi rispondere a domande come:

1. Quante persone tedesche e internazionali visitano le [pagine più popolari](#popular-pages).
1. Quante persone tedesche e internazionali in [totale](#totals) hanno interagito online con il tuo marchio questo mese.
1. Quali sono le [percentuali](#percentages) di tedeschi e di persone internazionali che hanno visitato le tue pagine popolari?

Consulta le sezioni seguenti per illustrare come le metriche filtrate possono aiutarti a rispondere a queste domande. Se del caso, si fa riferimento alla documentazione più dettagliata.

## Pagine popolari

1. [Creare una metrica calcolata](cm-workflow.md) da un progetto Workspace, denominato `German people`.
1. Dall&#39;interno del [Generatore di metriche calcolate](cm-build-metrics.md), [crea un filtro](/help/components/filters/filter-builder.md), denominato `Germany`, che utilizza il campo Paese CRM dai dati del tuo sistema di gestione delle relazioni con i clienti per determinare la provenienza di una persona.

   >[!TIP]
   >
   >Nel generatore di metriche calcolate, puoi creare un filtro direttamente utilizzando il pannello Componenti.
   >   

   Il filtro potrebbe essere simile al seguente.

   ![Filtra Germania](assets/filter-germany.png)

1. Nel generatore di metriche calcolate, utilizza il filtro per aggiornare la metrica calcolata.

   ![Metrica calcolata - Germania](assets/calculated-metric-germany.png)

Ripeti i passaggi precedenti per la versione internazionale della metrica calcolata.

1. Creare una metrica calcolata dal progetto Workspace, denominata `International people`.
1. Dall&#39;interno del generatore di metriche calcolate, creare un filtro, denominato `Not Germany`, che utilizza il campo Paese CRM dai dati del sistema di gestione delle relazioni con i clienti per determinare la provenienza di una persona.

   Il filtro dovrebbe essere simile al seguente.

   ![Filtra Germania](assets/filter-not-germany.png)

1. Nel generatore di metriche calcolate, utilizza il filtro per aggiornare la metrica calcolata.

   ![Metrica calcolata - Germania](assets/calculated-metric-notgermany.png)


1. Crea un progetto in Analysis Workspace, dove puoi vedere le pagine visitate da tedeschi e internazionali.

   ![Visualizzazione della tabella a forma libera di Workspace che mostra le persone tedesche rispetto a quelle internazionali](assets/workspace-german-vs-international.png)


## Totali

1. Crea due nuovi filtri basati sul totale complessivo. Aprire ciascuno dei filtri creati in precedenza, rinominare il filtro, impostare **[!UICONTROL Metric type]** per **[!UICONTROL People]** su **[!UICONTROL Grand Total]** e utilizzare **[!UICONTROL Save As]** per salvare il filtro utilizzando il nuovo nome. Ad esempio:

   ![Metrica totale per la Germania](assets/calculated-metric-germany-total.png)

1. Aggiungi al progetto Workspace una nuova visualizzazione a forma libera che mostra il totale delle pagine del mese corrente.

   ![Visualizzazione della tabella a forma libera di Workspace con tedesco rispetto al totale internazionale](assets/workspace-german-vs-international-totals.png)


## Percentuali

1. Crea due nuove metriche calcolate che calcolano una percentuale dalle metriche calcolate create in precedenza.

   ![Visualizzazione della tabella a forma libera di Workspace che mostra la percentuale di tedesco rispetto al totale internazionale delle persone](assets/calculated-metric-germany-total-percentage.png)


1. Aggiorna il progetto Workspace.

   ![Visualizzazione della tabella a forma libera di Workspace con tedesco rispetto al totale internazionale](assets/workspace-german-vs-international-totals-percentage.png)


+++ Ecco un video che illustra come utilizzare una metrica calcolata filtrata come metrica senza implementazione.

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

{{videoaa}}

+++
