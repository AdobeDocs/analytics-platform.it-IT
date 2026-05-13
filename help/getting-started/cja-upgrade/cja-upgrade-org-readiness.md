---
title: Aggiornare da Adobe Analytics a Customer Journey Analytics
description: Scopri i passaggi consigliati durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bd19250e-91c0-49f6-b6dc-3abd641344aa
TQID: https://experienceleague.adobe.com/DtETa7Qh3l2X9YSjkX56zX8CmDTWVpGvvyrd9HFayt4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 1186
ht-degree: 15%

---

# Preparare l’organizzazione all’aggiornamento a Customer Journey Analytics

Parte di un aggiornamento riuscito (come descritto in [Aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)) consiste nel preparare la tua organizzazione concentrandosi su alcune considerazioni operative. Per preparare la tua organizzazione, ti consigliamo di:

* Ottenere l’adesione e l’allineamento da parte delle principali parti interessate

* Definire e documentare gli obiettivi

* Impostare timeline realistiche e accurate

* Definire chiare responsabilità per i collaboratori

## Consenso e allineamento delle parti interessate

Le principali parti interessate e i responsabili decisionali della tua organizzazione devono allineare l’aggiornamento a Customer Journey Analytics.

Le sezioni seguenti descrivono come ottenere l’allineamento delle parti interessate.

### Concentrati sul valore

Concentrati sul valore che Customer Journey Analytics apporterà alla tua organizzazione e su come accelera il raggiungimento degli obiettivi aziendali.

Nella tabella seguente sono illustrate alcune funzioni chiave che è possibile evidenziare.

| Funzione | Beneficio | Esempio |
|---------|----------|---------|
| **[Pernottamento per tutti i tipi di dati](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home)** | Customer Journey Analytics è combinato con la capacità di Experience Platform di contenere tutti i tipi e schemi di dati. | Un’organizzazione di vendita al dettaglio può fornire visibilità all’intero percorso di clienti integrando i seguenti tipi di dati in un’unica vista: <ul><li>Transazioni clickstream web</li><li>Transazioni app mobili</li><li>Transazioni in-store</li><li>Dati CRM e fedeltà</li></ul> |
| **[Analisi cross-channel](/help/use-cases/cross-channel/cross-channel.md)** | Abilita una singola visualizzazione consolidata del comportamento dei clienti su vari canali, unificando i dati da varie proprietà web, mobili e offline. | Un’organizzazione di vendita al dettaglio che raccoglie dati da più canali potrebbe eseguire il seguente tipo di analisi:<p>Un acquirente fa clic su un annuncio di ricerca a pagamento, sfoglia i jeans online, riceve una notifica push e acquista il prodotto in-store due giorni dopo. Questa prospettiva unificata consente un’attribuzione cross-channel accurata, mostrando come i punti di contatto digitali contribuiscono alle vendite nel negozio. Supporta anche una segmentazione più precisa, come il targeting dei clienti &quot;sfogliati online, acquistati all’interno del negozio&quot; con offerte personalizzate. Inoltre, fornisce un reporting chiaro su tutti i canali dei ricavi in un’unica dashboard, sostituendo informazioni frammentate e segmentate con una comprensione olistica del comportamento dei clienti. |
| **[Elaborazione al momento del reporting](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | Applica impostazioni retroattive e crea più versioni di persistenza delle variabili senza dover modificare la modalità di raccolta dei dati sottostanti. | Poiché Customer Journey Analytics consente di creare e regolare metriche, dimensioni e modelli di attribuzione al volo senza riacquisire o rielaborare i dati, un’organizzazione di vendita al dettaglio potrebbe vedere in che modo una recente campagna social ha influenzato le vendite sia online che in negozio senza dover chiedere al team tecnico di ricostruire i set di dati. Possono modificare immediatamente il modello di attribuzione dall’ultimo contatto al primo contatto o all’attribuzione personalizzata basata su regole. |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | Aiuta gli esperti di marketing a comprendere in che modo i contenuti influiscono sugli indicatori prestazioni chiave definiti da un’azienda. Oltre ai dati comportamentali, Content Analytics raccoglie i dati sul modo in cui il contenuto viene utilizzato e su come genera un impatto. | Integrando dati web, app, e-mail e persino in un negozio, un’organizzazione di vendita al dettaglio potrebbe vedere esattamente in che modo ogni contenuto digitale che crea contribuisce al percorso e alla conversione dei clienti. <p>L’organizzazione retail potrebbe notare che una &quot;Guida estiva allo stile denim&quot; su una popolare piattaforma di social media determina un elevato coinvolgimento tra i membri fidelizzati, e che questi hanno il 40% di probabilità in più di acquistare denim in un negozio in una settimana.</p> |

### Nominare uno sponsor esecutivo

Trova e nomina uno sponsor esecutivo all’interno della tua organizzazione. Questo sponsor esecutivo deve capire come Customer Journey Analytics accelera il raggiungimento degli obiettivi aziendali.

Lo sponsor esecutivo è fondamentale in quanto:

* Campione Customer Journey Analytics all&#39;interno dell&#39;organizzazione

* Rimuovere i blocchi stradali

* Approvare le risorse

### Supporto sicuro da parte dei principali leader dell&#39;organizzazione

Con l’aiuto del tuo sponsor esecutivo, assicurati il supporto di altri leader chiave della tua organizzazione. È fondamentale che i leader delle seguenti aree dell’organizzazione comprendano i vantaggi di Customer Journey Analytics e siano disposti a contribuire a un’implementazione di successo:

* Analytics

* Marketing

* IT

* Legale e conformità

* Singole unità aziendali

## Sviluppare un piano di aggiornamento e comunicazione

### Sviluppa un piano di aggiornamento e distribuiscilo alle parti interessate

Un piano di aggiornamento può includere le seguenti informazioni:

* Una descrizione chiara del motivo per cui è in corso l’aggiornamento. Ad esempio, descrivi i vantaggi per gli utenti e per l’organizzazione o l’azienda nel suo complesso. Per ulteriori informazioni sui vantaggi, vedere [Concentrarsi sul valore](#focus-on-value).

* Una timeline generale, ad esempio quando è pianificato l’inizio dell’aggiornamento, un profilo delle principali tappe cardine e una stima del momento in cui è pianificato il completamento dell’aggiornamento.

* Un’indicazione di quando gli utenti possono iniziare i corsi di formazione ufficiali per imparare a utilizzare Customer Journey Analytics. Per ulteriori informazioni, consulta [Formazione degli utenti finali in tutta l&#39;organizzazione](#train-end-users-throughout-your-organization).

* Informazioni su chi sta guidando l’aggiornamento e come o quando le persone possono contattare per eventuali domande.

### Creare un piano di comunicazione

Un piano di comunicazione può includere le seguenti considerazioni:

* Una cadenza definita su quando le comunicazioni verranno inviate alle parti interessate e agli utenti

* Una descrizione del tipo di informazioni che verranno inviate

* Un piano per chi invierà le comunicazioni

* Cicli di feedback definiti per consentire alle parti interessate e agli utenti di porre domande o fornire feedback

## Valuta e controlla l’implementazione di Adobe Analytics

Esegui una valutazione e un controllo approfonditi dell’implementazione di Adobe Analytics, concentrandosi sulle seguenti aree chiave:

* Utenti attuali

* Accesso utente

* Progetti

* Processi aziendali

* Componenti personalizzati

Consulta le seguenti risorse per aiutarti a raccogliere queste informazioni:

* [Inventario di Analytics](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/analytics-inventory)

  Fornisce informazioni sul numero di progetti, segmenti, metriche calcolate, suite di rapporti e utenti all’interno dell’organizzazione.

* [Preparare la migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  Fornisce informazioni su come prepararsi per la migrazione di componenti, progetti e utenti.

## Identificare i campioni e i primi utilizzatori

Identifica i campioni della tua organizzazione. Questi campioni dovrebbero essere:

* Utenti avanzati di Adobe Analytics

* In grado di acquisire rapidamente esperienza in Customer Journey Analytics

* Disponibile per essere di aiuto e istruttore per gli altri, con l&#39;introduzione di Customer Journey Analytics a livello più ampio

## Formazione degli utenti finali in tutta l’organizzazione

* Offri una formazione pratica che si concentra sulle differenze nei modelli di dati, nei paradigmi di reporting e nelle nuove funzioni di Customer Journey Analytics.

* Offri sia sessioni live (workshop o orari di lavoro) che risorse on-demand (tutorial video, pagine wiki dinamiche e documentazione interna).

* Indirizza gli utenti a corsi di formazione, tutorial e documentazione pertinenti su Experience League.

  Le risorse seguenti possono essere utili per iniziare:

   * [Tutorial su Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/overview)

   * [Cos’è Customer Journey Analytics?](https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Introduzione a Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Supporto delle funzioni di Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)

## Segui i passaggi di aggiornamento consigliati

Quando sei pronto per iniziare il processo di aggiornamento, segui i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o i passaggi di aggiornamento generati in modo dinamico nella Guida all&#39;aggiornamento di Customer Journey Analytics. Per accedere alla guida da Customer Journey Analytics, seleziona la scheda **[!UICONTROL Workspace]**, quindi seleziona **[!UICONTROL Aggiornamento a Customer Journey Analytics]** nel pannello a sinistra. Segui le istruzioni visualizzate sullo schermo.
