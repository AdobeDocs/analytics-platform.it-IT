---
title: Creare una visualizzazione dati
description: Descrive come creare una visualizzazione dati di un set di dati di Platform in Customer Journey Analytics (CJA).
translation-type: tm+mt
source-git-commit: de265170126c1a9fc1f66364a79a74ff487d0b71
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 97%

---


# Creare una visualizzazione dati

Una visualizzazione dati è simile a una suite di rapporti virtuale in Analytics, in quanto è in un certo senso una visualizzazione “filtrata” dei dati. Puoi creare diverse visualizzazioni dati per la stessa connessione, con diverse impostazioni per timeout visita, attribuzione e così via. Puoi creare più viste dati per un singolo set di dati. Ad esempio, puoi avere una visualizzazione dati in cui tutte le dimensioni sono impostate su “Ultimo contatto” e, contemporaneamente, un’altra visualizzazione dati (basata sullo stesso set di dati) con tutte le dimensioni impostate su “Primo contatto”.

I progetti Workspace in Customer Journey Analytics si basano sulle visualizzazioni dati.

Fai clic [qui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) per una panoramica video.

## Prerequisito

Prima di poter creare visualizzazioni dati, devi [impostare una o più connessioni ai set di dati di Experience Platform](/help/connections/create-connection.md).

## Configurare impostazioni

1. In Customer Journey Analytics, accedi alla scheda **[!UICONTROL Data Views]**.

1. Fai clic su **[!UICONTROL Add]** per aggiungere una visualizzazione dati e configurarne le impostazioni.

   | Impostazione sessione | Definizione |
   |---|---|
   | Connessione | Questo campo collega la visualizzazione dati alla connessione stabilita in precedenza, che contiene i set di dati di [!UICONTROL Experience Platform]. |
   | Nome | È obbligatorio assegnare un nome alla visualizzazione dati. |
   | Descrizione | Una descrizione dettagliata non è obbligatoria, ma consigliata. |
   | Aggiungi tag | I tag ti consentono di organizzare le visualizzazioni dati in categorie. |
   | Fuso orario | Scegli il fuso orario per la visualizzazione dati. |
   | Timeout sessione | Seleziona la definizione di “sessione”. L’impostazione di timeout sessione definisce la quantità di inattività che un visitatore univoco deve avere prima dell’avvio automatico di una nuova sessione. Il valore predefinito è 30 minuti. Ad esempio, se imposti il timeout sessione su 45 minuti, viene creato un nuovo raggruppamento di sessioni per ciascuna sequenza di hit raccolta, separate da 45 minuti di inattività. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Avvia nuova sessione con evento | Viene avviata una nuova sessione quando un evento viene attivato, a prescindere dal timeout di una sessione. La nuova sessione creata include l’evento che l’ha avviata. Inoltre, puoi utilizzare più eventi per avviare una sessione e una nuova sessione viene avviata se nei dati viene rilevato uno qualsiasi degli eventi. Questa impostazione influirà sul conteggio delle visite, sul contenitore dei segmenti Sessione (in precedenza Visita) e sulla logica di scadenza della visita nelle dimensioni. |
   | Aggiungi filtri | “Filtri” è il termine per “segmenti” in Customer Journey Analytics. Per filtrare i dati, trascina qui il filtro appropriato dalla barra a sinistra. Se non selezioni un filtro, la visualizzazione dati conterrà tutti i dati. |

1. Fai clic su **[!UICONTROL Continue]**.

## Aggiungere componenti

1. Ora è il momento di aggiungere componenti (dimensioni, metriche) alla visualizzazione dati (in maniera simile all’esperienza di selezione nelle suite di rapporti virtuali). Tieni presente che ciascuno dei campi nei set di dati ora è convertito in dimensioni o metriche. Trascina dimensioni e metriche nel pannello o **[!UICONTROL Select All]** per aggiungere tutti i componenti.

   ![](assets/add-all-components.png)

1. Fai clic sulla scheda **[!UICONTROL Add Components]** per aggiungere dimensioni e metriche alla visualizzazione dati.

   ![](assets/add-all-components2.png)

1. Facoltativo: puoi rinominare un componente in un nome descrittivo o modificarne le impostazioni di attribuzione selezionandolo e modificandone l’impostazione. Il nome originale viene mantenuto. Per ulteriori informazioni, consulta [Configurare le visualizzazioni dati e l’attribuzione](/help/data-views/configure-dataviews.md).

1. Il passaggio successivo consiste nello [specificare le impostazioni di attribuzioni e componenti](/help/data-views/configure-dataviews.md).