---
title: Creare filtri
description: Scopri l’interfaccia utente per la creazione di filtri.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
source-git-commit: b907e62bfabd8cb42dc89d551d7b5285cb61298e
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 32%

---

# Creare filtri

Il Generatore di filtri fornisce un area di lavoro per trascinare e rilasciare metriche, dimensioni, filtri ed eventi per filtrare i visitatori in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato ti consente di generare e salvare filtri semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit pagina.

Puoi creare filtri istantanei rilasciando qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, filtro, modello di filtro, intervallo di date) nella zona di rilascio del filtro nella parte superiore di un pannello.

I tipi di componente vengono automaticamente convertiti in filtri. In alternativa, puoi fare clic sul simbolo &quot;+&quot; nel **[!UICONTROL Add Filter]** casella di rilascio.

Nota bene:

* You **impossibile** rilascia i seguenti tipi di componenti nella zona filtro: metriche calcolate e dimensioni/metriche da cui non è possibile creare filtri.
* Per eventi e dimensioni complete, Analysis Workspace crea filtri hit &quot;exists&quot; (esiste). Esempi: “Hit dove esiste eVar1” oppure “Hit dove esiste event1”.
* Se nella zona di rilascio del filtro viene rilasciato &quot;non specificato&quot; o &quot;nessuno&quot;, questo viene automaticamente convertito in un filtro &quot;non esiste&quot; in modo che venga trattato correttamente.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>I filtri creati in questo modo sono interni al progetto.

Puoi scegliere di rendere questi filtri pubblici (globali) seguendo questi passaggi:

1. Passa il puntatore del mouse sul filtro nella zona di rilascio e fai clic sull’icona &quot;i&quot;.
1. Nel pannello informazioni visualizzato, fai clic su **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Altri metodi per applicare i filtri

Esistono diversi altri metodi per applicare filtri a un progetto:

| Azione | Descrizione |
|--- |--- |
| Crea filtro da selezione | Crea un filtro in linea. Questo filtro si applica solo al progetto aperto e non viene salvato come filtro CJA.<p> 1. Selezionare le righe della tabella che si desidera far parte del filtro.  2. Fai clic con il pulsante destro del mouse sulla selezione.  3. Fai clic su *Crea filtro da selezione*. |
| Componenti > Nuovo filtro | Visualizza il Generatore di filtri. Vedi [Generatore di filtri](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=it) per ulteriori informazioni sul filtro. |
| Share (Condividi) > Share Project (Condividi progetto) or Share (Condividi) > Curate Project Data (Cura dati progetto) | In [Cura e condivisione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=it#concept_4A9726927E7C44AFA260E2BB2721AFC6), scopri come i filtri applicati al progetto sono disponibili al destinatario nelle analisi condivise. |
| Utilizza i filtri come dimensioni | Video: Utilizzo dei filtri come Dimension in Analysis Workspace |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
