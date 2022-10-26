---
title: Registri di controllo
description: Scopri come visualizzare e gestire i registri di controllo di CJA.
hide: true
hidefromtoc: true
source-git-commit: 6cf2d5ccbeeea7baeea8a675f2b7e96e6203fe24
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 11%

---


# Registri di controllo

Per aumentare la trasparenza e la visibilità delle attività eseguite nel sistema, il Customer Journey Analytics (CJA) consente di controllare l’attività degli utenti per vari servizi e funzionalità sotto forma di &quot;registri di controllo&quot;. Questi registri formano un percorso di audit che può aiutare a risolvere i problemi e aiutare la tua azienda a rispettare efficacemente le politiche di gestione dei dati aziendali e i requisiti normativi, come l&#39;Health Insurance Portability and Accountability Act (HIPAA).

In un certo senso, un registro di controllo comunica **chi** eseguito **cosa** e **quando**. Ogni azione registrata in un registro contiene metadati che indicano il tipo di azione, la data e l’ora, l’ID e-mail dell’utente che ha eseguito l’azione e gli attributi aggiuntivi relativi al tipo di azione.

Questo argomento tratta i registri di controllo di CJA, incluso come visualizzarli e gestirli nell’interfaccia utente.

## Accesso ai registri di controllo

Quando la funzione è abilitata per l’organizzazione, i registri di controllo vengono raccolti automaticamente quando si verifica l’attività. Non è necessario abilitare manualmente la raccolta di registri.

Per visualizzare ed esportare i registri di controllo, devi aver ricevuto il **[!UICONTROL Audit Logs Access]** autorizzazione per il controllo degli accessi in Adobe Console. Per informazioni su come gestire le autorizzazioni individuali per le funzionalità di CJA, consulta [documentazione sul controllo degli accessi](/help/getting-started/cja-access-control.md).

## Visualizza il registro di controllo nell’interfaccia utente

In CJA, passa a **[!UICONTROL Tools]** > **[!UICONTROL Audit Logs]**.

Il registro di controllo per oggi e ieri è mostrato per impostazione predefinita.

![registro di controllo](assets/audit_ui.png)

Per selezionare le colonne visibili, vai al selettore delle colonne in alto a destra.

## Visualizza informazioni sulle singole voci di registro

Fai doppio clic sul pulsante info (i) accanto a una descrizione.

![registro di controllo](assets/info-button-audit.png)

Vengono visualizzati i seguenti elementi:

| Elemento | Descrizione |
| --- | --- |
| Nome azione | Elenco delle azioni possibili: <ul><li>API_Request</li><li>Approva</li><li>Creare</li><li>Modifica</li><li>Esporta</li><li>Login_failed</li><li>Login_riuscito</li><li>Logout</li><li>Org_change</li><li>Aggiorna</li><li>Condividi</li><li>Transfer</li><li>Annulla approvazione</li><li>Unshare</li></ul> |
| Descrizione | Riepilogo dell’azione, del tipo di componente (con ID) e di altri valori. |
| Nome utente | L’utente che esegue l’azione. |
| Tipo di componente | I possibili tipi di componenti includono: <ul><li>Annotazione</li><li>Destinatari</li><li>Metrica calcolata</li><li>Connessione</li><li>Gruppo di dati</li><li>Visualizzazione dati</li><li>Feature_Access</li><li>Filtro</li><li>IMS_Org</li><li>Mobile</li><li>Progetto</li><li>Rapporto</li><li>Scheduled_Project</li><li>Utente</li><li>Gruppo_utenti</li></ul> |
| ID organizzazione IMS | Un ID univoco fornito all&#39;istanza al primo accesso a Adobe Experience Cloud. Deve essere nel formato: xxx@AdobeOrg. |
| ID utente | Un ID univoco che identifica l&#39;utente che ha eseguito questa azione. |
| Data creazione | Quando è stata intrapresa questa azione. |
| E-mail | L’e-mail dell’utente che esegue l’azione. |
| ID componente | Un ID univoco che identifica il componente sul quale viene eseguita l&#39;azione. |
| ID registro | Un ID univoco che identifica la voce di registro. |
| Tipo di utente | I tipi possibili includono: IMS, OKTA |

### Filtrare i registri di controllo

Seleziona l’icona funnel (![filter](assets/filter-icon.png)) per visualizzare un elenco di controlli filtro per limitare i risultati. Vengono visualizzati solo gli ultimi 1.000 record, indipendentemente dai vari filtri selezionati.

![filtri](assets/filters.png)

Nell’interfaccia utente sono disponibili i seguenti filtri per gli eventi di controllo:

| Filtro | Descrizione |
| --- | --- |
| [!UICONTROL Date Range] | Puoi filtrare in un intervallo di date diverso selezionando una data diversa o selezionando un intervallo di date trascinando il cursore su più date. Per impostazione predefinita, è selezionata la data odierna e quella di ieri. |
| [!UICONTROL Action] | Filtrare una o più delle azioni seguenti: <ul><li>API_Request</li><li>Approva</li><li>Creare</li><li>Modifica</li><li>Esporta</li><li>Login_failed</li><li>Login_riuscito</li><li>Logout</li><li>Org_change</li><li>Aggiorna</li><li>Condividi</li><li>Transfer</li><li>Annulla approvazione</li><li>Annulla condivisione</li></ul> |
| [!UICONTROL User ID] | Filtrare un utente specifico in base al relativo ID utente. L&#39;ID utente può essere trovato selezionando il pulsante info (i) accanto al nome utente. |
| [!UICONTROL Email] | Filtrare l’indirizzo e-mail di un utente specifico. L’e-mail può essere trovata selezionando il pulsante info (i) accanto al nome utente. |
| [!UICONTROL Component ID] | Filtrare con un ID componente specifico. L’ID utente può essere trovato selezionando il pulsante Info (i) per un componente desiderato. |
| [!UICONTROL Component Type] | Filtra su uno o più tipi di componente: <ul><li>Annotazione</li><li>Destinatari</li><li>Metrica calcolata</li><li>Connessione</li><li>Gruppo di dati</li><li>Visualizzazione dati</li><li>Feature_Access</li><li>Filtro</li><li>IMS_Org</li><li>Mobile</li><li>Progetto</li><li>Rapporto</li><li>Scheduled_Project</li><li>Utente</li><li>Gruppo_utenti</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Tipi di eventi acquisiti dai registri di audit

La tabella seguente indica quali azioni sui tipi di componenti vengono registrate dai registri di controllo:

| Tipo di componente | Azioni |
| --- | --- |
| [!UICONTROL Annotation] | <ul><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL Audience] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li><li>Esporta</li><li>Aggiorna</li></ul> |
| [!UICONTROL Calculated Metric] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL Connection] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL Data View] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL Date Range] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL Filter] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL IMS Org] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL Project] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL Report] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Scheduled Project] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL User] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |
| [!UICONTROL User Group] | <ul><li>API_Request</li><li>Creare</li><li>Delete (Elimina)</li><li>Modifica</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Download dei registri di controllo

Puoi scaricare i registri di controllo in formato CSV o JSON. Tutti i filtri applicati o le colonne selezionate vengono visualizzati nei file scaricati.

1. Fai clic su **[!UICONTROL Download]** in alto a destra dello schermo.
1. Specifica il formato.
1. Fai clic su **[!UICONTROL Download]** di nuovo.

## Gestire i registri di controllo nell’API

Tutte le azioni che puoi eseguire nell’interfaccia utente possono essere eseguite anche utilizzando le chiamate API. Consulta la sezione [Documento di riferimento API CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) per ulteriori informazioni.