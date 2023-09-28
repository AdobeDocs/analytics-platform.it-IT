---
description: Gestisci esportazioni esistenti
keywords: Analysis Workspace
title: Gestione esportazioni
feature: Components
hide: true
hidefromtoc: true
source-git-commit: a95be4cf8e11b7b62f6777abe8884779cfebf482
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 4%

---

# Gestione esportazioni

Dopo aver esportato una tabella completa come descritto in [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md), le esportazioni sono disponibili sul [!UICONTROL Exports] scheda della [!UICONTROL Exports] pagina.

Puoi visualizzare solo le esportazioni create.

## Filtrare e cercare le esportazioni

Per trovare le informazioni necessarie, puoi filtrare l’elenco delle esportazioni o cercare un’esportazione.

### Filtrare l’elenco delle esportazioni

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Esportazioni**] scheda.

1. Seleziona la **Filtro** icona.

   <!--add screenshot -->

   Puoi filtrare in base ai seguenti criteri:

   | Filtro | Descrizione |
   |---------|----------|
   | [!UICONTROL **Tipo di account**] | Il tipo di account a cui è associata l’esportazione. Sono disponibili i seguenti tipi di account: <ul><li>[!UICONTROL **Area di destinazione dati Adobe Experience Platform**]</li><li>[!UICONTROL **ARN per ruolo Amazon S3**]</li><li>[!UICONTROL **Piattaforma Google Cloud**]</li><li>[!UICONTROL **SAS di Azure**]</li><li>[!UICONTROL **RBAC di Azure**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Stato**] | Stato dell’esportazione. Sono disponibili i seguenti stati: <ul><li>[!UICONTROL **Attivo**]: indica che un’esportazione pianificata non è ancora scaduta. </li><li>[!UICONTROL **Completato**]: indica che un’esportazione è stata esportata correttamente. Per le esportazioni programmate, ciò indica che la pianificazione è scaduta.</li><li>[!UICONTROL **Non riuscito**]<p>Le situazioni seguenti possono causare un’esportazione non riuscita. Passa il cursore del mouse sullo stato Non riuscito per visualizzare i dettagli dell’errore. <ul><li>Scadenza esportazione pianificata</li><li>Limite di righe raggiunto per l’esportazione pianificata </li></ul> </p></li></ul> |
   | [!UICONTROL **Frequenza**] | La frequenza con cui si verifica l’esportazione. Sono disponibili le seguenti frequenze: <ul><li>[!UICONTROL **Una volta**]</li><li>[!UICONTROL **Giornaliero**]</li><li>[!UICONTROL **Settimanale**]</li><li>[!UICONTROL **Mensile**]</li><li>[!UICONTROL **Annuale**]</li></ul> |

   {style="table-layout:auto"}

### Cerca esportazioni

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Esportazioni**] scheda.

1. Nel campo di ricerca, inizia a digitare tutte le informazioni associate all’esportazione che stai cercando. Puoi cercare dati da qualsiasi colonna disponibile nella tabella.

## Modificare un’esportazione

Puoi modificare le proprietà, il formato, la pianificazione e le informazioni sulla posizione di un’esportazione.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , selezionare l&#39;esportazione da modificare.

   Questa opzione non è disponibile quando si selezionano più esportazioni.

1. Seleziona [!UICONTROL **Modifica**].

## Duplicare un’esportazione

Puoi duplicare un’esportazione esistente.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , selezionare l&#39;esportazione da duplicare.

   Questa opzione non è disponibile quando si selezionano più esportazioni.

1. Seleziona [!UICONTROL **Duplica**].

   Viene creato un duplicato dell’esportazione. Il nome della nuova esportazione corrisponde al nome dell’esportazione originale, con _[!UICONTROL - Copy]_aggiunta al nome del file.

1. (Facoltativo) [Modifica la nuova esportazione](#edit-an-export), incluso il nome del file e tutte le altre proprietà che desideri modificare.

## Avviare manualmente un’esportazione

Puoi avviare manualmente un’esportazione per un’esportazione pianificata o una esportazione una tantum precedentemente completata.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , selezionare l&#39;esportazione da eseguire.

   Questa opzione non è disponibile quando si selezionano più esportazioni.

1. Seleziona [!UICONTROL **Esporta ora**].

## Assegnare tag a un’esportazione

Quando applichi i tag a un’esportazione, puoi visualizzarli nella sezione [!UICONTROL Tags] colonna sulla [!UICONTROL Exports] pagina. Consulta [Configurare le colonne](#configure-columns) per ulteriori informazioni.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , seleziona una o più esportazioni alle quali desideri assegnare il tag.

1. Seleziona [!UICONTROL **Tag**].

1. Nella finestra di dialogo Esportazione tag, digita il nome di un tag per creare un nuovo tag oppure scegli un tag esistente dal menu a discesa.

   Eventuali tag comuni tra le esportazioni selezionate vengono visualizzati nella finestra di dialogo dei tag. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Seleziona [!UICONTROL **Applicare i tag**].

## Eliminare un’esportazione

Puoi eliminare le esportazioni dalla pagina Esportazioni. Le esportazioni pianificate che vengono eliminate non verranno più inviate.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , selezionare una o più esportazioni da eliminare.

1. Seleziona [!UICONTROL **Elimina**], quindi seleziona [!UICONTROL **Elimina**] quando viene visualizzato il messaggio di conferma.

## Configurare le colonne in [!UICONTROL Exports] pagina

È possibile aggiungere o rimuovere colonne nel [!UICONTROL Exports] per configurare le informazioni visualizzate.

1. Seleziona la **Personalizza tabella** icona ![personalizza tabella](assets/customize-table-icon.png) in alto a destra nella [!UICONTROL Exports] pagina.

   Sono disponibili le seguenti colonne:

   | Colonna disponibile | Descrizione |
   |---------|----------|
   | Nome | Nome dell’esportazione. Gli utenti assegnano un nome alle esportazioni quando le creano, come descritto in [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md). |
   | ID | L’ID assegnato automaticamente all’esportazione al momento della creazione. <!-- True? --> |
   | Stato | Stato dell’esportazione. Gli stati disponibili sono [!UICONTROL Active], [!UICONTROL Paused], [!UICONTROL Completed], e [!UICONTROL Failed].<p> **Nota:** Per informazioni sulla risoluzione dei problemi relativi alle esportazioni non riuscite, vedere [Risoluzione dei problemi di esportazione non riuscita](/help/components/exports/troubleshoot-exports.md).</p> |
   | Nome delle visualizzazioni dati | Nome della visualizzazione dati associata all’esportazione. Gli utenti possono selezionare la visualizzazione dati al momento della creazione dell’esportazione, come descritto in [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Stato | Stato dell’esportazione. Gli stati disponibili sono [!UICONTROL Pending], [!UICONTROL Delivered], e [!UICONTROL Failed]. |
   | Dimensione tabella (ultimo invio) | Dimensione dell&#39;esportazione l&#39;ultima volta che è stata inviata. |
   | Creato da | Utente che ha creato l’esportazione. |
   | Creato | La data e l’ora in cui è stata creata l’esportazione. <!-- true? --> |
   | Posizione | Posizione dell&#39;account in cui sono stati esportati i dati. |
   | Account | Account in cui sono stati esportati i dati. |
   | Frequenza | La frequenza con cui viene inviata l’esportazione. Le opzioni disponibili sono [!UICONTROL One time], [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly by day of the week], [!UICONTROL Monthly by day of the month], [!UICONTROL Yearly by day of the month], e [!UICONTROL Yearly by specific date]. |
   | Ora di invio | L’ora in cui è stata inviata l’esportazione. |
   | Ultimo invio | L’ultima volta che è stata inviata l’esportazione. |
   | Ultima modifica | L’ultima volta che l’esportazione è stata modificata. |
   | Tipo di account | Tipo di account cloud in cui sono stati esportati i dati. I tipi di account disponibili sono [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], e [!UICONTROL Adobe Experience Platform]. |
   | Tag | Visualizza tutti i tag applicati all&#39;esportazione. Per informazioni su come applicare i tag a un’esportazione, consulta [Assegnare tag a un’esportazione](#tag-an-export). |

   {style="table-layout:auto"}

1. Assicurati che tutte le colonne che desideri visualizzare siano selezionate. Le colonne selezionate vengono visualizzate nella pagina Esportazioni e le relative informazioni.