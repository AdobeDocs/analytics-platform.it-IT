---
description: Scopri come segmentare singole metriche per effettuare confronti di metriche all’interno della stessa visualizzazione.
title: Metriche segmentate
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
TQID: https://experienceleague.adobe.com/dOOOOGytHT-5IMC9LNcNlBKLufs9PUkvjBoAgw38bEI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 504
ht-degree: 1%

---

# Metriche segmentate

Nel [Generatore di metriche calcolate](cm-build-metrics.md#definition-builder), puoi applicare segmenti all&#39;interno della definizione della metrica. L’applicazione di segmenti è utile se desideri utilizzare nell’analisi le metriche per un sottoinsieme di dati.

>[!NOTE]
>
>Le definizioni dei segmenti vengono aggiornate tramite il [Generatore di segmenti](/help/components/segments/seg-builder.md). Se apporti una modifica a un segmento, questo viene aggiornato automaticamente ovunque venga utilizzato, incluso se il segmento fa parte di una definizione di metrica calcolata.
>

Vuoi confrontare le metriche per i tedeschi che interagiscono con il tuo marchio con quelle di persone al di fuori della Germania. Quindi puoi rispondere a domande come:

1. Quante persone tedesche e internazionali visitano le [pagine più popolari](#popular-pages).
1. Quante persone tedesche e internazionali in [totale](#totals) hanno interagito online con il tuo marchio questo mese.
1. Quali sono le [percentuali](#percentages) di tedeschi e di persone internazionali che hanno visitato le tue pagine popolari?

Consulta le sezioni seguenti per illustrare come le metriche segmentate possono aiutarti a rispondere a queste domande. Se del caso, si fa riferimento alla documentazione più dettagliata.

## Pagine popolari

1. [Creare una metrica calcolata](cm-workflow.md) da un progetto Workspace, denominato `German people`.
1. Dall&#39;interno del [Generatore di metriche calcolate](cm-build-metrics.md), [crea un segmento](/help/components/segments/seg-builder.md), denominato `Germany`, che utilizza il campo Paese CRM dai dati del tuo sistema di gestione delle relazioni con i clienti per determinare la provenienza di una persona.

   >[!TIP]
   >
   >Nel generatore di metriche calcolate, puoi creare un segmento direttamente utilizzando il pannello Componenti.
   >   

   Il segmento potrebbe essere simile a.

   ![Segmento Germania](assets/filter-germany.png)

1. Nel generatore di metriche calcolate, utilizza il segmento per aggiornare la metrica calcolata.

   ![Metrica calcolata - Germania](assets/calculated-metric-germany.png)

Ripeti i passaggi precedenti per la versione internazionale della metrica calcolata.

1. Creare una metrica calcolata dal progetto Workspace, denominata `International people`.
1. Dall&#39;interno del generatore di metriche calcolate, creare un segmento, denominato `Not Germany`, che utilizza il campo Paese CRM dai dati del sistema di gestione delle relazioni con i clienti per determinare la provenienza di una persona.

   Il segmento dovrebbe essere simile a.

   ![Segmento Germania](assets/filter-not-germany.png)

1. Nel generatore di metriche calcolate, utilizza il segmento per aggiornare la metrica calcolata.

   ![Metrica calcolata - Germania](assets/calculated-metric-notgermany.png)


1. Crea un progetto in Analysis Workspace, dove puoi vedere le pagine visitate da tedeschi e internazionali.

   ![Visualizzazione della tabella a forma libera di Workspace che mostra le persone tedesche rispetto a quelle internazionali](assets/workspace-german-vs-international.png)


## Totali

1. Crea due nuove metriche calcolate basate sul totale complessivo. Apri ciascuno dei segmenti creati in precedenza, rinomina il segmento, imposta il **[!UICONTROL tipo di metrica]** per **[!UICONTROL Persone]** su **[!UICONTROL Totale complessivo]** e utilizza **[!UICONTROL Salva con nome]** per salvare il segmento utilizzando il nuovo nome. Ad esempio:

   ![Metrica totale per la Germania](assets/calculated-metric-germany-total.png)

1. Aggiungi al progetto Workspace una nuova visualizzazione a forma libera che mostra il totale delle pagine del mese corrente.

   ![Visualizzazione della tabella a forma libera di Workspace con tedesco rispetto al totale internazionale](assets/workspace-german-vs-international-totals.png)


## Percentuali

1. Crea due nuove metriche calcolate che calcolano una percentuale dalle metriche calcolate create in precedenza.

   ![Visualizzazione della tabella a forma libera di Workspace che mostra la percentuale di tedesco rispetto al totale internazionale delle persone](assets/calculated-metric-germany-total-percentage.png)


1. Aggiorna il progetto Workspace.

   ![Visualizzazione della tabella a forma libera di Workspace con tedesco rispetto al totale internazionale](assets/workspace-german-vs-international-totals-percentage.png)



>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utilizza una metrica calcolata segmentata come metrica senza implementazione](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"} per un video dimostrativo.

{{videoaa}}

>[!ENDSHADEBOX]

