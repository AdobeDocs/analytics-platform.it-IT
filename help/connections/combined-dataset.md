---
title: Set di dati evento combinati
description: Scopri come il Customer Journey Analytics crea una connessione combinando set di dati.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 60%

---


# Set di dati evento combinati

Quando crei una connessione, Customer Journey Analytics combina tutti gli schemi e i set di dati in un unico set di dati. Questo &quot;set di dati evento combinato&quot; è ciò che il Customer Journey Analytics utilizza per il reporting. Quando includi più schemi o set di dati in una connessione:

* Gli schemi vengono combinati. I campi degli schemi duplicati vengono uniti.
* La colonna “ID persona” di ciascun set di dati viene unita in una singola colonna, indipendentemente dal suo nome. Questa colonna è la base per identificare le persone univoche nel Customer Journey Analytics.
* Le righe vengono elaborate in base alla marca temporale.
* Gli eventi vengono risolti a livello di millisecondi.

## Esempio

Prendi in considerazione l’esempio seguente. Ci sono due set di dati evento, ciascuno con campi diversi contenenti dati diversi.

>[!NOTE]
>
>Adobe Experience Platform in genere memorizza la marca temporale in millisecondi Unix. In questo esempio, sono utilizzate data e ora per questioni di leggibilità.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

Quando crei una connessione utilizzando questi due set di dati evento, per il reporting viene utilizzata la seguente tabella.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

Questo set di dati evento combinato è ciò che viene utilizzato nel reporting. Non importa da quale set di dati provenga una riga; il Customer Journey Analytics tratta tutti i dati come se fossero nello stesso set di dati. Se un ID persona corrispondente è presente in entrambi i set di dati, viene considerato la stessa persona univoca. Se un ID persona corrispondente è presente in entrambi i set di dati con una marca temporale entro 30 minuti, viene considerato parte della stessa sessione.

Questo concetto si applica anche all’attribuzione. Non importa da quale insieme di dati provenga una riga; l’attribuzione funziona esattamente come se tutti gli eventi provenissero da un singolo set di dati. Utilizzo delle tabelle precedenti in un esempio:

Se la connessione includesse solo la prima tabella e non la seconda, l’estrazione di un rapporto con la dimensione `string_color` e la metrica `metric_a` utilizzando l’attribuzione ultimo contatto apparirebbe così:

| string_color | metric_a |
| --- | --- |
| Non specificato | 6 |
| Blu | 3 |
| Rosso | 2 |

Tuttavia, se nella connessione includessi entrambe le tabelle, l’attribuzione sarebbe modificata poiché `user_847` si trova in entrambi i set di dati. Una riga del secondo set di dati attribuisce `metric_a` a “Giallo”, in precedenza non specificato:

| string_color | metric_a |
| --- | --- |
| Giallo | 6 |
| Blu | 3 |
| Rosso | 2 |

## Analisi cross-channel

Il livello successivo di combinazione dei set di dati è l’analisi cross-channel, in cui vengono combinati set di dati di canali diversi, in base a un identificatore comune (ID persona). L’analisi cross-channel può trarre vantaggio dalla funzionalità di unione, che consente di reimpostare l’ID persona di un set di dati in modo che il set di dati venga aggiornato correttamente per consentire una combinazione perfetta di più set di dati. L’unione esamina i dati utente provenienti da sessioni autenticate e non autenticate per generare un ID unico.

L’analisi cross-channel consente di rispondere a domande quali:

* Quante persone iniziano la loro esperienza in un canale, poi la finiscono in un altro?
* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through di campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i percorsi cross-device? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?


Per ulteriori informazioni sull’analisi cross-channel, consulta il caso d’uso specifico:

* [Analisi cross-channel](../use-cases/cross-channel/cross-channel.md)

Per una funzionalità di unione delle discussioni più approfondita, vai a:

* [Panoramica sull’unione](/help/stitching/overview.md)
* [Come funziona l’unione](../stitching/explained.md)
* [Domande frequenti](/help/stitching/faq.md)

