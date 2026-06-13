---
title: Mappatura del modello dati GA4 su Customer Journey Analytics
description: Scopri come il modello dati basato su eventi di GA4 si traduce in schemi e set di dati XDM in Customer Journey Analytics.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# Mappatura del modello dati GA4 su Customer Journey Analytics

GA4 e Customer Journey Analytics sono entrambe piattaforme basate su eventi, il che rende la traduzione del modello di dati tra di loro più diretta di quanto non sia stata da Universal Analytics. Comprendere come gli eventi e i parametri di GA4 corrispondano ai campi e ai set di dati XDM di Customer Journey Analytics semplifica l’interpretazione dei rapporti e la collaborazione con il team di implementazione.

## Modello dati basato su eventi di GA4

Ogni interazione in GA4 è un **evento**: un&#39;azione denominata con un set facoltativo di **parametri** che forniscono contesto. Non esistono tipi di oggetto distinti per visualizzazioni di pagina, sessioni o obiettivi; si tratta di eventi.

| Tipo di evento GA4 | Esempi |
|---|---|
| Raccolta automatica | `page_view`, `session_start`, `first_visit`, `scroll` |
| Misurazione avanzata | `file_download`, `video_start`, `form_submit` |
| Consigliato | `purchase`, `add_to_cart`, `sign_up` |
| Personalizzato | Qualsiasi nome evento definito |

Ogni evento può contenere fino a 25 parametri. Ad esempio, un evento `purchase` include `transaction_id`, `value`, `currency` e `items` come parametri.

## Archiviazione dei dati in Customer Journey Analytics

Customer Journey Analytics ottiene i dati da **Adobe Experience Platform**. I dati in Platform sono archiviati in **set di dati**, ciascuno conforme a uno **schema** creato utilizzando **Experience Data Model (XDM)**. XDM è lo standard aperto di Adobe per la rappresentazione dei dati sull’esperienza del cliente.

In Customer Journey Analytics sono disponibili tre tipi di set di dati:

| Tipo di set di dati di CJA | Equivalente GA4 | Cosa contiene |
|---|---|---|
| [!UICONTROL Set di dati evento] | Flusso di eventi GA4 | Interazioni di serie temporali (visualizzazioni di pagina, clic, acquisti) |
| [!UICONTROL Set di dati profilo] | Proprietà utente GA4 | Attributi a livello di persona (campi CRM, stato di fedeltà, dati demografici) |
| [!UICONTROL Set di dati di ricerca] | Dimensioni personalizzate GA4 utilizzate come tabelle di riferimento | Dati di riferimento del valore chiave (catalogo dei prodotti, nomi delle campagne) |

Customer Journey Analytics non dispone di eVar, prop o eventi di successo. Tutte le dimensioni e le metriche provengono direttamente dai campi dello schema XDM. Non esistono limiti al numero di valori di dimensione univoci.

## Eventi raccolti automaticamente

GA4 raccoglie automaticamente un set di eventi tramite il proprio SDK. La tabella seguente mappa tali eventi ai rispettivi equivalenti XDM o Customer Journey Analytics.

| Evento di raccolta automatica GA4 | Equivalente XDM/Customer Journey Analytics |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` (campo XDM standard) |
| `session_start` | Avvio della sessione (automatico, per definizione di sessione della visualizzazione dati) |
| `first_visit` | [!UICONTROL Segmento prima sessione] |
| `scroll` | Evento personalizzato (richiede una mappatura di implementazione esplicita) |
| `click` | `xdm.web.webInteraction` campi (è necessaria l&#39;implementazione) |
| `video_start` / `video_complete` | Campi dello schema di Media Collection (con Adobe Streaming Media Services) |
| `purchase` | `xdm.commerce.purchases`, `xdm.commerce.order` (schema di e-commerce XDM standard) |
| `add_to_cart` | `xdm.commerce.productListAdds` (schema commerce XDM standard) |

>[!NOTE]
>
>Molti degli eventi di misurazione avanzati di GA4 (come scorrimento, download di file o video) richiedono una mappatura esplicita ai campi XDM durante l’implementazione tramite Web SDK. Non vengono raccolti automaticamente nello stesso modo in cui vengono gestiti dalla SDK di GA4.

## Eventi e parametri personalizzati

In GA4, gli eventi personalizzati hanno un nome e fino a 25 parametri. In Customer Journey Analytics, gli eventi personalizzati vengono mappati sui campi di schema XDM personalizzati definiti durante l’implementazione:

* Il nome **evento** diventa un valore di campo in un campo XDM (in genere [`xdm.eventType`](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/classes/experienceevent)).
* Ogni **parametro** diventa un campo di schema XDM separato. Qualsiasi campo XDM può essere esposto come dimensione o metrica durante la [configurazione di una visualizzazione dati](/help/data-views/component-settings/overview.md).

>[!NOTE]
>
>I percorsi dei campi XDM specifici per gli eventi personalizzati dell’organizzazione vengono determinati durante l’implementazione di Web SDK. Collabora con il tuo team di implementazione per comprendere la mappatura dei campi specifica prima di creare rapporti. Per ulteriori informazioni, consulta [Architettura dello schema](../cja-upgrade/cja-upgrade-schema-architect.md).

## Proprietà utente

Le proprietà utente GA4 sono attributi persistenti impostati su un utente (ad esempio, `membership_tier` o `account_type`). In Customer Journey Analytics, questi sono mappati a **Set di dati profilo** in Platform.

Un set di dati profilo viene acquisito separatamente dai dati dell’evento e unito a esso in Customer Journey Analytics utilizzando un ID persona condiviso. Gli ID persona comuni utilizzati in questo contesto includono un ID cliente o un hash e-mail. Una volta uniti, questi attributi di profilo sono disponibili come dimensioni in Analysis Workspace insieme ai dati a livello di evento.

Questo approccio offre a Customer Journey Analytics maggiore flessibilità rispetto al modello di proprietà utente di GA4: GA4 ti limita alle proprietà utente definite nel suo SDK, mentre i set di dati del profilo di Customer Journey Analytics possono includere qualsiasi attributo da qualsiasi sistema (CRM, piattaforma fedeltà, record di supporto) purché condivida un identificatore unificabile.

Se la tua organizzazione deve comunque inserire dati GA in Adobe Experience Platform, consulta [Acquisire dati storici Google Analytics](/help/use-cases/third-party/ga/backfill.md) e [Configurare i dati streaming di Google Analytics](/help/use-cases/third-party/ga/streaming.md) per le guide all&#39;installazione rivolte agli amministratori.
