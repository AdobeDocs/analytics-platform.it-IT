---
title: Creazione di una visualizzazione dati
description: Descrive come creare una visualizzazione dati su un dataset della piattaforma in Customer Journey Analytics (CJA).
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# Creazione di una visualizzazione dati

Una visualizzazione dati è simile a una suite di rapporti virtuale in Analytics, in quanto è in un certo senso una visualizzazione &quot;filtrata&quot; dei dati. Puoi creare diverse viste dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Potete creare più viste dati per un singolo dataset. Ad esempio, è possibile avere una visualizzazione dati in cui tutte le dimensioni sono impostate su &quot;Last Touch&quot; e, contemporaneamente, un&#39;altra visualizzazione dati (basata sullo stesso dataset) con tutte le dimensioni impostate su &quot;First Touch&quot;.

I progetti Workspace in Analisi del percorso cliente si basano sulle viste dati.

Fate clic [qui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) per una panoramica video.

## Prerequisito

Prima di poter creare le viste dati, è necessario [impostare una o più connessioni ai set di dati](/help/connections/create-connection.md)di Adobe Experience Platform.

## Configura impostazioni

1. In Analisi percorso cliente, andate alla **[!UICONTROL Data Views]** scheda.

1. Fare clic **[!UICONTROL Add]** per aggiungere una visualizzazione dati e configurarne le impostazioni.

   | Impostazione sessione | Definizione |
   |---|---|
   | Connessione | Questo campo collega la visualizzazione dati alla connessione stabilita in precedenza, che contiene i set di dati della piattaforma. |
   | Nome | È obbligatorio assegnare un nome alla visualizzazione dati. |
   | Descrizione | Una descrizione dettagliata non è obbligatoria, ma consigliata. |
   | Aggiungi tag | I tag consentono di organizzare le viste dati in categorie. |
   | Fuso orario | Scegliere il fuso orario per la visualizzazione dati. |
   | Timeout sessione | Selezionate la definizione di &quot;sessione&quot;. L’impostazione di timeout sessione definisce la quantità di inattività che un visitatore univoco deve avere prima dell’avvio automatico di una nuova sessione. Il valore predefinito è 30 minuti. Ad esempio, se impostate il timeout sessione su 45 minuti, viene creato un nuovo raggruppamento di sessioni per ciascuna sequenza di hit raccolti, separati da 45 minuti di inattività. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Avvia nuova sessione con l&#39;evento | Una nuova sessione inizia quando un evento viene attivato, a prescindere dal timeout di una sessione. La nuova sessione creata include l’evento che l’ha avviata. Inoltre, potete utilizzare più eventi per avviare una sessione e una nuova sessione viene attivata se nei dati sono osservati degli eventi. Questa impostazione influirà sul conteggio delle visite, sul contenitore dei segmenti della sessione (già Visita) e sulla logica di scadenza della visita sulle dimensioni. |
   | Aggiungi filtri | &quot;Filtri&quot; è il termine per &quot;segmenti&quot; in Analisi del percorso cliente. Per filtrare i dati, trascinate il filtro appropriato dalla barra a sinistra. Se non si seleziona un filtro, la visualizzazione dati conterrà tutti i dati. |

1. Fai clic su **[!UICONTROL Continue]**.

## Aggiungi componenti

1. Ora è il momento di aggiungere componenti (dimensioni, metriche) alla visualizzazione dati (simile all’esperienza di gestione nelle suite di rapporti virtuali). Tenere presente che ciascuno dei campi nei set di dati ora è convertito in dimensioni o metriche. Trascina dimensioni e metriche nel pannello o **[!UICONTROL Seleziona tutto** per aggiungere tutti i componenti.

   ![](assets/add-all-components.png)

1. Fai clic sulla **[!UICONTROL Add Components]** scheda per aggiungere dimensioni e metriche alla visualizzazione dati.

   ![](assets/add-all-components2.png)

1. (Facoltativo) Per rinominare un componente in un nome descrittivo o modificarne le impostazioni di attribuzione, selezionatelo e modificatene l’impostazione. Il nome sottostante viene mantenuto. Per ulteriori informazioni, consulta [Configurare le viste dati e l’attribuzione](/help/data-views/configure-dataviews.md).

1. La procedura successiva consiste nel [specificare le impostazioni](/help/data-views/configure-dataviews.md)di attribuzione e componente.