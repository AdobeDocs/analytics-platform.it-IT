---
description: Come configurare gli utenti per l’utilizzo dell’app mobile per dashboard di Adobe Analytics
title: Preparare gli utenti direzionali a utilizzare le scorecard
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
source-git-commit: 9cffb57cc4a525c78ec171034adff0e02b936cbf
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 77%

---

# Impostare gli utenti direzionali per l’utilizzo delle dashboard

In alcuni casi, gli utenti direzionali potrebbero aver bisogno di ulteriore assistenza per accedere all’app e utilizzarla. Questa sezione offre informazioni per aiutare i curatori a fornire tale assistenza.

## Assicurarsi che gli utenti dell’app abbiano accesso ad Adobe Analytics

1. Imposta i nuovi utenti in [Admin Console di Experience Cloud](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=it).

1. Per poter condividere le scorecard, devi concedere agli utenti dell’app le autorizzazioni di accesso ai componenti delle scorecard come Analysis Workspace, alle visualizzazioni dati su cui si basano le scorecard, nonché a filtri, metriche e dimensioni.

## Prerequisiti di sistema per gli utenti dell’app

Per garantire che gli utenti direzionali possano accedere alle scorecard nell’app, assicurati che:

* Il sistema operativo per dispositivi mobili sui loro dispositivi sia iOS versione 10 o superiore o Android versione 4.4 (KitKat) o superiore.
* Hanno un accesso valido al Customer Journey Analytics.
* Le scorecard per dispositivi mobili a essi destinate siano state correttamente create e condivise.
* Abbiano accesso ai Componenti che la scorecard include. Tieni presente che quando condividi le scorecard puoi selezionare l’opzione **[!UICONTROL Share embedded components]**.

## Aiutare i dirigenti a scaricare e installare l’app

>[!NOTE]
>
>Anche se l’app mobile è denominata dashboard di Adobe Analytics nell’app store, può essere utilizzata allo stesso modo delle scorecard per dispositivi mobili di Customer Journey Analytics.

**Per gli utenti direzionali su iOS:**

Fare clic sul seguente link (è disponibile anche in Customer Journey Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (mobile opp)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

`[iOS link](https://apple.co/2zXq0aN)`

**Per gli utenti direzionali su Android:**

Fare clic sul seguente link (è disponibile anche in Customer Journey Analytics in **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (mobile app)]**) e segui le istruzioni per scaricare, installare e aprire l’app:

`[Android link](https://bit.ly/2LM38Oo)`

Una volta scaricata e installata, gli utenti esecutivi possono accedere all’app utilizzando le loro credenziali di Customer Journey Analytics esistenti; supportiamo sia gli ID Adobe che Enterprise ID e Federated ID.

![Schermata di benvenuto dell’app](assets/welcome.png)

## Aiutare i dirigenti ad accedere alla scorecard

1. Chiedi agli utenti direzionali di accedere all’app.

   Viene visualizzata la schermata **[!UICONTROL Choose a company]**. Questa schermata elenca le aziende di accesso a cui appartiene l’utente direzionale.

1. Chiedi loro di toccare il nome dell’azienda o dell’organizzazione Experience Cloud applicabile alla scorecard condivisa.

   Vengono quindi elencate tutte le scorecard che sono state condivise con l’utente direzionale per l’azienda con cui è stato eseguito l’accesso.

1. Aiutali a ordinare l’elenco in base a **[!UICONTROL Most recently modified]**, se applicabile.

1. Chiedi loro di toccare il nome della scorecard per visualizzarla.

   ![Scegliere un’azienda](assets/accesscard.png)


### Spiegare l’interfaccia utente della scorecard

Spiega all’utente direzionale come appaiono le sezioni nelle scorecard condivise.

![Spiegare le sezioni](assets/newexplain.png)

![Esempio di scorecard](assets/intro_scorecard.png)

Ulteriori informazioni sulle sezioni:

* La granularità dei grafici sparkline dipende dalla lunghezza dell’intervallo date:
* Un giorno mostra una tendenza oraria
   * Più di un giorno e meno di un anno mostra una tendenza giornaliera.
   * Un anno o più mostra una tendenza settimanale.
   * La formula della variazione percentuale del valore è metrica totale (intervallo date attuale) – metrica totale (intervallo date di confronto)/metrica totale (intervallo date di confronto).
   * È possibile trascinare lo schermo verso il basso per aggiornare la scorecard.


1. Tocca una sezione per mostrare come funziona un raggruppamento dettagliato della sezione.

   ![Vista Raggruppamento](assets/sparkline.png)

   * Tocca un punto qualsiasi di una sparkline per visualizzare i dati associati a tale punto sulla linea.

   * È inclusa una tabella per visualizzare i dati delle dimensioni aggiunte alla sezione. Tocca la freccia giù per selezionare le dimensioni. Se non è stata aggiunta alcuna dimensione alla sezione, nella tabella vengono visualizzati i dati relativi al grafico.

1. Per modificare gli intervalli di date per la scorecard, tocca l’intestazione Data e seleziona la combinazione di intervalli di date principali e di confronto che desideri visualizzare.

   ![Modificare le date](assets/changedate.png)

## Modificare le preferenze dell’app

Per modificare le preferenze, tocca l’opzione **[!UICONTROL Preferences]** mostrata sopra. Nelle preferenze, puoi attivare l’accesso biometrico oppure la modalità scura dell’app come illustrato di seguito:

![Modalità scura](assets/darkmode.png)

## Risoluzione dei problemi

Se l’utente direzionale effettua l’accesso e vede un messaggio che dice che non è stato condiviso nulla:

![Niente di condiviso](assets/nothing.png)

* L’utente direzionale potrebbe aver selezionato la sandbox di Customer Journey Analytics errata oppure
* la scorecard potrebbe non essere stata condivisa con l’utente direzionale.

Verifica che l’utente direzionale possa accedere alla sandbox di Customer Journey Analytics corretta e che la scorecard sia stata condivisa.
