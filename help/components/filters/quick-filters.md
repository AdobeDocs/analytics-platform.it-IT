---
description: Utilizzare filtri rapidi in Analysis Workspace per il Customer Journey Analytics
title: Filtri rapidi
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 7%

---

# Filtri rapidi

I filtri rapidi consentono di esplorare facilmente i dati all’interno di un determinato progetto, senza la necessità di creare un filtro più complesso per l’elenco dei componenti nel [Generatore di filtri](/help/components/filters/create-filters.md).

Quando crei dei filtri rapidi, tieni presente quanto segue:

* I filtri rapidi si applicano solo al progetto in cui sono stati creati. Non sono disponibili in altri progetti e non possono essere condivisi con altri utenti.
* Sono consentite fino a 3 regole.
* I contenitori nidificati o le regole sequenziali non sono supportati.

Il video seguente illustra come utilizzare i filtri rapidi. (Nota: questo video utilizza il termine &quot;segmenti rapidi&quot; invece di &quot;filtri rapidi&quot;. Tuttavia, la funzionalità è la stessa.)

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Creare un filtro rapido {#create}

Qualsiasi utente in Analysis Workspace può creare un filtro rapido.

Per creare un filtro rapido:

1. Scegliere uno dei metodi seguenti per iniziare a creare il filtro rapido:

   * **Ad hoc (trascinamento della selezione):** Dalla barra a sinistra, trascina un componente nell’area di rilascio accanto a **Filtro** nell’intestazione del pannello, quindi seleziona la **Modifica** per regolare il filtro.

      ![Modifica filtro ad hoc](assets/filter-adhoc-edit.png)

      >[!NOTE]
      >
      > Quando crei un filtro rapido ad hoc (trascinamento della selezione), tieni presente quanto segue:
      > * I seguenti tipi di componenti non sono supportati: metriche calcolate, dimensioni e metriche da cui non è possibile creare i filtri.
      > * Per eventi e dimensioni intere, Analysis Workspace crea dei filtri evento &quot;exists&quot; (esiste). Esempi: `Hit where eVar1 exists` o `Hit where event1 exists`.
      > * Se nella zona di rilascio dei filtri viene rilasciato &quot;Non specificato&quot; o &quot;Nessuno&quot;, vengono automaticamente convertiti in un filtro di tipo &quot;non esiste&quot; in modo da essere trattati correttamente nei filtri.



   * **Utilizzo dell’icona del filtro:** In una tabella a forma libera, seleziona la **Filtro** nell’intestazione del pannello.

      ![Filtro del segmento](assets/quick-seg1.png)

1. Regolare una delle seguenti impostazioni:

   | Impostazione | Descrizione |
   | --- | --- |
   | [!UICONTROL Name] | Il nome predefinito di un filtro è una combinazione dei nomi delle regole nel filtro. Puoi rinominare il filtro in un nome più descrittivo. |
   | [!UICONTROL Include/exclude] | Puoi includere o escludere componenti nella definizione del filtro, ma non entrambi. |
   | Contenitore [!UICONTROL Hit/Visit/Visitor] | I filtri rapidi includono uno [contenitore di filtri](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers) solo che ti consente di includere (o escludere) una dimensione, una metrica o un intervallo di date nel filtro. [!UICONTROL Visitor] contiene i dati generali specifici della persona per visite e visualizzazioni di pagina. A [!UICONTROL Visit] contenitore consente di impostare regole per suddividere i dati della persona in base alle visite e a [!UICONTROL Hit] Il contenitore consente di suddividere le informazioni sulla persona in base alle singole visualizzazioni di pagina. Il valore predefinito è [!UICONTROL Hit]. |
   | [!UICONTROL Components] (Dimension/metrica/intervallo di date) | Definisci fino a 3 regole aggiungendo componenti (dimensioni, metriche, intervalli di date o valori di dimensioni). Ci sono 3 modi per trovare il componente giusto:<ul><li>Inizia a digitare; il generatore di filtri rapidi trova automaticamente il componente appropriato.</li><li>Utilizza l’elenco a discesa per trovare il componente.</li><li>Trascina e rilascia i componenti dalla barra a sinistra.</li></ul> |
   | [!UICONTROL Operator] | Utilizza il menu a discesa per trovare gli operatori standard e gli operatori [!UICONTROL Distinct Count]. Consulta [Operatori filtro](operators.md). |
   | Segno più (+) | Aggiunge un’altra regola, |
   | Qualificatori AND/OR | Puoi aggiungere i qualificatori &quot;AND&quot; o &quot;OR&quot; alle regole, ma non puoi combinare &quot;AND&quot; e &quot;OR&quot; in una singola definizione di filtro. |
   | [!UICONTROL Apply] | Applica questo filtro al pannello. Se il filtro non contiene dati, verrà chiesto se si desidera continuare. |
   | [!UICONTROL Open builder] | Apre il Generatore di filtri. Dopo aver salvato o applicato il filtro nel Generatore di filtri, non viene più considerato un &quot;Filtro rapido&quot;. Diventa parte della libreria di filtri dell’elenco di componenti. <p>Per rendere il componente disponibile in tutti i progetti e nella barra a sinistra, seleziona l’opzione [!UICONTROL **Rendi questo filtro disponibile a tutti i tuoi progetti e aggiungilo all&#39;elenco dei tuoi componenti.**].</p><p>Per ulteriori informazioni, consulta la sezione [Salvare un filtro rapido come filtro per l’elenco dei componenti](#save-a-quick-filter-as-a-component-list-filter) in questo articolo.</p><p>**Nota:** Solo gli utenti con l’autorizzazione Creazione filtro in [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) può aprire il Generatore di filtri.</p> |
   | [!UICONTROL Cancel] | Annulla questo filtro rapido (non applicarlo). |
   | [!UICONTROL Date range] | La convalida utilizza l’intervallo di date del pannello per la ricerca dei dati. Tuttavia, qualsiasi intervallo di date applicato in un filtro rapido sovrascrive l’intervallo di date del pannello nella parte superiore del pannello. |
   | Anteprima (in alto a destra) | Consente di vedere se si dispone di un filtro valido e quanto è ampio il filtro. Rappresenta il raggruppamento del set di dati che dovrebbe essere visualizzato quando applichi questo filtro. Potresti ricevere un avviso che indica che questo filtro non contiene dati. In questo caso, puoi procedere o modificare la definizione del filtro. |

1. Seleziona [!UICONTROL **Applica**] per salvare le modifiche.

## Modificare un filtro rapido {#edit}

1. Passa il puntatore del mouse sul filtro rapido da modificare, quindi seleziona il **Modifica** icona.

   ![Modifica filtro ad hoc](assets/filter-adhoc-edit.png)

1. Modifica la definizione o il nome del filtro.
1. Seleziona [!UICONTROL **Applica**] per salvare le modifiche.

## Salvare un filtro rapido come filtro per l’elenco dei componenti {#save}

>[!IMPORTANT]
>
> Quando salvi un filtro rapido, considera quanto segue:
> 
> * Per salvare un filtro rapido, è necessario disporre dell’autorizzazione Creazione filtro in [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools).
> 
> * Dopo il salvataggio o l’applicazione del filtro, non è più possibile modificarlo nel generatore di filtri rapidi. Invece, devi utilizzare il Generatore di filtri regolare.


Puoi scegliere di salvare i filtri rapidi come filtri per l’elenco dei componenti. I vantaggi dei filtri per l’elenco dei componenti includono:

* Disponibilità in tutti i progetti Workspace
* Supporto di filtri più complessi e di filtri sequenziali

Puoi salvare i filtri dal generatore di filtri rapidi o dal [!UICONTROL Filter Builder].

### Salva nel generatore di filtri rapidi {#save2}

1. Dopo aver applicato il filtro rapido, posiziona il cursore su di esso e seleziona l’icona Info (&quot;i&quot;).
1. Seleziona **[!UICONTROL Make available to all projects and add to your component list]** (Aggiungi gruppi di campi).
1. (Facoltativo) Rinomina il filtro.
1. Seleziona **[!UICONTROL Save]** (Aggiungi gruppi di campi).

   Il filtro viene ora visualizzato nell’elenco dei componenti nella barra a sinistra. Inoltre, la barra laterale del filtro cambia da blu chiaro a blu più scuro, indicando che non può più essere modificata o aperta nel generatore di filtri rapidi.

### Salva nel Generatore di filtri {#save3}

1. Dopo aver applicato il filtro rapido, posiziona il cursore su di esso e seleziona l’icona Info (&quot;i&quot;).
1. Seleziona **[!UICONTROL Save filter]**
1. (Facoltativo) Rinomina il filtro, quindi seleziona [!UICONTROL **Applica**].

   Torna a Workspace e osserva che la barra laterale del filtro cambia da blu chiaro a blu scuro, indicando che non può più essere modificata o aperta nel generatore di filtri rapidi. E salvandolo, diventa parte dell&#39;elenco dei componenti.

   ![Filtra elenco componenti](assets/quick-seg4.png)

Dopo aver applicato il filtro, puoi scegliere di aggiungerlo all’elenco dei componenti del filtro e renderlo disponibile per tutti i progetti.

1. Passa il puntatore del mouse sul filtro salvato e seleziona l’icona della matita.

1. Seleziona [!UICONTROL **Apri generatore**].

1. Nella parte superiore del Generatore di filtri, osserva questa finestra di dialogo:

   ![Finestra di dialogo Filtro](assets/project-only-filter-dialog.png)

1. Seleziona la casella di controllo accanto a **[!UICONTROL Make this filtr available to all your projects and add it to your component list.]**

1. Seleziona **[!UICONTROL Save]** (Aggiungi gruppi di campi).

   Il filtro viene ora visualizzato nell’elenco dei componenti del filtro per tutti i progetti.
È inoltre possibile [condividere il filtro](/help/components/filters/manage-filters.md) con altre persone della tua organizzazione.

## Esempio di filtro rapido

Il seguente esempio di filtro combina dimensioni e metriche:

![Esempio di definizione del filtro](assets/quick-seg2.png)

