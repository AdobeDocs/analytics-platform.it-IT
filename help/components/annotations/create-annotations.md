---
title: Creare annotazioni
description: Come creare annotazioni in Workspace.
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 18%

---

# Creare annotazioni

Per impostazione predefinita, solo gli amministratori possono creare annotazioni. Gli utenti dispongono delle autorizzazioni per visualizzare le annotazioni, in modo analogo a come visualizzano altri componenti (come filtri, metriche calcolate e così via).

Tuttavia, gli amministratori possono assegnare l&#39;autorizzazione **[!UICONTROL Annotation Creation]** per **[!UICONTROL Reporting Tools]** in **[!UICONTROL Edit permissions for CJA Workspace Access]** agli utenti tramite l&#39;Admin Console. Per ulteriori informazioni, vedere [Controllo dell&#39;accesso a livello utente](/help/technotes/access-control.md#user-level-access).

È possibile creare un’annotazione nei modi seguenti:

![Creare un’annotazione](assets/create-annotation.png)

* ?? Nell&#39;interfaccia principale, selezionare **[!UICONTROL Components]** e selezionare **[!UICONTROL Annotations]**. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] dal gestore [[!UICONTROL Annotations]](/help/components/annotations/manage-annotations.md).
* ?? In un progetto Workspace, dal menu di scelta rapida di una visualizzazione, selezionare **[!UICONTROL Create annotation from selection]**.
* ?? In un progetto Workspace, dal menu di scelta rapida in un grafico a linee, selezionare **[!UICONTROL Annotate Selection]**.
* ??In un progetto Workspace, selezionare **[!UICONTROL Components]** dal menu e selezionare **[!UICONTROL Create annotation]**.
* ?? In un progetto Workspace, utilizzare il collegamento **[!UICONTROL ctrl+shift+o]** (Windows) o **[!UICONTROL shift+command+o]** (macOS)

Per definire l&#39;annotazione, utilizzare [[!UICONTROL Annotation builder]](#annotation-builder):

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Generatore di annotazioni {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_details"
>title="Dettagli annotazione"
>abstract="Le annotazioni consentono di comunicare in modo efficace dettagli sui dati contestuali a beneficio degli utenti in tutta l’organizzazione. Consentono di collegare gli eventi del calendario a dimensioni o metriche specifiche."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_scope"
>title="Portata"
>abstract="L’ambito ti consente di personalizzare i dati sui quali aggiungere annotazioni. Le metriche calcolate e i segmenti non ereditano automaticamente le annotazioni applicate ai componenti utilizzati nelle loro definizioni. Puoi aggiungere nuove metriche calcolate alla sezione dell’ambito di un’annotazione esistente. I nuovi segmenti richiedono una nuova annotazione."

<!-- markdownlint-enable MD034 -->


La finestra di dialogo **[!UICONTROL Annotations builder]** viene utilizzata per creare nuove annotazioni o modificare quelle esistenti. La finestra di dialogo si chiama **[!UICONTROL New annotation]** o **[!UICONTROL Edit annotation]** per le annotazioni create o gestite dal gestore [[!UICONTROL Annotations]](/help/components/annotations/manage-annotations.md).


>[!BEGINTABS]

>[!TAB Generatore di annotazioni]

![Finestra dei dettagli dell’annotazione con i campi e le opzioni descritti nella sezione successiva.](assets/annotation-builder.png)

>[!TAB Crea/Modifica annotazione]

![Finestra dei dettagli dell’annotazione con i campi e le opzioni descritti nella sezione successiva.](assets/create-edit-annotation.png)

>[!ENDTABS]

1. Specificare i dettagli seguenti (![Obbligatorio](/help/assets/icons/Required.svg) è obbligatorio):

   | Elemento | Descrizione |
   | --- | --- |
   | **[!UICONTROL Data view]** | Puoi selezionare la visualizzazione dati per l’annotazione. L’annotazione definita è disponibile come annotazione nei progetti Workspace in base alla visualizzazione dati selezionata. Questa selezione viene annullata se hai abilitato [!UICONTROL Apply to all data views]. |
   | **[!UICONTROL Project-only Annotation]** | Una casella di informazioni per spiegare che l’annotazione creata è visibile solo nel progetto Workspace su cui stai lavorando. Abilita **[!UICONTROL Make this Annotation available to all your projects]** per rendere l&#39;annotazione visibile a tutti i tuoi progetti. Questa casella di informazioni è visibile solo quando crei un’annotazione dall’interno di un progetto Workspace. |
   | **[!UICONTROL Title]** ![Obbligatorio](/help/assets/icons/Required.svg) | Denomina l&#39;annotazione, ad esempio `Needs further investigation`. |
   | **[!UICONTROL Description]** | Fornire una descrizione per l&#39;annotazione, ad esempio `We never expected such a fluctuation in numbers.`. |
   | **[!UICONTROL Tags]** | Organizza l’annotazione creando o applicando uno o più tag. Inizia a digitare per trovare i tag esistenti che puoi selezionare. Oppure premi **[!UICONTROL Enter]** per aggiungere un nuovo tag. Selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un tag. |
   | **[!UICONTROL Applied date]** ![Obbligatorio](/help/assets/icons/Required.svg) | Seleziona la data o l’intervallo di date in cui l’annotazione deve essere visibile. Quando crei un’annotazione utilizzando il collegamento, per impostazione predefinita l’annotazione viene impostata su un intervallo di dati relativo solo al giorno. Quando crei un’annotazione utilizzando una selezione in una visualizzazione, per impostazione predefinita l’annotazione si basa sull’intervallo di dati del pannello a cui appartiene la visualizzazione. |
   | **[!UICONTROL Color]** | Applica un colore all’annotazione. L’annotazione viene visualizzata nel progetto con il colore selezionato. Puoi scegliere colori diversi per diverse categorie di annotazioni, ad esempio festività, eventi esterni, problemi di tracciamento, ecc. |
   | **[!UICONTROL Scope]** | Trascina e rilascia le metriche dal pannello dei componenti che attivano l’annotazione. Ad esempio persone, sessioni ed eventi. Trascina quindi dal pannello dei componenti le dimensioni o i filtri che fungono da filtri per determinare se visualizzare o meno l’annotazione. Se non specifichi un ambito, l’annotazione viene applicata a tutti i dati. <br/>Sono disponibili due opzioni:<ul><li>**[!UICONTROL Any of these metrics are present]**: trascina fino a 10 metriche per attivare la visualizzazione dell&#39;annotazione.<br/>Ad esempio, la metrica Ricavi ha interrotto la raccolta dei dati per un intervallo di date specifico. Trascina la metrica Ricavi in questa casella.</li><li>**[!UICONTROL With all of these filters]**: trascina fino a 10 dimensioni o filtri per filtrare la visualizzazione dell&#39;annotazione.</li></ul><p><p>**Nota:** qualsiasi annotazione applicata a un componente e successivamente utilizzata come parte di una metrica calcolata o di una definizione di filtro NON eredita automaticamente l&#39;annotazione. Per visualizzare l’annotazione, è necessario aggiungere alla sezione dell’ambito anche la metrica calcolata desiderata. Tuttavia, è necessario creare una nuova annotazione per qualsiasi filtro a cui si desidera aggiungere le stesse informazioni. Ad esempio, si applica un&#39;annotazione a [!UICONTROL Orders] in un giorno specifico. Quindi utilizzi [!UICONTROL Orders] in una metrica calcolata per lo stesso intervallo di date. La nuova metrica calcolata non visualizza automaticamente l’annotazione per gli ordini. Aggiungi anche la metrica calcolata alla sezione dell’ambito per l’annotazione da visualizzare. |
   | **[!UICONTROL Apply to all data views]** | Per impostazione predefinita, l’annotazione si applica alla visualizzazione dati di origine. Selezionando questa casella, l’annotazione viene applicata a tutte le visualizzazioni dati dell’azienda. |

   {style="table-layout:auto"}

1. Seleziona
   * **[!UICONTROL Save]** per salvare l&#39;annotazione.
   * **[!UICONTROL Save As]** per salvare una copia dell&#39;annotazione.
   * **[!UICONTROL Delete]** per eliminare un&#39;annotazione.
   * **[!UICONTROL Cancel]** per annullare le modifiche apportate a un&#39;annotazione o per annullare la creazione di una nuova annotazione.
