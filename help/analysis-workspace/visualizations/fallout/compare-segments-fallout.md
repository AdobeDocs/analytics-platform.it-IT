---
description: In Analysis Workspace puoi creare filtri da un punto di contatto, aggiungere filtri come punto di contatto e confrontare flussi di lavoro chiave tra vari filtri.
keywords: fallout e filtri;filtri nell’analisi di fallout;confrontare filtri di fallout
title: Applicare i filtri nell’analisi dell’abbandono
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 93%

---

# Applicare i filtri nell’analisi dell’abbandono

In Analysis Workspace puoi creare filtri da un punto di contatto, aggiungere filtri come punto di contatto e confrontare flussi di lavoro chiave tra vari filtri.

>[!IMPORTANT]
>
>I filtri utilizzati come punti di controllo in Fallout devono utilizzare un contenitore di livello inferiore rispetto al contesto generale della visualizzazione Fallout. Con Fallout in contesto visitatore, i filtri utilizzati come punti di controllo devono essere basati su visite o eventi. Con Fallout in contesto visita, i filtri utilizzati come punto di controllo devono essere basati su eventi. Se usi una combinazione non valida, il fallout sarà 100%. Alla visualizzazione Fallout è stata aggiunta un’avvertenza che verrà attivata se aggiungi un filtro incompatibile come punto di contatto. Alcune combinazioni di contenitori di filtri non valide generano diagrammi di fallout non validi, ad esempio:

* Utilizzo di un filtro basato su visitatore come punto di contatto all’interno di una visualizzazione Fallout in contesto visitatore
* Utilizzo di un filtro basato su visitatore come punto di contatto all’interno di una visualizzazione Fallout in un contesto visita
* Utilizzo di un filtro basato su visita come punto di contatto all’interno di una visualizzazione Fallout in un contesto visita

## Creare un filtro da un punto di contatto {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Creare un filtro da un punto di contatto che ti interessa particolarmente e che potrebbe essere utile da applicare ad altri rapporti. A tale scopo, fai clic con il pulsante destro sul punto di contatto e seleziona **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Viene aperto il Generatore di filtri, precompilato con il filtro sequenziale precostruito che corrisponde al punto di contatto selezionato:

   ![](assets/segment-builder.png)

1. Assegna al filtro un titolo e una descrizione e salvalo.

   Ora puoi usare questo filtro in qualsiasi rapporto.

## Aggiungere un filtro come punto di contatto {#section_17611C1A07444BE891DC21EE8FC03EFC}

Per vedere ad esempio come gli utenti USA influenzano le metriche di fallout, trascina il filtro degli utenti USA nella sezione Fallout:

![](assets/segment-touchpoint.png)

Oppure puoi creare un punto di contatto AND trascinando il filtro degli utenti USA su un altro punto di controllo.

## Confrontare i filtri in Fallout {#section_E0B761A69B1545908B52E05379277B56}

Puoi confrontare un numero illimitato di filtri nella visualizzazione Fallout.

1. Seleziona i filtri che desideri confrontare dalla barra [!UICONTROL Filter] a sinistra. Nel nostro esempio, abbiamo selezionato 2 filtri: Utenti USA e Utenti non USA.
1. Trascinali nella zona di rilascio Filtro, in alto.

   ![](assets/segment-drop.png)

1. Facoltativo: puoi mantenere il contenitore predefinito “Tutte le visite” o eliminarlo.

   ![](assets/seg-compare.png)

1. Ora puoi confrontare i dati di fallout tra i due filtri, ad esempio dove un filtro ha prestazioni migliori dell’altro o altri approfondimenti.
