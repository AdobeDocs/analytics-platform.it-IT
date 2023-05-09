---
source-git-commit: f74dd6fa47c12c4616e8c5e50d4b351fb498252b
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 72%

---
# Snippet

## Fase di test del rilascio {#release-limited-testing}

>[!AVAILABILITY]
>
>La funzionalità descritta in questo articolo si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio del Customer Journey Analytics, vedi [Rilasci di funzioni di Customer Journey Analytics](/help/release-notes/releases.md).

## Sezione della fase di test del rilascio {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funzionalità descritta in questa sezione si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio del Customer Journey Analytics, vedi [Rilasci di funzioni di Customer Journey Analytics](/help/release-notes/releases.md).

## Criteri del filtro del dizionario dati {#dd-filter-criteria}

1. (Facoltativo) Seleziona l’icona **Filtro** ![icona Filtro dizionario dati](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | [!UICONTROL **Preferiti**] | Mostra solo i componenti inclusi nell’elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/components/overview.md). |
   | [!UICONTROL **Dimensioni**] | Mostra solo i componenti che sono Dimensioni. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Metriche**] | Mostra solo i componenti che sono Metriche. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Filtri**] | Mostra solo i componenti che sono Filtri. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono Intervalli di date. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Mostra tutti**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, questo è utile per identificare i componenti che richiedono la revisione e l’approvazione. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Descrizione mancante**] | Mostra solo i componenti che non dispongono ancora di una descrizione nel campo apposito. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Mostra duplicati**] | Mostra solo i componenti che hanno lo stesso nome o la stessa descrizione di un altro componente nella visualizzazione dati selezionata. Sono inclusi i componenti creati dall’utente e quelli forniti da Adobe. Per poter essere visualizzati come duplicati, i nomi o le descrizioni devono corrispondere esattamente. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

## Informazioni sui componenti del dizionario dati {#dd-component-information}

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Approvato**] | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un’opzione per [!UICONTROL **Annulla approvazione**]. Selezionando questa opzione, il componente viene contrassegnato come &quot;Non approvato&quot; dagli utenti.</p> |
| [!UICONTROL **Non approvato**] | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano l’opzione [!UICONTROL **Approva**]. Selezionando questa opzione, il componente viene visualizzato dagli utenti come “Approvato”.</p> |
| [!UICONTROL **Descrizione**] | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/components/add-component-descriptions.md).) |
| [!UICONTROL **Utilizzato di frequente con**] | <p>Mostra i componenti più comunemente utilizzati insieme a quello che stai visualizzando.</p><p>Sono visualizzati fino a 5 componenti tra i 5 tipi di componenti principali: Metrica, metrica calcolata, Dimension, filtro e intervallo di date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Gli amministratori possono curare i componenti che gli utenti possono visualizzare in questa sezione, selezionandoli nei campi a discesa [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**]. Prima di curare i componenti visualizzati dagli utenti, applica le **Mostra tutto** filtro per verificare di vedere tutti i componenti che non sono condivisi con te e che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Simile a**] | <p>Mostra i componenti con nomi simili al componente che stai visualizzando.</p><p>Sono visualizzati fino a 5 componenti tra i 5 tipi di componenti principali: Metrica, metrica calcolata, Dimension, filtro e intervallo di date.</p><p>Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Tutti i componenti duplicati nella visualizzazione dati verranno visualizzati qui. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare l’integrità del dizionario dati](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori possono curare i componenti che gli utenti possono visualizzare in questa sezione, selezionandoli nei campi a discesa [!UICONTROL **Includi sempre**] ed [!UICONTROL **Escludi sempre**]. Prima di curare i componenti visualizzati dagli utenti, applica le **Mostra tutto** filtro per verificare di vedere tutti i componenti che non sono condivisi con te e che potrebbero essere stati aggiunti da un altro amministratore.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTA:** attualmente, la sezione **Simile a** include solo i componenti che hai creato e non quelli forniti da Adobe. I componenti forniti da Adobe verranno aggiunti in una versione futura.</p> |
| [!UICONTROL **Tag**] | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
| [!UICONTROL **Tipo di componente**] | Elenca il tipo di componente, che si tratti di un Dimension, una metrica, un filtro o un intervallo di date. |
| [!UICONTROL **Creato da**] | Mostra il nome dell’utente che ha creato il componente. |
| [!UICONTROL **Anteprima**] | Mostra un’anteprima dell’aspetto del componente in Analysis Workspace. |
| [!UICONTROL **Data ultima modifica**] | Mostra il giorno dell’ultima modifica apportata al componente. Questa sezione viene visualizzata quando visualizzi Filtri, Metriche, Metriche calcolate e Intervalli di date. |

{style="table-layout:auto"}