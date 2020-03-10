---
title: Set di dati combinati
description: Scoprite come CJA crea una connessione combinando set di dati.
translation-type: tm+mt
source-git-commit: f9cdcb8a6efe688d553929c3081f3239e0691cd9

---


# Set di dati combinati

Quando si crea una connessione, CJA combina tutti gli schemi e i set di dati in un unico set di dati. Questo &#39;insieme di dati combinato&#39; è ciò che la CJA utilizza per la generazione dei rapporti. Quando si includono più schemi o set di dati in una connessione:

* Gli schemi sono combinati. I campi dello schema duplicati vengono uniti.
* La colonna &#39;ID persona&#39; di ciascun dataset viene unita in una singola colonna, indipendentemente dal suo nome. Questa colonna è la base per identificare i visitatori unici in CJA.
* Le righe vengono elaborate in base alla marca temporale.

## Esempio

Prendi in considerazione l’esempio seguente. Sono disponibili due set di dati, ciascuno con campi diversi contenenti dati diversi.

> [!NOTE] In genere, la marca temporale viene memorizzata in millisecondi Unix. In questo esempio, per la leggibilità si utilizza data e ora.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

Quando si crea una connessione utilizzando questi due set di dati, per il reporting viene utilizzata la seguente tabella.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

Questo insieme di dati combinato è ciò che viene utilizzato nel reporting. Non importa da quale insieme di dati proviene una riga; CJA tratta tutti i dati come se si trovassero nello stesso dataset. Se un ID persona corrispondente viene visualizzato in entrambi i set di dati, viene considerato lo stesso visitatore univoco. Se un ID persona corrispondente viene visualizzato in entrambi i set di dati con una marca temporale entro 30 minuti, viene considerato parte della stessa sessione.

Questo concetto si applica anche all&#39;attribuzione. Non importa da quale insieme di dati proviene una riga; l&#39;attribuzione funziona esattamente come se tutti gli eventi provenissero da un singolo dataset. Esempio di utilizzo delle tabelle precedenti:

Se la connessione includeva solo la prima tabella e non la seconda, l&#39;estrazione di un rapporto con la `string_color` `metric_a` dimensione e la metrica utilizzando l&#39;attribuzione dell&#39;ultimo tocco mostrerebbe:

| string_color | metriche_a |
| --- | --- |
| Blu | 5 |
| Non specificato | 6 |
| Rosso | 2 |

Tuttavia, se nella connessione sono incluse entrambe le tabelle, l&#39;attribuzione `user_847` viene modificata in quanto si trova in entrambi i set di dati. Una riga dagli attributi del secondo set di dati `metric_a` a &#39;Giallo&#39;, dove in precedenza non erano specificati:

| string_color | metriche_a |
| --- | --- |
| Giallo | 6 |
| Rosso | 2 |
| Blu | 3 |
