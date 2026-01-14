---
title: Configurare l’analisi del pubblico
description: Scopri come configurare l’analisi del pubblico
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 7926f043c9e2808a083f8947fa0882c0faa4051d
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 11%

---

# Configurare l’analisi del pubblico {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="Criterio di unione"
>abstract="I criteri di unione combinano dati di profilo da più set di dati in profili cliente unificati utilizzati per la creazione di tipi di pubblico. Se vengono visualizzati più criteri di unione e non si è sicuri di quale scegliere, selezionare &quot;Basato su tempo predefinito&quot;. In alternativa, consulta il team di dati per scoprire quali tipi di pubblico sono associati a ciascun criterio di unione."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="Sandbox"
>abstract="Seleziona la sandbox che contiene i set di dati di profilo di Experience Platform corretti. Questi set di dati devono contenere i dati del pubblico su cui desideri creare rapporti in Analysis Workspace. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="ID persona"
>abstract="Seleziona un campo dallo schema che rappresenta l’ID persona. La selezione è limitata all’elenco dei campi nello schema contrassegnati come Identità e con uno spazio dei nomi di identità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="Utilizza lo spazio dei nomi identità primaria"
>abstract="Abilita questa opzione se desideri che Customer Journey Analytics trovi l’identità in Identity Map contrassegnata con un attributo primary=true e quindi utilizzi tale identità come ID persona per quella riga. L’identità è la chiave primaria utilizzata in Experience Platform per il partizionamento. <br/>Se questa opzione viene lasciata disabilitata, selezionare uno spazio dei nomi dal campo dello spazio dei nomi Identity sottostante. Customer Journey Analytics cerca la chiave dello spazio dei nomi in Identity Map di ogni riga e utilizza l’identità in tale spazio dei nomi come ID persona per tale riga."

<!-- markdownlint-enable MD034 -->

L’analisi del pubblico consente di acquisire i dati sull’iscrizione del pubblico dai set di dati del profilo di Experience Platform in una connessione Customer Journey Analytics. I tipi di pubblico diventano disponibili come nuove dimensioni da utilizzare in Analysis Workspace. Per informazioni di panoramica più dettagliate sull&#39;analisi del pubblico, vedi [Panoramica dell&#39;analisi del pubblico](/help/connections/audience-analysis/audience-analysis-overview.md).

>[!IMPORTANT]
>
>I dati sul pubblico vengono rielaborati e generati ogni notte, rendendo i dati sul pubblico precisi per l’analisi solo per il giorno precedente (&quot;ieri&quot;).
>
>I tipi di pubblico sono disponibili nelle visualizzazioni dati di Customer Journey Analytics il giorno successivo alla creazione della configurazione di analisi del pubblico.

## Creare una configurazione di analisi del pubblico

Durante la creazione di una configurazione di analisi del pubblico, seleziona la sandbox e il criterio di unione associati ai tipi di pubblico di Experience Platform che desideri analizzare. Customer Journey Analytics crea un nuovo set di dati di ricerca, quindi aggiunge automaticamente il set di dati di ricerca e il set di dati del profilo alla connessione scelta.

Solo gli amministratori di sistema possono creare configurazioni di analisi del pubblico.

Per creare una configurazione di analisi del pubblico:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Configurazione analisi pubblico]**.

   ![Pagina principale analisi del pubblico](assets/audience-analysis-empty.png)

1. Selezionare **[!UICONTROL Crea configurazione]**.

   ![Crea configurazione analisi del pubblico](assets/audience-analysis-create.png)

1. Nella sezione **[!UICONTROL Dettagli]**, specifica le seguenti informazioni:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL Nome]** | Specifica un nome per la configurazione. |
   | **[!UICONTROL Sandbox]** | Seleziona la sandbox di Experience Platform che contiene il set di dati profilo da aggiungere alla connessione. Una singola sandbox può supportare fino a 100 configurazioni di analisi del pubblico. <p>Adobe Experience Platform fornisce [sandbox](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/home) che permettono di suddividere una singola istanza Platform in ambienti virtuali separati, utili per le attività di sviluppo e aggiornamento delle applicazioni di esperienza digitale. Puoi considerare le sandbox come “silos di dati” che contengono set di dati. Le sandbox vengono utilizzate per controllare l’accesso ai set di dati.</p> |

1. Nella sezione **[!UICONTROL Set di dati profilo]**, specifica le seguenti informazioni:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL Criterio di unione]** | Seleziona il criterio di unione che corrisponde al set di dati del profilo da utilizzare per l’analisi del pubblico. <p>I criteri di unione determinano il modo in cui Adobe Experience Platform combina i dati di profilo da più set di dati in profili cliente unificati utilizzati per la creazione di tipi di pubblico. Il criterio di unione selezionato influisce sugli attributi del profilo inclusi nei tipi di pubblico. Ogni giorno in Experience Platform viene generata un’istantanea di questi dati. Questa istantanea fornisce una visualizzazione statica dei dati in un momento specifico e non include dati di eventi.</p><p>Selezionare il criterio di unione **[!UICONTROL Basato su tempo predefinito]** se sono presenti più criteri di unione e non si è sicuri di quale scegliere. Puoi anche consultare il team di dati per capire meglio quali tipi di pubblico sono associati a ciascun criterio di unione.</p> |
   | **[!UICONTROL Set di dati profilo]** | Set di dati profilo associato al criterio di unione selezionato. Questo set di dati profilo include i dati del pubblico di Experience Platform che desideri analizzare. Questo set di dati profilo viene aggiunto alla connessione selezionata.<p>Dopo aver scelto un criterio di unione, viene visualizzata l’esportazione dello snapshot del profilo. Ad esempio: `Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`.</p><p>Per ulteriori informazioni, consulta [Set di dati di attributi di profilo](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets) nella Guida dei dashboard di Experience Platform.</p> |

1. Nella sezione **[!UICONTROL Connessione]** fare clic su **[!UICONTROL Seleziona una connessione]**.

1. Nella finestra di dialogo Connessioni, seleziona la casella di controllo accanto alla connessione in cui desideri aggiungere il set di dati del profilo, quindi seleziona **[!UICONTROL Usa connessione]**.

   Una connessione può essere associata a una sola configurazione di analisi del pubblico.

1. Specificare le informazioni seguenti per configurare la connessione:

   | Campo | Descrizione |
   |---------|----------|
   | **[!UICONTROL ID persona]** | Seleziona un campo dallo schema che rappresenta l’ID persona.<p>La selezione è limitata all’elenco dei campi nello schema contrassegnati come Identità e che hanno uno spazio dei nomi di identità. **[!UICONTROL IdentityMap]** è selezionato per impostazione predefinita ed è appropriato per la maggior parte delle configurazioni. </p><p>Se non è presente alcun ID persona tra cui scegliere, significa che uno o più ID persona non sono stati definiti nello schema. Per ulteriori informazioni, consulta [Definire i campi di identità nell’interfaccia utente](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/ui/fields/identity).</p> |
   | **[!UICONTROL Usa spazio dei nomi identità primaria]** | Questa opzione mostra se hai selezionato **[!UICONTROL Mappa identità]** per l&#39;ID persona. <p>Abilita questa opzione se desideri che Customer Journey Analytics trovi l’identità in Identity Map contrassegnata con un attributo primary=true e quindi utilizzi tale identità come ID persona per quella riga. L’identità è la chiave primaria utilizzata in Experience Platform per il partizionamento. E questa identità è anche il candidato principale per l’utilizzo come ID persona Customer Journey Analytics (a seconda di come il set di dati è configurato in una connessione Customer Journey Analytics).</p> |
   | **[!UICONTROL Spazio dei nomi identità]** | Questa opzione mostra se hai selezionato **[!UICONTROL Mappa identità]** per l&#39;ID persona. Questa opzione è disabilitata se utilizzi lo spazio dei nomi dell’ID primario. <p>Gli spazi dei nomi delle identità sono un componente del [servizio Identity di Experience Platform](https://experienceleague.adobe.com/it/docs/experience-platform/identity/features/namespaces). Gli spazi dei nomi fungono da indicatori del contesto a cui si riferisce un’identità. Se specifichi uno spazio dei nomi, Customer Journey Analytics cerca la chiave dello spazio dei nomi in Identity Map di ogni riga e utilizza l’identità in tale spazio dei nomi come ID persona per tale riga. Poiché Customer Journey Analytics non è in grado di eseguire una scansione completa del set di dati di tutte le righe per determinare quali spazi di nomi sono presenti, nel menu a discesa vengono visualizzati tutti i possibili spazi di nomi. È necessario sapere quali spazi dei nomi sono specificati nei dati; questi spazi dei nomi non vengono rilevati automaticamente.</p> |
   | **[!UICONTROL ID account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | (visualizzato solo per le connessioni basate sull’account) L’ID account utilizzato per supportare la generazione di rapporti basati sull’account per il set di dati. |

1. Nella sezione **[!UICONTROL Visualizzazioni dati]**, fai clic su **[!UICONTROL Seleziona visualizzazioni dati]**.

1. Nella finestra di dialogo Visualizzazioni dati, seleziona la casella di controllo accanto a una o più visualizzazioni dati che desideri utilizzare durante l’analisi dei dati del pubblico di Experience Platform all’interno di Analysis Workspace. Queste visualizzazioni dati vengono configurate automaticamente con i dati del pubblico di Experience Platform a scopo di reporting.

1. Selezionare **[!UICONTROL Usa visualizzazioni dati]**.

1. Seleziona **[!UICONTROL Crea]** per creare la configurazione.

   >[!IMPORTANT]
   >
   >Poiché il set di dati del profilo viene aggiornato una volta al giorno, i tipi di pubblico sono disponibili nelle visualizzazioni dati di Customer Journey Analytics il giorno successivo alla creazione della configurazione di analisi del pubblico.


1. Dopo 24 ore, [visualizza le dimensioni del pubblico nella visualizzazione dati](#view-audience-dimensions-in-the-data-view) per verificare che le dimensioni del pubblico siano disponibili nelle visualizzazioni dati selezionate.

## Visualizzare le dimensioni del pubblico nella visualizzazione dati

Dopo aver [creato una configurazione di analisi del pubblico](#create-an-audience-analysis-configuration), puoi verificare che le dimensioni del pubblico siano state aggiunte alle visualizzazioni dati selezionate durante la configurazione.

Per visualizzare le dimensioni del pubblico nella visualizzazione dati, devi essere un amministratore del profilo di prodotto per il profilo di prodotto a cui è assegnata la visualizzazione dati. Per ulteriori informazioni, vedere [Controllo degli accessi](/help/technotes/access-control.md).

Per visualizzare le dimensioni di analisi del pubblico nella visualizzazione dati:

1. In Customer Journey Analytics, seleziona **[!UICONTROL Gestione dati]** > **[!UICONTROL Visualizzazioni dati]**.

1. Nella sezione **[!UICONTROL Dimensions]** (Dimensioni), ora dovrebbero essere disponibili le seguenti dimensioni:

   * **[!UICONTROL Nome pubblico]**

   * **[!UICONTROL Origine pubblico]**

   * **[!UICONTROL Uscita da Audience Origin]**

   * **[!UICONTROL Nome Pubblico Uscito]**

   Ognuna di queste dimensioni è stata aggiunta al set di dati del profilo associato al criterio di unione selezionato durante la configurazione dell’analisi del pubblico e ogni dimensione è stata aggiunta al nuovo set di dati di ricerca creato.

   ![Dimensioni pubblico disponibili nella visualizzazione dati](assets/audience-analysis-dataview-dataset.png)

1. Utilizza le dimensioni di analisi del pubblico in Analysis Workspace.

   Gli utenti che hanno accesso all’utilizzo della visualizzazione dati in Analysis Workspace ora possono vedere le nuove dimensioni e utilizzarle nelle loro analisi. Per informazioni su come utilizzare le dimensioni di analisi del pubblico in Analysis Workspace, consulta [Analizzare i tipi di pubblico di Experience Platform in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).


