---
title: Configurare Experience Platform
description: Come configurare schemi e set di dati per Experience Platform Data Mirror for Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
source-git-commit: ebd6695cd5242c5443ccfbc5a38f337454f6de33
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 2%

---

# Configurare Experience Platform

La funzionalità Data Mirror di Experience Platform per Customer Journey Analytics richiede la corretta configurazione di diversi componenti Experience Platform:

* schema
* set di dati
* connettore di origine

Di seguito sono riportati i dettagli da tenere in considerazione per la configurazione di ciascuno di questi componenti.

## Schema

È necessario creare uno schema basato su modello che modella la tabella nativa del data warehouse di cui si desidera eseguire il mirroring. Quando crei lo schema basato su modello, assicurati che siano soddisfatti i seguenti requisiti:

* Quando viene richiesto il tipo di schema basato su modello, accertati di selezionare l’opzione manuale.
* Seleziona lo schema appropriato per il tipo di dati. La funzionalità Data Mirror viene utilizzata principalmente per i dati di serie temporali (ad esempio, i dati evento).

* Definisci i campi nello schema e i relativi attributi
* Configura gli attributi richiesti per i campi in uno schema basato su modello:

   * chiave primaria
   * identificatore di versione
   * identificatore della marca temporale (per i dati di serie temporali).

## Set di dati

Puoi impostare in anticipo un set di dati per lo schema o creare un set di dati quando configuri il connettore di origine.
Quando crei un set di dati in anticipo o selezioni un set di dati, assicurati che i dati utilizzino uno [schema](#schema) basato su modello creato in precedenza.


## Connettore di origine

Per impostare il connettore di origine sulle soluzioni native di data warehouse supportate, utilizza il flusso di lavoro Origini che ti guida attraverso la configurazione. Tale flusso di lavoro è costituito dai seguenti passaggi:

### Autenticazione

Per l&#39;autenticazione rispetto alla soluzione nativa data warehouse supportata, consulta la documentazione Experience Platform pertinente:

* [Database di Azure](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake)


### Selezionare i dati

Una volta connessa correttamente alla soluzione nativa del data warehouse, selezionare la tabella dalla soluzione nativa del data warehouse che si desidera utilizzare per il mirroring dei dati. Una volta selezionata, viene visualizzata un’anteprima del contenuto dei dati.


### Dettagli del flusso di dati

Assicurati di abilitare l’acquisizione dei dati di modifica. Viene visualizzato un pannello di informazioni che illustra i requisiti per l&#39;acquisizione dei dati di modifica.

Specifica un set di dati nuovo o esistente basato sullo schema basato su modello creato in precedenza. Specificate e selezionate altre opzioni nell&#39;interfaccia dei dettagli del flusso di dati.


### Mappatura

Mappa i campi della tabella nella soluzione nativa di data warehouse ai campi specificati per lo schema basato su modello.


### Pianificazione

Definisci una pianificazione per eseguire il mirroring dei dati dalla tabella nella soluzione nativa di data warehouse al set di dati in Experience Platform.


### Rivedete

Rivedi le impostazioni del connettore di origine per la soluzione nativa del data warehouse che supporta il mirroring dei dati e modifica l’acquisizione dei dati.


Una volta completata l’impostazione del connettore di origine, viene creato un flusso di dati. Da quel momento in poi le modifiche ai dati (inserimenti, aggiornamenti, eliminazioni) nella soluzione nativa di data warehouse vengono rispecchiate nel set di dati specificato.


>[!MORELIKETHIS]
>
>[Guida rapida di Data Mirror: simulare e utilizzare dati basati su modelli](data-mirror.md)
>
