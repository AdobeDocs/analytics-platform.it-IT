---
title: Panoramica sulle connessioni Customer Journey Analytics
description: Scopri le connessioni in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 14cdc7bd8817dbf1d7a9950fa6ff62aedff82640
workflow-type: ht
source-wordcount: '188'
ht-degree: 100%

---

# Panoramica sulle connessioni

Le connessioni consentono agli amministratori di prodotto di Customer Journey Analytics di stabilire connessioni con diverse origini dati AEP, come set di dati di eventi, ricerche e profili. Queste connessioni consentono l’integrazione di dati da una connessione a una visualizzazione dati derivata. È consigliabile limitare l’accesso alla gestione delle connessioni a un gruppo di gestione di base. Le configurazioni a livello di connessione hanno implicazioni contrattuali per quanto riguarda l’assegnazione di volumi per i dati inseriti in Customer Journey Analytics.
Le connessioni sono le basi di CJA e vengono create dai set di dati di origine di AEP. L’accesso alle connessioni consente inoltre di visualizzare il gestore Connessioni, con il quale si possono visualizzare i set di dati sottostanti che compongono la connessione, nonché effettuare selezioni critiche di modifica e configurazione.

Panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Autorizzazioni necessarie

Per creare una connessione Customer Journey Analytics, è necessario disporre delle seguenti autorizzazioni in [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html):

Adobe Experience Platform:
* Modellazione dati: visualizzare schemi, gestire schemi
* Gestione dati: visualizzare i set di dati, gestire i set di dati
* Acquisizione dei dati: gestisci origini
* Visualizzare gli spazi dei nomi delle identità

Customer Journey Analytics
* Accesso amministratore prodotto

>[!IMPORTANT]
>
>È possibile combinare più set di dati [!DNL Experience Platform] in una singola connessione.
