---
description: Gestisci esportazioni esistenti
keywords: Analysis Workspace
title: Gestione esportazioni
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
source-git-commit: 05cc65f3a463bc71db85d85292a172784c3d7c75
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 3%

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
   | [!UICONTROL **Tipo di account**] | Il tipo di account a cui è associata l’esportazione. Sono disponibili i seguenti tipi di account: <ul><li>[!UICONTROL **Area di destinazione dati AEP**]</li><li>[!UICONTROL **ARN per ruolo Amazon S3**]</li><li>[!UICONTROL **SAS di Azure**]</li><li>[!UICONTROL **RBAC di Azure**]</li><li>[!UICONTROL **Piattaforma Google Cloud**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Stato**] | Stato dell’esportazione. Sono disponibili i seguenti stati: <ul><li>[!UICONTROL **Attivo**]: indica che un’esportazione pianificata non è ancora scaduta o che un’esportazione una tantum non è ancora stata completata. </li><li>[!UICONTROL **Completa**]: indica che un’esportazione è stata esportata correttamente. Per le esportazioni programmate, ciò indica che la pianificazione è scaduta.</li><li>[!UICONTROL **Non riuscito**]<p>Le situazioni seguenti possono causare un’esportazione non riuscita. Passa il puntatore del mouse sopra [!UICONTROL **Non riuscito**] stato per visualizzare i dettagli sull’errore. <ul><li>Scadenza esportazione pianificata</li><li>Limite di righe raggiunto per l’esportazione pianificata </li></ul> </p></li></ul> |
   | [!UICONTROL **Frequenza**] | La frequenza con cui si verifica l’esportazione. Sono disponibili le seguenti frequenze: <ul><li>[!UICONTROL **Una volta**]</li><li>[!UICONTROL **Giornaliero**]</li><li>[!UICONTROL **Settimanale**]</li><li>[!UICONTROL **Mensile**]</li><li>[!UICONTROL **Annuale**]</li></ul> |

   {style="table-layout:auto"}

### Cerca esportazioni

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Seleziona la [!UICONTROL **Esportazioni**] scheda.

1. Nel campo di ricerca, inizia a digitare tutte le informazioni associate all’esportazione che stai cercando. Puoi cercare dati da qualsiasi colonna disponibile nella tabella.

## Modificare un’esportazione

Puoi modificare le proprietà, il formato, la pianificazione e le informazioni sulla posizione di un’esportazione.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , seleziona la casella di controllo accanto all’esportazione da modificare.

   Questa opzione non è disponibile quando si selezionano più esportazioni.

1. Seleziona [!UICONTROL **Modifica**].

   Il [!UICONTROL **Esporta tabella completa**] viene visualizzata una finestra di dialogo.

1. Aggiorna una qualsiasi delle opzioni disponibili. Per informazioni su ciascuna opzione, consulta [Esportare tabelle complete da Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) in [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md).

## Duplicare un’esportazione

Puoi duplicare un’esportazione esistente.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , selezionare la casella di controllo accanto all&#39;esportazione da duplicare.

   Questa opzione non è disponibile quando si selezionano più esportazioni.

1. Seleziona [!UICONTROL **Duplica**].

   Viene creato un duplicato dell’esportazione. Il nome della nuova esportazione corrisponde al nome dell’esportazione originale, con _[!UICONTROL - Copy]_aggiunta al nome del file.

1. (Facoltativo) [Modifica la nuova esportazione](#edit-an-export), incluso il nome del file e tutte le altre proprietà che desideri modificare.

## Avviare manualmente un’esportazione

Puoi avviare manualmente un’esportazione per un’esportazione pianificata o una esportazione una tantum precedentemente completata.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , selezionare la casella di controllo accanto all&#39;esportazione da eseguire.

   Questa opzione non è disponibile quando si selezionano più esportazioni.

1. Seleziona [!UICONTROL **Esporta ora**].

## Assegnare tag a un’esportazione

Quando applichi i tag a un’esportazione, puoi visualizzarli nella sezione [!UICONTROL Tags] colonna sulla [!UICONTROL Exports] pagina. Consulta [Configurare le colonne](#configure-columns) per ulteriori informazioni.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , seleziona la casella di controllo accanto a una o più esportazioni a cui desideri assegnare il tag.

1. Seleziona [!UICONTROL **Modifica tag**].

1. In [!UICONTROL **Esportazione tag**] digitare il nome di un tag per creare un nuovo tag oppure scegliere un tag esistente dal menu a discesa.

   Eventuali tag comuni tra le esportazioni selezionate vengono visualizzati nella finestra di dialogo dei tag. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Seleziona [!UICONTROL **Applicare i tag**].

## Eliminare un’esportazione

Puoi eliminare le esportazioni dalla pagina Esportazioni. Le esportazioni pianificate che vengono eliminate non verranno più inviate.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , selezionare la casella di controllo accanto a una o più esportazioni che si desidera eliminare.

1. Seleziona [!UICONTROL **Elimina**], quindi seleziona [!UICONTROL **Elimina**] quando viene visualizzato il messaggio di conferma.

## Configurare le colonne in [!UICONTROL Exports] pagina

È possibile aggiungere o rimuovere colonne nel [!UICONTROL Exports] per configurare le informazioni visualizzate.

Seleziona un’intestazione di colonna per ordinare le esportazioni in base a tale colonna. Per impostazione predefinita, le esportazioni vengono ordinate in base alla data e all’ora dell’ultima modifica.

1. In Customer Journey Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Esportazioni**].

1. Il giorno [!UICONTROL **Esportazioni**] , seleziona la scheda **Personalizza tabella** icona ![personalizza tabella](assets/customize-table-icon.png) in alto a destra nella [!UICONTROL Exports] pagina.

   Sono disponibili le seguenti colonne:

   | Colonna disponibile | Descrizione |
   |---------|----------|
   | Nome | Nome dell’esportazione. Gli utenti assegnano un nome alle esportazioni quando le creano, come descritto in [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md). |
   | ID | L’ID assegnato automaticamente all’esportazione al momento della creazione. <!-- True? --> |
   | Nome delle visualizzazioni dati | Nome della visualizzazione dati associata all’esportazione. Gli utenti possono selezionare la visualizzazione dati al momento della creazione dell’esportazione, come descritto in [Esportare i rapporti di Customer Journey Analytics nel cloud](/help/analysis-workspace/export/export-cloud.md). |
   | Stato | Stato dell’esportazione. Gli stati disponibili sono [!UICONTROL Active], [!UICONTROL Complete], e [!UICONTROL Failed].<p> **Nota:** Per informazioni sulla risoluzione dei problemi relativi alle esportazioni non riuscite, vedere [Risoluzione dei problemi di esportazione non riuscita](/help/components/exports/troubleshoot-exports.md).</p> |
   | Tag | Visualizza tutti i tag applicati all&#39;esportazione. Per informazioni su come applicare i tag a un’esportazione, consulta [Assegnare tag a un’esportazione](#tag-an-export). |
   | Dimensione tabella (ultimo invio) | Dimensione dell&#39;esportazione l&#39;ultima volta che è stata inviata. |
   | Creato da | Utente che ha creato l’esportazione. |
   | Creato | La data e l’ora in cui è stata creata l’esportazione. <!-- true? --> |
   | Posizione | Posizione dell&#39;account in cui sono stati esportati i dati. |
   | Account | Account in cui sono stati esportati i dati. |
   | Frequenza | La frequenza con cui viene inviata l’esportazione. Le opzioni disponibili sono [!UICONTROL One time], [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly by day of the week], [!UICONTROL Monthly by day of the month], [!UICONTROL Yearly by day of the month], e [!UICONTROL Yearly by specific date]. |
   | Ora di invio | L’ora in cui è stata inviata l’esportazione. |
   | Ultimo invio | L’ultima volta che è stata inviata l’esportazione. |
   | Ultima modifica | L’ultima volta che l’esportazione è stata modificata. Per impostazione predefinita, gli elementi nella pagina Esportazioni sono ordinati in base a questa colonna. |
   | Tipo di account | Tipo di account cloud in cui sono stati esportati i dati. I tipi di account disponibili sono [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], e [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. Assicurati che tutte le colonne che desideri visualizzare siano selezionate. Le colonne selezionate vengono visualizzate nella pagina Esportazioni e le relative informazioni.
