---
title: Scegli il percorso di aggiornamento Customer Journey Analytics
description: Scopri i vantaggi e gli svantaggi dei possibili percorsi di aggiornamento durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '2975'
ht-degree: 51%

---

# Passaggio 2: scegliere il percorso di aggiornamento

+++Espandi questa sezione per vedere dove le informazioni su questa pagina si inseriscono nel processo di aggiornamento più ampio. Assicurati che tutti i passaggi precedenti dell’aggiornamento siano stati completati.

Prima di continuare con questa sezione, assicurati di aver completato tutte le attività di aggiornamento precedenti.

Le informazioni contenute in questa pagina descrivono il passaggio 2 del processo di aggiornamento, come evidenziato nella tabella seguente:

| Attività di aggiornamento | Dettagli |
|---------|----------|
| **Passaggio 1: [Introduzione all&#39;aggiornamento](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Scopri i vantaggi dell’aggiornamento a Customer Journey Analytics e il processo di aggiornamento di base. |
| <span class="preview">**Passaggio 2: scegliere il percorso di aggiornamento**</span> | <span class="preview">Sono disponibili diversi metodi per l&#39;aggiornamento a Customer Journey Analytics. Scegli il metodo migliore per l’organizzazione, in base all’ambiente Adobe Analytics corrente e agli obiettivi a lungo termine.</span> |
| **Passaggio 3: [Invia i dati ad Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Il processo di invio dei dati a Adobe Experience Platform varia a seconda del percorso di aggiornamento scelto nel passaggio 2. |
| **Passaggio 4: [Conserva i dati storici](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La maggior parte delle organizzazioni deve conservare i dati storici di Adobe Analytics per un certo periodo di tempo. Sono disponibili varie opzioni per eseguire questa operazione. |
| **Passaggio 5: [Esegui ulteriori attività di implementazione](/help/getting-started/cja-getting-started.md)** | A questo punto del processo di aggiornamento, è necessario eseguire varie attività prima che l’ambiente Customer Journey Analytics sia pronto per l’uso.<p>Queste attività aggiuntive riguardano gli aggiornamenti da Adobe Analytics e le nuove implementazioni Customer Journey Analytics.</p><p>Queste attività includono:</p><ul><li>Inserimento di altri dati in Experience Platform</li><li>Creazione di connessioni tra set di dati di Platform e Customer Journey Analytics</li><li>Creazione di visualizzazioni dati</li><li>Conversione dell’utilizzo dell’API di reporting</li><li>Contabilità per feed di dati e Data Warehouse</li><li>Migrazione di progetti e componenti</li><li>Pianificazione dell’onboarding degli utenti</li></ul> <p>Per ulteriori informazioni, consulta [Guida introduttiva a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Le informazioni contenute in questa pagina verranno sostituite dalle seguenti informazioni di aggiornamento più complete: <ul><li>**Passaggi di aggiornamento consigliati**<p>Per informazioni dettagliate, vedere [Percorso consigliato durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guida all&#39;aggiornamento di Customer Journey Analytics**<p>È disponibile una nuova guida all’aggiornamento che genera in modo dinamico passaggi di aggiornamento personalizzati per la tua organizzazione e le tue circostanze specifiche.</p><p>Per accedere alla guida da Customer Journey Analytics, seleziona la scheda **[!UICONTROL Workspace]**, quindi seleziona **[!UICONTROL Upgrade to Customer Journey Analytics]** nel pannello a sinistra. Seguire le istruzioni visualizzate.</p></li></ul>


Dopo aver deciso di effettuare l’aggiornamento a Customer Journey Analytics, devi determinare il percorso di aggiornamento ottimale per la tua organizzazione.

Il percorso scelto per l’aggiornamento da Adobe Analytics a Customer Journey Analytics dipende dai seguenti fattori:

* L’implementazione di Adobe Analytics esistente

* Gli obiettivi per il futuro

Utilizza le informazioni in questa pagina per determinare quale percorso di aggiornamento di Customer Journey Analytics si allinea meglio con l’implementazione corrente e gli obiettivi futuri della tua organizzazione.

Per determinare il percorso di aggiornamento ottimale per l’organizzazione, le sezioni seguenti devono essere lette in sequenza:

1. In primo luogo, [comprendere i percorsi di aggiornamento disponibili](#understand-upgrade-paths).

1. Quindi, [valuta quali percorsi di aggiornamento sono disponibili](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Infine, [valutano i vantaggi e gli svantaggi di ogni percorso di aggiornamento](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you).

## Informazioni sui percorsi di aggiornamento

Esistono diversi percorsi di aggiornamento per l’aggiornamento da Adobe Analytics a Customer Journey Analytics.

In generale, ogni percorso di aggiornamento varia in base al livello di impegno richiesto per eseguire l’aggiornamento, nonché in base alla redditività a lungo termine raggiunta al termine dell’aggiornamento.

Nella tabella seguente sono elencati i percorsi di aggiornamento, il livello di impegno e la redditività a lungo termine:

| Percorso di aggiornamento | Livello di impegno | Redditività a lungo termine |
|---------|----------|---------|
| **Nuova implementazione di Experience Platform Web SDK con il connettore di origine di Analytics**</br>&#x200B;È possibile iniziare a utilizzare Customer Journey Analytics eseguendo una nuova implementazione di Experience Platform Web SDK. Questo ti consente di iniziare a inviare dati a Adobe Experience Platform Edge Network e Customer Journey Analytics. Inoltre, utilizza il connettore di origine di Analytics per inserire dati storici in Customer Journey Analytics.<p>Per le organizzazioni non ancora presenti sul Web SDK, questo percorso di aggiornamento è forse il più semplice per ottenere dati da Edge Network perché richiede il minor numero di passaggi; tuttavia, poiché tutto il lavoro è svolto in anticipo (ad esempio la creazione dello schema XDM), richiede uno sforzo iniziale maggiore.</p><p>I passaggi di base sono:</p><ol><li>Creare uno schema XDM per l’organizzazione.</li><li>Implementare Web SDK.</li><li>Inviare i dati a Platform.</li><li>Configura il connettore di origine di Analytics.</br>Il connettore di origine di Analytics viene utilizzato per inserire dati storici di Adobe Analytics in Customer Journey Analytics.<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | Alto | Alto |
| **Nuova implementazione di Experience Platform Web SDK**</br>&#x200B;È possibile iniziare a utilizzare Customer Journey Analytics eseguendo una nuova implementazione di Experience Platform Web SDK. Questo consente di iniziare a inviare dati ad Adobe Experience Platform Edge Network e Customer Journey Analytics. <p>Per le organizzazioni non ancora presenti sul Web SDK, questo percorso di aggiornamento è forse il più semplice per ottenere dati da Edge Network perché richiede il minor numero di passaggi; tuttavia, poiché tutto il lavoro è svolto in anticipo (ad esempio la creazione dello schema XDM), richiede uno sforzo iniziale maggiore.</p><p>I passaggi di base sono:</p><ol><li>Creare uno schema XDM per l’organizzazione.</li><li>Implementare Web SDK.</li><li>Inviare i dati a Platform.</li></ol> | Alto | Alto |
| **Migrare l’implementazione di Adobe Analytics per utilizzare Web SDK**</br> Se l’implementazione di Adobe Analytics è AppMeasurement o l’estensione Analytics, puoi migrarla per utilizzare Adobe Experience Platform Web SDK per iniziare a inviare dati ad Edge Network e Adobe Analytics, prima di inviarli a Customer Journey Analytics.<p>Per le organizzazioni che non utilizzano ancora Web SDK, questo è il modo più semplice e fluido per ottenere i dati su Edge Network; ciò richiede più passaggi, ma offre una transizione più metodica da Adobe Analytics a Customer Journey Analytics, con fasi più tangibili.</p><p>I passaggi di base sono:</p><ol><li>Sposta l’implementazione Adobe Analytics esistente in Web SDK e verifica che tutto funzioni in Adobe Analytics.</li><li>Crea uno schema XDM per l’organizzazione non appena hai tempo.</li><li>Utilizza la mappatura dello stream di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.</li><li>Inviare i dati a Platform.</li></ol> | Moderare | Alto |
| **Configura l&#39;implementazione di Adobe Analytics Web SDK esistente**</br> Se l&#39;implementazione di Adobe Analytics utilizza già Adobe Experience Platform Web SDK, puoi iniziare a inviare dati a Platform configurando uno stream di dati. Oppure, se invii già dati a Platform, devi semplicemente creare una connessione tra i set di dati di Platform e Customer Journey Analytics.<p>Prima di inviare i dati a Platform per l’utilizzo in Customer Journey Analytics, è consigliabile aggiornare lo schema Adobe Analytics in base alle esigenze specifiche dell’organizzazione e di qualsiasi altra applicazione Platform utilizzata.</p><p>I passaggi di base sono:</p><ol><li>Inizia a inviare dati a Platform.<p>Se invii già dati a Platform con la tua implementazione di Adobe Analytics, questo passaggio non è necessario. È sufficiente creare una connessione tra i set di dati di Platform e Customer Journey Analytics, come descritto più avanti in questo processo.</p></li><li>(Facoltativo) Crea uno schema XDM per l’organizzazione non appena hai tempo.</li><li>(Condizionale) Se hai creato uno schema XDM, utilizza la mappatura dello stream di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.</li></ol> | Basso | Alto |
| **Utilizzare il connettore di origine di Analytics**</br> Se l’implementazione di Adobe Analytics è AppMeasurement o l’estensione Analytics, puoi iniziare a inviare dati a una visualizzazione dati in Customer Journey Analytics.<p>Questo è il modo più semplice per ottenere i dati in Customer Journey Analytics, ma è il metodo meno sostenibile a lungo termine.</p> <p>**Nota:** questo percorso di aggiornamento può essere utilizzato in modo indipendente. Tuttavia, per ottenere risultati ottimali, è consigliabile utilizzare questo percorso di aggiornamento insieme a una nuova implementazione di Experience Platform WebSDK. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | Basso | Basso |

{style="table-layout:auto"}

Utilizza il diagramma seguente per visualizzare in che modo ogni percorso di aggiornamento rientra nello spettro in termini di livello di sforzo e redditività a lungo termine:

![percorsi di aggiornamento cja](assets/cja-upgrade-path-chart.png)

## Valuta i percorsi di aggiornamento disponibili in base all’implementazione Adobe Analytics corrente

Non tutti i percorsi di aggiornamento sono disponibili per ciascun tipo di implementazione di Adobe Analytics.

Utilizza le informazioni seguenti per capire quale percorso di aggiornamento è più appropriato per la tua organizzazione.

Se hai bisogno di consigli, indicazioni o supporto più specifici, contatta il rappresentante Adobe.

| Implementazione esistente di Adobe Analytics | Percorsi di aggiornamento disponibili |
|---------|----------|
| AppMeasurement | <ul><li>Nuova implementazione di Experience Platform Web SDK</li><li>Migrare da Adobe Analytics a Web SDK</li><li>Connettore di origine di Analytics</li><li>(Consigliata) Nuova implementazione di Experience Platform Web SDK con il connettore Source di Analytics</li></ul> |
| Estensione Adobe Analytics | <ul><li>Nuova implementazione di Experience Platform Web SDK</li><li>Migrare da Adobe Analytics a Web SDK</li><li>Connettore di origine di Analytics</li><li>(Consigliata) Nuova implementazione di Experience Platform Web SDK con il connettore Source di Analytics</li></ul> |
| Web SDK | <ul><li>Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform</li><li>(Consigliata) Nuova implementazione di Experience Platform Web SDK con il connettore Source di Analytics</li></ul> |

{style="table-layout:auto"}

## Valuta i vantaggi e gli svantaggi dei percorsi di aggiornamento disponibili

I vantaggi e gli svantaggi di un determinato percorso di aggiornamento dipendono dall’implementazione di Adobe Analytics esistente.

Prima di utilizzare le informazioni riportate di seguito per determinare il percorso di aggiornamento corretto, esaminare le informazioni in [Comprendere i percorsi di aggiornamento](#understand-migration-methods), se non lo si è già fatto.

>[!NOTE]
>
>Anche se ciascuno dei percorsi di aggiornamento descritti nelle sezioni seguenti può essere utilizzato in modo indipendente, Adobe consiglia un approccio di aggiornamento su due livelli durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics, indipendentemente dall&#39;implementazione corrente di Adobe Analytics: **il connettore di origine di Adobe Analytics** e una **nuova implementazione di Experience Platform WebSDK**.
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### Per le implementazioni di Adobe Analytics che utilizzano: l’estensione AppMeasurement e Adobe Analytics

Di seguito sono riportati i percorsi di aggiornamento disponibili per le organizzazioni che hanno implementato Adobe Analytics con AppMeasurement o l’estensione Adobe Analytics. Espandere ogni sezione per visualizzare i vantaggi e gli svantaggi di ogni percorso di aggiornamento.

#### Percorsi di aggiornamento

+++Nuova implementazione di Experience Platform Web SDK

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)</li></ul></li><li>**All’avanguardia**: gli aggiornamenti futuri dell’implementazione sono più facili.</li></ul> | <ul><li>**Richiede una nuova implementazione da zero**: la necessità di eseguire una nuova implementazione da zero comporta i seguenti svantaggi: </li><ul><li>**Tempo impiegato**: questo è il percorso di aggiornamento più lungo e impegnativo, in quanto richiede una nuova implementazione.</li><li>**È necessario ricreare lo schema completo in XDM**: prima di poter iniziare a implementare Web SDK, è necessario ricreare lo schema completo in XDM.</li><li>**È necessario ricreare le regole e gli elementi di dati**: prima di poter iniziare a implementare Web SDK, devi ricreare le condizioni delle regole e gli elementi di dati dall’implementazione di Adobe Analytics.</li></ul><li>**Non tiene conto della conservazione dei dati storici:** Adobe consiglia di utilizzare il connettore di origine di Analytics insieme a una nuova implementazione di Experience Platform Web SDK per conservare i dati storici dopo l&#39;aggiornamento a Customer Journey Analytics. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**Non tiene conto del confronto dei dati dell&#39;implementazione originale con quelli della nuova implementazione:** Adobe consiglia di utilizzare il connettore di origine di Analytics insieme a una nuova implementazione di Experience Platform Web SDK per confrontare i dati dopo l&#39;aggiornamento a Customer Journey Analytics. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

   Migrare Adobe Analytics a Experience Platform Web SDK

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)</li></ul><li>**Utilizza l’implementazione esistente**: sebbene questo approccio richieda alcune modifiche all’implementazione, non richiede un’implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti apportando modifiche minime alla logica di implementazione senza influire sulla reportistica di Adobe Analytics esistente.</li><li>**Fornisce la flessibilità necessaria per creare uno schema XDM per l’organizzazione in un secondo momento**: puoi eseguire la migrazione dell’implementazione esistente di Adobe Analytics per utilizzare Web SDK e verificare che tutto funzioni in Adobe Analytics, quindi creare lo schema XDM. Questa flessibilità consente un aggiornamento più metodico e attento a Customer Journey Analytics.</li></ul> | <ul><li>**Richiede la mappatura per inviare i dati a Platform**: quando l’organizzazione è pronta per utilizzare Customer Journey Analytics, devi inviare i dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell’oggetto dati sia una voce nello strumento di mappatura del flusso di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita solo una volta per questo flusso di lavoro e non implica l’apportazione di modifiche all’implementazione. Tuttavia, si tratta di un passaggio aggiuntivo non richiesto quando si inviano dati in un oggetto XDM.</li><li>**Debito tecnico**: poiché questo approccio utilizza una forma modificata dell’implementazione esistente, può essere più difficile tenere traccia della logica di implementazione ed eseguire modifiche in futuro quando necessario. </li></ul> |

{style="table-layout:auto"}

+++

+++Utilizzare il connettore di origine di Analytics

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>Percorso di aggiornamento meno lungo e impegnativo. <p>La migrazione dei dati a Customer Journey Analytics avviene rapidamente con un investimento minimo</p></li></ul> | <ul><li>**I dati non vengono inviati a Edge Network**: <p>Ciò comporta i seguenti svantaggi:</p><ul><li>Livello massimo di [latenza](/help/technotes/guardrails.md#latencies) nel reporting per tutti i percorsi di aggiornamento; non ottimizzato per i casi di utilizzo di personalizzazione in tempo reale.</li><li>I dati non possono essere condivisi con altre applicazioni Adobe Experience Platform; è limitato solo a Customer Journey Analytics</li><li>Si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento e così via)</li></ul><li>**Difficoltà di passare al Web SDK in futuro**: è probabile che si desideri accedere ai vantaggi offerti da Experience Platform Web SDK. Per iniziare a utilizzare Experience Platform Web SDK, è necessario eseguire una nuova implementazione.</li><li>**Utilizza il gruppo di campi evento esperienza di Analytics nello schema**: questo gruppo di campi aggiunge molti eventi Adobe Analytics che non sono necessari nello schema di Customer Journey Analytics.  Ciò può portare a uno schema più disordinato e complesso di quello altrimenti necessario per Customer Journey Analytics.</li></ul><p>A causa di questi svantaggi, Adobe consiglia di utilizzare il connettore di origine di Analytics insieme a una nuova implementazione di Experience Platform Web SDK. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### Per le implementazioni di Adobe Analytics che utilizzano: Web SDK

Il seguente percorso di aggiornamento è disponibile per le organizzazioni che hanno implementato Adobe Analytics con Experience Platform Web SDK.

Quando scegli questo percorso di aggiornamento, devi anche scegliere lo schema.

#### Percorso di aggiornamento

+++Configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform

| Vantaggi | Svantaggi |
|----------|---------|
| Questo è il percorso di aggiornamento preferito se l’implementazione di Adobe Analytics utilizza già il Web SDK.<ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)</li></ul><li>**Utilizza l’implementazione esistente**: sebbene questo approccio richieda alcune modifiche all’implementazione, non richiede un’implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti apportando modifiche minime alla logica di implementazione senza influire sulla reportistica di Adobe Analytics esistente.</li><li>**Fornisce un’opzione per utilizzare uno schema XDM**: puoi scegliere di utilizzare lo schema di Adobe Analytics esistente o di creare uno schema XDM e mappare i campi nell’oggetto dati per lo schema XDM. Gli [schemi XDM](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home#xdm-schemas) consistono in uno schema flessibile per definire tutti i campi necessari e solo quelli rilevanti. <p>Per ulteriori informazioni sui vantaggi derivanti dall’utilizzo dello schema XDM, consulta “Utilizzo del proprio schema XDM” di seguito.</p></li><li>**Conserva regole ed elementi di dati**: sebbene richieda nuove azioni relative alle regole, puoi riutilizzare gli elementi di dati esistenti e le condizioni delle regole con modifiche minime.</li><li>**All’avanguardia**: se scegli di utilizzare lo schema XDM, i futuri aggiornamenti dell’implementazione saranno più semplici.</li></ul> | Nessuno |

{style="table-layout:auto"}

+++

#### Scegliere lo schema

Se hai scelto il percorso di aggiornamento che ti consente di configurare l’implementazione di Adobe Analytics Web SDK per inviare dati a Platform, puoi scegliere lo schema da utilizzare.

Puoi scegliere se utilizzare lo schema di Adobe Analytics esistente oppure aggiornare lo schema XDM per allinearlo meglio alle esigenze dell’organizzazione quando inizi a utilizzare altri servizi di Platform.

+++Utilizzare lo schema di Adobe Analytics con l’implementazione di Adobe Analytics Web SDK

| Vantaggi | Svantaggi |
|----------|---------|
| <p>I vantaggi derivanti dall’utilizzo dello schema di Adobe Analytics includono:</p><ul><li>Facilità di aggiornamento<p>Se stai già inviando dati ad Adobe Analytics con Adobe Experience Platform Web SDK, puoi aggiungere un servizio aggiuntivo allo stream di dati per inviare dati ad Adobe Experience Platform (che potrà quindi essere utilizzato nella configurazione di Customer Journey Analytics).</p></li></ul> | <p>Gli svantaggi dell’utilizzo dello schema di Adobe Analytics includono:</p><ul><li>Sebbene l’utilizzo dello schema di Adobe Analytics non limiti in termini di come può essere utilizzato con altre applicazioni di Platform, risulta in uno schema più complesso di quanto potrebbe essere altrimenti. Questo perché lo schema di Adobe Analytics contiene molti oggetti specifici di Adobe Analytics che difficilmente verranno utilizzati dall’organizzazione.<p>Quando sono necessarie delle modifiche allo schema, è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></li></ul> |

+++

+++Utilizzare il proprio schema XDM con l’implementazione di Adobe Analytics Web SDK

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><p>I vantaggi dell’aggiornamento del proprio schema XDM includono:</p><ul><li>Uno schema semplificato personalizzato in base alle esigenze dell’organizzazione e alle specifiche applicazioni di Platform che utilizzi.</li><p>Quando sono necessarie delle modifiche allo schema, non è necessario esaminare minuziosamente migliaia di campi inutilizzati per trovare il campo che richiede l’aggiornamento.</p></ul> | <p>Gli svantaggi dell’aggiornamento del proprio schema XDM includono:</p><ul><li>L’aggiornamento dello schema è un processo che richiede molto tempo prima di iniziare a inviare dati a Platform.</li></ul> |

+++

## Successivamente, inviare i dati ad Adobe Experience Platform

Dopo aver utilizzato le informazioni precedenti per scegliere un percorso di aggiornamento, scopri come [inviare dati a Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md) in base al percorso di aggiornamento scelto.
