---
title: Impostazioni dei componenti di attribuzione
description: Consente di impostare l’attribuzione predefinita per una metrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 7d354ce65f72838c007d2b9faf02848d86fd7c0f
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 93%

---

# Impostazioni dei componenti di attribuzione {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Attribution"
>abstract="Configura il modello di attribuzione predefinito applicato a una metrica nei report."

<!-- markdownlint-enable MD034 -->


Attribution consente di personalizzare il modo in cui gli elementi dimensionali ricevono credito per gli eventi di successo.

Ad esempio:

1. Un visitatore del sito fa clic su un collegamento di ricerca a pagamento a una delle pagine dei tuoi prodotti. Aggiunge il prodotto al carrello, ma non lo acquista.
2. Il giorno dopo, vede il post di un amico sui social media. Fa clic sul collegamento, quindi completa l’acquisto.

In alcuni rapporti, potresti desiderare che l’ordine sia attribuito a Ricerca a pagamento. In altri rapporti, potresti desiderare che l’ordine sia attribuito a Social. Attribution ti consente di controllare questo aspetto del reporting.

## Impostare il modello di attribuzione predefinito di un componente

Puoi impostare un modello di attribuzione predefinito per una data metrica aggiornando l’impostazione della metrica nella visualizzazione dati. In questo modo si sovrascrive il modello di attribuzione della metrica ogni volta che viene utilizzato in Analysis Workspace.

>[!NOTE]
>
>Quando abiliti Attribution su una metrica, tieni presente quanto segue:
>
>* **Quando utilizzi il componente in un report con *una singola dimensione*:** l’attribuzione del componente ignora il modello di allocazione quando viene utilizzato un modello di attribuzione non predefinito.
>
>* **Quando utilizzi il componente in un report con *più dimensioni*:** l’attribuzione del componente mantiene il modello di allocazione quando viene utilizzato un modello di attribuzione non predefinito.
>
>   Più dimensioni sono disponibili solo durante l’[esportazione di dati nel cloud](/help/analysis-workspace/export/export-cloud.md).
>
> Per ulteriori informazioni sull’allocazione, consulta [Impostazioni dei componenti di persistenza](/help/data-views/component-settings/persistence.md).

Per aggiornare il modello di attribuzione predefinito di un componente:

1. Vai alla visualizzazione dati che contiene il componente di cui desideri aggiornare il modello di attribuzione predefinito.

1. Seleziona il componente, quindi espandi la sezione **[!UICONTROL Attribution]** sul lato destro dello schermo.

   ![Finestra Visualizzazioni dati che evidenzia l’opzione Set attribution (Imposta attribuzione)](../assets/attribution-settings.png)

1. Seleziona [!UICONTROL **Imposta attribuzione**], quindi seleziona la finestra [modello di attribuzione](#attribution-models), [contenitore](#container) e [lookback](#lookback-window).



1. Seleziona [!UICONTROL **Salva e continua**].

>[!TIP]
>
>Se l’organizzazione richiede che una metrica abbia più impostazioni di attribuzione, puoi effettuare una delle seguenti operazioni:
>
> * Copiare la metrica nella visualizzazione dati con ogni impostazione di attribuzione desiderata. Puoi includere la stessa metrica più volte in una visualizzazione dati, assegnando a ciascuna metrica un’impostazione diversa. Assicurati di etichettare correttamente ogni metrica in modo che gli analisti possano capire la differenza tra queste metriche durante la generazione dei rapporti.
>
> * Sovrascrivere la metrica in Analysis Workspace. Nelle [impostazioni colonna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) di una metrica, seleziona **[!UICONTROL Use non-default attribution model]** per modificare il modello di attribuzione e l’intervallo di lookback della metrica per quel rapporto specifico.

## Modelli di attribuzione {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="Modello"
>abstract="Seleziona un modello di attribuzione per la metrica."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}

## Contenitore

{{attribution-container}}

## Intervallo di lookback

{{attribution-lookback-window}}

## Esempio

{{attribution-example}}
