---
title: Considerazioni su Data Mirror
description: Considerazioni aggiuntive da tenere in considerazione quando si desidera sincronizzare i dati tra soluzioni native di data warehouse e Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
autotag-review: '2026-05-19T06:55:09.938Z'
TQID: 'https://experienceleague.adobe.com/uZjXZUKUMeXLxxpTRrkCZrPsGhxseSxOtJ9X0ZjG5wU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 832
ht-degree: 1%

---

# Considerazioni su Experience Platform Data Mirror

Questo articolo descrive i fattori da considerare durante la configurazione dei set di dati di Data Mirror.

## Nuova colonna nella tabella di origine

Quando viene aggiunta una nuova colonna a una tabella di origine in un set di dati con mirroring dei dati abilitato per CDC, tale modifica può attivare gli aggiornamenti per tutte le righe esistenti. Questi aggiornamenti vengono elaborati come modifiche tramite CDC, che:

* Può comportarsi come una riscrittura di tabella completa da una prospettiva progressiva.
* Può aumentare notevolmente il volume di acquisizione, il che potrebbe causare il superamento del limite di acquisizione da parte dell’aggiornamento.

Strategia consigliata per le colonne nella tabella di origine:

* Assicurati che tutte le colonne pertinenti siano state definite inizialmente.
* Esegui la mappatura di ogni colonna che potresti ritenere necessaria inizialmente.

Se desideri aggiungere una nuova colonna, esistono due opzioni, a seconda che sia necessaria la retrocompilazione retroattiva:

* Retroattività:

   * Rimuovi il set di dati corrente.
   * Configura nuovamente il connettore con la colonna aggiornata.

  In questo modo i dati vengono recuperati in modo più efficiente e tempestivo.

* Nessuna retrocompilazione retroattiva:

   * Aggiungi la colonna nella tabella di origine.
   * Aggiungi la colonna nello schema del set di dati di destinazione.
   * Aggiorna il mapping per includere il nuovo campo (colonna) dalla tabella di origine al set di dati di destinazione.

Questa strategia:

* Evita costose evoluzioni degli schemi in un secondo momento (aggiornamenti di massa durante l’aggiunta di colonne).
* Consente di modificare il volume in modo più prevedibile rispetto a quando le colonne vengono aggiunte o modificate in un secondo momento.
* Consente di limitare i potenziali costi di calcolo sul lato del database esterno, in quanto il data warehouse potrebbe interpretare la nuova colonna come un aggiornamento di tutte le righe.


## Privacy Service

Le richieste di accesso a dati personali devono avvenire nello stesso modo in cui vengono gestite oggi le richieste di accesso a dati personali per gli schemi non relazionali, in quanto le richieste di accesso a dati personali sono indifferenti alla struttura dei dati.

I dati specchiati da uno schema relazionale esterno diventano parte dell’ecosistema Adobe e possono essere condivisi in tutto l’ecosistema, ad esempio tramite la pubblicazione dei tipi di pubblico di Customer Journey Analytics. L’invio di una richiesta di accesso a dati personali garantisce che le identità e i dati associati siano gestiti correttamente in tutto l’ecosistema Adobe.

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

In [schemi](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition) XDM e concetti sottostanti come [gruppi di campi](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition#field-group), un [campo](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition#field) definito all&#39;interno di un gruppo di campi propaga le etichette in tutti i set di dati in cui viene utilizzato il gruppo di campi. Ad esempio, un campo e-mail `emailID` in un gruppo di campi `identities`, è etichettato come lo stesso in tutti i set di dati in cui viene utilizzato il gruppo di campi `identities`.

In uno schema relazionale, il nome di una colonna è indipendente. Una colonna denominata `email` nella tabella `customers` è indipendente e distinta da una colonna denominata `email` in una tabella `prospects`. Questo comportamento implica che le etichette (come le etichette di utilizzo DULE, i criteri) devono essere applicate singolarmente ai campi nei set di dati con mirroring. In base all&#39;esempio precedente, è necessario applicare etichette sia al campo `email` nel set di dati `customers` che al campo `email` nel set di dati `prospects`.

La differenza di governance ha il seguente impatto:

* In qualità di cliente, è necessario eseguire un maggior numero di operazioni manuali di governance e configurazione.
* Potresti aver bisogno di indicazioni esplicite, pertanto non presumere che l’etichettatura una tantum tramite i gruppi di campi sia sufficiente per una governance corretta.

## Unione

Gli schemi relazionali hanno le seguenti considerazioni in quanto si riferiscono all’unione:

* L’unione basata su grafico è parzialmente supportata. Gli schemi relazionali non possono essere abilitati per il profilo o per il contributo al grafico.
* L’unione basata sui campi è completamente supportata.


## Chiavi di sistema e campi

Le considerazioni seguenti si applicano alle chiavi di sistema e ai campi:

* Il descrittore della chiave primaria, del descrittore della versione e della marca temporale deve essere un campo di livello principale nello schema XDM relazionale. Utilizza [mappatura campi](https://experienceleague.adobe.com/it/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema) durante l&#39;acquisizione per supportare questo requisito.
* È possibile omettere i campi di origine appropriati durante la [fase di mappatura](https://experienceleague.adobe.com/it/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema).
