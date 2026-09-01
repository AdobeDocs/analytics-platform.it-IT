---
title: Casi d’uso di reporting e filtro del consenso
description: Esplora i casi d’uso per la generazione di rapporti sull’iscrizione alla policy di consenso dei visitatori e per il filtraggio dei visitatori non consenzienti al momento dell’acquisizione in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 4661a066f90991e6fb149c6909ef4a9f75cf02ac
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 0%

---

# Casi d’uso di reporting e filtraggio del consenso

La funzione di reporting e filtro del consenso consente di creare rapporti sull’iscrizione alla politica di consenso dei visitatori e, facoltativamente, di escludere i visitatori non consenzienti prima che i loro dati entrino in Customer Journey Analytics. Per informazioni generali, consulta [Panoramica sui rapporti di consenso e filtri](/help/connections/consent-reporting-filtering/consent-overview.md).

Questo articolo descrive alcuni casi d’uso di esempio. Prima di rivederle, acquisisci familiarità con le considerazioni riportate di seguito, in quanto influiscono sui risultati visualizzati nei rapporti.

## Considerazioni sul reporting

* **Il filtro si applica al livello di connessione**: quando si abilita il filtro, tutte le visualizzazioni dati nella connessione configurata ereditano lo stesso comportamento. Non è possibile filtrare una visualizzazione dati in una connessione in modo diverso da un’altra.

* **Il filtro utilizza la logica di inclusione**: i dati di un visitatore vengono acquisiti solo se il visitatore corrisponde a tutti i criteri di consenso applicabili alle azioni di marketing abilitate. Un visitatore a cui mancano i criteri applicabili è escluso.

* **I dati esclusi non sono recuperabili**: poiché il filtro si verifica al momento dell&#39;acquisizione, i dati esclusi non vengono memorizzati in Customer Journey Analytics. La modifica della configurazione in un secondo momento non comporta il recupero dei dati esclusi per le date passate.

* **L&#39;appartenenza ai criteri di consenso proviene dal set di dati profilo**: il reporting riflette l&#39;appartenenza ai criteri di consenso presente nel campo `consentPoliciesIDMap` del set di dati profilo. Un visitatore deve avere un evento corrispondente nella connessione per essere visualizzato nel reporting.

## Casi d’uso di esempio

### Caso d’uso 1: rapporto sul consenso senza filtrare i dati

Scopri quanti visitatori corrispondono a ciascun criterio di consenso prima di decidere se filtrare, per rispondere a domande come:

* _&quot;Quanti dei nostri visitatori hanno acconsentito all&#39;utilizzo di Analytics?&quot;_
* _&quot;Quali criteri di consenso hanno la copertura più e meno estesa tra i visitatori?&quot;_

**Flusso di configurazione:**

1. Crea una configurazione e seleziona la sandbox, il set di dati profilo e la connessione che contengono i dati di iscrizione al criterio di consenso.

1. Lascia entrambi i filtri **[!UICONTROL Dati di Analytics]** e **[!UICONTROL Dati scientifici]** disattivati.

1. In Analysis Workspace, crea una tabella a forma libera con la dimensione **[!UICONTROL Nome criterio]** e la metrica **[!UICONTROL Visitatori con consenso]** per visualizzare la copertura per criterio.

Utilizza queste informazioni per decidere se abilitare i filtri e per quali azioni di marketing.

### Caso d’uso 2: escludere i visitatori non consenzienti dai rapporti di Analytics

Assicurati che il reporting standard includa solo i visitatori che hanno acconsentito all’utilizzo di Analytics, per rispondere a domande come:

* _&quot;Come si comporta il nostro pubblico quando eseguiamo report solo sui visitatori consenzienti?&quot;_
* _&quot;Possiamo essere certi che i dati dei visitatori non consenti non entrino mai nei nostri rapporti di analisi?&quot;_

**Flusso di configurazione:**

1. Crea o modifica una configurazione per la connessione che abilita i rapporti di analisi.

1. Attiva/disattiva filtro **[!UICONTROL Dati di Analytics]**.

1. Conferma la configurazione. Da questo momento in poi, Customer Journey Analytics acquisisce i dati di un visitatore solo se il visitatore corrisponde a tutti i criteri di consenso applicabili all’azione di marketing Analytics.

Poiché il filtro si verifica al momento del caricamento, i rapporti a valle, le esportazioni e le API riflettono automaticamente solo i visitatori che acconsentono, senza richiedere modifiche al momento del reporting.

### Caso d’uso 3: filtrare i casi d’uso di analisi e scienza dei dati in modo indipendente

Applica requisiti di consenso diversi alla generazione di rapporti standard e ai casi di utilizzo di data science, per rispondere a domande come:

* _&quot;È possibile includere un set più ampio di visitatori in Analytics applicando al contempo un consenso più severo per l&#39;apprendimento automatico?&quot;_

**Flusso di configurazione:**

1. Crea o modifica una configurazione per la connessione pertinente.

1. Attiva l&#39;interruttore **[!UICONTROL Dati di Analytics]**, l&#39;interruttore **[!UICONTROL Dati scientifici]** o entrambi, a seconda dei requisiti di consenso per ogni caso d&#39;uso.

1. Conferma la configurazione. Customer Journey Analytics valuta in modo indipendente i criteri di consenso applicabili a ogni azione di marketing abilitata.

Utilizza questo approccio quando la tua organizzazione applica requisiti di consenso diversi a diverse categorie di utilizzo dei dati.
