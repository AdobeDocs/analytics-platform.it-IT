---
title: Formattare le impostazioni dei componenti
description: Configura la formattazione di una metrica.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 3626a9f97048b68a57fca25fec396684c4f95449
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 29%

---

# Formattare le impostazioni dei componenti

Il formato consente di determinare la modalità di visualizzazione di una data metrica.

![Impostazioni formato](../assets/format-settings.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Format]** | Consente di specificare la formattazione di una metrica come Decimale, Tempo, Percentuale o Valuta. |
| **[!UICONTROL Decimal Places]** | Non visibile sui tipi di dati dello schema a numero intero. Consente di specificare il numero di posizioni decimali visualizzate da una metrica. |
| **[!UICONTROL Date]** | Consente di determinare come visualizzare il campo data-ora quando viene utilizzato come dimensione nel reporting. [Ulteriori informazioni](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Date-Time]** | Consente di determinare come visualizzare il campo data-ora quando viene utilizzato come dimensione nel reporting. [Ulteriori informazioni](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Currency]** | Consente di determinare la valuta con cui visualizzare la metrica. Consulta [Valuta](#currency) ulteriori dettagli. |
| **[!UICONTROL Show upward trend as]** | Consente di specificare se la tendenza verso l’alto per questa metrica è positiva (verde) o negativa (rossa). |
| **[!UICONTROL True value]** e **[!UICONTROL False value]** | Visibile solo sui tipi di dati dello schema booleano. Consente di personalizzare l’etichetta per elemento dimensione per i valori `true` e `false`. |

{style="table-layout:auto"}


## Valuta

Quando selezioni **[!UICONTROL Currency]** come [!UICONTROL Format] per una metrica, puoi determinare come visualizzare e convertire le valute.

### Visualizza valuta

Per visualizzare una valuta per una metrica:

1. Immetti il numero di **[!UICONTROL Decimal places]**.

1. Seleziona una valuta da **[!UICONTROL Display currency in]** elenco.


### Conversione e visualizzazione della valuta

{{release-limited-testing-section}}

Per abilitare la conversione di una valuta per una o più metriche:

- Imposta la connessione di Customer Journey Analytics in modo che contenga almeno un set di dati evento che contiene una dimensione di codice valuta per ogni evento contenente una metrica di valuta. La dimensione del codice valuta utilizza un codice valuta alfabetico conforme al [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard per la rappresentazione delle valute. Questi valori devono essere in formato maiuscolo completo, ad esempio USD per $, EUR per €, GBP per £.

   1. Seleziona la dimensione da uno dei set di dati che contiene i codici valuta. Esempio: [!UICONTROL Currency code].

   1. Seleziona **[!UICONTROL Currency Code]** dall’elenco delle dimensioni.

- Ripeti questi passaggi nel caso in cui siano presenti più dimensioni contenenti codici valuta da utilizzare per la conversione della valuta.

>[!NOTE]
>
>La metrica selezionata per la conversione della valuta deve avere un tipo numerico (Double, Long, Integer, Short, Byte).


Per definire come convertire e visualizzare una valuta per una metrica:

1. Immetti il numero di **[!UICONTROL Decimal places]**.

1. Seleziona **[!UICONTROL Convert Concurrency]** (Aggiungi gruppi di campi).

1. Seleziona la dimensione appropriata dall’elenco di dimensioni contenente il campo codice valuta.

1. Seleziona una valuta da **[!UICONTROL Convert and display currency in]** elenco.

### Domande frequenti

+++ Come viene eseguita la conversione della valuta?

Al momento della generazione del rapporto, il valore della metrica e il codice della valuta originale vengono convertiti in USD e quindi nella valuta configurata per la visualizzazione. Per questa conversione vengono utilizzati i tassi di cambio giornalieri applicabili al momento dell’evento.

+++


+++ Quanto indietro nel tempo vengono mantenuti i tassi di conversione giornalieri?

I tassi di conversione giornalieri vengono mantenuti per gli ultimi quattro anni?

+++


+++ Cosa succede se non dispongo di un campo del codice valuta come parte dello schema di dati corrente?

Esistono diverse opzioni per la creazione di un nuovo campo del codice valuta, tra cui Preparazione dati, Distiller dati e Campi derivati. La preparazione dati sarebbe ideale per le nuove implementazioni in quanto sarebbe solo su base progressiva. A seconda della configurazione di un’organizzazione, Data Distiller e Campi derivati possono essere utilizzati per accedere ai valori del codice valuta in modo storico.

+++

