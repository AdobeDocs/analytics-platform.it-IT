---
title: Trasferire le risorse
description: Scopri come trasferire componenti da un utente all’altro
role: Admin
solution: Customer Journey Analytics
source-git-commit: 9663a24c2430d3822cb83876ea048b6423405215
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 1%

---


# Trasferire le risorse

Lo strumento Asset Transfer (Trasferimento risorse) consente di trasferire la proprietà delle risorse ad altri utenti. Assets può includere componenti quali progetti, filtri, intervalli di date, metriche calcolate, annotazioni, avvisi e progetti pianificati.

Assets è spesso associato a un singolo proprietario e in alcuni casi, ad esempio per quanto riguarda i filtri e le metriche calcolate, non può essere modificato o condiviso anche dagli amministratori. Quando gli utenti abbandonano l’organizzazione o il loro ruolo cambia, potrebbe diventare necessario trasferire la proprietà di queste risorse ad altri utenti per garantire la continuità e l’accesso appropriato.

## Autorizzazioni

Il trasferimento delle risorse richiede l’autorizzazione di amministratore di prodotto per il Customer Journey Analytics.

## Trasferire le risorse

1. In CJA, passa a **[!UICONTROL Tools]** > **[!UICONTROL Asset Transfer]**.

   ![Voce di menu Trasferimento risorse](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Nella finestra di dialogo **[!UICONTROL Users]**, cerca e seleziona l&#39;utente da cui desideri trasferire le risorse.

   >[!IMPORTANT]
   >
   >È possibile effettuare un trasferimento solo 1:1, da un utente all&#39;altro. I trasferimenti uno-a-molti o molti-a-uno non sono supportati.


1. Dopo aver selezionato un utente, nella parte inferiore della schermata viene visualizzata l’opzione Trasferisci risorse.

   ![opzione di menu](/help/tools/asset-transfer/assets/after-selection.png)

1. Fai clic su **[!UICONTROL Transfer assets]**.

1. Nella schermata **[!UICONTROL Transfer assets]**, seleziona innanzitutto il destinatario a cui desideri trasferire le risorse.

1. Ora scorri la cartella di ciascun componente nel menu di navigazione a sinistra per selezionare i singoli componenti o tutte le risorse in una cartella da trasferire.

   >[!NOTE]
   >
   >Il trasferimento delle risorse da un amministratore a un non amministratore non comporta l’aggiornamento del destinatario a un amministratore.


   >[!NOTE]
   >
   >    Quando si trasferiscono risorse che fanno riferimento ad altri componenti (ad esempio progetti che fanno riferimento ad altri filtri e metriche calcolate), i componenti non di proprietà dell’attuale proprietario del progetto verranno condivisi solo con il destinatario. La proprietà di tutti gli altri componenti verrà trasferita al destinatario.

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

## Trasferire le risorse durante l’aggiornamento da Adobe Analytics al Customer Journey Analytics

Uno dei casi d’uso principali per il trasferimento delle risorse è durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

La funzionalità [Migrazione componenti](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) in Adobe Analytics consente di migrare i progetti di proprietà dell&#39;amministratore ad altri amministratori. Tutti i componenti che compongono questi progetti vengono quindi ricreati in Customer Journey Analytics e l’amministratore del destinatario possiede tutti questi componenti, indipendentemente da chi li ha creati.

Questo strumento di trasferimento delle risorse consente successivamente agli amministratori di riassegnare i componenti ai legittimi proprietari, che siano amministratori o meno.

>[!IMPORTANT]
>
>Anche se puoi trasferire i componenti utilizzando questo strumento, l’amministratore deve comunque assicurarsi che il destinatario abbia accesso alle visualizzazioni dati necessarie per visualizzare/utilizzare questi componenti. Puoi visualizzare e assegnare le autorizzazioni nell&#39;[Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html).

## Export to CSV (Esporta in CSV)

L&#39;opzione **[!UICONTROL Export to CSV]** consente solo agli amministratori di scaricare un elenco di utenti visualizzato in un file .csv. Non consente loro di esportare un elenco di risorse trasferite in un file .csv.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->