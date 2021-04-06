---
description: Utilizza i modelli in Workspace e crea modelli personalizzati.
title: Modelli
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
exl-id: 464032a1-6dae-4df5-b4db-b277788e88c2
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 95%

---

# Modelli

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Puoi scegliere di creare un progetto da:

* **Progetto vuoto (predefinito)**: per le istruzioni consulta [Creazione di un progetto di Analysis Workspace](/help/analysis-workspace/home.md).
* **Modello standard**: questi modelli vengono creati da Adobe e vengono forniti con il prodotto.
* **Modello personalizzato**: questi modelli possono essere creati, condivisi o eliminati da utenti con diritti di amministratore o da non amministratori, a condizione che dispongano dell’autorizzazione [!UICONTROL Analysis Workspace: Save as Template] in Admin Console. [Ulteriori informazioni...](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Creare un modello personalizzato {#create-custom-template}

Gli utenti con diritti di amministratore possono trasformare qualunque progetto che creano in un modello personalizzato effettuando le seguenti operazioni:

1. Apri il progetto.
1. Vai a **[!UICONTROL Project]** > **[!UICONTROL Save As Template]**.

   ![](assets/save_project_template.png)

   Il progetto viene salvato con il nome corrente, seguito dalla parola (Modello) tra parentesi. Gli amministratori possono cambiare questo nome modificando il modello.

   >[!NOTE]
   >
   >Per impostazione predefinita, i modelli di progetto sono visibili a tutti gli utenti dell’organizzazione. Puoi utilizzare dei tag per organizzare i modelli. (Vai a **[!UICONTROL Project]** (Progetto) > **[!UICONTROL Project Info & Settings]** (Informazioni e impostazioni progetto) per modificare tag e descrizioni.)

### Azioni eseguibili sui modelli personalizzati

![](assets/custom_templates.png)

| Azione | Descrizione |
|--- |--- |
| Modificare un modello | Consente a un amministratore di modificare il modello cambiandone l’origine dati e modificando componenti, visualizzazioni, intervalli di date ecc.  Sono disponibili due modi per modificare un modello personalizzato:<ul><li>Visualizza l’elenco dei modelli personalizzati in Analysis Workspace, selezionane uno e fai clic su Modifica modello, oppure</li><li>In Analytics, vai a Componenti > Progetti, quindi applica il filtro Modelli. Fai clic sul nome del modello da modificare.</li></ul>**Nota:** dopo aver modificato un modello, a seconda della situazione, puoi scegliere Salva o Salva con nome. Queste sono le differenze tra le due opzioni:<ul><li>**Salva:** aggiorna il modello personalizzato per tutti gli utenti. Quando un altro utente crea un progetto basato su questo modello personalizzato, vedrà le modifiche che hai apportato.</li><li>**Salva con nome:** crea una copia del modello personalizzato con le modifiche apportate. Per verificare che sia attiva la modalità di modifica, controlla che la voce di menu Condividi > Condividi progetto sia disabilitata.</li></ul> |
| Cercare nei modelli | Nella finestra di dialogo Modelli personalizzati, fai clic su Cerca modelli. |
| Ordinare i modelli | Puoi organizzare i modelli in ordine alfabetico, per rilevanza e per data di creazione.  Nella finestra di dialogo Modelli personalizzati, fai clic su Ordina. |
| Applicare tag a un modello | Apri il modello e vai a Progetto > Informazioni e impostazioni progetto. Fai clic su Aggiungi tag. |
| Modificare la descrizione di un modello | Apri il modello e vai a Progetto > Informazioni e impostazioni progetto. Fai doppio clic sulla descrizione e modificala. |


## Modelli standard

La prima volta che si apre un’Workspace i modelli sono disponibili nella barra a sinistra. I modelli di Analysis Workspace coprono i casi d’uso più comuni. Sono raggruppati in base alla verticale a cui appartengono e sono compilati con dimensioni, filtri, metriche e visualizzazioni diversi, a seconda della visualizzazione dati selezionata.

Puoi usare questi modelli precompilati così come sono o adattarli alle tue esigenze (ad esempio, aggiungendo o sostituendo metriche o visualizzazioni) e salvarli con un nuovo nome.

>[!VIDEO](https://video.tv.adobe.com/v/23960)

*(2:46)*

Di seguito sono riportati i modelli disponibili e le domande che ogni modello può rispondere.

### Formazione

Questi modelli standard illustrano la terminologia e i passaggi comuni per lo svolgimento della prima analisi in Workspace. Sono disponibili come modello standard nel modale Nuovo progetto e sostituiscono il progetto di esempio attuale per i nuovi utenti che non hanno altri progetti nel loro elenco.

* **Esercitazione - analisi delle ricerche interne**: l’esercitazione di Internal Search (ricerca interna) consente di comprendere cosa cercano e non trovano i visitatori sul sito web o sull’app. L’analisi di questo tipo di dati può far emergere opportunità di ottimizzazione dei contenuti.

* **Esercitazione - analisi di marketing**: questa esercitazione mostra come creare un’analisi di marketing per i dirigenti che individui anche quali sono le dimensioni e le metriche personalizzate più importanti.

### Media

* **Consumo audio**: quali contenuti vengono maggiormente consumati e coinvolgono maggiormente gli utenti?
* **Recency - Frequenza - Fedeltà**: Chi sono i miei lettori più fedeli?


### Vendita al dettaglio

* **Prestazione campagna:** quali campagne generano maggior fatturato?
* **Prodotti:** quali prodotti hanno prestazioni migliori?

### Web

* **Acquisizione:** quali fattori generano maggior traffico verso il sito Web?
* **Consumo di contenuti:** quali sono le aree del sito più visitate?
* **Fidelizzazione:** che tipi di utenti hanno più probabilità di diventare utenti fedeli del sito?
* **Tecnologia:** quali tecnologie vengono usate per accedere al sito?

