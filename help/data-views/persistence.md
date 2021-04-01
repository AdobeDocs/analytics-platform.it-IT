---
title: Cos’è la persistenza della dimensione nel Customer Journey Analytics?
description: La persistenza del Dimension è una combinazione di allocazione e scadenza. Insieme, determinano quali valori di dimensione persistono.
translation-type: tm+mt
source-git-commit: efe92e25229addadf57bff3f2ba73d831a3161ea
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 14%

---


# Persistenza

La persistenza del Dimension è una combinazione di allocazione e scadenza. Insieme, determinano quali valori di dimensione persistono. L’Adobe consiglia vivamente di discutere all’interno dell’organizzazione in che modo vengono gestiti più valori per ciascuna dimensione (allocazione) e quando i valori delle dimensioni smettono di mantenere i dati (scadenza).

* Per impostazione predefinita, un valore di dimensione utilizza ? assegnazione.
* Per impostazione predefinita, un valore di dimensione utilizza una scadenza di [!UICONTROL Session].

## Allocazione

L&#39;allocazione applica una trasformazione al valore sottostante utilizzato. I modelli di allocazione supportati includono:

* Più recente
* Originale
* Tutto
* Primo noto
* Ultimo noto

### [!UICONTROL Most recent] assegnazione

Di seguito è riportato un esempio precedente e successivo di allocazione [!UICONTROL Most recent]:

| Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valori originali |  | C | B |  | A |
| Allocazione più recente |  | C | B | B | A |

### [!UICONTROL Original] assegnazione

Di seguito è riportato un esempio precedente e successivo di allocazione [!UICONTROL Original]:

| Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 3 | 2 | 3 | 6 | 7 |
| valori originali |  | C | B |  | A |
| Allocazione originale |  | C | C | C | C |

### [!UICONTROL All] assegnazione

Questa nuova allocazione di dimensioni può essere applicata sia a dimensioni basate su array che a dimensioni a valore singolo. Funziona in modo simile al modello di attribuzione [!UICONTROL Participation] per le metriche. La differenza consiste nel fatto che i singoli valori all’interno del campo possono scadere in punti diversi. Ad esempio, supponiamo di avere 5 eventi in un campo stringa, con allocazione impostata su &quot;All&quot; e scadenza impostata su 5 minuti. Ci aspettiamo il seguente comportamento:

| Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valori originali | A | B | C |  | A |
| post-persistenza | A | A,B | A,B,C | B,C | A,C |

Tieni presente che il valore di A persiste finché non raggiunge la soglia di 5 minuti, mentre B e C continuano a persistere nell’Hit 4 perché per tali valori non sono ancora passati 5 minuti. Tieni presente che questa allocazione creerà una dimensione con più valori da un campo con un solo valore. Questo modello deve essere supportato anche sulle dimensioni basate su array:

| Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valori originali | A,B | C | B,C |  | A |
| post-persistenza | A,B | A,B,C | A,B,C | B,C | A,B,C |

### allocazioni &quot;Primo noto&quot; e &quot;Ultimo noto&quot;

Questi due nuovi modelli di allocazione prendono il primo o l’ultimo valore osservato per una dimensione all’interno di un ambito di persistenza specificato (sessione, persona o periodo di tempo personalizzato con lookback) e lo applicano a tutti gli eventi nell’ambito specificato. Esempio:

| Dimensione | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valori originali |  | C | B |  | A |
| primo noto | C | C | C | C | C |
| ultimo noto | A | A | A | A | A |

Il primo o l’ultimo valore noto può essere applicato a una sola sessione o all’ambito della persona (intervallo di reporting) o a un ambito personalizzato o basato su un’ora (essenzialmente un ambito della persona con un intervallo di lookback aggiunto).

## Scadenza

[!UICONTROL Expiration] consente di specificare la finestra di persistenza per una dimensione.

Esistono quattro modi per far scadere un valore di dimensione:

* Sessione (impostazione predefinita): Scade dopo una determinata sessione.
* Persona: ?
* Ora: Puoi impostare la scadenza del valore della dimensione dopo un determinato periodo di tempo o evento.
* Metrica: Puoi specificare una qualsiasi delle metriche definite come fine di scadenza per questa dimensione (ad esempio una metrica &quot;Acquisto&quot;).
* Personalizzato:

### Qual è la differenza tra Allocazione e Attribuzione?

**Allocazione**: Considera l&#39;allocazione come &quot;trasformazione dei dati&quot; della dimensione. L’allocazione avviene prima del filtro. Se crei un filtro, questo verrà escluso dalla dimensione trasformata.

**Attribuzione**: Come posso distribuire il credito di una metrica alla dimensione a cui è applicata? L’attribuzione viene eseguita dopo il filtraggio.

