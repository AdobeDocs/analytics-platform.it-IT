---
description: Invia un progetto di Analysis Workspace per e-mail o programmane la consegna.
keywords: Analysis Workspace
title: Invia report ad altri per e-mail
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: a462e736ddcdf1a5ea84a85eea2c2ce0b8a34fb0
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 69%

---

# Inviare file ad altri

Puoi inviare i report di Customer Journey Analytics come file agli utenti selezionati per e-mail. Puoi inviare file ad hoc oppure configurare i file da inviare secondo una pianificazione. I file possono essere inviati in formato CSV o PDF.

Tutti i tag applicati al progetto vengono applicati automaticamente all’esportazione.

Sono disponibili anche altri metodi di esportazione dei dati di Customer Journey Analytics, come descritto in [Panoramica sull’esportazione](/help/analysis-workspace/export/export-project-overview.md).

![Invia file](assets/send-file.png)

## Invia file

Per inviare un file ai destinatari tramite e-mail:

1. Seleziona **[!UICONTROL Share]>[!UICONTROL Send file]**.
1. Specifica il tipo di file:
   * [!UICONTROL **CSV**]: scegli questa opzione se desideri utilizzare dati in formato testo normale.
   * [!UICONTROL **PDF**]: scegli questa opzione se vuoi che il file scaricato contenga tutte le tabelle e le visualizzazioni mostrate (visibili) nel progetto.
1. (Facoltativo) Utilizzare **[!UICONTROL Description]** per aggiungere una descrizione da includere nell&#39;e-mail.
1. Aggiungi destinatari o gruppi. Puoi anche immettere indirizzi e-mail.
1. (Solo per i clienti Healthcare Shield) Fornisci una password per [proteggere con password un report pianificato](#password-protect-a-new-scheduled-project).
1. (Facoltativo) Selezionare **[!UICONTROL Show scheduling options]** per [pianificare un&#39;esportazione di file](#schedule-file-export).
1. Fai clic su **[!UICONTROL Send Now]**. Seleziona **[!UICONTROL Cancel]** per annullare.


## Pianificare l’esportazione di file {#schedule}

Per inviare un file in base a una pianificazione ai destinatari tramite e-mail

1. Seleziona **[!UICONTROL Share]>[!UICONTROL Schedule file export]**.
1. Specifica il tipo di file:
   * [!UICONTROL **CSV**]: scegli questa opzione se desideri utilizzare dati in formato testo normale.
   * [!UICONTROL **PDF**]: scegli questa opzione se vuoi che il file scaricato contenga tutte le tabelle e le visualizzazioni mostrate (visibili) nel progetto.
1. (Facoltativo) Utilizzare **[!UICONTROL Description]** per aggiungere una descrizione da includere nell&#39;e-mail.
1. Aggiungi destinatari o gruppi. Puoi anche immettere indirizzi e-mail.
1. (Solo per i clienti Healthcare Shield) Fornisci una password per [proteggere con password un report pianificato](#password-protect-a-new-scheduled-project).
1. Assicurarsi che **[!UICONTROL Show scheduling options]** sia selezionato.
1. Seleziona una **[!UICONTROL Frequency]**. Puoi scegliere tra:

   | Frequenza | Opzioni |
   |---|---|
   | **[!UICONTROL Send hourly]** | Immettere un valore per **[!UICONTROL Send every number of hours]**. |
   | **[!UICONTROL Send daily]** | Selezionare un **[!UICONTROL Daily frequency]**: **[!UICONTROL Send every day]**, **[!UICONTROL Send every weekday]** o **[!UICONTROL Custom frequency]**.<br/>Se si seleziona **[!UICONTROL Custom frequency]**, immettere un valore per **[!UICONTROL Send every number of days]**. |
   | **[!UICONTROL Send weekly]** | Immettere un valore per **[!UICONTROL Send every number of weeks]**. E seleziona un **[!UICONTROL Day of week]**. |
   | **[!UICONTROL Send monthly by day of the week]** | Selezionare **[!UICONTROL Day of week]** e **[!UICONTROL Week of month]**. |
   | **[!UICONTROL Send monthly by day of the month]** | Selezionare un valore da **[!UICONTROL Send on this day of the month]**. |
   | **[!UICONTROL Send yearly by day of the month]** | Selezionare un **[!UICONTROL Day of week]**, selezionare un **[!UICONTROL Week of month]** e selezionare un **[!UICONTROL Monthly of year]**. |
   | **[!UICONTROL Send yearly by specific date]** | Selezionare un **[!UICONTROL Month of year]** e un valore da **[!UICONTROL Send on this day of the month]**. |

1. Immettere una data di inizio in **[!UICONTROL Starting on]**. In alternativa, selezionare ![Calendario](/help/assets/icons/Calendar.svg) per scegliere una data di inizio dal calendario.

1. Immettere una data di fine in **[!UICONTROL Ending on]**. In alternativa, selezionare ![Calendario](/help/assets/icons/Calendar.svg) per scegliere una data di fine dal calendario.
1. Seleziona **[!UICONTROL Send on schedule]**. Seleziona **[!UICONTROL Cancel]** per annullare.


## Proteggere un progetto pianificato tramite password {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="Crittografia password"
>abstract="La password fornita verrà utilizzata per crittografare il file per il progetto pianificato. I requisiti di sicurezza dell’organizzazione richiedono la crittografia della password."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>L’opzione per proteggere un progetto pianificato tramite password viene visualizzata solo per i clienti Customer Journey Analytics che hanno acquistato il prodotto aggiuntivo [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html?lang=it).

Adobe utilizza la password per crittografare i progetti pianificati, sia che siano inviati in formato .pdf o .csv.

Dopo che la tua azienda ha acquistato lo SKU Healthcare Shield ed è stata abilitata a usarlo, il messaggio di richiesta di creazione di una password per un progetto pianificato viene visualizzato nelle circostanze seguenti:

* Quando un utente crea un nuovo progetto pianificato.

* Quando un progetto pianificato esistente sta per essere inviato. Il progetto attualmente pianificato verrà disattivato fino a quando non sarà attiva la protezione tramite password. Il proprietario del progetto pianificato riceve un messaggio e-mail con informazioni su questo requisito.

### Requisiti per la password

I requisiti relativi alla password sono conformi agli standard Adobe che richiede un minimo di 8 caratteri con almeno un numero e un carattere speciale.

### Proteggere un nuovo progetto pianificato tramite password

1. Dopo aver salvato il progetto, passa a **[!UICONTROL Share]** > **[!UICONTROL Send file now]** oppure **[!UICONTROL Share]** > **[!UICONTROL Send file on schedule]**.
1. Segui le istruzioni precedenti, in [Invia il file ora](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=it#now) o [Invia il file secondo pianificazione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=it#schedule).

### Proteggere un progetto pianificato esistente tramite password

Quando proteggi con password un progetto pianificato esistente, il proprietario del progetto riceve un’e-mail simile alla seguente:

![La notifica e-mail di Customer Journey Analytics indicante che la crittografia della password è obbligatoria per l’organizzazione.](assets/email-password.png)

1. Accedi a Customer Journey Analytics.
1. Seleziona **[!UICONTROL View Scheduled Project]**.
1. Nella finestra di dialogo **[!UICONTROL Edit scheduled project]**, immetti e reimmetti una password.
1. Consenti ai destinatari del progetto pianificato di conoscere la password. Non distribuire la password a persone che non sono destinatari del progetto pianificato.



## Gestione progetti programmati {#manager}

I progetti Analysis Workspace pianificati possono essere gestiti dall&#39;interfaccia principale, utilizzando **[!UICONTROL Components]** > **[!UICONTROL Scheduled Projects]**. Per ulteriori informazioni, consulta [Progetti pianificati](/help/components/scheduled-projects-manager.md).
