---
title: Aggiungere il set di dati del connettore di origine di Analytics alla connessione
description: Scopri come aggiungere il set di dati del connettore di origine di Analytics alla connessione
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 9cfe89aef069d777424eb8a5d9ef8ae03a9d0486
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 43%

---

# Disabilita Adobe Analytics {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Disabilita la raccolta dati di AppMeasurement"
>abstract="Con i dati di Web SDK completamente funzionanti, collabora con il team di sviluppatori per rimuovere AppMeasurement.js dal tuo sito Web o dalla proprietà.<br><br>La rimozione di AppMeasurement da un sito Web richiede solo alcuni minuti, ma il completamento delle operazioni affidate al team tecnico richiede molto tempo. Assicurati tuttavia che gli utenti di Analytics utilizzino Customer Journey Analytics e non Adobe Analytics; se non l’hai già fatto, il processo di annuncio per trasferire tutti i dati potrebbe richiedere molto più tempo."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oppure i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

Prima di disabilitare Adobe Analytics, controlla le informazioni in [Valuta quando disabilitare Adobe Analytics dopo l&#39;aggiornamento a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

* **Tag:** disabilita l&#39;estensione Adobe Analytics

* **AppMeasurment:** Sostituisci la libreria AppMeasurement.js s s=newobject
