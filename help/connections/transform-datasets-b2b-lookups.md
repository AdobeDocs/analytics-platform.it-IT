---
title: Trasformare i set di dati per le ricerche B2B
description: Descrive come trasformare i dati in set di dati di schemi di ricerca B2B specifici
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: ffa57c19174bf1618957efe7191c8486c8e3a900
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Trasformare i set di dati per le ricerche B2B

Per supportare le ricerche basate su persone sui dati B2B (tra cui account, opportunità, elenchi di marketing e campagne), è necessaria la trasformazione dei set di dati di ricerca B2B.

Questa trasformazione è disponibile solo per i set di dati con dati per schemi di ricerca B2B, in base alle classi seguenti:

* Relazione della persona dell’account aziendale XDM
* Relazione della persona dell’opportunità di business XDM
* Membri dell’elenco di marketing aziendale XDM
* Membri della campagna aziendale XDM

Per abilitare la trasformazione per un set di dati di questo tipo:

![Abilita set di dati di trasformazione](assets/transform-dataset.gif)

* Accertati di selezionare l’identificatore corretto per **[!UICONTROL Key]** e **[!UICONTROL Matching key]**, ad esempio `personKey.sourceKey`.

* Seleziona le opzioni per importare nuovi dati e la retrocompilazione del set di dati.

* Seleziona **[!UICONTROL Transform dataset for B2B lookups]**.

  Questa opzione trasforma il set di dati in modo che possa essere utilizzato per ricerche basate su persone in scenari B2B.


  >[!IMPORTANT]
  >
  >Una volta attivata e salvata la connessione, la trasformazione è irreversibile. Non è possibile modificare l’impostazione di trasformazione per un set di dati una volta salvata una connessione, se non rimuovendo e aggiungendo nuovamente il set di dati alla connessione.

Per abilitare la trasformazione per uno o più set di dati che fanno già parte di una connessione esistente:

1. Rimuovi i set di dati dalla connessione.
1. Salva la connessione.
1. Aggiungi i set di dati alla connessione durante l’attivazione della trasformazione per i set di dati

## Informazioni di base

I set di dati non trasformati, per gli schemi basati sulle quattro classi di schema sopra menzionate, possono contenere più righe per un singolo identificatore persona. Le ricerche basate su persona corrispondono solo all’occorrenza più recente dell’identificatore della persona, impedendo una ricerca corretta basata sull’ID persona di account, opportunità, elenchi di marketing o campagne.

La trasformazione modifica il set di dati di ciascuna delle quattro classi di schema (arancione nell’illustrazione seguente) in modo che per ogni identificatore della persona venga creato un array (oggetto) per i dati rilevanti (account, opportunità, elenchi di marketing o campagne) nei set di dati di ricerca (rosa nell’illustrazione seguente). Questa trasformazione consente il corretto funzionamento delle ricerche basate su ID persona.

![Schemi B2B](./assets/b2b-schemas.svg)
