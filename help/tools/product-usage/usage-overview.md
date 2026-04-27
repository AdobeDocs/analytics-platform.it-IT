---
title: Panoramica di utilizzo del prodotto
description: Visualizza approfondimenti e rapporti sull’utilizzo di Customer Journey Analytics da parte della tua organizzazione.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 73238f03021b14567c20c686ab72d84afbaa9f81
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 52%

---

# Panoramica di utilizzo del prodotto

Utilizzo del prodotto consente all’organizzazione di visualizzare i dati analitici relativi al modo in cui utilizza Customer Journey Analytics. È disponibile per tutte le organizzazioni che utilizzano Customer Journey Analytics. Una volta abilitata la funzionalità, vengono creati e collegati automaticamente i seguenti componenti Adobe Experience Platform. Questi componenti sono tutti di proprietà del sistema, sono di sola lettura e non possono essere modificati.

* Schema in Adobe Experience Platform
* Set di dati in Adobe Experience Platform
* Connessione in Customer Journey Analytics
* Visualizzazione dati in Customer Journey Analytics

Una volta abilitate, tutte le raccolte e le impostazioni dei dati vengono configurate automaticamente. Ogni volta che un utente esegue un’azione in Analysis Workspace, questa viene tracciata ed è disponibile per i rapporti.

>[!IMPORTANT]
>
>Se si abilita l’utilizzo del prodotto, i dati di utilizzo vengono memorizzati nel data lake di Adobe Experience Platform. Assicurati che l’allocazione dell’archiviazione del data lake nell’organizzazione possa contenere i set di dati aggiuntivi generati dall’abilitazione di questa funzione.
>
>Questa funzione non viene conteggiata rispetto ai limiti delle righe di reporting di Customer Journey Analytics concessi in licenza o alle adesioni ai dati evento.

## Abilita Utilizzo del prodotto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Strumenti]** > **[!UICONTROL Utilizzo prodotto]**

Passando a questa sezione dell’interfaccia in Customer Journey Analytics arrivi a [Impostazioni dati](data-settings.md), dove puoi abilitare la funzione.

## Dimensioni disponibili

Quando abiliti Utilizzo del prodotto, sono disponibili le seguenti dimensioni. Se desideri modificare le impostazioni di dimensione, crea una copia della visualizzazione dati di proprietà del sistema e utilizza la visualizzazione dati copiata in Analysis Workspace.

* **[!UICONTROL Nome azione]**: tipo di azione eseguita dall&#39;utente. Puoi utilizzare questa dimensione come qualsiasi metrica desiderata creando una copia nelle impostazioni della visualizzazione dati. Gli elementi dimensionali includono:
   * [!UICONTROL Aggiungi attribuzione]
   * [!UICONTROL Aggiungi componente]
   * [!UICONTROL Aggiungi pannello]
   * [!UICONTROL Aggiungi visualizzazione]
   * [!UICONTROL Crea nuova analisi guidata]
   * [!UICONTROL Crea nuovo progetto]
   * [!UICONTROL Cura componenti]
   * [!UICONTROL Scarica CSV]
   * [!UICONTROL Scarica PDF]
   * [!UICONTROL Carica analisi guidata]
   * [!UICONTROL Carica progetto]
   * [!UICONTROL Nuova scorecard caricata]
   * [!UICONTROL Apri dizionario dati]
   * [!UICONTROL Apri didascalie intelligenti]
   * [!UICONTROL Condivisione progetto]
   * [!UICONTROL Esegui pannello Sperimentazione]
   * [!UICONTROL Salva progetto]
   * [!UICONTROL Scorecard salvata]
   * [!UICONTROL Invia file]
   * [!UICONTROL Invia file secondo programma]
   * [!UICONTROL Condividi progetto con qualcuno]
   * [!UICONTROL Condividi progetto con utenti Workspace]
   * [!UICONTROL Cambia visualizzazione dati]
* **[!UICONTROL Modello di attribuzione utilizzato]**: tipo di modello di attribuzione utilizzato dal componente. Gli elementi dimensionali includono:
   * [!UICONTROL Ultimo contatto]
   * [!UICONTROL Primo contatto]
   * [!UICONTROL Lineare]
   * [!UICONTROL Partecipazione]
   * [!UICONTROL Stesso contatto]
   * [!UICONTROL A forma di U]
   * [!UICONTROL J curva]
   * [!UICONTROL J inversa]
   * [!UICONTROL Decadimento nel tempo]
   * [!UICONTROL Personalizzato]
   * [!UICONTROL Algoritmico]
* **[!UICONTROL ID componente]**: ID del componente aggiunto, rimosso o modificato.
* **[!UICONTROL Nome componente]**: il nome descrittivo del componente aggiunto, rimosso o modificato.
* **[!UICONTROL Tipo di componente]**: tipo di componente aggiunto, rimosso o modificato. Gli elementi dimensionali includono:
   * [!UICONTROL Dimensione]
   * [!UICONTROL Metrica]
   * [!UICONTROL Segmento]
   * [!UICONTROL Metrica calcolata]
   * [!UICONTROL Intervallo date]
   * [!UICONTROL Annotazione]
   * [!UICONTROL Avviso]
* **[!UICONTROL ID visualizzazione dati]**: ID della visualizzazione dati.
* **[!UICONTROL Nome visualizzazione dati]**: il nome descrittivo della visualizzazione dati.
* **[!UICONTROL Utente di accesso]**: l&#39;utente che ha eseguito l&#39;azione.
* **[!UICONTROL Pannello utilizzato]**: pannello aggiunto, rimosso o modificato. Gli elementi dimensionali includono:
   * [!UICONTROL Attribuzione]
   * [!UICONTROL Pannello vuoto]
   * [!UICONTROL Sperimentazione]
   * [!UICONTROL A forma libera]
   * [!UICONTROL Elemento successivo o precedente]
   * [!UICONTROL Quick Insights]
   * [!UICONTROL Tendenze]
   * [!UICONTROL Funnel]
   * [!UICONTROL Crescita utenti]
   * [!UICONTROL Impatto]
   * [!UICONTROL Flusso utente]
   * [!UICONTROL Mantenimento]
   * [!UICONTROL Matrice di funzioni]
* **[!UICONTROL ID progetto]**: ID del progetto.
* **[!UICONTROL Nome progetto]**: il nome descrittivo del progetto.
* **[!UICONTROL Tipo di progetto]**: il tipo di progetto. Gli elementi dimensionali includono:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Visualizzazione utilizzata]**: visualizzazione aggiunta, rimossa o modificata. Gli elementi dimensionali includono:
   * [!UICONTROL Tabella a forma libera]
   * [!UICONTROL Tabella coorte]
   * [!UICONTROL Fallout]
   * [!UICONTROL Flusso]
   * [!UICONTROL reportlet area di lavoro Percorsi]
   * [!UICONTROL Superfici]
   * [!UICONTROL Area sovrapposta]
   * [!UICONTROL Barre]
   * [!UICONTROL Barre sovrapposte]
   * [!UICONTROL Bullet]
   * [!UICONTROL Combinato]
   * [!UICONTROL Anello]
   * [!UICONTROL Istogramma]
   * [!UICONTROL Barre orizzontali]
   * [!UICONTROL Barra orizzontale sovrapposta]
   * [!UICONTROL Riepilogo delle metriche chiave]
   * [!UICONTROL Linee]
   * [!UICONTROL Mappa]
   * [!UICONTROL A dispersione]
   * [!UICONTROL Intestazione di sezione]
   * [!UICONTROL Variazione di riepilogo]
   * [!UICONTROL Numero di riepilogo]
   * [!UICONTROL Testo]
   * [!UICONTROL Mappa ad albero]
   * [!UICONTROL Venn]

L’utilizzo del prodotto non tiene traccia dei singoli componenti del progetto quando questo viene semplicemente aperto o visualizzato. Tuttavia, viene tenuta traccia dell’azione dell’utente di apertura di un progetto.

## Modello disponibile

È disponibile un [modello Adobe](/help/analysis-workspace/templates/use-templates.md) che utilizza i componenti generati automaticamente da questa funzione.

**[!UICONTROL Modelli Adobe]** > **[!UICONTROL Altro]** > **[!UICONTROL Panoramica sull&#39;utilizzo del prodotto]**

Seleziona la visualizzazione dati creata automaticamente dall&#39;utilizzo del prodotto nel selettore della visualizzazione dati, quindi seleziona il modello **[!UICONTROL Panoramica sull&#39;utilizzo del prodotto]**. Seleziona **[!UICONTROL Anteprima]** per visualizzare i pannelli utilizzati dal modello e i casi d&#39;uso ideali, oppure seleziona **[!UICONTROL Usa modello]** per aprirlo in Analysis Workspace.
