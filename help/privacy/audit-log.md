---
title: Registri di controllo
description: Scopri come visualizzare e gestire i registri di controllo di Customer Journey Analytics.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 2ef96ad194f8c7acec35bd7635c650af4370531a
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 80%

---

# Registri di controllo {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_userid"
>title="ID utente"
>abstract="Per trovare l’ID utente, premi il pulsante Info su una voce di registro contenente l’utente desiderato."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_componentid"
>title="ID componente"
>abstract="Per trovare l’ID componente, premi il pulsante Info su una voce di registro contenente il componente desiderato."

<!-- markdownlint-enable MD034 -->


Per aumentare la trasparenza e la visibilità delle attività eseguite nel sistema, Customer Journey Analytics consente di verificare le attività degli utenti per vari servizi e funzionalità, mediante i “registri di controllo”. Questi rappresentano una traccia di audit (o audit trail) che risulta utile per risolvere eventuali problemi, nonché per rispettare i criteri aziendali relativi alla gestione dei dati e i requisiti normativi, come l’Health Insurance Portability and Accountability Act (HIPAA).

In pratica, un registro di controllo comunica **chi** ha eseguito **quale** azione, e **quando** l’ha eseguita. Ogni azione registrata contiene metadati che indicano il tipo di azione, la data e l’ora, l’ID e-mail dell’utente che l’ha eseguita ed eventuali attributi aggiuntivi relativi al tipo di azione.

I registri di audit vengono conservati per 90 giorni. Successivamente, i registri di audit vengono eliminati automaticamente.

Questo argomento tratta i registri di controllo di Customer Journey Analytics, e spiega come visualizzarli e gestirli nell’interfaccia utente.

## Accedere ai registri di controllo

Se questa funzione è abilitata per la tua organizzazione, i registri di controllo vengono raccolti automaticamente quando si verifica un’attività. Non è necessario abilitare manualmente la raccolta dei registri.

Per visualizzare ed esportare i registri di controllo, è necessario disporre dell&#39;autorizzazione di controllo dell&#39;accesso **[!UICONTROL Accesso ai registri di controllo]** in Adobe Console. Per scoprire come gestire le singole autorizzazioni per le funzionalità di Customer Journey Analytics, consulta la [documentazione sul controllo degli accessi](../technotes/access-control.md).

## Visualizza il registro di controllo nell’interfaccia utente

In Customer Journey Analytics, passa a **[!UICONTROL Strumenti]** > **[!UICONTROL Registri di controllo]**.

Per impostazione predefinita vengono visualizzati i registri di controllo relativi alla data odierna e al giorno precedente.

![Registro di controllo in cui sono evidenziati Oggi e Ieri. &#x200B;](assets/audit_ui.png)

Per specificare quali colonne devono essere visibili, utilizza il selettore delle colonne in alto a destra.

## Visualizzare informazioni sulle singole voci del registro

Fai doppio clic sul pulsante Info (i) accanto a una descrizione.

![Registro di controllo in cui è evidenziato il pulsante Informazioni. &#x200B;](assets/info-button-audit.png)

Vengono visualizzati i seguenti elementi:

* **[!UICONTROL Nome azione]**: l&#39;azione intrapresa. I valori possibili includono:
   * API_REQUEST: qualsiasi azione attiva una richiesta API back-end. Vengono visualizzati i dettagli relativi alla richiesta API.
   * APPROVE: è stata eseguita un’azione di “approvazione”.
   * CREATE: è stata eseguita un’azione “crea”.
   * DELETE: è stata eseguita un’azione “elimina”.
   * EDIT: è stata eseguita un’azione di “modifica”.
   * EMBARGO: quando viene limitata una richiesta in [Reporting Activity Manager](https://experienceleague.adobe.com/it/docs/analytics-platform/using/reporting-activity-manager/reporting-activity-cancel-requests), l’azione viene registrata nel Registro di controllo in EMBARGO.
   * EXPORT: è stata eseguita un’azione di “esportazione”.
   * ORG_CHANGE: è stata eseguita un’azione di modifica dell’organizzazione.
   * REFRESH: è stata eseguita un’azione di “aggiornamento”.
   * SHARE: È stata eseguita un’azione “condividi”.
   * TRANSFER: è stata eseguita un’azione di trasferimento.
   * UNAPPROVE: è stata eseguita un’azione “annulla approvazione”.
   * UNSHARE: è stata eseguita un’azione “annulla condivisione”.
* **[!UICONTROL Data di creazione]**: la data e l&#39;ora in cui è stata eseguita l&#39;azione.
* **[!UICONTROL Descrizione]**: riepilogo dell&#39;azione.
* **[!UICONTROL Nome utente]**: l&#39;utente che ha eseguito l&#39;azione. A volte, il nome utente potrebbe mancare. Valuta l’utilizzo della funzionalità [Utilizzo prodotto](https://experienceleague.adobe.com/it/docs/analytics-platform/using/tools/product-usage/usage-overview), in quanto include sempre il nome utente di accesso.
* **[!UICONTROL E-mail]**: l&#39;indirizzo e-mail dell&#39;utente che ha eseguito l&#39;azione.
* **[!UICONTROL Nome componente]**: il componente su cui l&#39;utente ha eseguito l&#39;azione.
* **[!UICONTROL Tipo di componente]**: il tipo di componente. I valori possibili includono:
   * ANNOTATION
   * PUBBLICO
   * CALCULATED_METRIC
   * CONNECTION
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTRO
   * IMS_ORG
   * MOBILE
   * PROJECT (Workspace)
   * REPORT
   * SCHEDULED_PROJECT
   * USER
   * USER_GROUP
* **[!UICONTROL ID componente]**: ID del componente su cui l&#39;utente ha eseguito l&#39;azione.
* **[!UICONTROL ID organizzazione IMS]**: ID IMS dell&#39;organizzazione, nel formato `ABC123@AdobeOrg`.
* **[!UICONTROL ID registro]**: ID univoco che identifica la voce del registro.
* **[!UICONTROL ID utente]**: ID univoco che identifica l&#39;utente che ha eseguito l&#39;azione.
* **[!UICONTROL Tipo utente]**: tipo di autenticazione utilizzato. I valori validi includono:
   * IMS
   * OKTA

### Filtrare i registri di controllo

Seleziona l’icona a imbuto (![filtro](assets/filter-icon.png)) per visualizzare un elenco di filtri con cui limitare i risultati. Vengono visualizzati solo gli ultimi 1.000 record, a prescindere dai filtri selezionati.

![Registro di controllo con i filtri visualizzati per Intervallo di date.](assets/filters.png)

Nell’interfaccia utente sono disponibili i seguenti filtri per gli eventi di audit:

| Filtro | Descrizione |
| --- | --- |
| [!UICONTROL Intervallo date] | Per filtrare in base a un intervallo di date diverso, puoi selezionare un’altra data oppure puoi selezionare un intervallo di date trascinando il cursore su più date. Per impostazione predefinita, è selezionata la data odierna e quella del giorno precedente. |
| [!UICONTROL Azione] | Filtra in base al nome di qualunque azione elencata sopra. |
| [!UICONTROL ID utente] | Puoi filtrare per un utente specifico in base al suo ID utente. Per trovare l’ID utente, seleziona il pulsante Info (i) accanto al nome dell’utente. |
| [!UICONTROL E-mail] | Puoi filtrare in base all’indirizzo e-mail di un utente. Per trovare l’e-mail, seleziona il pulsante Info (i) accanto al nome dell’utente. |
| [!UICONTROL ID componente] | Puoi filtrare per uno specifico ID componente. Per trovare l’ID del componente, seleziona il pulsante Info (i) accanto al componente. |
| [!UICONTROL Tipo di componente] | Filtra in base al tipo di componente elencato sopra. |

{style="table-layout:auto"}

## Tipi di eventi acquisiti dai registri di controllo

La tabella seguente presenta le azioni che vengono riportate nei registri di controllo per i diversi tipo di componente:

| Tipo di componente | Azioni |
| --- | --- |
| [!UICONTROL Annotazione] | <ul><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Pubblico] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li><li>Esportare</li><li>Aggiornamento</li></ul> |
| [!UICONTROL Metrica calcolata] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Connessione] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Visualizzazione dati] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Intervallo date] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Filtro] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Organizzazione IMS] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Progetto] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Rapporto] | <ul><li>Richiesta API</li></ul> |
| [!UICONTROL Progetto pianificato] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Utente] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |
| [!UICONTROL Gruppo utenti] | <ul><li>Richiesta API</li><li>Creazione</li><li>Eliminazione</li><li>Modifica</li></ul> |

{style="table-layout:auto"}

## Scaricare i registri di controllo

Puoi scaricare i registri di controllo in formato CSV o JSON. Nei file scaricati vengono mantenuti tutti i filtri applicati o le colonne selezionate.

1. Fai clic su **[!UICONTROL Scarica]** in alto a destra dello schermo.
1. Specifica il formato.
1. Fai di nuovo clic su **[!UICONTROL Scarica]**.

## Gestire i registri di controllo tramite l’API

Tutte le azioni che possono essere eseguite nell’interfaccia utente possono essere eseguite anche utilizzando le chiamate API. Per maggiori informazioni, consulta la [documentazione di riferimento delle API Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs).
