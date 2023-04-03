---
description: Invia un progetto di Analysis Workspace via e-mail o programmane la consegna.
keywords: Analysis Workspace
title: Programmare progetti
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 19ed9553a147c87e20ecfcf536d03b7c6b2e9b91
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 82%

---

# Programmare progetti

Dal **[!UICONTROL Share]** menu   di Workspace, puoi inviare progetti Analysis Workspace tramite e-mail a destinatari selezionati. I file possono essere inviati in formato CSV o PDF.

## Invia subito file {#now}

Per inviare immediatamente un file ai destinatari tramite e-mail:

1. Fai clic su **[!UICONTROL Share]>[!UICONTROL Export file]**.
1. Specifica il tipo di file (CSV o PDF).
1. (Facoltativo) Aggiungi una descrizione del file che verrà inclusa nell’e-mail.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. (Solo per i clienti Healthcare Shield) Fornisci una password. Consulta la sezione Proteggere un rapporto pianificato tramite password.
1. Fai clic su **[!UICONTROL Send Now]** (Usa modello di attribuzione non predefinito).
1. (Facoltativo) Fai clic su **[!UICONTROL Show scheduling options]** per specificare una pianificazione della consegna.

![Invia subito file](assets/send-file-no-scheduling-options.JPG)

## Invia file secondo programma {#schedule}

Per inviare un file tramite e-mail secondo una pianificazione periodica:

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

I progetti Analysis Workspace programmati possono essere gestiti in **[!UICONTROL Analytics]> [!UICONTROL Components] >[!UICONTROL Scheduled Projects]**.

In Gestione progetti programmati, puoi modificare ed eliminare pianificazioni ricorrenti di progetti. Cerca una pianificazione nella barra di ricerca o utilizzando le opzioni filtro nella barra a sinistra. Puoi filtrare per tag, pianificazioni approvate, proprietari e altro ancora.

| Campo | Descrizione |
| --- | --- |
| [!UICONTROL Favorites] | Selezionando l’icona a forma di stella, questa pianificazione diventa un’opzione preferita. |
| [!UICONTROL Schedule ID] | Questo ID viene utilizzato principalmente a scopo di debug. |
| [!UICONTROL Title and Description] | Titolo e descrizione del progetto. |
| [!UICONTROL Owner] | Utente che ha creato e proprietario del progetto. |
| [!UICONTROL Tags] | (Facoltativo) L’assegnazione tag è un buon modo per organizzare i progetti. Tutti gli utenti possono creare tag e applicarne uno o più a un progetto. Tuttavia, puoi visualizzare solo i tag per i progetti di tua proprietà o che sono stati condivisi con te. |
| [!UICONTROL Delivered To] | Destinatari del progetto pianificato. |
| [!UICONTROL Expiration Date] | Puoi impostare la data di scadenza fino a un anno, indipendentemente dalla frequenza della pianificazione. |
| [!UICONTROL Frequency] | Con quale frequenza desideri che questo progetto di pianificazione venga inviato ai destinatari. |
| [!UICONTROL Execution Time] | A che ora viene inviato il progetto pianificato. |
| [!UICONTROL Number of Queries] | Numero di query relative al progetto. |

Di seguito sono riportate le azioni comuni di Gestione progetti programmati:

| Azione | Descrizione |
|---|---|
| **[!UICONTROL Edit schedule]** | Fai clic sul titolo della pianificazione per aggiornare le impostazioni di consegna. |
| **[!UICONTROL Delete schedule]** | Seleziona il progetto programmato nell’elenco, quindi fai clic su Elimina dal menu. In questo modo verrà eliminata la pianificazione selezionata per il progetto, mentre il progetto stesso non verrà eliminato. |
| **[!UICONTROL Add tags]** | Seleziona il progetto programmato nell’elenco, quindi scegli “Assegna tag” o “Approva” per organizzare le pianificazioni e semplificarne la ricerca. |
| **[!UICONTROL View failed schedules]** | Passa alla barra a sinistra > Altri filtri > Non riuscite per visualizzare le pianificazioni non riuscite. |
| **[!UICONTROL View expired schedules]** | Passa alla barra a sinistra > Altri filtri > Scadute per visualizzare le pianificazioni scadute. Fai clic sul titolo della pianificazione per impostare una nuova pianificazione di consegna. |
| **[!UICONTROL View schedule ID]** | Passa alle opzioni della colonna in alto a destra e aggiungi la colonna ID pianificazione alla tabella. L’ID pianificazione è spesso utile per il debug. |

Lo strumento di gestione dei progetti programmati mostra gli elementi creati da uno specifico utente. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte.

## Proteggere un progetto pianificato tramite password {#password}

>[!NOTE]
>
>L’opzione per proteggere un progetto pianificato tramite password viene visualizzata solo per i clienti CJA che hanno acquistato il componente aggiuntivo [Healthcare Shield](https://business.adobe.com/it/solutions/experience-cloud-for-healthcare.html).

Adobe utilizza la password per crittografare i progetti pianificati, sia che siano inviati in formato .pdf o .csv.

Dopo che la tua azienda ha acquistato lo SKU Healthcare Shield ed è stata abilitata per esso, il messaggio di richiesta di creazione di una password per un progetto pianificato viene visualizzato in due circostanze:

* Quando un utente crea un nuovo progetto pianificato.

* Quando un progetto pianificato esistente sta per essere inviato. Il progetto attualmente pianificato verrà disattivato fino a quando non sarà attiva la protezione tramite password. A tale scopo, il proprietario del progetto pianificato riceverà un’e-mail.

![protezione tramite password](assets/password.png)

### Requisiti per la password

I requisiti relativi alla password sono conformi allo standard Adobe che richiede un minimo di 8 caratteri con almeno un numero e un carattere speciale.

### Proteggere un nuovo progetto pianificato tramite password

1. Dopo aver salvato il progetto, vai a **[!UICONTROL Share]** > **[!UICONTROL Send file now]**, oppure [!UICONTROL Share] > **[!UICONTROL Send file on schedule]**.
1. Segui le istruzioni precedenti, in [Invia il file ora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=it#now) o [Invia il file secondo pianificazione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=it#schedule).

### Proteggere un progetto pianificato esistente tramite password

Prima dell’orario pianificato per un progetto, il proprietario del progetto riceverà un’e-mail simile alla seguente:

![e-mail](assets/email-password.png)

1. Accedi nuovamente a Customer Journey Analytics.
1. Fai clic su **[!UICONTROL View Scheduled Project]**.
1. Nella finestra di dialogo **[!UICONTROL Edit scheduled project]**, immetti e reimmetti una password.
1. Consenti (solo) ai destinatari del progetto pianificato di conoscere la password.


