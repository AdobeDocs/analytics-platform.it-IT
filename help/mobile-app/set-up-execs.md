---
description: Come configurare gli utenti per l’utilizzo dell’app mobile di Analytics
title: Preparare gli utenti manageriali a utilizzare le scorecard
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 90%

---

# Configurare gli utenti esecutivi per l’utilizzo delle dashboard

In alcuni casi, gli utenti esecutivi potrebbero aver bisogno di ulteriore assistenza per accedere all’app e utilizzarla. Questa sezione fornisce informazioni utili ai curatori per fornire tale assistenza.

## Assicurarsi che gli utenti dell’app abbiano accesso ad Adobe Analytics

1. Imposta i nuovi utenti in [Admin Console di Experience Cloud](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=it).

1. Per poter condividere le scorecard, devi concedere agli utenti dell’app le autorizzazioni per accedere ai componenti delle scorecard come Analysis Workspace, alle visualizzazioni dati su cui sono basate le scorecard, nonché ai filtri, alle metriche e alle dimensioni.

## Prerequisiti di sistema per gli utenti dell’app

Per garantire che gli utenti manageriali possano accedere alle scorecard nell’app, assicurati che:

* Il sistema operativo per dispositivi mobili sui loro dispositivi sia iOS versione 10 o superiore o Android versione 4.4 (KitKat) o superiore
* Abbiano un accesso valido ad Adobe Analytics.
* Le scorecard per dispositivi mobili a essi destinate siano state correttamente create e condivise.
* Abbiano accesso ai Componenti che la scorecard include. Tieni presente che quando condividi le scorecard puoi selezionare l’opzione **[!UICONTROL Share embedded components]**.

## Aiutare i dirigenti a scaricare e installare l’app

**Per gli utenti esecutivi su iOS:**

Fai clic sul seguente collegamento (disponibile anche in Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

`[iOS link](https://apple.co/2zXq0aN)`

**Per gli utenti esecutivi su Android:**

Fai clic sul seguente collegamento (disponibile anche in Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

`[Android link](https://bit.ly/2LM38Oo)`

Una volta scaricata e installata, gli utenti esecutivi possono accedere all’app utilizzando le loro credenziali esistenti di Adobe Analytics; supportiamo sia gli ID Adobe che Enterprise ID e Federated ID.

![Schermata di benvenuto dell’app](assets/welcome.png)

## Aiutare i dirigenti ad accedere alla scorecard

1. Chiedi agli utenti manageriali di accedere all’app.

   Viene visualizzata la schermata **[!UICONTROL Choose a company]**. Questa schermata elenca le aziende di accesso a cui appartiene l’utente esecutivo.

1. Chiedi loro di toccare il nome dell’azienda o dell’organizzazione Experience Cloud applicabile alla scorecard condivisa.

   Vengono quindi elencate tutte le scorecard che sono state condivise con l’utente manageriale per l’azienda con cui è stato eseguito l’accesso.

1. Aiutali a ordinare l’elenco in base a **[!UICONTROL Most recently modified]**, se applicabile.

1. Chiedi loro di toccare il nome della scorecard per visualizzarla.

   ![Scegliere un’azienda](assets/accesscard.png)


### Spiegare l’interfaccia utente della scorecard

Spiega all’utente manageriale come appaiono le tessere nelle scorecard condivise.

![Spiegare le tessere](assets/newexplain.png)

![Esempio di scorecard](assets/intro_scorecard.png)

Ulteriori informazioni sulle tessere:

* La granularità dei grafici sparkline dipende dalla lunghezza dell’intervallo date:
* Un giorno mostra una tendenza oraria
   * Più di un giorno e meno di un anno mostra una tendenza giornaliera
   * Un anno o più mostra una tendenza settimanale
   * La formula della variazione percentuale del valore è metrica totale (intervallo date attuale) – metrica totale (intervallo date di confronto)/metrica totale (intervallo date di confronto).
   * È possibile trascinare lo schermo verso il basso per aggiornare la scorecard.


1. Toccare una tessera per mostrare come funziona un raggruppamento dettagliato della tessera.

   ![Vista Raggruppamento](assets/sparkline.png)

   * Tocca un punto qualsiasi di una sparkline per visualizzare i dati associati a tale punto sulla linea.

   * È inclusa una tabella per visualizzare i dati delle dimensioni aggiunte alla tessera. Tocca la freccia giù per selezionare le dimensioni. Se non è stata aggiunta alcuna dimensione alla tessera, nella tabella vengono visualizzati i dati relativi al grafico.

1. Per modificare gli intervalli di date per la scorecard, tocca l’intestazione Data e seleziona la combinazione di intervalli di date principali e di confronto che desideri visualizzare.

   ![Modificare le date](assets/changedate.png)

## Modificare le preferenze dell’app

Per modificare le preferenze, tocca l’opzione **[!UICONTROL Preferences]** mostrata sopra. Nelle preferenze, puoi attivare l’accesso biometrico oppure la modalità scura dell’app come illustrato di seguito:

![Modalità scura](assets/darkmode.png)

## Risoluzione dei problemi

Se l’utente esecutivo effettua l’accesso e vede un messaggio che dice che non è stato condiviso nulla:

![Niente di condiviso](assets/nothing.png)

* L’utente manageriale potrebbe aver selezionato l’istanza di Analytics sbagliata oppure
* la scorecard potrebbe non essere stata condivisa con l’utente manageriale.

Verifica che l’utente manageriale possa accedere all’istanza appropriata di Adobe Analytics e che la scorecard sia stata condivisa.
