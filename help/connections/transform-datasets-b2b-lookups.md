---
title: Trasformare i set di dati per le ricerche B2B
description: Descrive come trasformare i dati in set di dati di schemi di ricerca B2B specifici
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: d1097ca5f981623283a7d02200d5023548046429
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 4%

---

# Trasformare i set di dati per le ricerche B2B

Per supportare le ricerche basate su persone sui dati B2B (tra cui account, opportunità, elenchi di marketing e campagne), la trasformazione dei set di dati di ricerca B2B può migliorare l’accuratezza dei dati.

Questa trasformazione è disponibile solo per i set di dati con dati per schemi di ricerca B2B, in base alle classi seguenti:

* [Relazione della persona dell&#39;account aziendale XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [Relazione della persona dell&#39;opportunità di business XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [Membri dell&#39;elenco di marketing aziendale XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [Membri della campagna aziendale XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>Per ogni ID è previsto un limite massimo di 10.000 elementi. Questo limite implica che per ogni ID persona dato puoi avere solo 10.000 account, o 10.000 opportunità, o 10.000 elenchi di marketing, o 10.000 campagne.

>[!PREREQUISITES]
>
>Per il corretto funzionamento dell’acquisizione, è necessario verificare che i set di dati di ricerca B2B includano dati compilati per i seguenti campi (come definiti negli schemi di ricerca B2B):
>
>| Set di dati contenente dati conformi allo schema | Campo popolato con dati |
>|---|---|
>| Relazione della persona dell’account aziendale XDM | `accountPersonID` |
>| Persona dell’opportunità di business XDM | `opportunityPersonID` |
>| Elenco di marketing aziendale XDM | `marketingListMemberID` |
>| Membri della campagna aziendale XDM | `campaign.sourceKey` |
>

Per abilitare la trasformazione per un set di dati di ricerca B2B:

![Abilita set di dati di trasformazione](/help/connections/assets/transform.gif)

* Verificare per ogni set di dati i valori consigliati per **[!UICONTROL Key]** e **[!UICONTROL Matching key]**. Se si modificano i valori dai valori suggeriti, verrà visualizzato un avviso che richiede di continuare. Devi accertarti che:

   * Il valore selezionato per **Chiave** si basa sul tipo di dati ID persona.
   * Il valore selezionato per **Chiave corrispondente** è definito come campo di identità principale per il set di dati dell&#39;evento.

* Seleziona le opzioni per importare nuovi dati e la retrocompilazione del set di dati.

* Seleziona **[!UICONTROL Transform dataset for B2B lookups]**.

  Questa opzione trasforma il set di dati in modo che possa essere utilizzato per ricerche basate su persone in scenari B2B.


  >[!IMPORTANT]
  >
  >Una volta attivata e salvata la connessione, la trasformazione è irreversibile. Non puoi modificare la configurazione di Chiave, Chiave corrispondente e Set di dati Trasforma. Puoi solo rimuovere, aggiungere e riconfigurare il set di dati.

Per abilitare la trasformazione per uno o più set di dati che fanno già parte di una connessione esistente:

1. Rimuovi i set di dati dalla connessione.
1. Salva la connessione.
1. Aggiungi i set di dati alla connessione durante l’attivazione della trasformazione per i set di dati.

## Informazioni di base

I set di dati non trasformati, per gli schemi basati sulle quattro classi di schema sopra menzionate, possono contenere più righe per un singolo identificatore persona. Le ricerche basate su persona corrispondono solo all’occorrenza più recente dell’identificatore della persona, impedendo una ricerca corretta basata sull’ID persona di account, opportunità, elenchi di marketing o campagne.

La trasformazione modifica il set di dati di ciascuna delle quattro classi di schema (arancione nell’illustrazione seguente) in modo che per ogni identificatore della persona venga creato un array (oggetto) per i dati rilevanti (account, opportunità, elenchi di marketing o campagne) nei set di dati di ricerca (rosa nell’illustrazione seguente). Questa trasformazione consente il corretto funzionamento delle ricerche basate su ID persona.

![Schemi B2B](./assets/b2b-schemas.svg)
