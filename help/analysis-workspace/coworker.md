---
title: Analizzare e creare progetti Workspace con il collaboratore
description: Utilizza l’esperienza interna al prodotto per Collaboratore per riepilogare il progetto aperto, trovare informazioni approfondite e creare pannelli, tabelle e segmenti da prompt in linguaggio naturale.
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 2c55e526968ca2f064f32c457ee112c07a0b10ff
workflow-type: tm+mt
source-wordcount: '1945'
ht-degree: 0%
---
# Utilizzare l’esperienza interna al prodotto per il collaboratore

{{release-limited-testing}}

L’esperienza interna al prodotto per Collaboratore è disponibile in un pannello di chat sul lato destro di Analysis Workspace. Cooker utilizza il progetto aperto come contesto, in modo da poter chiedere informazioni sull’analisi o chiedere a Cooker di creare il progetto senza dover spiegare cosa contiene.

## Comprendere Collaboratore in Workspace

### Prerequisiti

* **Collaboratore abilitato per la tua organizzazione**: l&#39;esperienza interna al prodotto per Collaboratore è disabilitata per impostazione predefinita. Un amministratore Customer Journey Analytics deve abilitarlo per l’organizzazione prima che gli utenti possano accedervi.

  Se non riesci ad accedere a Collaboratore in Workspace, contatta l’amministratore. Per ulteriori informazioni, consulta [Preferenze organizzazione IMS](/help/analysis-workspace/user-preferences.md#ims-organization-preferences). <!-- need to update this section with the new toggle -->

<!-- FOLLOW-UP: Coworker permissions are still being finalized. The Coworker permission name below is a placeholder. Confirm the name, category, and Admin Console steps with the SME. -->

* **Autorizzazioni**: in [!UICONTROL Adobe Admin Console], l&#39;autorizzazione [!UICONTROL Strumenti di reporting] **[!UICONTROL Collaboratore]** determina l&#39;accesso a Collaboratore. Un [amministratore del profilo di prodotto](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html?lang=it) deve aggiungere questa autorizzazione al tuo profilo di prodotto. Per ulteriori informazioni, vedere [Controllo degli accessi](/help/technotes/access-control.md#access-control).

* **Accesso alla visualizzazione dati**: il collaboratore utilizza le autorizzazioni esistenti per Analysis Workspace e la visualizzazione dati. Non può accedere a dati o componenti a cui non hai già accesso.

### Scegliere tra Collaboratore in Workspace e l’applicazione Collaboratore

L&#39;esperienza interna al prodotto per Coworker ha molte delle stesse funzionalità dell&#39;[applicazione CX Enterprise Coworker](https://experienceleague.adobe.com/it/docs/coworker/content/chat/use-cases/data-insights/analytics-chat), incluse le abilità a cui hai accesso. Tuttavia, esistono importanti differenze che determinano quando è possibile utilizzare uno rispetto all’altro:

| | Esperienza nel prodotto per il collaboratore | Applicazione di collaborazione |
| --- | --- | --- |
| **Quando utilizzare** | Desideri creare un progetto che intendi mantenere, condividere con altri utenti o aggiornare nel tempo. | Vuoi una risposta rapida. Se necessario, puoi scegliere di trasformare l’analisi in un progetto Workspace in un secondo momento. |
| **Contesto** | Incentrato sul progetto<p>Utilizza il progetto Workspace aperto come punto di partenza. Puoi fare riferimento a e creare su pannelli, tabelle e componenti già presenti nel progetto.</p> | Basato sulla visualizzazione dati<p>Utilizza le visualizzazioni dati a cui hai accesso o quelle impostate come preferenza nella memoria di Collaborator. Descrivi cosa desideri analizzare nel prompt.</p> |
| **Utente tipico** | Analisti che creano e convalidano l’analisi in Workspace. | Utenti aziendali che desiderano ricevere risposte senza dover accedere a Workspace o apprenderne. |
| **Output** | In Coworker vengono aggiunti pannelli, tabelle e componenti direttamente al progetto Workspace. <p>Quando appropriato, risponde anche nella chat.</p> | Le risposte e le analisi vengono fornite nella conversazione, con l’opzione di aprire in Analysis Workspace. |

### Cosa puoi fare con Collaboratore

#### Fai domande sul progetto aperto

Puoi fare a Cooker domande del tipo:

* Riepiloga il progetto.
* Trova informazioni approfondite e contrassegna le anomalie nei dati.
* Eseguire un’analisi della causa principale su un pannello.
* Spiega come eseguire un’operazione in Analysis Workspace, ad esempio come aggiungere un grafico a linee o come colorare le celle delle tabelle in base ai loro valori.
* Spiega un componente, ad esempio una metrica o dimensione.

Per ulteriori informazioni, vedere [Poni domande su un progetto](#ask-questions-about-a-project).

#### Creare e modificare il progetto aperto

Puoi chiedere a Collaboratore di fare cose come:

* Crea un pannello a forma libera con le dimensioni, le metriche e l’intervallo di date specificati.
* Aggiungi pannelli al progetto. Cooker aggiunge nuovi pannelli senza sovrascrivere quelli esistenti.
* Suddividere una tabella o aggiungere colonne di confronto.
* Modifica l’intervallo di date o il tipo di visualizzazione di un pannello, ad esempio la modifica di una tabella in un grafico a linee.
* Rinominare un pannello.
* Applica un segmento esistente per nome, crea un segmento da una descrizione in linguaggio semplice oppure copia un segmento e modificane la logica.
* Creare intervalli di date e metriche calcolate semplici.
* Aggiungi descrizioni o una visualizzazione di testo che contiene informazioni approfondite sul progetto.
* Crea un progetto con più pannelli, oppure copia un progetto e adattalo per un pubblico o un’area geografica diversa.
* Salva il progetto.

Per ulteriori informazioni, vedere [Aggiornare un progetto](#update-a-project).

### Quando Collaboratore aggiorna il progetto o le risposte nella chat

Il collaboratore decide se rispondere nel pannello chat o modificare il progetto in base a ciò che chiedi. Per ulteriori informazioni, vedere [Aggiornare un progetto](#update-a-project) e [Porre domande su un progetto](#ask-questions-about-a-project).

Puoi anche essere esplicito su ciò che desideri che faccia Collaboratore. Ad esempio, puoi utilizzare frasi come _in chat_ o _dimmi_ per ottenere una risposta nel pannello chat, oppure frasi come _aggiungi al progetto_ o _in questa tabella_ per aggiornare il progetto.

## Utilizzare Collaboratore con i progetti

Il collaboratore può visualizzare ogni pannello e tabella nel progetto aperto. Puoi chiedere a Collaboratore di rispondere a domande sul progetto o di aiutarti ad aggiornarlo.

>[!TIP]
>
>Puoi interrompere Collaboratore o aggiornare il progetto in qualsiasi momento:
>
>* **Ruota o interrompi un&#39;attività**: mentre Coworker è in funzione, premi **Maiusc+Invio** per darle più direzione, oppure premi **Esc** per interromperla.
>
>* **Aggiornamenti a un progetto in Workspace**: se si modifica il progetto mentre Coworker è in esecuzione, le modifiche verranno riconosciute da Coworker.

### Aggiornare un progetto

Quando chiedi a Collaboratore di creare o modificare qualcosa nel progetto, il progetto viene aggiornato di conseguenza. Sono incluse le richieste che iniziano con parole come _add_, _create_, _edit_, _breakdown_, _change_ e _compare_. Ad esempio, puoi chiedere a Collaboratore di aggiungere pannelli e tabelle, suddividere i dati o creare segmenti.

1. In Customer Journey Analytics, apri un progetto Workspace esistente o creane uno nuovo.

1. Seleziona l&#39;icona **Collaboratore** ![Chiedi a Collaboratore](/help/assets/icons/coworker.svg) nell&#39;angolo superiore destro dell&#39;intestazione di aprire il pannello di chat di Collaboratore.

1. Nel pannello chat, descrivi cosa desideri fare in Collaboratore.

   Nella tabella seguente sono elencati alcuni esempi di prompt.

   | Prompt | Funzionamento di Collaborator |
   | --- | --- |
   | _Mostra sessioni per pagina per l&#39;ultimo mese_ | Aggiunge un nuovo pannello a forma libera con la dimensione, la metrica e l’intervallo di date specificati. I pannelli esistenti non vengono sovrascritti. |
   | _Suddividere questa tabella per dispositivo_ | Aggiunge il raggruppamento alla tabella a cui si fa riferimento. |
   | _Aggiungere un confronto con il mese scorso in questa tabella_ | Aggiunge una colonna di confronto alla tabella a cui si fa riferimento. |
   | _Modifica l&#39;intervallo di date di questo pannello all&#39;ultimo mese_ | Aggiorna l’intervallo di date del pannello. |
   | _Cambia questa tabella in un grafico a linee_ | Modifica il tipo di visualizzazione del pannello. |
   | _Rinomina questo pannello in Prestazioni mobili_ | Rinomina il pannello. |
   | _Applica il segmento utenti di dispositivi mobili a questo pannello_ | Applica il segmento esistente al pannello. Il collaboratore non conosce la definizione del segmento, quindi verifica che il segmento contenga ciò che ti aspetti. |
   | _Crea un segmento per i visitatori dal Canada_ | Crea il segmento e lo aggiunge al progetto. Il segmento viene visualizzato nell’elenco dei componenti dopo l’aggiornamento della pagina. |
   | _Copia il segmento dei visitatori del Canada e modificalo in visitatori dal Messico_ | Crea una copia del segmento con la logica aggiornata e la aggiunge al progetto. |
   | _Crea un intervallo di date per le ultime 6 settimane_ | Crea l’intervallo di date. L’intervallo di date viene visualizzato nell’elenco dei componenti senza un aggiornamento. |
   | _Crea una metrica calcolata per i ricavi per sessione_ | Crea la metrica calcolata. Il collaboratore può creare semplici metriche calcolate. |
   | _Aggiungi una descrizione a questo pannello per spiegare il calo delle visite_ | Aggiunge la descrizione al pannello. |
   | _Aggiungi una visualizzazione di testo con le informazioni chiave_ | Aggiunge al progetto una visualizzazione di testo contenente le informazioni approfondite. |
   | _Crea un progetto con pannelli per traffico, conversione e ricavi_ | Crea un progetto con un pannello per ogni area descritta. |
   | _Copia il progetto e adattalo per l&#39;area EMEA_ | Crea una copia del progetto e la adatta all&#39;area specificata. |
   | _Salva il progetto_ | Salva il progetto. |
   | _Annulla il raggruppamento aggiunto_ | Annulla la modifica specificata. |
   | _Elimina i vecchi pannelli_ | Elenca i pannelli che intende eliminare e attende la conferma prima di eliminarli. |

1. Esamina le modifiche apportate da Collaboratore al progetto. Per ulteriori informazioni, vedere [Verificare i risultati di Collaborator](#verify-coworker-results).

### Poni domande su un progetto

Quando fai domande su un progetto, Collaboratore risponde nel pannello di chat. Questo include richieste come _explain_, _summary_, _talk_ e _tell me more_. Anche i risultati dell’analisi della causa principale e competenze simili rimangono nel pannello chat fino a quando non chiedi a Collaboratore di aggiungerli al progetto.

1. In Customer Journey Analytics, apri un progetto Workspace esistente o creane uno nuovo.

1. Seleziona l&#39;icona **Collaboratore** ![Chiedi a Collaboratore](/help/assets/icons/coworker.svg) nell&#39;angolo superiore destro dell&#39;intestazione di aprire il pannello di chat di Collaboratore.

1. Nel pannello chat, descrivi cosa desideri fare in Collaboratore.

   Nella tabella seguente sono elencati alcuni esempi di prompt.

   | Prompt | Funzionamento di Collaborator |
   | --- | --- |
   | _Riepiloga il progetto_ | Fornisce un riepilogo nel pannello chat e offre di aggiungerlo al progetto come visualizzazione di testo. |
   | _Trova informazioni in questo progetto_ | Fornisce informazioni approfondite nel pannello chat e offre di aggiungere i risultati al progetto. |
   | _Segnala eventuali anomalie in questo pannello_ | Descrive le anomalie nel pannello chat. Se chiedi a Collaboratore di mostrare le anomalie in una visualizzazione, queste potrebbero non essere visualizzate. Vedi [Limitazioni correnti](#current-limitations). |
   | _Eseguire un&#39;analisi della causa principale al calo delle visite dei dispositivi mobili_ | Fornisce l’analisi nel pannello chat e offre di aggiungere i risultati al progetto. |
   | _Come si colorano le celle in base ai relativi valori?_ | Descrive i passaggi del pannello chat. |
   | _Spiegare la metrica Percentuale non recapitate_ | Spiega il componente nel pannello chat. La spiegazione non proviene dal [dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md). Il supporto per le definizioni del dizionario dati è pianificato per una versione futura. |

1. Rivedi la risposta fornita da Collaboratore. Per ulteriori informazioni, vedere [Verificare i risultati di Collaborator](#verify-coworker-results).

## Verificare i risultati di Collaboratore

Collaboratore consente di verificare l’accuratezza dei risultati. Quando li esaminate, tenete presente quanto segue:

* **Il lavoro di Coworker**: i segmenti, le metriche e i filtri utilizzati da Coworker per rispondere a una domanda vengono aggiunti al progetto in modo da poterli verificare.

* **Domande chiarificatrici**: quando una richiesta è vaga o corrisponde a più di un componente, Collaboratore pone una domanda chiarificatrice o suggerisce le opzioni tra cui scegliere. Ad esempio, se più metriche corrispondono al nome utilizzato, Collaboratore consiglia le metriche corrispondenti.

* **Note sulla qualità dei dati**: nelle risposte di Collaboratore sono incluse le note sulla qualità dei dati. Ad esempio, se confronti un mese che è appena iniziato con un mese intero, Collaboratore ti dice che il confronto è basato su dati parziali.

## Limitazioni attuali

L’esperienza interna al prodotto per Collaboratore presenta le seguenti limitazioni:

* **Definizioni dei segmenti**: quando si fa riferimento a un segmento per nome, Collaboratore non conosce la definizione del segmento. Il collaboratore potrebbe dedurre cosa contiene il segmento in base al suo nome. Verifica la definizione del segmento prima di affidarti ai risultati.

* **Dizionario dati**: il collaboratore non è connesso al [Dizionario dati](/help/components/data-dictionary/data-dictionary-overview.md). Non può utilizzare le definizioni nel dizionario dati per spiegare metriche e dimensioni.

* **Componenti approvati**: il collaboratore non concede la preferenza ai componenti approvati rispetto ai componenti simili.

* **Copia dei pannelli**: impossibile copiare o duplicare un pannello.

* **Nuovi segmenti nell&#39;elenco dei componenti**: i segmenti creati da Collaborator non vengono visualizzati nell&#39;elenco dei componenti nella barra a sinistra finché non aggiorni la pagina. Gli intervalli di date creati da Collaboratore vengono visualizzati senza aggiornamento.

* **Rilevamento anomalie**: quando si chiede a Collaboratore di visualizzare le anomalie in una visualizzazione, è possibile che queste non vengano visualizzate.

* **Cronologia conversazioni**: le conversazioni vengono salvate per ogni utente, non con il progetto. Gli altri utenti che aprono il progetto non possono visualizzare la conversazione con Collaboratore. Per condividere il contesto con altri utenti, aggiungilo alle descrizioni dei pannelli nel progetto.

* **Più schede del browser**: se apri la stessa conversazione in più di una scheda del browser, è possibile che Coworker perda la traccia di ciò che sta funzionando.

* **Lingue diverse dall&#39;inglese**: nelle visualizzazioni dati che utilizzano una lingua diversa dall&#39;inglese, nelle risposte di Collaborator è possibile utilizzare una combinazione di inglese e lingua della visualizzazione dati.


