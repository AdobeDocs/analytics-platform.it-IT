---
description: Descrizione della strategia di rilascio continuo delle funzioni per Customer Journey Analytics
title: Strategia di rilascio delle funzioni di Customer Journey Analytics
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 88%

---

# Strategia di rilascio delle funzioni di Customer Journey Analytics

I rilasci di Customer Journey Analytics funzionano su un modello di distribuzione continua che consente un approccio scalabile e graduale alla distribuzione delle funzioni.

## Strategia di rilascio

[!UICONTROL Analysis Workspace] utilizza i flag di funzione (noti anche come “interruttori”) per controllare la visibilità delle nuove funzioni, consentendo test su scala controllati prima del rilascio completo. Questa strategia di rilascio include le seguenti fasi:

* **Test limitati**: un rilascio graduale inizia con il test da parte di utenti Adobe interni. Viene quindi reso disponibile a un piccolo gruppo di account cliente per garantire che la funzione soddisfi le loro esigenze e aspettative.

* **Inizio del rollout**: il rollout di un rilascio graduale inizia con la fase di test limitato. La versione viene quindi scalata dallo 0% al 100% di disponibilità ai clienti nel corso di un paio di mesi. Il rollout graduale avviene a livello di organizzazione Experience Cloud, in modo che tutti gli utenti autorizzati in un’organizzazione ricevano la stessa esperienza.

* **Disponibilità generale (GA, General Availability)**: la funzione è disponibile per il 100% delle organizzazioni Experience Cloud autorizzate e il rilascio è completo.

Con ogni rilascio di funzioni, la timeline da RTP a GA può variare. L’obiettivo è mantenere i rilasci brevi, in modo che entro 2 mesi dall’inizio del rilascio (RTP) una funzione sarà in GA.

## Flag di funzioni

I flag di funzioni consentono di controllare la visibilità delle nuove funzioni durante la fase di rilascio. L’Adobe consiglia di consentire `app.launchdarkly.com` attraverso il firewall dell’organizzazione per un’esperienza ottimale durante le versioni. Questi flag vengono rimossi dopo il rilascio di una funzione a tutti. Consulta [Domini utilizzati dal Customer Journey Analytics](../technotes/domains.md) per ulteriori informazioni.

Puoi visualizzare i flag di funzioni attivi in qualsiasi momento, da **Aiuto > Informazioni su Workspace > Flag di funzioni attivi**.

## Vantaggi

I rilasci graduali consentono ad Adobe di scalare meglio il processo di distribuzione del software e assicurano che le funzioni siano completamente consolidate prima della disponibilità generale. Consente inoltre di pubblicare le funzioni non appena sono disponibili, piuttosto che attenersi a un intervallo di rilascio mensile fisso.

## Domande frequenti

| Domanda | Risposta |
| --- | --- |
| Posso richiedere l’accesso anticipato a una funzione? | No. Non sarà concesso un accesso anticipato.<br>Se desideri testare concetti di Analytics in fase iniziale, ti invitiamo a provare [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=it) per fornire feedback sulle innovazioni leader del settore. |
| Questa strategia di rilascio influisce sull’accesso alle funzioni? | No. Una volta che una funzione raggiunge la fase GA, potrai accedervi se è inclusa nel tuo pacchetto Analytics. |
