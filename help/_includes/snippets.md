---
source-git-commit: c202effa3b25b1703cad38975786252637291b48
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 13%

---
# Snippet

## Fase di test del rilascio {#release-limited-testing}

>[!AVAILABILITY]
>
>La funzionalità descritta in questo articolo si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Customer Journey Analytics](/help/release-notes/releases.md).

## Sezione della fase di test del rilascio {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funzionalità descritta in questa sezione si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Customer Journey Analytics](/help/release-notes/releases.md).

## Criteri di filtro del dizionario dati {#dd-filter-criteria}

1. (Facoltativo) Seleziona la **Filtro** icona ![Icona Filtro dizionario dati](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png), quindi seleziona una delle seguenti opzioni di filtro per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | [!UICONTROL **Preferiti**] | Mostra solo i componenti inclusi nell&#39;elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/components/overview.md). |
   | [!UICONTROL **Dimensioni**] | Mostra solo i componenti che sono Dimension. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] al primo accesso al dizionario dati). |
   | [!UICONTROL **Metriche**] | Mostra solo i componenti che sono metriche. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] al primo accesso al dizionario dati). |
   | [!UICONTROL **Filtri**] | Mostra solo i componenti che sono Filtri. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] al primo accesso al dizionario dati). <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono intervalli di date. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] al primo accesso al dizionario dati). |
   | [!UICONTROL **Mostra tutto**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, è utile per identificare i componenti che richiedono la revisione e l’approvazione dell’utente. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Descrizione mancante**] | Nel campo Descrizione è possibile visualizzare solo i componenti che non dispongono ancora di una descrizione. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Mostra duplicati**] | Mostra solo i componenti che hanno lo stesso nome o la stessa descrizione di un altro componente della suite di rapporti selezionata. Sono inclusi i componenti creati dall’utente e quelli forniti da Adobe. Per poter essere visualizzati come duplicati, i nomi o le descrizioni devono corrispondere esattamente. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

## Informazioni sui componenti del dizionario dati {#dd-component-information}

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Approvato**] | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un’opzione per [!UICONTROL **Annulla approvazione**]. Selezionando questa opzione, il componente viene contrassegnato come &quot;Non approvato&quot; dagli utenti.</p> |
| [!UICONTROL **Non approvato**] | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un’opzione per [!UICONTROL **Approva**]. Selezionando questa opzione, il componente viene contrassegnato come &quot;Approvato&quot; dagli utenti.</p> |
| [!UICONTROL **Descrizione**] | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Frequentemente utilizzato con**] | <p>Mostra i componenti più comunemente utilizzati con il componente che stai visualizzando.</p><p>Sono visualizzati fino a 5 componenti tra i 5 tipi di componenti principali: Metrica, metrica calcolata, Dimension, filtro e intervallo di date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono visualizzati solo i componenti a cui hai accesso.</p><p>Gli amministratori possono curare i componenti visualizzati dagli utenti in questa sezione selezionando i componenti desiderati nel [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**] campi a discesa. Prima di curare i componenti visualizzati dagli utenti, applica le **Mostra tutto** filtro per verificare di vedere tutti i componenti che non sono condivisi con te e che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Simile a**] | <p>Mostra i componenti con nomi simili al componente che stai visualizzando.</p><p>Sono visualizzati fino a 5 componenti tra i 5 tipi di componenti principali: Metrica, metrica calcolata, Dimension, filtro e intervallo di date.</p><p>Vengono visualizzati solo i componenti a cui hai accesso.</p><p>Eventuali componenti duplicati nella suite di rapporti verranno visualizzati qui. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare lo stato del dizionario dati](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori possono curare i componenti visualizzati dagli utenti in questa sezione selezionando i componenti desiderati nel [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**] campi a discesa. Prima di curare i componenti visualizzati dagli utenti, applica le **Mostra tutto** filtro per verificare di vedere tutti i componenti che non sono condivisi con te e che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTA:** Attualmente, il **Simile a** include solo i componenti creati e non quelli forniti da Adobe. I componenti forniti da Adobe verranno aggiunti in una versione futura.</p> |
| [!UICONTROL **Tag**] | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
| [!UICONTROL **Tipo di componente**] | Elenca il tipo di componente, che si tratti di un Dimension, una metrica, un filtro o un intervallo di date. |
| [!UICONTROL **Creato da**] | Visualizza il nome dell’utente che ha creato il componente. |
| [!UICONTROL **Anteprima**] | Mostra un’anteprima del componente in Analysis Workspace. |
| [!UICONTROL **Data ultima modifica**] | Visualizza il giorno dell’ultima modifica apportata al componente. Questa sezione viene visualizzata quando visualizzi Filtri, Metriche, Metriche calcolate e Intervalli di date. |

{style="table-layout:auto"}