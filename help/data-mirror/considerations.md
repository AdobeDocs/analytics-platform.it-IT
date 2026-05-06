---
title: Considerazioni su Data Mirror
description: Considerazioni aggiuntive da tenere in considerazione quando si desidera sincronizzare i dati tra soluzioni native di data warehouse e Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
hide: true
source-git-commit: 93f38f57021bf66cacd700ce6fbc46338fd6a034
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# Considerazioni su Experience Platform Data Mirror

Questo articolo descrive i fattori da considerare durante la configurazione dei set di dati di Data Mirror.

## Nuova colonna nella tabella di origine

Quando viene aggiunta una nuova colonna a una tabella di origine in un set di dati con mirroring dei dati abilitato per CDC, tale modifica può attivare gli aggiornamenti per tutte le righe esistenti. Questi aggiornamenti vengono elaborati come modifiche tramite CDC, che:

* Può comportarsi come una riscrittura di tabella completa da un punto di vista dei costi.
* Può aumentare notevolmente il volume di acquisizione, in particolare con qualsiasi prezzo futuro *cambiare moltiplicatore* (ad esempio, le operazioni di unione potrebbero essere addebitate a tassi più elevati).

Strategia consigliata per le colonne nella tabella di origine:

* Assicurati che la maggior parte delle colonne rilevanti, se non tutte, siano definite inizialmente.
* Esegui la mappatura di ogni colonna che potresti ritenere necessaria inizialmente.

Questa strategia:

* Evita costose evoluzioni degli schemi in un secondo momento (aggiornamenti di massa durante l’aggiunta di colonne).
* Consente di modificare il volume in modo più prevedibile rispetto a quando le colonne vengono aggiunte o modificate in un secondo momento.
* Potrebbero verificarsi alcuni costi di calcolo aggiuntivi sul lato del database esterno, in quanto il data warehouse potrebbe interpretare tutte le colonne come aggiornamenti.

Per gestire le nuove colonne nelle tabelle del data warehouse esterno, eseguire la procedura seguente:

1. Crea un nuovo schema con la colonna aggiunta.
1. Configura un nuovo connettore di origine che inserisce i dati.
1. Carica la retrocompilazione in modo appropriato.
1. Utilizza le modifiche CDC in futuro.

Questo approccio riduce al minimo l&#39;impatto su entrambe le parti.

## Privacy Service

Le richieste di accesso a dati personali devono avvenire nello stesso modo in cui vengono gestite oggi le richieste di accesso a dati personali per gli schemi non relazionali, in quanto le richieste di accesso a dati personali sono indifferenti alla struttura dei dati.

I dati specchiati in un set di dati da dati esterni basati su uno schema relazionale diventano parte dell’ecosistema Adobe e possono essere condivisi in molti modi. Ad esempio, tramite la pubblicazione di tipi di pubblico.

Pertanto, le richieste di accesso a dati personali non devono essere limitate al set di dati in mirroring, ma devono anche comportare aggiornamenti ai dati di origine nel database esterno.

## Comportamento igienico

Il servizio di igiene opera su *identità primarie*, ma le tabelle nel database esterno con mirroring hanno *chiavi primarie*, non identità primarie.

Le conseguenze della differenza tra le identità primarie e le chiavi primarie sono che le eliminazioni di igiene non possono essere eseguite direttamente su queste tabelle relazionali. Di conseguenza, devi:

* Eliminare i dati nelle proprie tabelle di origine all&#39;interno della soluzione data warehouse e assicurarsi che le operazioni di eliminazione passino attraverso CDC (o la colonna di modifica manuale).
* Invia richieste di igiene e privacy in Adobe per qualsiasi set di dati basato su XDM a valle con informazioni sull’identità (ad esempio: visualizzazioni di Customer Journey Analytics, set di dati di Real-Time Customer Data Platform, set di dati specifici di Adobe Journey Optimizer e altro).

La differenza tra identità primaria e chiave primaria introduce un modello di responsabilità condivisa:

* Adobe elabora l’igiene in cui sono presenti identità.
* In qualità di cliente, sei responsabile dell’allineamento dei tuoi processi di igiene nel database di origine con le richieste di igiene inviate ad Adobe.

## Differenze di governance

In [schemi](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition) XDM e concetti sottostanti come [gruppi di campi](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group), un [campo](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field) definito all&#39;interno di un gruppo di campi propaga le etichette in tutti i set di dati in cui viene utilizzato il gruppo di campi. Ad esempio, un campo e-mail `emailID` in un gruppo di campi `identities`, è etichettato come lo stesso in tutti i set di dati in cui viene utilizzato il gruppo di campi `identities`.

In uno schema relazionale, il nome di una colonna è indipendente. Una colonna denominata `email` nella tabella `customers` è indipendente e distinta da una colonna denominata `email` in una tabella `prospects`. Questo comportamento implica che le etichette (come le etichette di utilizzo DULE, i criteri) devono essere applicate singolarmente ai campi nei set di dati con mirroring. In base all&#39;esempio precedente, è necessario applicare etichette sia al campo `email` nel set di dati `customers` che al campo `email` nel set di dati `prospects`.

La differenza di governance ha il seguente impatto:

* In qualità di cliente, è necessario eseguire un maggior numero di operazioni manuali di governance e configurazione.
* Potresti aver bisogno di indicazioni esplicite, pertanto non presumere che l’etichettatura una tantum tramite i gruppi di campi sia sufficiente per una governance corretta.
