---
title: Trasferire le risorse
description: Scopri come trasferire componenti da un utente all’altro
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 3e521cb4ef532d57b9f408fc12dcf138f130f059
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 1%

---

# Trasferire le risorse

Lo strumento Asset Transfer (Trasferimento risorse) consente di trasferire la proprietà delle risorse ad altri utenti. Assets può includere componenti quali progetti, segmenti, intervalli di date, metriche calcolate, annotazioni, avvisi e progetti pianificati.

Assets è spesso associato a un singolo proprietario e in alcuni casi, come segmenti e metriche calcolate, non può essere modificato o condiviso anche dagli amministratori. Quando gli utenti abbandonano l’organizzazione o il loro ruolo cambia, potrebbe diventare necessario trasferire la proprietà di queste risorse ad altri utenti per garantire la continuità e l’accesso appropriato.

## Autorizzazioni

Il trasferimento delle risorse richiede l’autorizzazione di amministratore di prodotto per Customer Journey Analytics.

## Trasferire le risorse

1. In CJA, passa a **[!UICONTROL Tools]** > **[!UICONTROL Asset Transfer]**.

   ![Voce di menu Trasferimento risorse](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Nella finestra di dialogo **[!UICONTROL Users]**, cerca e seleziona l&#39;utente da cui desideri trasferire le risorse.

   >[!IMPORTANT]
   >
   >È possibile effettuare un trasferimento solo 1:1, da un utente all&#39;altro. I trasferimenti uno-a-molti o molti-a-uno non sono supportati.


1. Dopo aver selezionato un utente, nella parte inferiore della schermata viene visualizzata l’opzione Trasferisci risorse.

   ![Opzione di menu Trasferisci risorse](/help/tools/asset-transfer/assets/after-selection.png)

1. Fai clic su **[!UICONTROL Transfer assets]**.

1. Nella schermata **[!UICONTROL Transfer assets]**, seleziona innanzitutto il destinatario a cui desideri trasferire le risorse.

1. Ora scorri la cartella di ciascun componente nel menu di navigazione a sinistra per selezionare i singoli componenti o tutte le risorse in una cartella da trasferire.

   >[!NOTE]
   >
   >Il trasferimento delle risorse da un amministratore a un non amministratore non comporta l’aggiornamento del destinatario a un amministratore.


   >[!NOTE]
   >
   >    Quando si trasferiscono risorse che fanno riferimento ad altri componenti (ad esempio progetti che fanno riferimento ad altri segmenti e metriche calcolate), i componenti non di proprietà dell’attuale proprietario del progetto verranno condivisi solo con il destinatario. La proprietà di tutti gli altri componenti verrà trasferita al destinatario.

1. Per selezionare _tutte_ le risorse in una cartella, seleziona la casella accanto a **[!UICONTROL Name]** nella parte superiore della tabella.

   ![selezionare le risorse da trasferire](/help/tools/asset-transfer/assets/select-assets.png)

1. Fai clic su **[!UICONTROL Transfer]** in alto a destra dopo aver effettuato tutte le selezioni.

1. Fare clic su **[!UICONTROL Confirm]** quando viene visualizzato il messaggio di conferma.

   >[!IMPORTANT]
   >
   >Non chiudere la schermata durante il trasferimento per evitare l&#39;interruzione del processo. Questo garantisce un’esperienza di trasferimento fluida.

## Trasferisci risultati

Esistono tre possibili risultati per un trasferimento:

- **Trasferimento completato**: &quot;Trasferimento di Assets completato.&quot;

- **Operazione parzialmente riuscita**: &quot;Alcune risorse sono state trasferite correttamente&quot;.

- **Errore di trasferimento**: &quot;Impossibile trasferire le risorse. Riprova.&quot;

### Possibili cause di errore nel trasferimento delle risorse

- Servizi dipendenti che causano errori: il trasferimento delle risorse interagisce con un servizio diverso per ciascun tipo di componente (ad esempio problemi di rete o di servizio a valle), pertanto potrebbero verificarsi errori parziali o completi o errori intermittenti.

- Componente mancante o trasferito da un altro amministratore: un componente è stato eliminato da un altro utente o trasferito da un altro amministratore mentre era ancora in corso un processo di trasferimento di risorse.

- Il corpo del POST API non viene popolato correttamente: un componente potrebbe non essere inviato nel corpo del POST API quando sono selezionati più tipi di componente.

- L’utente non esiste: l’utente è stato eliminato dal trasferimento intermedio o non è valido per un altro motivo. Se l’utente non è valido prima dell’inizio del trasferimento, lo strumento rileva tale situazione e non elabora il processo. Se l’utente veniva eliminato durante il trasferimento intermedio, potevano verificarsi errori parziali.

- Errore di connessione/rete: la connessione si interrompe durante il trasferimento intermedio. Eventuali batch di processi di trasferimento già trasmessi al backend continuano a essere elaborati fino al completamento, ma l’utente non visualizzerà il messaggio dei risultati del trasferimento con un riepilogo di ciò che è stato completato e di ciò che non è riuscito.

- Scheda browser chiusa trasferimento intermedio: per trasferimenti molto grandi, se la scheda del browser è chiusa o la pagina viene spostata da trasferimento intermedio, solo le richieste di rete effettuate prima della chiusura della scheda o della navigazione della pagina trasferiranno correttamente le risorse. Se l’utente torna alla pagina, non riceverà il messaggio di stato della risposta che indica quali risorse sono state trasferite e quali no.

## Trasferire le risorse durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics

Uno dei casi d’uso principali per il trasferimento delle risorse è durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

La funzionalità [Migrazione componenti](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/component-migration) in Adobe Analytics consente di migrare i progetti di proprietà dell&#39;amministratore ad altri amministratori. Tutti i componenti che compongono questi progetti vengono quindi ricreati in Customer Journey Analytics e l’amministratore del destinatario possiede tutti questi componenti, indipendentemente da chi li ha creati.

Questo strumento di trasferimento delle risorse consente successivamente agli amministratori di riassegnare i componenti ai legittimi proprietari, che siano amministratori o meno.

>[!IMPORTANT]
>
>Anche se puoi trasferire i componenti utilizzando questo strumento, l’amministratore deve comunque assicurarsi che il destinatario abbia accesso alle visualizzazioni dati necessarie per visualizzare/utilizzare questi componenti. Puoi visualizzare e assegnare le autorizzazioni in [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html).

## Export to CSV (Esporta in CSV)

L&#39;opzione **[!UICONTROL Export to CSV]** consente solo agli amministratori di scaricare un elenco di utenti visualizzato in un file .csv. Non consente loro di esportare un elenco di risorse trasferite in un file .csv.

## Utenti inattivi

Tutti gli utenti eliminati in precedenza vengono visualizzati in una voce &quot;Utenti inattivi&quot;, insieme a tutti i relativi componenti orfani. Questi componenti possono essere trasferiti a un nuovo destinatario. Questa funzione sarà disponibile a gennaio.

![Utenti inattivi visualizzati nell&#39;interfaccia utente Trasferisci risorse](assets/inactive-users.png)

