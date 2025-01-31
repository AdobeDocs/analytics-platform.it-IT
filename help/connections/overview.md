---
title: Panoramica sulle connessioni Customer Journey Analytics
description: Scopri le connessioni in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: a2262e446a15ee58be2f3f674c77223368fc8f76
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 100%

---

# Panoramica sulle connessioni

Le connessioni consentono agli amministratori di prodotto di Customer Journey Analytics di stabilire connessioni con diverse origini dati [!DNL Adobe Experience Platform], come set di dati di eventi, ricerche e profili. Queste connessioni consentono l’integrazione di dati da una connessione a una visualizzazione dati derivata. Le connessioni sono le basi di CJA e vengono create dai set di dati di origine di [!DNL Experience Platform]. L’accesso alle connessioni consente inoltre di visualizzare il gestore Connessioni, con il quale si possono visualizzare i set di dati sottostanti che compongono la connessione, nonché effettuare selezioni critiche di modifica e configurazione.

È consigliabile limitare l’accesso alla gestione delle connessioni a un gruppo di gestione di base. Le configurazioni a livello di connessione hanno implicazioni contrattuali per quanto riguarda l’assegnazione di volumi per i dati inseriti in Customer Journey Analytics.

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target=&#34;_blank&#34;} for a demo video.

>[!ENDSHADEBOX]

-->

## Autorizzazioni necessarie

Per creare una connessione Customer Journey Analytics, è necessario disporre delle seguenti autorizzazioni. Per ulteriori dettagli sulle autorizzazioni, consulta la documentazione di [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) e le [Autorizzazioni Adobe Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/access-control/home).

### In Adobe Admin Console:

* Customer Journey Analytics: amministratore prodotto
* Adobe Experience Platform: aggiunto al profilo di prodotto denominato *AEP-Default-All-Users*

### In Autorizzazioni Adobe Experience Platform:

* Modellazione dati: visualizzare schemi, gestire schemi
* Gestione dati: visualizzare i set di dati, gestire i set di dati
* Acquisizione dei dati: gestisci origini
* Identity Management: visualizzare gli spazi dei nomi di identità
* Sandbox: sandbox utilizzate nelle connessioni di Customer Journey Analytics correlate

>[!IMPORTANT]
>
>È possibile combinare più set di dati [!DNL Experience Platform] in una singola connessione.
