---
description: Spiega la strategia di rilascio continuo delle funzioni per il Customer Journey Analytics
title: Rilasci di funzioni di Customer Journey Analytics
source-git-commit: b740d3a18d1090b04cc50869d38600f016cf30d5
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Rilasci di funzioni di Customer Journey Analytics

I rilasci di Customer Journey Analytics funzionano su un modello di distribuzione continua che consente un approccio scalabile e graduale alla distribuzione delle funzioni.

## Strategia di rilascio

[!UICONTROL Analysis Workspace] utilizza i flag di funzione (noti anche come “interruttori”) per controllare la visibilità delle nuove funzioni, consentendo test su scala controllati prima del rilascio completo. Questa strategia di rilascio include le seguenti fasi:

* **Rilascio in produzione (RTP, Release to Production)**: il codice viene rilasciato in produzione con la visibilità delle funzioni disattivata in Analysis Workspace. A volte la funzione è disponibile nell’API CJA.

* **Test limitati**: un rilascio graduale inizia con il test da parte degli utenti Adobe interni. Il rilascio viene quindi scalato dallo 0% al 100% di disponibilità nel corso di un paio di mesi. Il rollout graduale avviene a livello di organizzazione Experience Cloud, in modo che tutti gli utenti autorizzati in un’organizzazione ricevano la stessa esperienza.

* **Disponibilità generale (GA, General Availability)**: la funzione è disponibile per il 100% delle organizzazioni Experience Cloud autorizzate e il rilascio è completo.

Con ogni rilascio di funzioni, la timeline da RTP a GA può variare. L’obiettivo è mantenere i rilasci brevi, in modo che entro 2 mesi dall’inizio del rilascio (RTP) una funzione sarà in GA.

## Flag di funzioni

I flag di funzioni consentono di controllare la visibilità delle nuove funzioni durante la fase di rilascio. Adobe consiglia di aggiungere `app.launchdarkly.com` all’[elenco di indirizzi consentiti](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=it) del firewall, per garantire un’esperienza ottimale durante la fase di rilascio. Una volta che la versione definitiva viene rilasciata al pubblico, il flag viene rimosso.

Puoi visualizzare i flag di funzioni attivi in qualsiasi momento, da **Aiuto > Informazioni su Workspace > Flag di funzioni attivi**.

## Vantaggi

I rilasci graduali consentono ad Adobe di scalare meglio il processo di distribuzione del software e assicurano che le funzioni siano completamente consolidate prima della disponibilità generale. Consente inoltre di pubblicare le funzioni non appena sono disponibili, piuttosto che attenersi a un intervallo di rilascio mensile fisso.

## Domande frequenti

| Domanda | Risposta |
| --- | --- |
| Posso richiedere l’accesso anticipato a una funzione? | No. Non sarà concesso un accesso anticipato.<br>Se desideri testare concetti di Analytics in fase iniziale, ti invitiamo a provare [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html) per fornire feedback sulle innovazioni leader del settore. |
| Questa strategia di rilascio influisce sull’accesso alle funzioni? | No. Una volta che una funzione raggiunge la fase GA, potrai accedervi se è inclusa nel tuo pacchetto Analytics. |