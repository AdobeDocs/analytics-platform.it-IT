---
description: Invia un progetto di Analysis Workspace via e-mail o programmane la consegna.
keywords: Analysis Workspace
title: Programmare progetti
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 6267b7ea3e0a72c86f3ab042c537ddca6f99539f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Programmare progetti

Dal **menu Share** di Workspace, puoi inviare progetti Analysis Workspace tramite e-mail a destinatari selezionati. I file possono essere inviati in formato CSV o PDF.

## Invia subito file {#now}

Per inviare immediatamente un file ai destinatari tramite e-mail:

1. Fai clic su **Condividi > Invia subito file**.
1. Specifica il tipo di file (CSV o PDF).
1. (Facoltativo) Aggiungi una descrizione del file che verrà inclusa nell’e-mail.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. (Solo per i clienti Healthcare Shield) Fornire una password. Vedi la sezione Protezione tramite password di un rapporto pianificato.
1. Fai clic su **Invia subito**.
1. (Facoltativo) Fai clic su **Mostra opzioni di pianificazione** per specificare la pianificazione della consegna.

![Invia subito file](assets/send-file-no-scheduling-options.JPG)

## Invia file secondo programma {#schedule}

Per inviare un file tramite e-mail secondo una pianificazione periodica:

1. Fai clic su **Condividi > Invia file secondo programma**.
1. Specifica il tipo di file (CSV o PDF).
1. (Facoltativo) Aggiungi una descrizione del file che verrà inclusa nell’e-mail.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. (Solo per i clienti Healthcare Shield) Fornire una password. Vedi la sezione Protezione tramite password di un rapporto pianificato.
1. Specifica l’intervallo per il quale la pianificazione deve essere consegnata modificando l’opzione Inizia e Termina negli input. La data di fine deve essere compresa entro un anno dal giorno in cui la pianificazione viene creata o modificata.
1. Specifica la frequenza di consegna. Ogni frequenza consente diverse personalizzazioni.
1. Fai clic su **Invia secondo programma**.

![](assets/send-file.JPG)

## Gestione progetti programmati {#manager}

I progetti programmati di Analysis Workspace possono essere gestiti in **Analytics > Componenti > Progetti programmati**.

In Gestione progetti programmati, puoi modificare ed eliminare pianificazioni ricorrenti di progetti. Cerca una pianificazione nella barra di ricerca o utilizzando le opzioni filtro nella barra a sinistra. Puoi filtrare per tag, pianificazioni approvate, proprietari e altro ancora.

Di seguito sono riportate le azioni comuni di Gestione progetti programmati:

| Azione | Descrizione |
|---|---|
| **Modifica pianificazione** | Fai clic sul titolo della pianificazione per aggiornare le impostazioni di consegna. |
| **Elimina pianificazione** | Seleziona il progetto programmato nell’elenco, quindi fai clic su Elimina dal menu. In questo modo verrà eliminata la pianificazione selezionata per il progetto, mentre il progetto stesso non verrà eliminato. |
| **Aggiungi tag** | Seleziona il progetto programmato nell’elenco, quindi scegli “Assegna tag” o “Approva” per organizzare le pianificazioni e semplificarne la ricerca. |
| **Visualizza pianificazioni non riuscite** | Passa alla barra a sinistra > Altri filtri > Non riuscite per visualizzare le pianificazioni non riuscite. |
| **Visualizza pianificazioni scadute** | Passa alla barra a sinistra > Altri filtri > Scadute per visualizzare le pianificazioni scadute. Fai clic sul titolo della pianificazione per impostare una nuova pianificazione di consegna. |
| **Visualizza ID pianificazione** | Passa alle opzioni della colonna in alto a destra e aggiungi la colonna ID pianificazione alla tabella. L’ID pianificazione è spesso utile per il debug. |

Lo strumento di gestione dei progetti programmati mostra gli elementi creati da uno specifico utente. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte.

## Protezione tramite password di un progetto pianificato {#password}

>[!NOTE]
>
>L’opzione per proteggere con password un progetto pianificato viene visualizzata solo per i clienti CJA che hanno acquistato il [Scudo sanitario](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) prodotto aggiuntivo.

Adobe utilizza la password per crittografare i progetti pianificati, sia che siano inviati in formato .pdf o .csv .

Dopo che la tua azienda ha acquistato lo SKU Healthcare Shield ed è stato abilitato per esso, viene visualizzato il messaggio di richiesta di creazione di una password per un progetto pianificato in due circostanze:

* Quando un utente crea un nuovo progetto pianificato.

* Quando un progetto pianificato esistente sta per essere inviato. Il progetto attualmente pianificato verrà disattivato fino a quando non sarà attiva la protezione tramite password. A questo scopo, il proprietario del progetto pianificato riceverà un’e-mail.

![protezione tramite password](assets/password.png)

### Requisiti per le password

I requisiti relativi alla password sono conformi allo standard Adobe, che richiede un minimo di 8 caratteri con almeno un numero e un carattere speciale.

### Nuovo progetto pianificato

1. Dopo aver salvato il progetto, vai a **[!UICONTROL Share]** > **[!UICONTROL Send file now]** oppure [!UICONTROL Share] > **[!UICONTROL Send file on schedule]**.
1. Seguire le istruzioni di cui sopra, in [Invia subito file](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#now) o [Invia file secondo programma](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#schedule).

### Progetto pianificato esistente

Prima dell’orario di pianificazione di un progetto, il proprietario del progetto riceverà un’e-mail simile a questa:

![e-mail](assets/email-password.png)

1. Accedi di nuovo al Customer Journey Analytics.
1. Fai clic su **[!UICONTROL View Scheduled Project]**.
1. In **[!UICONTROL Edit scheduled project]** , immettere e reimmettere una password.
1. Consenti ai destinatari del progetto pianificato di conoscere questa password.


