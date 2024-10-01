---
description: In Analysis Workspace puoi creare filtri da un punto di contatto, aggiungere filtri come punto di contatto e confrontare flussi di lavoro chiave tra vari filtri.
keywords: fallout e filtri;filtri nell’analisi di fallout;confrontare filtri di fallout
title: Applicare i filtri nell’analisi dell’abbandono
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 46%

---

# Applicare i filtri nell’analisi dell’abbandono

In Analysis Workspace puoi creare filtri da un punto di contatto, aggiungere filtri come punto di contatto e confrontare flussi di lavoro chiave tra vari filtri.

>[!IMPORTANT]
>
>I filtri utilizzati come punti di controllo in Fallout devono utilizzare un contenitore di livello inferiore rispetto al contesto generale della visualizzazione Fallout. Con Fallout in contesto persona, i filtri utilizzati come punti di controllo devono essere basati su visite o eventi. Con Fallout in contesto visita, i filtri utilizzati come punto di controllo devono essere basati su eventi. Se utilizzi una combinazione non valida, l’abbandono è del 100%. Quando aggiungi un filtro incompatibile come punto di contatto, viene visualizzato un avviso per la visualizzazione Abbandono. Alcune combinazioni di contenitori di filtri non valide generano diagrammi di fallout non validi, ad esempio:

* Utilizzo di un filtro basato su persona come punto di contatto all’interno di una visualizzazione Abbandono in un contesto persona
* Utilizzo di un filtro basato su persona come punto di contatto all’interno di una visualizzazione Abbandono in un contesto visita
* Utilizzo di un filtro basato su visita come punto di contatto all’interno di una visualizzazione Fallout in un contesto visita

## Creare un filtro da un punto di contatto

1. Creare un filtro da un punto di contatto che ti interessa particolarmente e che potrebbe essere utile da applicare ad altri rapporti. Fare clic con il pulsante destro del mouse sul punto di contatto e selezionare **[!UICONTROL Create filter from touchpoint]**.

   ![Menu a discesa Punto di contatto con Crea segmento dal punto di contatto evidenziato.](assets/fallout-createfilter.png)

   Verrà aperto [!UICONTROL Filter builder], precompilato con il filtro sequenziale predefinito che corrisponde al punto di contatto selezionato:

   ![Il Generatore di filtri visualizza il filtro sequenziale precompilato e precompilato.](assets/fallout-definefilter.png)

1. Assegna al filtro un titolo e una descrizione e salvalo.

   Ora puoi usare questo filtro in qualsiasi rapporto.

## Aggiungere un filtro come punto di contatto

Per vedere ad esempio come gli utenti USA influenzano le metriche di fallout, trascina il filtro degli utenti USA nella sezione Fallout:

![Il filtro Utenti USA selezionato ed evidenziato da trascinare nell&#39;abbandono.](assets/fallout-addfilter.png)

Oppure puoi creare un punto di contatto AND trascinando il filtro degli utenti USA su un altro punto di controllo.

## Confrontare i filtri in Fallout

Puoi confrontare un numero illimitato di filtri nella visualizzazione Fallout.

1. Selezionare i filtri da confrontare dal pannello [!UICONTROL Filter] a sinistra. Nell&#39;esempio sono selezionati tre filtri: *Dettagli volo: Pagina Versione A*, *Dettagli volo: Pagina Versione B* e *Dettagli volo: Pagina Versione C*.
1. Trascina i tre filtri nella zona di rilascio Filtro, nella parte superiore della visualizzazione.


1. Facoltativo: è possibile mantenere *Tutte le visite* come contenitore predefinito o eliminare il contenitore.

   ![Fallout che mostra tutte le visite insieme ai due filtri trascinati nel passaggio precedente.](assets/fallout-multiplefilters.png)

1. Ora puoi confrontare l’abbandono tra i tre filtri, ad esempio quando un filtro ha prestazioni migliori di un altro o altre informazioni.
