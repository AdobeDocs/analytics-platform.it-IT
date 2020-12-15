---
title: Creare filtri
description: Scopri l’interfaccia utente per la creazione di filtri.
translation-type: tm+mt
source-git-commit: 21bf268600c12dbf1db24dbc10028a0c29fc48a7
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 33%

---


# Creare filtri

Il Generatore di filtri fornisce un area di lavoro per trascinare e rilasciare metriche, dimensioni, filtri ed eventi per filtrare i visitatori in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato ti consente di generare e salvare filtri semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit pagina.

Potete creare filtri istantanei rilasciando qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, segmento, modello di segmento, intervallo di date) nella zona di rilascio del filtro nella parte superiore di un pannello.

I tipi di componente vengono automaticamente convertiti in filtri. In alternativa, è possibile fare clic sul segno &quot;+&quot; nella casella di rilascio **[!UICONTROL Add Filter]**.

Nota bene:

* **impossibile** rilasciare i seguenti tipi di componenti nella zona filtro: metriche calcolate e dimensioni/metriche da cui non è possibile creare filtri.
* Per eventi e dimensioni intere,  Analysis Workspace crea dei filtri hit &quot;exists&quot; (esiste). Esempi: “Hit dove esiste eVar1” oppure “Hit dove esiste event1”.
* Se nella zona di rilascio del filtro viene rilasciata &quot;unspecified&quot; o &quot;none&quot;, viene automaticamente convertita in un filtro &quot;inesistente&quot; in modo da essere trattata correttamente.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>I filtri creati in questo modo sono interni al progetto.

Potete scegliere di rendere pubblici (globali) questi filtri attenendovi alla procedura seguente:

1. Passa il mouse sul filtro nella zona di rilascio e fai clic sull’icona &quot;i&quot;.
1. Nel pannello informazioni visualizzato, fai clic su **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Altri metodi per applicare i filtri

Esistono diversi altri metodi per applicare i filtri a un progetto:

| Azione | Descrizione |
|--- |--- |
| Crea filtro dalla selezione | Creare un filtro in linea. Selezionate le righe, fate clic con il pulsante destro del mouse sulla selezione, quindi create un filtro in linea. Questo filtro si applica solo al progetto aperto e non viene salvato come filtro CJA. 1. Seleziona le righe.  2. Fai clic con il pulsante destro del mouse sulla selezione.  3. Fare clic su *Crea filtro da selezione*. |
| Componenti > Nuovo filtro | Visualizza il generatore di filtri. Per ulteriori informazioni sui filtri, vedere [Generatore di filtri](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/segmentation-workflow/seg-build.html). |
| Share (Condividi) > Share Project (Condividi progetto) or Share (Condividi) > Curate Project Data (Cura dati progetto) | In [Cura e condivisione](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), scopri in che modo i filtri applicati al progetto sono disponibili nell&#39;analisi condivisa per il destinatario. |
| Usa filtri come dimensioni | Video: Utilizzo dei filtri come Dimension in  Analysis Workspace |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
