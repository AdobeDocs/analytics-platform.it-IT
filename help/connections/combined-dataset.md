---
title: Set di dati evento combinato
description: Scopri come CJA crea una connessione combinando set di dati.
translation-type: tm+mt
source-git-commit: ef05a948cb2036db24c8e308695e3615613d98d8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Set di dati evento combinato

Quando crei una connessione, CJA combina tutti gli schemi e i set di dati in un unico set di dati. Questo &#39;insieme di dati evento combinato&#39; è ciò che CJA utilizza per i report. Quando includi più schemi o set di dati in una connessione:

* Gli schemi vengono combinati. I campi degli schemi duplicati vengono uniti.
* La colonna “ID persona” di ciascun set di dati viene unita in una singola colonna, indipendentemente dal suo nome. Questa colonna è la base per identificare i visitatori unici in CJA.
* Le righe vengono elaborate in base alla marca temporale.

## Esempio

Prendi in considerazione l’esempio seguente. Sono disponibili due set di dati evento, ciascuno con campi diversi contenenti dati diversi.

>[!NOTE]
>
>Adobe Experience Platform in genere memorizza la marca temporale in millisecondi Unix. In questo esempio, sono utilizzate data e ora per questioni di leggibilità.

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

Quando si crea una connessione utilizzando questi due set di dati evento, per il reporting viene utilizzata la tabella seguente.

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

Questo insieme di dati evento combinato è ciò che viene utilizzato nel reporting. Non importa da quale set di dati provenga una riga; CJA tratta tutti i dati come se si trovassero nello stesso set di dati. Se un ID persona corrispondente è presente in entrambi i set di dati, viene considerato lo stesso visitatore univoco. Se un ID persona corrispondente è presente in entrambi i set di dati con una marca temporale entro 30 minuti, viene considerato parte della stessa sessione.

Questo concetto si applica anche all’attribuzione. Non importa da quale insieme di dati provenga una riga; l’attribuzione funziona esattamente come se tutti gli eventi provenissero da un singolo set di dati. Utilizzo delle tabelle precedenti in un esempio:

Se la connessione includesse solo la prima tabella e non la seconda, l’estrazione di un rapporto con la dimensione `string_color` e la metrica `metric_a` utilizzando l’attribuzione ultimo contatto apparirebbe così:

| string_color | metric_a |
| --- | --- |
| Non specificato | 6 |
| Blu | 3 |
| Rosso | 2 |

Tuttavia, se nella connessione includessi entrambe le tabelle, l’attribuzione sarebbe modificata poiché `user_847` si trova in entrambi i set di dati. Una riga del secondo set di dati attribuisce `metric_a` a “Giallo”, in precedenza non specificato:

| string_color | metriche_a |
| --- | --- |
| Giallo | 6 |
| Blu | 3 |
| Rosso | 2 |
