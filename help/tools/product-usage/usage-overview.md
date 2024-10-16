---
title: Panoramica sull’utilizzo del prodotto
description: Visualizzare approfondimenti e rapporti sul modo in cui l’organizzazione utilizza il Customer Journey Analytics.
hide: true
hidefromtoc: true
source-git-commit: f337dfbd780aab4ae40534c5c1151dba35681b21
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 3%

---

# Panoramica sull’utilizzo del prodotto

{{release-limited-testing}}

L’utilizzo del prodotto consente all’organizzazione di visualizzare i dati analitici sul modo in cui l’organizzazione utilizza il Customer Journey Analytics. È disponibile per tutte le organizzazioni che utilizzano Customer Journey Analytics. Una volta abilitati, i seguenti componenti Adobe Experience Platform vengono creati e collegati automaticamente:

* Uno schema in Adobe Experience Platform. Questo schema è di proprietà del sistema, è di sola lettura e non può essere modificato.
* Un set di dati in Adobe Experience Platform. Questo set di dati è di proprietà del sistema, è di sola lettura e non può essere modificato.
* Connessione nel Customer Journey Analytics. Questa connessione è di proprietà del sistema, è di sola lettura e non può essere modificata.
* Una visualizzazione dati nel Customer Journey Analytics. Puoi modificare questa visualizzazione dati o crearne altre utilizzando la connessione precedente. Il proprietario della visualizzazione dati è la persona che abilita l’utilizzo del prodotto per la tua organizzazione.

Una volta abilitata, la raccolta e l’impostazione dei dati vengono configurate automaticamente. Ogni volta che un utente esegue un’azione in Analysis Workspace, questa viene tracciata e disponibile per i rapporti.

>[!IMPORTANT]
>
>Questa funzione conta per i limiti di riga contrattuali in Adobe Experience Platform. Assicurati che la tua organizzazione possa inserire i dati generati da questa funzione prima di abilitarla.

## Dimensioni disponibili

Quando abiliti l’utilizzo del prodotto, sono disponibili le seguenti dimensioni:

| Dimensione | Descrizione |
| --- | --- |
| Nome azione | Tipo di azione eseguita dall&#39;utente. Puoi utilizzare questa dimensione come qualsiasi metrica desiderata creando una copia nelle impostazioni della visualizzazione dati. |
| Modello di attribuzione utilizzato | Tipo di modello di attribuzione utilizzato dal componente. |
| Componente | Campo derivato che include il tipo di componente e il nome del componente. |
| Tipo di componente | Il tipo di componente aggiunto, rimosso o modificato. |
| Utente di accesso | Utente che ha eseguito l&#39;azione. |
| Pannello utilizzato | Il pannello in cui il componente è stato aggiunto, rimosso o modificato. |
| Nome progetto | Nome intuitivo del progetto. |
| Tipo di progetto | Il tipo di progetto. |
| ID utente | ID utente che ha attivato l’evento. |
| Visualizzazione utilizzata | Visualizzazione aggiunta, rimossa o modificata. |

L’utilizzo del prodotto non tiene traccia dei singoli componenti del progetto quando un progetto viene semplicemente aperto o visualizzato. Tuttavia, viene tenuta traccia dell’azione dell’utente di apertura di un progetto.
