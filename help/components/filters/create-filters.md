---
title: Creare filtri
description: Scopri l’interfaccia utente per la creazione di filtri.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
source-git-commit: 7013237e11cb173d54dcbe236967b49d89810975
workflow-type: ht
source-wordcount: '364'
ht-degree: 100%

---

# Creare filtri

Il Generatore di filtri fornisce un area di lavoro per trascinare e rilasciare metriche, dimensioni, filtri ed eventi per filtrare i visitatori in base alla logica gerarchica del contenitore, alle regole e agli operatori. Questo strumento di sviluppo integrato ti consente di generare e salvare filtri semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit pagina.

Puoi creare all’istante dei filtri rilasciando qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, filtro, modello di filtri, intervallo di date) nella zona di rilascio dei filtri, nella parte superiore di un pannello.

I tipi di componente vengono automaticamente convertiti in filtri. In alternativa, fai clic sul simbolo “+” nell’area di rilascio **[!UICONTROL Add Filter]**.

Aspetti da considerare:

* Nella zona dei filtri **non** è possibile rilasciare i seguenti tipi di componenti: metriche calcolate e dimensioni o metriche da cui non è possibile creare i filtri.
* Per eventi e dimensioni intere, Analysis Workspace crea dei filtri di hit di tipo “exists” (esiste). Esempi: “Hit dove esiste eVar1” oppure “Hit dove esiste event1”.
* Se nella zona di rilascio dei filtri viene rilasciato “Non specificato” o “Nessuno”, vengono automaticamente convertiti in un filtro di tipo “does not exist” (non esiste) in modo da essere trattati correttamente.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>I filtri creati in questo modo sono interni al progetto.

Per scegliere di rendere questi filtri pubblici (globali):

1. Passa il mouse sul filtro nella zona di rilascio e fai clic sull’icona “i”.
1. Nel pannello informazioni visualizzato, fai clic su **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Altri metodi per applicare i filtri

Esistono molti altri metodi per applicare i filtri a un pannello

| Azione | Descrizione |
| --- | --- |
| Creare un filtro dalla selezione | Crea un filtro in linea. Questo tipo di filtro è applicabile solo al progetto aperto e non viene salvato come filtro di CJA.<p> 1. Seleziona le righe della tabella da includere nel filtro. 2. Fai clic con il pulsante destro del mouse sulla selezione. 3. Fai clic su *Create filter from selection* (Crea filtro da selezione). |
| [!UICONTROL Components] Workspace > [!UICONTROL New Filter] | Viene visualizzato il generatore di filtri. Per ulteriori informazioni sui filtri, consulta l’articolo su come [generare i filtri](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=it). |
| Condividi > Condividi progetto oppure Condividi > Cura dati progetto | In [Curare e condividere](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=it#concept_4A9726927E7C44AFA260E2BB2721AFC6), scopri come i filtri applicati al progetto sono disponibili al destinatario nelle analisi condivise. |
| Utilizzare i filtri come dimensioni | Guarda il video di seguito: Using Segments as Dimensions in Analysis Workspace (Uso dei filtri come dimensioni in Analysis Workspace) |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
