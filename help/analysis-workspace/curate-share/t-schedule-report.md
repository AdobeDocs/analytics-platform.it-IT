---
description: Invia un progetto di Analysis Workspace via e-mail o programmane la consegna.
keywords: Analysis Workspace
title: Programmare progetti
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 6f3ae14e4d34de17ed64ae30cee4611e4d6f3226
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 81%

---

# Programmare progetti

Dal **[!UICONTROL Share]** menu   di Workspace, puoi inviare progetti Analysis Workspace tramite e-mail a destinatari selezionati. I file possono essere inviati in formato CSV o PDF.

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

I progetti Analysis Workspace pianificati possono essere gestiti in **[!UICONTROL Analytics]> [!UICONTROL Components] >[!UICONTROL Scheduled Projects]**.

Per ulteriori informazioni, consulta [Progetti pianificati](/help/components/scheduled-projects-manager.md)

## Proteggere un progetto pianificato tramite password {#password}

>[!NOTE]
>
>L’opzione per proteggere un progetto pianificato tramite password viene visualizzata solo per i clienti del Customer Journey Analytics che hanno acquistato il [Healthcare Shield](https://business.adobe.com/it/solutions/experience-cloud-for-healthcare.html) componente aggiuntivo.

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


