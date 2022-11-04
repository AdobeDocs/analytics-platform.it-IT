---
title: Registri di audit
description: Scopri come visualizzare e gestire i registri di audit di CJA.
source-git-commit: 37a23a4669c08c8f7d9c6595286998ebd7e60ac4
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 100%

---


# Registri di audit

Per aumentare la trasparenza e la visibilità delle attività eseguite nel sistema, Customer Journey Analytics (CJA) consente di verificare le attività degli utenti per vari servizi e funzionalità, mediante i registri di audit. Questi rappresentano una traccia di audit (o audit trail) che risulta utile per risolvere eventuali problemi, nonché per rispettare i criteri aziendali relativi alla gestione dei dati e i requisiti normativi, come l’Health Insurance Portability and Accountability Act (HIPAA).

In un certo senso, un registro di audit comunica **chi** ha eseguito **quale** azione, e **quando** l’a eseguita. Ogni azione registrata contiene metadati che indicano il tipo di azione, la data e l’ora, l’ID e-mail dell’utente che l’ha eseguita ed eventuali attributi aggiuntivi relativi al tipo di azione.

Questo argomento tratta i registri di audit di CJA, e spiega come visualizzarli e gestirli nell’interfaccia utente.

## Accedere ai registri di audit

Se questa funzione è abilitata per la tua organizzazione, i registri di audit vengono raccolti automaticamente quando si verifica un’attività. Non è necessario abilitare manualmente la raccolta dei registri.

Per poter visualizzare ed esportare i registri di audit, con la funzione di controllo degli accessi in Adobe Console ti deve essere stata concessa l’autorizzazione **[!UICONTROL Audit Logs Access]**. Per informazioni su come gestire le singole autorizzazioni per le funzionalità di CJA, consulta la [documentazione sul controllo degli accessi](/help/getting-started/cja-access-control.md).

## Visualizza il registro di controllo nell’interfaccia utente

In CJA, passa a **[!UICONTROL Tools]** > **[!UICONTROL Audit Logs]**.

Per impostazione predefinita vengono visualizzati i registri di audit relativi alla data odierna e al giorno precedente.

![registro di audit](assets/audit_ui.png)

Per specificare quali colonne devono essere visibili, utilizza il selettore delle colonne in alto a destra.

## Visualizzare informazioni sulle singole voci del registro

Fai doppio clic sul pulsante Info (i) accanto a una descrizione.

![registro di audit](assets/info-button-audit.png)

Vengono visualizzati i seguenti elementi:

| Elemento | Descrizione |
| --- | --- |
| Nome azione | Elenco delle azioni possibili: <ul><li>Richiesta API</li><li>Approvazione</li><li>Creazione</li><li>Modifica</li><li>Esportazione</li><li>Accesso non riuscito</li><li>Accesso riuscito</li><li>Logout</li><li>Modifica organizzazione</li><li>Aggiornamento</li><li>Condivisione</li><li>Trasferimento</li><li>Annullamento approvazione</li><li>Annullamento condivisione</li></ul> |
| Descrizione | Riepilogo dell’azione, del tipo di componente (con ID) e altri valori. |
| Nome utente | Utente che ha eseguito l’azione. |
| Tipo di componente | I possibili tipi di componenti includono: <ul><li>Annotazione</li><li>Destinatari</li><li>Metrica calcolata</li><li>Connessione</li><li>Gruppo di dati</li><li>Vista dati</li><li>Accesso a funzione</li><li>Filtro</li><li>Organizzazione IMS</li><li>Mobile</li><li>Progetto</li><li>Rapporto</li><li>Progetto pianificato</li><li>Utente</li><li>Gruppo di utenti</li></ul> |
| ID organizzazione IMS | ID univoco assegnato alla tua istanza la prima volta che accedi ad Adobe Experience Cloud. Deve essere nel seguente formato: xxx@AdobeOrg. |
| ID utente | ID univoco che identifica l’utente che ha eseguito l’azione. |
| Data creazione | Quando è stata eseguita l’azione. |
| E-mail | Indirizzo e-mail dell’utente che ha eseguito l’azione. |
| ID componente | ID univoco che identifica il componente sul quale è stata eseguita l’azione. |
| ID registro | ID univoco che identifica la voce del registro. |
| Tipo di utente | I tipi possibili includono: IMS, OKTA |

### Filtrare i registri di audit

Seleziona l’icona a imbuto (![filtro](assets/filter-icon.png)) per visualizzare un elenco di filtri con cui limitare i risultati. Vengono visualizzati solo gli ultimi 1.000 record, a prescindere dai filtri selezionati.

![filtri](assets/filters.png)

Nell’interfaccia utente sono disponibili i seguenti filtri per gli eventi di audit:

| Filtro | Descrizione |
| --- | --- |
| [!UICONTROL Date Range] | Per filtrare in base a un intervallo di date diverso, puoi selezionare un’altra data oppure puoi selezionare un intervallo di date trascinando il cursore su più date. Per impostazione predefinita, è selezionata la data odierna e quella del giorno precedente. |
| [!UICONTROL Action] | Puoi filtrare per una o più delle azioni seguenti: <ul><li>Richiesta API</li><li>Approvazione</li><li>Creazione</li><li>Modifica</li><li>Esportazione</li><li>Accesso non riuscito</li><li>Accesso riuscito</li><li>Logout</li><li>Modifica organizzazione</li><li>Aggiornamento</li><li>Condivisione</li><li>Trasferimento</li><li>Annullamento approvazione</li><li>Annullamento condivisione</li></ul> |
| [!UICONTROL User ID] | Puoi filtrare per un utente specifico in base al suo ID utente. Per trovare l’ID utente, seleziona il pulsante Info (i) accanto al nome dell’utente. |
| [!UICONTROL Email] | Puoi filtrare in base all’indirizzo e-mail di un utente. Per trovare l’e-mail, seleziona il pulsante Info (i) accanto al nome dell’utente. |
| [!UICONTROL Component ID] | Puoi filtrare per uno specifico ID componente. Per trovare l’ID del componente, seleziona il pulsante Info (i) accanto al componente. |
| [!UICONTROL Component Type] | Puoi filtrare per uno o più tipi di componente: <ul><li>Annotazione</li><li>Destinatari</li><li>Metrica calcolata</li><li>Connessione</li><li>Gruppo di dati</li><li>Vista dati</li><li>Accesso a funzione</li><li>Filtro</li><li>Organizzazione IMS</li><li>Mobile</li><li>Progetto</li><li>Rapporto</li><li>Progetto pianificato</li><li>Utente</li><li>Gruppo di utenti</li></ul> |

{style=&quot;table-layout:auto&quot;}

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

{style=&quot;table-layout:auto&quot;}

## Scaricare i registri di audit

Puoi scaricare i registri di audit in formato CSV o JSON. Nei file scaricati vengono mantenuti tutti i filtri applicati o le colonne selezionate.

1. Fai clic su **[!UICONTROL Download]** in alto a destra nella schermata.
1. Specifica il formato.
1. Fai di nuovo clic su **[!UICONTROL Download]**.

## Gestire i registri di audit tramite l’API

Tutte le azioni che possono essere eseguite nell’interfaccia utente possono essere eseguite anche utilizzando le chiamate API. Per maggiori informazioni, consulta la [documentazione delle API CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs).