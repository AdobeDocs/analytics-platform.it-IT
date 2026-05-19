---
description: Come configurare gli utenti per l’utilizzo dell’app mobile per dashboard di Adobe Analytics
title: Preparare il management a utilizzare le dashboard
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/78Bp5YSZg7Qs-qBnCfIoS6mjxda7CAglDG19Qq07Fw4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b743a5d9-dc51-41ed-8b2f-86a1f8de430f
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b21c7889-c659-4a99-a779-de1bae57e47e
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 14557a59902110b1768d61e621adfb3f76ee9930
workflow-type: tm+mt
source-wordcount: 720
ht-degree: 61%

---

# Impostare gli utenti direzionali per l’utilizzo delle dashboard

In alcuni casi, gli utenti direzionali potrebbero aver bisogno di ulteriore assistenza per accedere all’app e utilizzarla. Questa sezione offre informazioni per aiutare i curatori a fornire tale assistenza.

## Assicurarsi che gli utenti dell’app abbiano accesso ad Adobe Analytics

1. Configurare nuovi utenti in [CX Enterprise Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=it).

1. Per poter condividere le scorecard, devi concedere agli utenti dell’app le autorizzazioni di accesso ai componenti delle scorecard come Analysis Workspace, alle visualizzazioni dati su cui sono basate le scorecard, nonché ai segmenti, alle metriche e alle dimensioni.

## Prerequisiti di sistema per gli utenti dell’app

Per garantire che gli utenti direzionali possano accedere alle scorecard nell’app, assicurati che:

* Il sistema operativo per dispositivi mobili sui loro dispositivi sia iOS versione 10 o superiore o Android versione 4.4 (KitKat) o superiore.
* Abbiano un accesso valido a Customer Journey Analytics.
* Le scorecard per dispositivi mobili a essi destinate siano state correttamente create e condivise.
* Abbiano accesso ai Componenti che la scorecard include. Tieni presente che puoi selezionare un&#39;opzione quando condividi le scorecard per **[!UICONTROL Condividere componenti incorporati]**.

## Aiutare i dirigenti a scaricare e installare l’app

>[!NOTE]
>
>Anche se l’app mobile è denominata dashboard di Adobe Analytics nell’app store, può essere utilizzata in egual misura con le scorecard per dispositivi mobili Customer Journey Analytics.

**Per gli utenti direzionali su iOS:**

Fare clic sul seguente collegamento (disponibile anche in Customer Journey Analytics in **[!UICONTROL Strumenti]** > **[!UICONTROL Dashboard di Analytics (opp mobile)]**) e seguire le istruzioni per scaricare, installare e aprire l&#39;app:

`[iOS link](https://apple.co/2zXq0aN)`

**Per gli utenti direzionali su Android:**

Fare clic sul seguente collegamento (disponibile anche in Customer Journey Analytics in **[!UICONTROL Strumenti]** > **[!UICONTROL Dashboard di Analytics (app mobile)]**) e seguire le istruzioni per scaricare, installare e aprire l&#39;app:

`[Android link](https://bit.ly/2LM38Oo)`

Una volta scaricata e installata, gli utenti esecutivi possono accedere all’app utilizzando le loro credenziali esistenti di Customer Journey Analytics; supportiamo sia gli ID Adobe che Enterprise ID e Federated ID.

![Schermata di benvenuto dei dashboard di Adobe Analytics](assets/welcome.png)

## Aiutare i dirigenti ad accedere alla scorecard

1. Chiedi agli utenti direzionali di accedere all’app.

   Viene visualizzata la schermata **[!UICONTROL Scegli un&#39;azienda]**. Questa schermata elenca le aziende di accesso a cui appartiene l’utente direzionale.

1. Chiedi loro di toccare il nome della società di accesso o dell’organizzazione CX Enterprise applicabile alla scorecard condivisa.

   Vengono quindi elencate tutte le scorecard che sono state condivise con l’utente direzionale per l’azienda con cui è stato eseguito l’accesso.

1. Chiedi loro di ordinare l&#39;elenco in base a **[!UICONTROL Modificato più di recente]**, se applicabile.

1. Chiedi loro di toccare il nome della scorecard per visualizzarla.

   ![Scegliere un’azienda](assets/accesscard.png)


### Spiegare l’interfaccia utente della scorecard

Spiega all’utente direzionale come appaiono le sezioni nelle scorecard condivise.

![Spiega le tessere, inclusi l&#39;intervallo di date, il segmento e le metriche e dimensioni selezionate](assets/newexplain.png)

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

* L’utente direzionale potrebbe aver selezionato la sandbox di Customer Journey Analytics sbagliata oppure
* la scorecard potrebbe non essere stata condivisa con l’utente direzionale.

Verifica che l’utente manageriale possa accedere alla sandbox Customer Journey Analytics corretta e che la scorecard sia stata condivisa.
