---
title: Concetti e funzionalità di Customer Journey Analytics B2B edition
description: Concetti e funzionalità per B2B edition di Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 3812b10e558c1b8a3ee4fe474405543c68433d8e
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# Concetti e funzionalità di B2B edition

{{draft-b2b}}

Questo articolo spiega i concetti e le funzioni generali su set di dati e contenitori e le differenze tra lo standard e il B2B edition di Customer Journey Analytics.

I set di dati sono le origini di una connessione. Come parte dell’impostazione di una connessione, puoi definire i set di dati da includere in tale connessione.

I contenitori sono utilizzati in Customer Journey Analytics per supportare e facilitare funzioni come filtri, metriche calcolate e funzionalità di analisi avanzate.




## Contenitori standard

La versione *standard* di Customer Journey Analytics è basata sul concetto di tre contenitori: persona, sessione ed evento. In una configurazione standard di Customer Journey Analytics, questi contenitori rilevanti vengono generati implicitamente in base alla configurazione.

È possibile ridefinire il modo in cui questi contenitori vengono denominati quando si configura una visualizzazione dati, ma concettualmente la versione standard utilizza una gerarchia di contenitori basata su persona.

![B2C](assets/b2c-containers.svg){zoomable="yes"}

Nella connessione vengono aggiunti i set di dati Evento, Profilo e Ricerca e vengono selezionate le identità da utilizzare per definire la connessione tra questi set di dati. Come parte della connessione, viene generata automaticamente una gerarchia di contenitori basata su persona. In questa gerarchia il contenitore Sessione è definito dalle [Impostazioni sessione](/help/data-views/session-settings.md) nella visualizzazione dati.


## contenitori B2B

In Customer Journey Analytics B2B edition, all’elenco dei contenitori generati viene aggiunto un contenitore Account.  Inoltre puoi configurare la generazione di contenitori aggiuntivi, come Account globale, Gruppo di acquisto e Opportunità.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

Nella connessione puoi aggiungere i set di dati Evento, Account, Account globale, Opportunità, Gruppo di acquisto e altri set di dati di ricerca. Seleziona Account come ID principale per la connessione in modo da poter utilizzare le identità basate su account per definire la connessione tra i set di dati. Come parte della connessione, viene generata automaticamente una gerarchia di contenitori basata sull’account. In tale gerarchia il contenitore Sessione tra il contenitore Persona e il contenitore Evento è definito dalle [Impostazioni sessione](/help/data-views/session-settings.md) nella visualizzazione dati. Inoltre, i contenitori Sessione, ad esempio tra Account ed Evento, non sono attualmente supportati.

Opportunità, Gruppo di acquisto e Persona sono tutti contenitori di pari livello del contenitore Account. Per una descrizione e un utilizzo di base, consulta la tabella seguente.

| Contenitore B2B | Descrizione<br/>Caso d&#39;uso di base |
|---|---|
| Account | Un&#39;azienda cliente o potenziale cliente della tua attività. Potrebbe trattarsi di una filiale o di una divisione di un’organizzazione più grande. Conto rappresenta l&#39;organizzazione per la quale si effettua la vendita e di cui si desidera tenere traccia a livello di organizzazione. |
| Account globale (facoltativo) | Società capogruppo di un gruppo di società collegate. Un conto globale non ha una società madre, ma può avere affiliate o divisioni appartenenti al conto globale. Un account senza padre o affiliate deve essere elencato sia nel campo account che nel campo account globale, se entrambi sono abilitati come parte dell&#39;impostazione di una connessione. |
| Opportunità (facoltativo) | Una raccolta di prodotti e servizi venduti insieme. Un’opportunità spesso coinvolgeva varie fasi del ciclo di vendita per chiuderla come una vendita.<br>I dati sulle opportunità vengono utilizzati per misurare la progressione delle opportunità attraverso il funnel di vendita. Ad esempio, un report che fornisce dettagli sulle principali opportunità passate dalla fase 3 alla fase 4. |
| Gruppo di acquisto (facoltativo) | Una raccolta di persone all’interno di un’organizzazione coinvolte nel processo decisionale per l’acquisto di un prodotto o di un servizio. <br/>Puoi utilizzare i dati del gruppo di acquisto per tenere traccia dei gruppi di acquisto tramite la gestione delle campagne. Ad esempio, crea un segmento di pubblico di gruppi di acquisto chiave.<br/> È probabile che si desideri una ricerca dal gruppo di acquisto ai dati del profilo, in modo da poter creare rapporti sulle persone in un gruppo di acquisto. |
| Persona | Un individuo, spesso identificato da un indirizzo e-mail univoco che ha interagito con l&#39;azienda. <br/>Utilizzare i dati del profilo per identificare le persone che lavorano per un account. Ad esempio: esegui il targeting di tutte le persone di un account che si sono iscritte a una conferenza. |


## Corrispondenza per contenitore o campo

Quando definisci una connessione in Customer Journey Analytics, puoi definire per ogni set di dati di record (profilo o ricerca), se tale set di dati corrisponde per contenitore o per campo.

### Corrispondenza per contenitore

Se un set di dati record trova corrispondenza in base al contenitore, ad esempio Gruppo acquisti, il set di dati record viene considerato come un tipo di set di dati profilo e come un set di dati profilo nell’interfaccia utente.

### Corrispondenza per campo

Se a un set di dati record corrisponde un campo, ad esempio Membro elenco marketing, nell’interfaccia utente il set di dati record viene considerato come un tipo di set di dati di ricerca e come un set di dati di ricerca.



## Rapporto sui dati basati su persone e account

Se desideri creare rapporti sui contenitori basati su persone (e sulle identità di persona) e sui contenitori basati su account (e sulle identità di account), imposta due connessioni separate in Customer Journey Analytics. Una connessione in cui si seleziona Persona come ID primario e una connessione in cui si seleziona Account come ID primario. Customer Journey Analytics non supporta la generazione di rapporti basati su persone e account dallo stesso contenitore.
