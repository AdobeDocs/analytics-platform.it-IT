---
description: Utilizzare filtri rapidi per Customer Journey Analytics in Analysis Workspace
title: Filtri rapidi
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: a69f9eef39c0eceee1964a3b8741b7538b218ece
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 9%

---

# Filtri rapidi

I filtri rapidi consentono di esplorare facilmente i dati all’interno di un determinato progetto, senza la necessità di creare un filtro per l’elenco dei componenti più complesso nel [Generatore di filtri](/help/components/filters/create-filters.md).

Quando crei filtri rapidi, considera quanto segue:

* I filtri rapidi si applicano solo al progetto in cui sono stati creati. Non sono disponibili in altri progetti e non possono essere condivisi con altri utenti.
* È consentito un massimo di 3 regole.
* I contenitori nidificati o le regole sequenziali non sono supportati.

Il video seguente illustra come utilizzare i filtri rapidi. (Nota: questo video utilizza il termine &quot;segmenti rapidi&quot; invece di &quot;filtri rapidi&quot;. Tuttavia, la funzionalità è la stessa.)

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Creare un filtro rapido {#create}

Qualsiasi utente in Analysis Workspace può creare un filtro rapido.

Per creare un filtro rapido:

1. Scegli uno dei metodi seguenti per iniziare a creare il filtro rapido:

   * **Ad hoc (trascinamento della selezione):** Dalla barra a sinistra, trascina un componente nella zona di rilascio accanto alla **Filtro** nell’intestazione del pannello, quindi seleziona la **Modifica** per regolare il filtro.

      ![Modifica filtro ad hoc](assets/filter-adhoc-edit.png)

      >[!NOTE]
      >
      > Quando crei un filtro rapido ad hoc (trascinamento della selezione), considera quanto segue:
      > * I seguenti tipi di componenti non sono supportati: metriche e dimensioni calcolate e metriche da cui non è possibile creare filtri.
      > * Per eventi e dimensioni intere, Analysis Workspace crea dei filtri di hit di tipo “exists” (esiste). Esempi: `Hit where eVar1 exists` o `Hit where event1 exists`.
      > * Se nella zona di rilascio del filtro viene rilasciato &quot;non specificato&quot; o &quot;nessuno&quot;, questo viene automaticamente convertito in un filtro &quot;non esiste&quot; in modo che venga trattato correttamente nel filtro.



   * **Utilizzando l’icona del filtro:** In una tabella a forma libera, seleziona la **Filtro** nell’intestazione del pannello.

      ![Filtro del segmento](assets/quick-seg1.png)

1. Regola una delle seguenti impostazioni:

   | Impostazione | Descrizione |
   | --- | --- |
   | [!UICONTROL Name] | Il nome predefinito di un filtro è una combinazione dei nomi delle regole nel filtro. È possibile rinominare il filtro in un nome più semplice. |
   | [!UICONTROL Include/exclude] | Puoi includere o escludere componenti nella definizione del filtro, ma non entrambi. |
   | Contenitore [!UICONTROL Hit/Visit/Visitor] | I filtri rapidi ne includono uno [contenitore filtro](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers) solo che ti consente di includere una dimensione/metrica/intervallo di date nel filtro (o escluderlo da esso). [!UICONTROL Visitor] contiene i dati generali specifici del visitatore per visite e visualizzazioni di pagina. A [!UICONTROL Visit] consente di impostare regole per suddividere i dati del visitatore in base alle visite e a [!UICONTROL Hit] Il contenitore ti consente di suddividere le informazioni sui visitatori in base alle singole visualizzazioni di pagina. Il valore predefinito è [!UICONTROL Hit]. |
   | [!UICONTROL Components] (Dimension/metrica/intervallo di date) | Definisci fino a 3 regole aggiungendo componenti (dimensioni, metriche, intervalli di date o valori di dimensione). Ci sono 3 modi per trovare il componente giusto:<ul><li>Inizia a digitare e il generatore di filtri rapidi individua automaticamente il componente appropriato.</li><li>Utilizza l’elenco a discesa per trovare il componente.</li><li>Trascina e rilascia i componenti dalla barra a sinistra.</li></ul> |
   | [!UICONTROL Operator] | Utilizza il menu a discesa per trovare gli operatori standard e gli operatori [!UICONTROL Distinct Count]. Vedi [Operatori di filtro](operators.md). |
   | Segno più (+) | Aggiunge un’altra regola, |
   | Qualificatori AND/OR | Puoi aggiungere i qualificatori &quot;AND&quot; o &quot;OR&quot; alle regole, ma non puoi combinare &quot;AND&quot; e &quot;OR&quot; in una singola definizione di filtro. |
   | [!UICONTROL Apply] | Applica questo filtro al pannello. Se il filtro non contiene dati, viene richiesto se si desidera continuare. |
   | [!UICONTROL Open builder] | Apre il Generatore di filtri. Dopo aver salvato o applicato il filtro nel Generatore di filtri, non viene più considerato un &quot;Filtro rapido&quot;. Diventa parte della libreria di filtri per elenchi di componenti. <p>Per rendere il componente disponibile in tutti i progetti e nella barra a sinistra, seleziona l’opzione . [!UICONTROL **Rendi questo filtro disponibile per tutti i tuoi progetti e aggiungilo all’elenco dei componenti**].</p><p>Per ulteriori informazioni, consulta la sezione . [Salvare un filtro rapido come filtro elenco di componenti](#save-a-quick-filter-as-a-component-list-filter) in questo articolo.</p><p>**Nota:** Solo gli utenti con l&#39;autorizzazione per la creazione di filtri nel [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) può aprire il Generatore di filtri.</p> |
   | [!UICONTROL Cancel] | Annulla questo filtro rapido (non applicarlo). |
   | [!UICONTROL Date range] | La convalida utilizza l’intervallo di date del pannello per la ricerca dei dati. Tuttavia, qualsiasi intervallo di date applicato in un filtro rapido sostituisce l’intervallo di date del pannello nella parte superiore del pannello. |
   | Anteprima (in alto a destra) | Consente di verificare se si dispone di un filtro valido e la sua ampiezza. Rappresenta il raggruppamento del set di dati che si prevede di visualizzare quando si applica questo filtro. Potresti ricevere un avviso che indica che questo filtro non ha dati. In questo caso, puoi procedere o modificare la definizione del filtro. |

1. Seleziona [!UICONTROL **Applica**] per salvare le modifiche.

## Modificare un filtro rapido {#edit}

1. Passa il puntatore del mouse sul filtro rapido da modificare, quindi seleziona la **Modifica** icona.

   ![Modifica filtro ad hoc](assets/filter-adhoc-edit.png)

1. Modifica la definizione del filtro o il nome del filtro.
1. Seleziona [!UICONTROL **Applica**] per salvare le modifiche.

## Salvare un filtro rapido come filtro elenco di componenti {#save}

>[!IMPORTANT]
>
> Quando salvi un filtro rapido, considera quanto segue:
> 
> * Per salvare un filtro rapido, è necessario disporre dell&#39;autorizzazione Creazione filtro nel [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools).
> 
> * Dopo aver salvato o applicato il filtro, non sarà più possibile modificarlo nel generatore di filtri rapidi. È invece necessario utilizzare il normale Generatore di filtri.


È possibile scegliere di salvare i filtri rapidi come filtri elenco componenti. I vantaggi dei filtri per elenco di componenti includono:

* Disponibilità in tutti i progetti Workspace
* Supporta filtri più complessi e filtri sequenziali

È possibile salvare i filtri sia dal Generatore di filtri rapidi sia dal [!UICONTROL Filter Builder].

### Salva nel generatore di filtri rapidi {#save2}

1. Dopo aver applicato il filtro rapido, passa il puntatore del mouse su di esso e seleziona l’icona info (&quot;i&quot;).
1. Seleziona **[!UICONTROL Make available to all projects and add to your component list]** (Aggiungi gruppi di campi).
1. (Facoltativo) Rinomina il filtro.
1. Seleziona **[!UICONTROL Save]** (Aggiungi gruppi di campi).

   Il filtro viene ora visualizzato nell’elenco dei componenti nella barra a sinistra. Inoltre, la barra laterale del filtro cambia da blu chiaro a blu scuro, il che indica che non può più essere modificata o aperta nel generatore di filtri rapidi.

### Salva nel Generatore filtri {#save3}

1. Dopo aver applicato il filtro rapido, passa il puntatore del mouse su di esso e seleziona l’icona info (&quot;i&quot;).
1. Seleziona **[!UICONTROL Save filter]**
1. (Facoltativo) Rinomina il filtro, quindi seleziona [!UICONTROL **Applica**].

   Torna a Workspace e osserva che la barra laterale del filtro cambia da blu chiaro a blu scuro, per indicare che non può più essere modificata o aperta nel generatore di filtri rapidi. E salvandolo, diventa parte dell&#39;elenco dei componenti.

   ![Elenco dei componenti filtro](assets/quick-seg4.png)

Dopo aver applicato il filtro, puoi scegliere di aggiungerlo all’elenco dei componenti del filtro e renderlo disponibile per tutti i tuoi progetti.

1. Passa il puntatore del mouse sul filtro salvato e seleziona l’icona a forma di matita .

1. Nella parte superiore del Generatore di filtri, notare questa finestra di dialogo:

   ![Finestra di dialogo Filtro](assets/project-only.png)

1. Seleziona la casella di controllo accanto a **[!UICONTROL Make available to all your projects and add to your component list.]**
1. Seleziona **[!UICONTROL Save]** (Crea schema). Il filtro viene ora visualizzato nell’elenco dei componenti filtro per tutti i progetti.
È inoltre possibile [condividere il filtro](/help/components/filters/manage-filters.md) con altre persone della tua organizzazione.

## Esempio di filtro rapido

L’esempio seguente di un filtro combina dimensioni e metriche:

![Esempio di definizione del filtro](assets/quick-seg2.png)

