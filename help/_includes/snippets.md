---
source-git-commit: 02ff498456fb3d770b9e3c73c3847ac5a55cd705
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 15%

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

## Criteri del filtro del dizionario dati {#dd-filter-criteria}

1. (Facoltativo) Seleziona la **Filtro** icona ![Icona Filtro dizionario dati](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png), quindi seleziona una delle seguenti opzioni di filtro per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come Approvati da un amministratore. |
   | [!UICONTROL **Preferiti**] | Mostra solo i componenti presenti nell&#39;elenco Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/components/overview.md). |
   | [!UICONTROL **Dimensioni**] | Mostra solo i componenti Dimension. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] quando si accede per la prima volta al dizionario dati.) |
   | [!UICONTROL **Metriche**] | Mostra solo i componenti che sono metriche. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] quando si accede per la prima volta al dizionario dati.) |
   | [!UICONTROL **Filtri**] | Mostra solo i componenti che sono filtri. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] quando si accede per la prima volta al dizionario dati.) <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono intervalli di date. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] quando si accede per la prima volta al dizionario dati.) |
   | [!UICONTROL **Mostra tutto**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, è utile per identificare i componenti che richiedono la tua revisione e approvazione. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Descrizione mancante**] | Mostra solo i componenti per i quali non è ancora disponibile una descrizione nel campo Descrizione. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Mostra duplicati**] | Mostra solo i componenti con la stessa etichetta o descrizione di un altro componente nella suite di rapporti selezionata. Sono inclusi i componenti creati e quelli forniti da Adobe. Le etichette o le descrizioni devono avere corrispondenze esatte per poter essere visualizzate come duplicati. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

## Informazioni sul componente del dizionario dati {#dd-component-information}

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Approvato**] | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un’opzione per [!UICONTROL **Annulla approvazione**]. Selezionando questa opzione, il componente viene contrassegnato come &quot;Non approvato&quot; per gli utenti.</p> |
| [!UICONTROL **Non approvato**] | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un’opzione per [!UICONTROL **Approva**]. Selezionando questa opzione, il componente viene contrassegnato come &quot;Approvato&quot; per gli utenti.</p> |
| [!UICONTROL **Descrizione**] | Descrive la funzione prevista del componente. Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungere descrizioni dei componenti](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Utilizzato di frequente con**] | <p>Mostra i componenti più comunemente utilizzati con il componente visualizzato.</p><p>Vengono visualizzati fino a 5 componenti nei 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Filtro e Intervallo date.</p><p>Questo elenco si basa sui dati degli ultimi 90 giorni. Vengono visualizzati solo i componenti per i quali si dispone dell&#39;accesso in visualizzazione.</p><p>Gli amministratori visualizzano le opzioni per [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**]. Queste opzioni consentono agli amministratori di curare i componenti visualizzati dagli utenti in questa sezione.</p> |
| [!UICONTROL **Simile a**] | <p>Mostra i componenti con etichette simili a quelle del componente che stai visualizzando.</p><p>Vengono visualizzati fino a 5 componenti nei 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Filtro e Intervallo date.</p><p>Vengono visualizzati solo i componenti per i quali si dispone dell&#39;accesso in visualizzazione.</p><p>Tutti i componenti duplicati nella suite di rapporti verranno visualizzati qui. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare l’integrità del dizionario dati](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori visualizzano le opzioni per [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**]. Queste opzioni consentono agli amministratori di curare i componenti visualizzati dagli utenti in questa sezione.</p> |
| [!UICONTROL **Tag**] | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
| [!UICONTROL **Tipo di componente**] | Elenca il tipo di componente, sia esso un Dimension, una metrica, un filtro o un intervallo di date. |
| [!UICONTROL **Creato da**] | Visualizza il nome dell&#39;utente che ha creato il componente. |
| [!UICONTROL **Anteprima**] | Mostra un’anteprima dell’aspetto del componente in Analysis Workspace. |
| [!UICONTROL **Data ultima modifica**] | Visualizza il giorno dell&#39;ultima modifica apportata al componente. Questa sezione viene visualizzata quando si visualizzano Filtri, Metriche, Metriche calcolate e Intervalli di date. |

{style="table-layout:auto"}