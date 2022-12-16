---
title: Stimare e gestire l’utilizzo di CJA
description: Mostra due metodi per stimare l'utilizzo e un metodo per gestirlo.
role: Admin
feature: CJA Basics
source-git-commit: 58d582b693708f883842fb6a18cc57d481f2b2ab
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 67%

---


# Stimare e gestire l’utilizzo di CJA

Per comprendere l’utilizzo di CJA, puoi utilizzare 2 metodi:

* Aggiungi i dati dell&#39;evento per ogni connessione (vedi **Stimare la dimensione della connessione** sotto)
* Usa Analysis Workspace per...

Per gestire l’utilizzo di CJA:

* Utilizzare l’API CJA

## Stimare la dimensione della connessione {#estimate-size}

Potrebbe essere necessario sapere quante righe di dati evento si dispone attualmente in [!UICONTROL Customer Journey Analytics]. Per ottenere un resoconto accurato dell’utilizzo dei record di dati evento (righe di dati) per la tua organizzazione, procedi come segue **per ciascuna delle connessioni create dall’organizzazione**.

>[!NOTE]
>
>Effettua questa operazione il primo venerdì di ogni mese, in quanto Adobe esegue il rapporto sull’utilizzo più recente in quel giorno.

1. In [!UICONTROL Customer Journey Analytics], fai clic sulla scheda **[!UICONTROL Connections]**.

   Viene visualizzato un elenco di tutte le connessioni correnti.

1. Fai clic sul nome di ciascuna connessione per accedere alla funzione di gestione delle connessioni.

1. Ottieni il totale di **[!UICONTROL Records of event data available]** per tutte le connessioni create. (A seconda delle dimensioni della connessione, la visualizzazione di questo valore potrebbe richiedere del tempo.)

   ![Dati evento](assets/event-data.png)

1. Una volta ottenuta la somma di tutte le righe di dati evento, controlla il diritto “Rows of Data” (Righe di dati) nel contratto per Customer Journey Analytics sottoscritto dalla tua azienda con Adobe.

   Si tratta del numero massimo di righe di dati autorizzato nell’ordine di vendita. Se il numero di righe di dati risultanti dal passaggio 3 è maggiore di questo valore massimo, si verifica un superamento del limite.

1. Per risolvere questa situazione, puoi scegliere tra diverse soluzioni:

   * Cambia le [impostazioni di conservazione dei dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=it#set-rolling-window-for-connection-data-retention).
   * [Elimina le connessioni non utilizzate](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#implications-of-deleting-data-components).
   * [Elimina un set di dati in AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=it#implications-of-deleting-data-components).
   * Rivolgiti al tuo Adobe Account Manager per aggiungere alla licenza ulteriore capacità.
