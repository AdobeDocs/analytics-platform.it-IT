---
description: Utilizza filtri rapidi in Analysis Workspace.
title: Filtri rapidi
feature: Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 300bc4069b77b62ae13fd5baf2eec5846676fc6e
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 1%

---

# Filtri rapidi

Puoi creare filtri rapidi all’interno di un progetto per ignorare la complessità del [Generatore di filtri](/help/components/filters/create-filters.md) completo. Filtri rapidi

* Applicabile solo ai progetti in cui sono stati creati (è possibile modificare questa opzione).
* Consenti fino a 3 regole
* Non inserire contenitori nidificati o regole sequenziali.
* Lavora in progetti con più suite di rapporti

Per un confronto tra ciò che i filtri rapidi possono fare e i filtri completi dell&#39;elenco dei componenti, vai [qui](/help/components/filters/filters-overview.md).

>[!IMPORTANT]
> I filtri rapidi sono attualmente in fase di test limitati e non sono ancora disponibili in genere.

## Prerequisiti

Per creare filtri rapidi, gli utenti devono disporre dell’ autorizzazione [!UICONTROL Segment Creation] in [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) .

## Creare filtri rapidi

In una tabella a forma libera, fai clic sull’icona del filtro+ nell’intestazione del pannello:

![](assets/quick-seg1.png)

| Impostazione | Descrizione |
| --- | --- |
| Nome | Il nome predefinito di un filtro è una combinazione dei nomi delle regole nel filtro. È possibile rinominare il filtro in un nome più semplice. |
| Includi/escludi | Puoi includere o escludere componenti nella definizione del filtro, ma non entrambi. |
| Contenitore Hit/Visita/Visitatore | I filtri rapidi includono un solo [contenitore filtro](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) che consente di includere una dimensione/metrica/intervallo di date nel filtro (o escluderlo da esso). [!UICONTROL Visitor] contiene i dati generali specifici del visitatore per visite e visualizzazioni di pagina. Un contenitore [!UICONTROL Visit] consente di impostare regole per suddividere i dati del visitatore in base alle visite e un contenitore [!UICONTROL Hit] consente di suddividere le informazioni del visitatore in base alle singole visualizzazioni di pagina. Il contenitore predefinito è [!UICONTROL Hit]. |
| Componenti (Dimension/metrica/intervallo di date) | Definisci fino a 3 regole aggiungendo dimensioni e/o metriche dei componenti e/o intervalli di date e relativi valori. Ci sono 3 modi per trovare il componente giusto:<ul><li>Inizia a digitare e il generatore [!UICONTROL Quick Filter] trova automaticamente il componente appropriato.</li><li>Utilizza l’elenco a discesa per trovare il componente.</li><li>Trascina i componenti dalla barra a sinistra.</li></ul> |
| Operatore | Utilizza il menu a discesa per trovare gli operatori standard e gli operatori [!UICONTROL Distinct Count] . [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/components/filteration/segment-reference/seg-operators.html?lang=en) |
| Segno più (+) | Aggiungi un&#39;altra regola |
| Qualificatori AND/OR | Puoi aggiungere i qualificatori &quot;AND&quot; o &quot;OR&quot; alle regole, ma non puoi combinare &quot;AND&quot; e &quot;OR&quot; in una singola definizione di filtro. |
| Applica | Applica questo filtro al pannello. Se il filtro non contiene dati, ti verrà chiesto se desideri continuare. |
| Open builder | Apre il Generatore di filtri. Una volta salvato il filtro nel Generatore di filtri, non viene più considerato un &quot;Filtro rapido&quot;. Diventa parte della libreria di filtri per elenchi di componenti. |
| Annulla | Annulla questo filtro rapido - non applicarlo. |
| Intervallo date | La convalida utilizza l&#39;intervallo di date del pannello per la ricerca dei dati. Tuttavia, qualsiasi intervallo di date applicato in un filtro rapido sostituisce l’intervallo di date del pannello nella parte superiore del pannello. |
| Anteprima (in alto a destra) | Consente di verificare se si dispone di un filtro valido e la sua ampiezza. Rappresenta il raggruppamento del set di dati che si prevede di visualizzare quando si applica questo filtro. potresti ricevere un avviso che indica che questo filtro non ha dati. Puoi procedere o modificare la definizione del filtro. |

Ecco un esempio di filtro che combina dimensioni e metriche:

![](assets/quick-seg2.png)

Il filtro viene visualizzato nella parte superiore. Osserva la sua barra laterale a strisce blu, invece della barra laterale blu per i filtri a livello di componente nella libreria dei filtri a sinistra.

![](assets/quick-seg3.png)

## Modificare i filtri rapidi

1. Passa il puntatore del mouse sul filtro rapido e seleziona l’icona a forma di matita .
1. Modifica la definizione del filtro o il nome del filtro.

## Salvare i filtri rapidi

È possibile scegliere di salvare i filtri rapidi sia in [!UICONTROL Quick Filter Builder] che in [!UICONTROL Filter Builder].

>[!IMPORTANT]
>Una volta salvato o applicato il filtro, non è più possibile modificarlo nel Generatore di filtri rapidi, solo nel Generatore di filtri regolare.

### Salva nel generatore di filtri rapidi

1. Dopo aver applicato il filtro rapido, passa il cursore sopra di esso e seleziona l’icona info (&quot;i&quot;).
1. Fai clic su **[!UICONTROL Make available to all projects and add to your component list]**.
1. (Facoltativo) Rinomina il filtro.
1. Fai clic su **[!UICONTROL Save]**.

La barra laterale del filtro cambia da blu a blu a righe. Ora viene visualizzato nell’elenco dei componenti nella barra a sinistra.

### Salva nel generatore di filtri

1. Passa il puntatore del mouse sul filtro rapido e seleziona l’icona Info (&quot;i&quot;).
1. Select **[!UICONTROL Save filter]**
1. Lascia il nome così com’è o rinomina il filtro.

   Torna a Workspace e osserva come il filtro ora ha una barra laterale blu. Questo indica che non è più possibile modificarlo o aprirlo nel Generatore di filtri rapidi. E salvandolo, diventa parte dell&#39;elenco dei componenti.

   ![](assets/quick-seg4.png)

Dopo aver applicato il filtro, puoi scegliere di aggiungerlo all’elenco dei componenti del filtro e renderlo disponibile per tutti i tuoi progetti.

1. Passa il puntatore del mouse sul filtro salvato e seleziona l’icona a forma di matita .

1. Nella parte superiore del Generatore di filtri, notare questa finestra di dialogo:

   ![](assets/project-only.png)

1. Seleziona la casella di controllo accanto a **[!UICONTROL Make available to all your projects and add to your component list.]**
1. Fai clic su **[!UICONTROL Save]**.
1. Il filtro viene ora visualizzato nell’elenco dei componenti filtro per tutti i progetti.
1. Puoi anche [condividere il filtro](/help/components/filters/manage-filters.md) con altre persone dell&#39;organizzazione.

## Cosa sono i filtri per soli progetti?

I filtri solo progetto sono filtri rapidi o filtri di progetto ad hoc di Workspace. Quando li modifico li aprite in [!UICONTROL Filter Builder], viene visualizzata la casella solo progetto. Se applichi un filtro rapido nel generatore ma non selezioni la casella rendi disponibile, si tratta comunque di un filtro solo progetto ma non può più essere aperto nel [!UICONTROL Quick Filter Builder]. Se selezioni la casella e fai clic su **[!UICONTROL SAVE]**, ora è un filtro per l’elenco dei componenti.
