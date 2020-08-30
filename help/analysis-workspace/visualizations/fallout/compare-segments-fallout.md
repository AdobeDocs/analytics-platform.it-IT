---
description: Puoi creare segmenti da un punto di contatto, aggiungere segmenti come punto di contatto e confrontare flussi di lavoro chiave tra vari segmenti in Analysis Workspace.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Applicare i segmenti nell’analisi dell’abbandono
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 29%

---


# Applicare i filtri nell’analisi dell’abbandono

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Puoi creare filtri da un punto di contatto, aggiungere segmenti come punto di contatto e confrontare flussi di lavoro chiave tra vari filtri in  Analysis Workspace.

>[!IMPORTANT]
>
>I filtri utilizzati come punti di controllo in Abbandono devono utilizzare un contenitore di livello inferiore rispetto al contesto generale della visualizzazione Abbandono. Con un abbandono del contesto del visitatore, i filtri utilizzati come punti di controllo devono essere filtri basati su visite o hit. Con un Abbandono del contesto della visita, i filtri utilizzati come punto di controllo devono essere segmenti basati sugli hit. Se si usa una combinazione non valida, l’abbandono sarà 100%. È stato aggiunto un avviso alla visualizzazione Abbandono che verrà visualizzata quando aggiungi un filtro incompatibile come punto di contatto. Alcune combinazioni di contenitori di filtri non valide genereranno diagrammi di abbandono non validi, ad esempio:

* Utilizzo di un filtro basato su visitatore come punto di contatto all’interno di una visualizzazione Abbandono contesto visitatore
* Utilizzo di un filtro basato su visitatore come punto di contatto all’interno di una visualizzazione Abbandono contesto visita
* Utilizzo di un filtro basato sulle visite come punto di contatto all’interno di una visualizzazione Abbandono contesto visita

## Creare un filtro da un punto di contatto {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Crea un filtro da un punto di contatto specifico che ti interessa e che potrebbe essere utile da applicare ad altri rapporti. A tale scopo, fai clic con il pulsante destro sul punto di contatto e seleziona **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Viene aperto il Generatore di filtri, precompilato con il filtro sequenziale pregenerato che corrisponde al punto di contatto selezionato:

   ![](assets/segment-builder.png)

1. Assegnate al filtro un titolo e una descrizione e salvatelo.

   Ora potete utilizzare questo filtro in qualsiasi progetto desiderato.

## Aggiungere un filtro come punto di contatto {#section_17611C1A07444BE891DC21EE8FC03EFC}

Per vedere, ad esempio, in che modo gli utenti USA tendono e influenzano l’abbandono, trascina il filtro degli utenti USA nell’abbandono:

![](assets/segment-touchpoint.png)

Oppure puoi creare un punto di contatto AND trascinando il filtro degli utenti USA su un altro punto di controllo.

## Confrontare i filtri nell’abbandono {#section_E0B761A69B1545908B52E05379277B56}

Puoi confrontare un numero illimitato di filtri nella visualizzazione Abbandono.

1. Seleziona i segmenti che desideri confrontare dalla barra [!UICONTROL Filter] a sinistra. Nel nostro esempio, abbiamo selezionato 2 segmenti: Utenti USA e Utenti non USA.
1. Trascinali nella zona di rilascio Filtro in alto.

   ![](assets/segment-drop.png)

1. Facoltativo: puoi mantenere il contenitore predefinito “Tutte le visite”, o eliminarlo.

   ![](assets/seg-compare.png)

1. È ora possibile confrontare l&#39;abbandono tra i due filtri, ad esempio dove un filtro ha prestazioni migliori di un altro, o altre informazioni.
