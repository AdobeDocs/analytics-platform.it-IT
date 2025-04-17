---
title: Impostazioni dei componenti di attribuzione
description: Consente di impostare l’attribuzione predefinita per una metrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: ht
source-wordcount: '843'
ht-degree: 100%

---

# Impostazioni dei componenti di attribuzione {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Attribution"
>abstract="Configura il modello di attribuzione predefinito applicato a una metrica nei report."

<!-- markdownlint-enable MD034 -->


Attribution consente di personalizzare il modo in cui gli elementi dimensionali ricevono credito per gli eventi di successo.

![Finestra Visualizzazioni dati che evidenzia l’opzione Set attribution (Imposta attribuzione)](../assets/attribution-settings.png)

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

1. Seleziona il componente, quindi espandi la sezione Attribution sul lato destro della schermata.

   ![Finestra Visualizzazioni dati che evidenzia l’opzione Set attribution](../assets/attribution-settings.png)

1. Seleziona [!UICONTROL **Set attribution**], quindi seleziona il modello di attribuzione nel menu a discesa [!UICONTROL **Modello di attribuzione**].

   Per scoprire ciascun modello di attribuzione, consulta [Modelli di attribuzione](#attribution-models).

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


## Intervallo di lookback

{{attribution-lookback-window}}



## Esempio di attribuzione {#attribution-example}

Prendi in considerazione l’esempio seguente:

1. Il 15 settembre, un visitatore arriva sul tuo sito tramite un annuncio pubblicitario di ricerca a pagamento, poi se ne va.
1. Il 18 settembre, il visitatore ritorna sul tuo sito tramite un collegamento social media ricevuto da un amico. Aggiunge diversi articoli al carrello, ma non acquista nulla.
1. Il 24 settembre, il team marketing gli invia un’e-mail con un coupon da utilizzare su alcuni degli elementi nel carrello. Applica il coupon, ma visita diversi altri siti per vedere se sono disponibili altri coupon. Ne trova un altro tramite un annuncio pubblicitario, quindi completa un acquisto dal valore di 50 $.

A seconda dell’intervallo di lookback e del modello di attribuzione definiti, ai canali saranno assegnati crediti diversi. Di seguito sono riportati alcuni esempi:

* Utilizzando il **primo contatto** e un **intervallo di lookback per sessione**, l’attribuzione considera solo la terza visita. Tra e-mail e visualizzazione, e-mail è avvenuta prima, quindi e-mail ottiene il 100% di credito per l’acquisto di 50 €.

* Utilizzando il **primo contatto** e un **intervallo di lookback per persona**, l’attribuzione esamina tutte e tre le visite. La ricerca a pagamento è avvenuta prima, quindi ottiene il 100% di credito per l’acquisto di 50 $.

* Utilizzando un modello **lineare** e un **intervallo di lookback per sessione**, il credito è suddiviso tra e-mail e visualizzazione. Entrambi questi canali ricevono un credito di 25 $.
Utilizzando un modello **lineare** e un **intervallo di lookback per persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Ogni canale ottiene un credito di 12,50 $ per questo acquisto.

* Utilizzando un modello **a forma di J** e un **intervallo di lookback per persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione.

   * Il 60% di credito è assegnato alla visualizzazione, per un valore di 30 $.
   * Il 20% di credito è assegnato alla ricerca a pagamento, per un valore di 10 $.
   * Il restante 20% è suddiviso tra social e e-mail, ovvero 5 $ ciascuno.

* Utilizzando **Decadimento nel tempo** e un **intervallo di lookback per persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Utilizzando la mezza durata predefinita di 7 giorni:

   * Intervallo di 0 giorni tra il punto di contatto visualizzazione e la conversione. `2^(-0/7) = 1`
   * Intervallo di 0 giorni tra il punto di contatto e-mail e la conversione. `2^(-0/7) = 1`
   * Intervallo di 6 giorni tra il punto di contatto social e la conversione. `2^(-6/7) = 0.552`
   * Intervallo di 9 giorni tra il punto di contatto ricerca a pagamento e la conversione. `2^(-9/7) = 0.41`
   * La normalizzazione di questi valori determina quanto segue:

      * Visualizzazione: 33,8%, ovvero 16,88 $
      * E-mail: 33,8% ovvero 16,88 $
      * Social: 18,6%, ovvero 9,32 $
      * Ricerca a pagamento: 13,8%, ovvero 6,92 $

Gli eventi di conversione che in genere hanno numeri interi vengono suddivisi se il credito appartiene a più di un canale. Ad esempio, se due canali contribuiscono a un ordine utilizzando un modello di attribuzione lineare, entrambi i canali ottengono lo 0,5 di tale ordine. Queste metriche parziali vengono sommate tra tutte le persone, quindi arrotondate al numero intero più vicino per la generazione del rapporto.


