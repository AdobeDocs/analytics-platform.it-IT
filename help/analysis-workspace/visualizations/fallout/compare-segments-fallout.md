---
description: Puoi creare filtri da un punto di contatto, aggiungere filtri come punto di contatto e confrontare flussi di lavoro chiave tra vari filtri in Analysis Workspace.
keywords: abbandono e filtri;filtri nell’analisi dell’abbandono;confrontare filtri nell’abbandono
title: Applicare i filtri nell’analisi dell’abbandono
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 17%

---

# Applicare i filtri nell’analisi dell’abbandono

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Puoi creare filtri da un punto di contatto, aggiungere filtri come punto di contatto e confrontare flussi di lavoro chiave tra vari filtri in Analysis Workspace.

>[!IMPORTANT]
>
>I filtri utilizzati come punti di controllo in Abbandono devono utilizzare un contenitore di livello inferiore rispetto al contesto generale della visualizzazione Abbandono. Con un Abbandono in contesto visitatore, i filtri utilizzati come punti di controllo devono essere filtri basati su visite o hit. Con un Abbandono in contesto visita, i filtri utilizzati come punto di controllo devono essere filtri basati su hit. Se si usa una combinazione non valida, l’abbandono sarà 100%. È stato aggiunto un avviso alla visualizzazione Abbandono che verrà visualizzato quando aggiungi un filtro incompatibile come punto di contatto. Alcune combinazioni di contenitori filtro non valide genereranno diagrammi di abbandono non validi, ad esempio:

* Utilizzo di un filtro basato su visitatore come punto di contatto all’interno di una visualizzazione Abbandono in un contesto visitatore
* Utilizzo di un filtro basato su visitatore come punto di contatto all’interno di una visualizzazione Abbandono in un contesto Visita
* Utilizzo di un filtro basato su visite come punto di contatto all’interno di una visualizzazione Abbandono in un contesto Visita

## Creare un filtro da un punto di contatto {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Crea un filtro da un punto di contatto specifico di tuo interesse e che potrebbe essere utile da applicare ad altri rapporti. A tale scopo, fai clic con il pulsante destro sul punto di contatto e seleziona **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Viene aperto il Generatore di filtri, precompilato con il filtro sequenziale predefinito corrispondente al punto di contatto selezionato:

   ![](assets/segment-builder.png)

1. Assegna al filtro un titolo e una descrizione e salvalo.

   Ora puoi utilizzare questo filtro in qualsiasi progetto desideri.

## Aggiungere un filtro come punto di contatto {#section_17611C1A07444BE891DC21EE8FC03EFC}

Per vedere, ad esempio, come gli utenti USA tendono e influenzano l’abbandono, trascina il filtro per gli utenti USA nell’abbandono:

![](assets/segment-touchpoint.png)

Oppure puoi creare un punto di contatto AND trascinando il filtro degli utenti USA su un altro punto di controllo.

## Confrontare i filtri nell’abbandono {#section_E0B761A69B1545908B52E05379277B56}

Puoi confrontare un numero illimitato di filtri nella visualizzazione Abbandono.

1. Seleziona i filtri da confrontare dalla barra [!UICONTROL Filter] a sinistra. Nel nostro esempio, abbiamo selezionato 2 filtri: Utenti USA e utenti non USA.
1. Trascinali nella zona di rilascio Filtro nella parte superiore.

   ![](assets/segment-drop.png)

1. Facoltativo: puoi mantenere il contenitore predefinito “Tutte le visite”, o eliminarlo.

   ![](assets/seg-compare.png)

1. Ora puoi confrontare l’abbandono tra i due filtri, ad esempio dove un filtro sta superando un altro, o altre informazioni.
