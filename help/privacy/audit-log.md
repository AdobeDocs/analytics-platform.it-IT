---
title: Registri di audit
description: Scopri come visualizzare e gestire i registri di audit del Customer Journey Analytics.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 68%

---

# Registri di audit

Per aumentare la trasparenza e la visibilità delle attività eseguite nel sistema, Adobe Customer Journey Analytics consente di controllare le attività degli utenti per vari servizi e funzionalità sotto forma di &quot;registri di audit&quot;. Questi rappresentano una traccia di audit (o audit trail) che risulta utile per risolvere eventuali problemi, nonché per rispettare i criteri aziendali relativi alla gestione dei dati e i requisiti normativi, come l’Health Insurance Portability and Accountability Act (HIPAA).

In un certo senso, un registro di audit comunica **chi** ha eseguito **quale** azione, e **quando** l’a eseguita. Ogni azione registrata contiene metadati che indicano il tipo di azione, la data e l’ora, l’ID e-mail dell’utente che l’ha eseguita ed eventuali attributi aggiuntivi relativi al tipo di azione.

Questo argomento descrive i registri di audit nel Customer Journey Analytics, e spiega come visualizzarli e gestirli nell’interfaccia utente.

## Accedere ai registri di audit

Se questa funzione è abilitata per la tua organizzazione, i registri di audit vengono raccolti automaticamente quando si verifica un’attività. Non è necessario abilitare manualmente la raccolta dei registri.

Per poter visualizzare ed esportare i registri di audit, con la funzione di controllo degli accessi in Adobe Console ti deve essere stata concessa l’autorizzazione **[!UICONTROL Audit Logs Access]**. Per informazioni su come gestire le singole autorizzazioni per le funzioni di Customer Journey Analytics, consulta [documentazione sul controllo degli accessi](../admin/cja-access-control.md).

## Visualizza il registro di controllo nell’interfaccia utente

In Customer Journey Analytics, passa a **[!UICONTROL Tools]** > **[!UICONTROL Audit Logs]**.

Per impostazione predefinita vengono visualizzati i registri di audit relativi alla data odierna e al giorno precedente.

![registro di audit](assets/audit_ui.png)

Per specificare quali colonne devono essere visibili, utilizza il selettore delle colonne in alto a destra.

## Visualizzare informazioni sulle singole voci del registro

Fai doppio clic sul pulsante Info (i) accanto a una descrizione.

![registro di audit](assets/info-button-audit.png)

Vengono visualizzati i seguenti elementi:

* **[!UICONTROL Action Name]**: azione eseguita. Possibili valori:
   * API_REQUEST
   * APPROVA
   * CREA
   * DELETE
   * MODIFICA
   * ESPORTA
   * ORG_CHANGE
   * AGGIORNA
   * CONDIVIDI
   * TRASFERIMENTO
   * ANNULLA APPROVAZIONE
   * ANNULLA CONDIVISIONE
* **[!UICONTROL Date Created]**: data e ora in cui è stata eseguita l’azione.
* **[!UICONTROL Description]**: riepilogo dell’azione.
* **[!UICONTROL User Name]**: utente che ha eseguito l’azione.
* **[!UICONTROL Email]**: indirizzo e-mail dell’utente che ha eseguito l’azione.
* **[!UICONTROL Component Name]**: componente su cui l’utente ha agito.
* **[!UICONTROL Component Type]**: tipo di componente. Possibili valori:
   * ANNOTAZIONE
   * PUBBLICO
   * METRICA_CALCOLATA
   * CONNESSIONE
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTRO
   * ORGANIZZAZIONE IMS
   * DISPOSITIVI MOBILI
   * PROGETTO
   * RAPPORTO
   * PROGETTO_PIANIFICATO
   * UTENTE
   * GRUPPO_UTENTI
* **[!UICONTROL Component ID]**: ID del componente su cui l’utente ha intrapreso un’azione.
* **[!UICONTROL IMS Org ID]**: ID IMS dell’organizzazione, nel formato di `ABC123@AdobeOrg`.
* **[!UICONTROL Log ID]**: ID univoco che identifica la voce del registro.
* **[!UICONTROL User ID]**: ID univoco che identifica l’utente che ha eseguito l’azione.
* **[!UICONTROL User Type]**: tipo di autenticazione utilizzato. I valori validi includono:
   * IMS
   * OKTA

### Filtrare i registri di audit

Seleziona l’icona a imbuto (![filtro](assets/filter-icon.png)) per visualizzare un elenco di filtri con cui limitare i risultati. Vengono visualizzati solo gli ultimi 1.000 record, a prescindere dai filtri selezionati.

![filtri](assets/filters.png)

Nell’interfaccia utente sono disponibili i seguenti filtri per gli eventi di audit:

| Filtro | Descrizione |
| --- | --- |
| [!UICONTROL Date Range] | Per filtrare in base a un intervallo di date diverso, puoi selezionare un’altra data oppure puoi selezionare un intervallo di date trascinando il cursore su più date. Per impostazione predefinita, è selezionata la data odierna e quella del giorno precedente. |
| [!UICONTROL Action] | Puoi filtrare in base al nome dell’azione elencato sopra. |
| [!UICONTROL User ID] | Puoi filtrare per un utente specifico in base al suo ID utente. Per trovare l’ID utente, seleziona il pulsante Info (i) accanto al nome dell’utente. |
| [!UICONTROL Email] | Puoi filtrare in base all’indirizzo e-mail di un utente. Per trovare l’e-mail, seleziona il pulsante Info (i) accanto al nome dell’utente. |
| [!UICONTROL Component ID] | Puoi filtrare per uno specifico ID componente. Per trovare l’ID del componente, seleziona il pulsante Info (i) accanto al componente. |
| [!UICONTROL Component Type] | Puoi filtrare in base al tipo di componente elencato sopra. |

{style="table-layout:auto"}

## Tipi di eventi acquisiti dai registri di audit

La tabella seguente presenta le azioni che vengono riportate nei registri di audit per i diversi tipo di componente:

| Tipo di componente | Azioni |
| --- | --- |
| [!UICONTROL Annotation] | <ul><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Audience] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li><li>Esportazione</li><li>Aggiornamento</li></ul> |
| [!UICONTROL Calculated Metric] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Connection] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Data View] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Date Range] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Filter] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL IMS Org] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Project] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Report] | <ul><li>Richiesta API</li></ul> |
| [!UICONTROL Scheduled Project] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL User] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL User Group] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |

{style="table-layout:auto"}

## Scaricare i registri di audit

Puoi scaricare i registri di audit in formato CSV o JSON. Nei file scaricati vengono mantenuti tutti i filtri applicati o le colonne selezionate.

1. Fai clic su **[!UICONTROL Download]** in alto a destra nella schermata.
1. Specifica il formato.
1. Fai di nuovo clic su **[!UICONTROL Download]**.

## Gestire i registri di audit tramite l’API

Tutte le azioni che possono essere eseguite nell’interfaccia utente possono essere eseguite anche utilizzando le chiamate API. Consulta la [Documento di riferimento API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) per ulteriori informazioni.
