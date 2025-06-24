---
title: Trasferire le risorse
description: Scopri come trasferire i componenti da un utente all’altro
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 3e521cb4ef532d57b9f408fc12dcf138f130f059
workflow-type: ht
source-wordcount: '817'
ht-degree: 100%

---

# Trasferire le risorse

Lo strumento Asset Transfer (Trasferimento risorse) consente di trasferire la proprietà delle risorse ad altri utenti. Le risorse possono includere componenti quali progetti, segmenti, intervalli di date, metriche calcolate, annotazioni, avvisi e progetti pianificati.

Le risorse sono associate a un singolo proprietario e in alcuni casi, come segmenti e metriche calcolate, non possono essere modificate o condivise anche dagli amministratori. Quando gli utenti abbandonano l’organizzazione o il rispettivo ruolo cambia, potrebbe diventare necessario trasferire la proprietà di queste risorse ad altri utenti per garantire la continuità e l’accesso appropriato.

## Autorizzazioni

Il trasferimento delle risorse richiede l’autorizzazione dell’amministratore di prodotto per Customer Journey Analytics.

## Trasferire le risorse

1. In CJA, passa a **[!UICONTROL Tools]** > **[!UICONTROL Asset Transfer]**.

   ![Voce di menu Trasferimento risorse](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Nella finestra di dialogo **[!UICONTROL Users]**, cerca e seleziona l’utente da cui desideri trasferire le risorse.

   >[!IMPORTANT]
   >
   >È possibile effettuare solo un trasferimento 1:1, da un utente all’altro. I trasferimenti uno-a-molti o molti-a-uno non sono supportati.


1. Dopo aver selezionato un utente, nella parte inferiore della schermata viene visualizzata l’opzione Transfer assets (Trasferisci risorse).

   ![Opzione di menu Trasferisci risorse](/help/tools/asset-transfer/assets/after-selection.png)

1. Fai clic su **[!UICONTROL Transfer assets]**.

1. Nella schermata **[!UICONTROL Transfer assets]**, seleziona innanzitutto il destinatario a cui desideri trasferire le risorse.

1. Ora scorri la cartella di ciascun componente nel menu di navigazione a sinistra per selezionare i singoli componenti o tutte le risorse di una cartella da trasferire.

   >[!NOTE]
   >
   >Quando si trasferiscono delle risorse da un amministratore a un utente non amministratore, quest’ultimo non diventa a sua volta amministratore.


   >[!NOTE]
   >
   >    Quando si trasferiscono risorse che fanno riferimento ad altri componenti (ad esempio progetti che fanno riferimento ad altri segmenti e metriche calcolate), i componenti che non appartengono all’attuale proprietario del progetto verranno solo condivisi con il destinatario. Tutti gli altri componenti diventeranno di proprietà del destinatario.

1. Per selezionare _tutte_ le risorse di una cartella, seleziona la casella accanto al **[!UICONTROL Name]** nella parte superiore della tabella.

   ![selezionare le risorse da trasferire](/help/tools/asset-transfer/assets/select-assets.png)

1. Fai clic su **[!UICONTROL Transfer]** in alto a destra dopo aver effettuato tutte le selezioni.

1. Fai clic su **[!UICONTROL Confirm]** quando viene visualizzato il messaggio di conferma.

   >[!IMPORTANT]
   >
   >Durante il trasferimento, non chiudere la schermata; in caso contrario, il processo verrà interrotto. Questo garantisce un’esperienza di trasferimento fluida.

## Risultati del trasferimento

Esistono tre possibili risultati per un trasferimento:

- **Trasferimento completato**: “Risorse trasferite correttamente”.

- **Parzialmente completato**: “Alcune risorse sono state trasferite correttamente”.

- **Trasferimento non riuscito**: “Impossibile trasferire le risorse. Riprova più tardi”.

### Possibili motivi per trasferimento non riuscito

- Errori causati da servizi dipendenti: il trasferimento delle risorse interagisce con un servizio diverso per ciascun tipo di componente (ad esempio problemi di rete o di servizio a valle), pertanto la mancata riuscita potrebbe essere parziale, completa o intermittente.

- Componente mancante o trasferito da un altro amministratore: un componente è stato eliminato da un altro utente o trasferito da un altro amministratore a un altro utente mentre era ancora in corso un processo di trasferimento di risorse.

- Il corpo del POST API non viene popolato correttamente: un componente potrebbe non essere inviato nel corpo del POST API quando sono selezionati più tipi di componente.

- L’utente non esiste: l’utente è stato eliminato mentre era in corso il trasferimento oppure non è valido per un altro motivo. Se l’utente non è valido prima che inizi il trasferimento, lo strumento rileva tale situazione e non elabora il processo. Se l’utente viene eliminato mentre il trasferimento è in corso, si possono verificare errori parziali.

- Errore di connessione o rete: la connessione si interrompe durante il trasferimento. Eventuali batch di processi di trasferimento già trasmessi al back-end continuano a essere elaborati fino al completamento, ma l’utente non riceverà il messaggio dei risultati del trasferimento con un riepilogo di ciò che è stato completato e ciò che non è riuscito.

- Scheda del browser chiusa durante il trasferimento: per trasferimenti molto grandi, se la scheda del browser viene chiusa o si passa a un’altra pagina mentre è in corso il trasferimento, il corretto trasferimento delle risorse verrà eseguito solo per le richieste di rete effettuate prima della chiusura della scheda o del passaggio a un’altra pagina. Se l’utente ritorna sulla pagina, non riceverà il messaggio di stato della risposta che indica quali risorse sono state trasferite e quali no.

## Trasferire le risorse durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics

Uno dei casi d’uso principali per il trasferimento delle risorse è durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

La funzione [Component Migration](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/component-migration) (Migrazione componenti) di Adobe Analytics consente di migrare ad altri amministratori i progetti di proprietà dell’amministratore. Tutti i componenti di questi progetti vengono quindi ricreati in Customer Journey Analytics e diventano di proprietà dell’amministratore destinatario, a prescindere da chi li ha creati.

Lo strumento Asset Transfer (Trasferimento risorse) consente poi agli amministratori di riassegnare i componenti ai legittimi proprietari, che siano amministratori o meno.

>[!IMPORTANT]
>
>Anche se puoi trasferire i componenti utilizzando questo strumento, l’amministratore deve comunque assicurarsi che il destinatario abbia accesso alle visualizzazioni dati necessarie per visualizzare o utilizzare questi componenti. Puoi visualizzare e assegnare le autorizzazioni in [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html).

## Export to CSV (Esporta in CSV)

L’opzione **[!UICONTROL Export to CSV]** consente agli amministratori di scaricare in un file .csv solo l’elenco degli utenti visualizzati. Non consente loro di esportare in un file .csv un elenco di risorse trasferite.

## Utenti inattivi

Tutti gli utenti eliminati in precedenza vengono visualizzati in una voce “Inactive users” (Utenti inattivi), insieme a tutti i relativi componenti orfani. Questi componenti possono essere trasferiti a un nuovo destinatario. Questa funzione sarà disponibile a gennaio.

![Utenti inattivi visualizzati nell&#39;interfaccia utente per il trasferimento delle risorse](assets/inactive-users.png)

