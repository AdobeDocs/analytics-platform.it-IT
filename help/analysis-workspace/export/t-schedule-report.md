---
description: Invia un progetto Analysis Workspace tramite e-mail o programmane la consegna.
keywords: Analysis Workspace
title: Inviare dati di Customer Journey Analytics ad altri tramite e-mail
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: a2b2c6bca0557521ac7b6bcf635f467ca41731b7
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 61%

---

# Inviare dati di Customer Journey Analytics ad altri tramite e-mail

Puoi esportare i rapporti sul Customer Journey Analytics inviandoli a destinatari selezionati tramite e-mail. Puoi inviare file ad hoc oppure configurare i file da inviare in base a una pianificazione. I file possono essere inviati in formato CSV o PDF.

Tutti i tag applicati al progetto vengono applicati automaticamente all’esportazione.

Sono disponibili anche altri metodi di esportazione dei dati del Customer Journey Analytics, come descritto in [Panoramica sull’esportazione](/help/analysis-workspace/export/export-project-overview.md).

## Invia subito file {#now}

Per inviare immediatamente un file ai destinatari tramite e-mail:

1. Fai clic su **[!UICONTROL Share]>[!UICONTROL Export file]**.
1. Specifica il tipo di file:
   * [!UICONTROL **CSV**]: scegli questa opzione se desideri dati in formato testo normale.
   * [!UICONTROL **PDF**]: scegli questa opzione se vuoi che il file scaricato contenga tutte le tabelle e le visualizzazioni visualizzate (visibili) nel progetto.
1. (Facoltativo) Aggiungi una descrizione da includere nell’e-mail per spiegare il file ricevuto.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. (Solo per i clienti Healthcare Shield) Fornisci una password. Consulta la sezione Proteggere un rapporto pianificato tramite password.
1. Fai clic su **[!UICONTROL Send Now]** (Usa modello di attribuzione non predefinito).
1. (Facoltativo) Fai clic su **[!UICONTROL Show scheduling options]** per specificare una pianificazione di consegna.

![Invia subito file](assets/send-file-no-scheduling-options.JPG)

## Invia file secondo programma {#schedule}

Per inviare un file ai destinatari in base a una pianificazione ricorrente tramite e-mail:

1. Fai clic su **[!UICONTROL Share]>[!UICONTROL Schedule file export]**.
1. Specifica il tipo di file (CSV o PDF).
1. (Facoltativo) Aggiungi una descrizione del file che verrà inclusa nell’e-mail.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. (Solo per i clienti Healthcare Shield) Fornisci una password. Consulta la sezione Proteggere un rapporto pianificato tramite password.
1. Specifica l’intervallo per il quale la pianificazione deve essere consegnata modificando l’opzione Inizia e Termina negli input. La data di fine deve essere compresa entro un anno dal giorno in cui la pianificazione viene creata o modificata.
1. Specifica la frequenza di consegna. Ogni frequenza consente diverse personalizzazioni.
1. Fai clic su **[!UICONTROL Send on schedule]** (Usa modello di attribuzione non predefinito).

![](assets/send-file.JPG)

## Gestione progetti programmati {#manager}

I progetti Analysis Workspace pianificati possono essere gestiti in **[!UICONTROL Analytics]> [!UICONTROL Components] >[!UICONTROL Scheduled Projects]**.

In Gestione progetti programmati, puoi modificare ed eliminare pianificazioni ricorrenti di progetti. Cerca una pianificazione nella barra di ricerca o utilizzando le opzioni filtro nella barra a sinistra. Puoi filtrare per tag, pianificazioni approvate, proprietari e altro ancora.

| Campo | Descrizione |
| --- | --- |
| [!UICONTROL Favorites] | Selezionando l’icona a forma di stella, questa pianificazione diventa la preferita. |
| [!UICONTROL Schedule ID] | Questo ID viene utilizzato principalmente a scopo di debug. |
| [!UICONTROL Title and Description] | Titolo e descrizione di questo progetto. |
| [!UICONTROL Owner] | La persona che ha creato ed è proprietaria del progetto. |
| [!UICONTROL Tags] | (facoltativo) Assegnare tag è un modo efficace per organizzare progetti. Tutti gli utenti possono creare tag e applicarne uno o più a un progetto. Tuttavia, puoi visualizzare solo i tag dei progetti di tua proprietà o che sono stati condivisi con te. |
| [!UICONTROL Delivered To] | Il/i destinatario/i del progetto programmato. |
| [!UICONTROL Expiration Date] | Puoi impostare la data di scadenza fino a un anno, indipendentemente dalla frequenza di pianificazione. |
| [!UICONTROL Frequency] | Con quale frequenza desideri che questo progetto programmato venga inviato ai destinatari. |
| [!UICONTROL Execution Time] | A che ora del giorno viene inviato questo progetto programmato. |
| [!UICONTROL Number of Queries] | Il numero di query su questo progetto. |

Di seguito sono riportate le azioni comuni di Gestione progetti programmati:

| Azione | Descrizione |
|---|---|
| **[!UICONTROL Edit schedule]** | Fai clic sul titolo della pianificazione per aggiornare le impostazioni di consegna. |
| **[!UICONTROL Delete schedule]** | Seleziona il progetto programmato nell’elenco, quindi fai clic su Elimina dal menu. In questo modo verrà eliminata la pianificazione selezionata per il progetto, mentre il progetto stesso non verrà eliminato. |
| **[!UICONTROL Add tags]** | Seleziona il progetto programmato nell’elenco, quindi scegli “Assegna tag” o “Approva” per organizzare le pianificazioni e semplificarne la ricerca. |
| **[!UICONTROL View failed schedules]** | Passa alla barra a sinistra > Altri filtri > Non riuscite per visualizzare le pianificazioni non riuscite. |
| **[!UICONTROL View expired schedules]** | Passa alla barra a sinistra > Altri filtri > Scadute per visualizzare le pianificazioni scadute. Fai clic sul titolo della pianificazione per impostare una nuova programmazione di consegna. |
| **[!UICONTROL View schedule ID]** | Passa alle opzioni della colonna in alto a destra e aggiungi la colonna ID pianificazione alla tabella. L’ID pianificazione è spesso utile per il debug. |

Lo strumento di gestione dei progetti programmati mostra gli elementi creati da uno specifico utente. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte.
Per ulteriori informazioni, consulta [Progetti pianificati](/help/components/scheduled-projects-manager.md).

## Proteggere un progetto pianificato tramite password {#password}

>[!NOTE]
>
>L’opzione per proteggere un progetto pianificato tramite password viene visualizzata solo per i clienti del Customer Journey Analytics che hanno acquistato il [Healthcare Shield](https://business.adobe.com/it/solutions/experience-cloud-for-healthcare.html) componente aggiuntivo.

Adobe utilizza la password per crittografare i progetti pianificati, sia che siano inviati in formato .pdf o .csv.

Dopo che la società ha acquistato lo SKU Healthcare Shield ed è stata abilitata per esso, la richiesta di creare una password per un progetto pianificato viene visualizzata nelle seguenti circostanze:

* Quando un utente crea un nuovo progetto pianificato.

* Quando un progetto pianificato esistente sta per essere inviato. Il progetto attualmente pianificato viene disattivato fino a quando non è attiva la protezione tramite password. Il proprietario del progetto pianificato riceve un messaggio e-mail con informazioni su questo requisito.

![protezione tramite password](assets/password.png)

### Requisiti per la password

I requisiti per la password sono conformi agli standard Adobi, che richiedono un minimo di 8 caratteri con almeno un numero e un carattere speciale.

### Proteggere un nuovo progetto pianificato tramite password

1. Dopo aver salvato il progetto, vai a **[!UICONTROL Share]** > **[!UICONTROL Send file now]**, o **[!UICONTROL Share]** > **[!UICONTROL Send file on schedule]**.
1. Segui le istruzioni precedenti, in [Invia il file ora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=it#now) o [Invia il file secondo pianificazione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=it#schedule).

### Proteggere un progetto pianificato esistente tramite password

Prima di pianificare un progetto, il proprietario del progetto riceve un messaggio e-mail simile al seguente:

![e-mail](assets/email-password.png)

1. Accedi al Customer Journey Analytics.
1. Seleziona **[!UICONTROL View Scheduled Project]**.
1. Nella finestra di dialogo **[!UICONTROL Edit scheduled project]**, immetti e reimmetti una password.
1. Informa i destinatari del progetto pianificato della password. Non distribuire la password a persone che non sono destinatari del progetto pianificato.
