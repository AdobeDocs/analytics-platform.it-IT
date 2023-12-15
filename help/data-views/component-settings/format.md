---
title: Formattare le impostazioni dei componenti
description: Configura la formattazione di una metrica.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: cf9e8c90eec78658e470d3a7a56cb2e3414591d4
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 17%

---

# Formattare le impostazioni dei componenti

Il formato consente di determinare come viene visualizzata una particolare metrica quando viene utilizzata nei rapporti.

## Configurare le impostazioni di formato per una metrica

È possibile determinare la modalità di visualizzazione di una particolare metrica regolandone le impostazioni di formato.

1. In Customer Journey Analytics, seleziona la [!UICONTROL **Visualizzazioni dati**] scheda.

1. Seleziona la visualizzazione dati che contiene il componente di cui desideri configurare l’impostazione di formato.

1. Seleziona la [!UICONTROL **Componenti**] scheda.

1. Seleziona il componente da configurare, quindi espandi la sezione [!UICONTROL **Formato**] sul lato destro della pagina.

   ![Impostazioni formato](../assets/format-settings.png)

1. Specifica le seguenti informazioni:

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Format]** | Consente di specificare la formattazione di una metrica come Decimale, Tempo, Percentuale o Valuta. |
   | **[!UICONTROL Decimal]** | Non visibile sui tipi di dati dello schema a numero intero. Consente di specificare il numero di posizioni decimali visualizzate da una metrica. |
   | **[!UICONTROL Date]** | Consente di determinare come visualizzare il campo data-ora quando viene utilizzato come dimensione nel reporting. [Ulteriori informazioni](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Date-Time]** | Consente di determinare come visualizzare il campo data-ora quando viene utilizzato come dimensione nel reporting. [Ulteriori informazioni](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Currency]** | Consente di determinare la valuta in cui visualizzare la metrica. <p>Se si analizzano i dati globali in cui le transazioni si verificano in valute diverse, vedere  [Usa conversione valuta](#use-currency-conversion).</p> |
   | **[!UICONTROL Show upward trend as]** | Consente di specificare se la tendenza verso l’alto per questa metrica è positiva (verde) o negativa (rossa). |
   | **[!UICONTROL True value]** e **[!UICONTROL False value]** | Visibile solo sui tipi di dati dello schema booleano. Consente di personalizzare l’etichetta per elemento dimensione per i valori `true` e `false`. |

   {style="table-layout:auto"}

## Usa conversione valuta

La conversione valutaria in Customer Journey Analytics può essere estremamente utile per le imprese che operano a livello internazionale. Rimuovendo le complessità della conversione manuale della valuta, la conversione della valuta in Customer Journey Analytics porta uniformità e chiarezza ai dati finanziari. La conversione valutaria tiene traccia dei tassi di cambio storici giornalieri e mantiene tali tassi per un periodo di 4 anni.

Ad esempio, se un’azienda di e-commerce opera negli Stati Uniti, nel Regno Unito e nell’UE, i dati di vendita possono essere automaticamente convertiti in USD, garantendo un facile confronto e una comprensione olistica delle prestazioni.

>[!NOTE]
>
>Prima di iniziare a configurare una metrica per la conversione della valuta, considera quanto segue:
>
>* La metrica selezionata per la conversione della valuta deve avere un tipo numerico (Double, Long, Integer, Short, Byte).
>* Imposta la connessione di Customer Journey Analytics in modo che contenga almeno un set di dati evento che contiene una dimensione di codice valuta per ogni evento contenente una metrica di valuta. La dimensione del codice valuta utilizza un codice valuta alfabetico conforme al [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard per la rappresentazione delle valute. Questi valori devono essere in formato maiuscolo completo, ad esempio USD per $, EUR per €, GBP per £.

Per determinare come vengono visualizzate e convertite le valute per una data metrica:

1. Inizia a configurare la metrica per la quale desideri utilizzare la valuta come formato, come descritto in precedenza, in [Configurare le impostazioni di formato per una metrica](#configure-format-settings-for-a-metric).

1. Con la metrica selezionata, effettua le seguenti selezioni nella [!UICONTROL **Formato**] sezione sul lato destro della pagina:

   * In [!UICONTROL **Formato**] campo, seleziona [!UICONTROL **Valuta**].

   * In [!UICONTROL **Cifre decimali**] scegliere il numero di posizioni decimali visualizzate dalla metrica.

     Questa opzione è disponibile solo se la metrica ha un tipo numerico &quot;Double&quot; (Doppio).

   * Seleziona la [!UICONTROL **Converti valuta**] opzione.

   * In [!UICONTROL **Seleziona dimensione codice valuta**] , seleziona la dimensione che rappresenta la valuta da cui stai eseguendo la conversione (la valuta su cui si basano i dati). Ad esempio, selezionate una quota denominata [!UICONTROL **Codice valuta**].

     Se nello schema dati corrente non è presente una dimensione contenente un campo codice valuta, puoi creare un nuovo campo codice valuta utilizzando [Preparazione dati](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=it), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html), o [Campi derivati](/help/data-views/derived-fields/derived-fields.md). La preparazione dati è adatta solo per le nuove implementazioni perché è solo su base di avanzamento. A seconda della configurazione di un’organizzazione, Data Distiller e Campi derivati possono essere utilizzati per accedere ai valori del codice valuta in modo storico.

   * In [!UICONTROL **Conversione e visualizzazione della valuta in**] scegliere la valuta in cui si desidera convertire i dati.

1. Ripeti questi passaggi se desideri applicare la conversione della valuta ad altre metriche.



### Domande frequenti

+++ Come viene eseguita la conversione della valuta?

Al momento della generazione del rapporto, il valore della metrica e il codice della valuta originale vengono convertiti in USD e quindi nella valuta configurata per la visualizzazione. Per questa conversione vengono utilizzati i tassi di cambio giornalieri applicabili al momento dell’evento.

+++

