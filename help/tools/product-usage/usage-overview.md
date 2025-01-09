---
title: Panoramica sull’utilizzo del prodotto
description: Visualizzare approfondimenti e rapporti sul modo in cui l’organizzazione utilizza il Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 9e29a16fc8d2cfe9a7a2e926b5f592280b2c1c7a
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# Panoramica sull’utilizzo del prodotto

{{release-limited-testing}}

L’utilizzo del prodotto consente all’organizzazione di visualizzare i dati analitici sul modo in cui l’organizzazione utilizza il Customer Journey Analytics. È disponibile per tutte le organizzazioni che utilizzano Customer Journey Analytics. Una volta abilitati, i seguenti componenti Adobe Experience Platform vengono creati e collegati automaticamente. Questi componenti sono tutti di proprietà del sistema, sono di sola lettura e non possono essere modificati.

* Uno schema in Adobe Experience Platform
* Un set di dati in Adobe Experience Platform
* Una connessione nel Customer Journey Analytics
* Una visualizzazione dati nel Customer Journey Analytics

Una volta abilitata, la raccolta e l’impostazione dei dati vengono configurate automaticamente. Ogni volta che un utente esegue un’azione in Analysis Workspace, questa viene tracciata e disponibile per i rapporti.

>[!IMPORTANT]
>
>Questa funzione conta per i limiti di riga contrattuali in Adobe Experience Platform. Assicurati che la tua organizzazione possa inserire i dati generati da questa funzione prima di abilitarla.

## Abilita utilizzo prodotto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL Product Usage]**

Passando a questa sezione dell&#39;interfaccia nel Customer Journey Analytics, puoi passare a [Impostazioni dati](data-settings.md), dove puoi abilitare questa funzione.

## Dimensioni disponibili

Quando abiliti l’utilizzo del prodotto, sono disponibili le seguenti dimensioni. Se desideri modificare le impostazioni di dimensione, crea una copia della visualizzazione dati di proprietà del sistema e utilizza la visualizzazione dati copiata in Analysis Workspace.

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
