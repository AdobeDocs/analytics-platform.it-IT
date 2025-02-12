---
title: Aggiungere il set di dati del connettore di origine di Analytics alla connessione
description: Scopri come aggiungere il set di dati del connettore di origine di Analytics alla connessione
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 9%

---

# Disabilita la raccolta dati di AppMeasurement {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Disabilita la raccolta dati di AppMeasurement"
>abstract="Con i dati di Web SDK completamente funzionanti, collabora con il team di sviluppatori per rimuovere AppMeasurement.js dal sito web o dalla proprietà.<br><br>L&#39;operazione di rimozione di AppMeasurement da un sito Web richiede solo alcuni minuti, ma il completamento richiede tempo da parte del team di progettazione. Tuttavia, assicurati che i tuoi utenti di Analytics utilizzino Customer Journey Analytics e non Adobe Analytics; se non lo hai già fatto, questo processo di annuncio per spostare tutti potrebbe richiedere molto più tempo."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Segui i passaggi descritti in questa pagina solo dopo aver completato tutti i passaggi di aggiornamento precedenti. Puoi seguire i [passaggi di aggiornamento consigliati](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) oppure i passaggi di aggiornamento generati in modo dinamico per la tua organizzazione con il [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Dopo aver completato i passaggi descritti in questa pagina, continua seguendo i passaggi di aggiornamento consigliati o generati in modo dinamico.

<!-- need to work on this -->

* **Tag:** disabilita l&#39;estensione Adobe Analytics

* **AppMeasurment:** Sostituisci la libreria AppMeasurement.js s s=newobject
