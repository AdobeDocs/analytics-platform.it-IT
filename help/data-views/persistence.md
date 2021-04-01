---
title: Cos’è la persistenza della dimensione nel Customer Journey Analytics?
description: La persistenza del Dimension è una combinazione di allocazione e scadenza. Insieme, determinano quali valori di dimensione persistono.
translation-type: tm+mt
source-git-commit: b99e108e9f6dd1c27c6ebb9b443f995beb71bdbd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Persistenza

La persistenza del Dimension è una combinazione di allocazione e scadenza. Insieme, determinano quali valori di dimensione persistono. L’Adobe consiglia vivamente di discutere all’interno dell’organizzazione in che modo vengono gestiti più valori per ciascuna dimensione (allocazione) e quando i valori delle dimensioni smettono di mantenere i dati (scadenza).

* Per impostazione predefinita, un valore di dimensione utilizza l’ultima allocazione. I nuovi valori sovrascrivono quelli persistenti.
* Per impostazione predefinita, un valore di dimensione utilizza una scadenza di [!UICONTROL Session].

## Allocazione

Determina il modo in cui CJA assegna il credito per un evento di successo se una variabile riceve più valori prima dell’evento. I valori supportati includono:

* Più recente: L’ultimo valore di eVar riceve sempre crediti per eventi di successo fino alla scadenza di tale eVar.
* Valore originale: Il primo eVar riceve sempre crediti per eventi di successo fino alla scadenza di tale eVar.
* Istanza: ??

Nota: Il passaggio dell’allocazione a o da Lineare impedisce la visualizzazione dei dati storici. La combinazione di tipi di allocazione nell’interfaccia di reporting può portare a dati errati nei rapporti. Ad esempio, l’allocazione lineare potrebbe dividere i ricavi in diversi valori di eVar. Dopo aver ripristinato l&#39;allocazione più recente, il 100% di tali entrate sarebbe associato al valore singolo più recente. Questa associazione può portare a conclusioni errate da parte degli utenti.

Per evitare la probabilità di confusione nei rapporti, Analytics rende i dati storici non disponibili nell’interfaccia. Può essere visualizzato se si decide di ripristinare l&#39;eVar specificato all&#39;impostazione di allocazione iniziale, anche se non è necessario modificare le impostazioni di allocazione eVar semplicemente per accedere ai dati storici. L’Adobe consiglia di utilizzare un nuovo eVar quando si desidera impostare nuove impostazioni di allocazione per i dati già registrati, anziché modificare le impostazioni di allocazione su un eVar che dispone già di una quantità significativa di dati storici.

## Scadenza

I valori Dimension scadono dopo il periodo di tempo specificato. Una volta scaduto il valore della dimensione, non riceve più crediti per una metrica. È inoltre possibile configurare Dimension in modo che scadano sulle metriche. Ad esempio, se hai una promozione interna che scade alla fine di una visita, la promozione interna riceve credito solo per gli acquisti o le registrazioni che si verificano durante la visita in cui sono stati attivati.

Ci sono due modi per scadere un eVar:

Puoi impostare l’eVar in modo che scada dopo un determinato periodo di tempo o evento.
È possibile utilizzare la forza della scadenza di un eVar reimpostandolo, utile quando si ripropone una variabile.
Ad esempio, se modifichi la scadenza di un eVar da 30 a 90 giorni, i valori eVar raccolti continueranno a persistere per la durata del nuovo set di scadenza (in questo caso, 90 giorni). Il sistema controlla semplicemente l&#39;impostazione di scadenza corrente e l&#39;ultima marca temporale impostata del valore eVar raccolto per determinare la scadenza. Solo l’opzione Ripristina scade i valori e lo fa immediatamente.

Un altro esempio: Se un eVar viene utilizzato a maggio per riflettere le promozioni interne e scade dopo 21 giorni, e a giugno viene utilizzato per acquisire le parole chiave di ricerca interne, il 1° giugno è necessario forzare la scadenza o reimpostare la variabile. In questo modo i valori delle promozioni interne rimarranno esclusi dalle relazioni di giugno.