---
title: Creare annotazioni
description: Come creare annotazioni in Workspace.
role: User, Admin
feature: Components
exl-id: 3cf9a0fd-11c9-4375-8bbe-9551ba86f86d
source-git-commit: 7164c90fe50434a07db8154de173c3c7d8e5cb14
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 100%

---

# Creare annotazioni

1. Per creare le annotazioni, è possibile iniziare in diversi modi:

| Metodo di creazione | Dettagli |
| --- | --- |
| **Vai a [!UICONTROL Components] > [!UICONTROL Annotation].** | Viene visualizzata la pagina Annotations Manager (Gestione annotazioni). Fai clic su [!UICONTROL Create New Annotation]; viene aperto [!UICONTROL Annotation builder]. |
| **Fai clic con il pulsante destro del mouse su un punto di una tabella.** | Viene aperto [!UICONTROL The Annotation builder]. Per impostazione predefinita, le annotazioni create in questo modo sono visibili solo nel progetto in cui sono state create. Ma puoi renderle disponibili in tutti i progetti. Inoltre, le date, le metriche e così via sono già state compilate.<p>![](assets/annotate-table.png) |
| **Fai clic con il pulsante destro del mouse su un punto in un grafico [!UICONTROL Line].** | Viene aperto [!UICONTROL Annotation builder]. Per impostazione predefinita, le annotazioni create in questo modo sono visibili solo nel progetto in cui sono state create. Ma puoi renderle disponibili in tutti i progetti. Inoltre, le date, le metriche e così via sono già state compilate.<p>![](assets/annotate-line.png) |
| **In Workspace, vai a [!UICONTROL Components] > [!UICONTROL Create annotation].** | Viene aperto [!UICONTROL Annotation builder]. |
| **Usa questa scelta rapida da tastiera** per aprire il generatore di annotazioni: (PC) `ctrl` `shift` + o, (Mac) `shift` + `command` + o | Tieni presente che, se utilizzi la scelta rapida da tastiera, puoi creare un’annotazione per un singolo giorno alla data corrente, e non viene preselezionato alcun ambito (metriche o dimensioni). |
| **Utilizzare le [API per annotazioni CJA](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | Le API per annotazioni CJA consentono di creare, aggiornare o recuperare le annotazioni a livello di programmazione tramite Adobe Developer. Queste API utilizzano gli stessi dati e metodi utilizzati da Adobe nell’interfaccia utente del prodotto. |

1. Compila gli elementi di [!UICONTROL Annotation builder].

   ![](assets/ann-builder.png)

   | Elemento | Descrizione |
   | --- | --- |
   | [!UICONTROL Title] | Nome dell’annotazione, ad esempio “Memorial Day” |
   | [!UICONTROL Description] | (Facoltativo) Specifica una descrizione dell’annotazione, ad esempio “Festività negli Stati Uniti”. |
   | [!UICONTROL Tags] | (Facoltativo) Organizza le annotazioni creando o applicando un tag. |
   | [!UICONTROL Applied date] | Seleziona la data o l’intervallo di date in cui l’annotazione sarà visibile. |
   | [!UICONTROL Color] | Applica un colore all’annotazione. L’annotazione viene visualizzata nel progetto con il colore selezionato. Puoi scegliere colori diversi per diverse categorie di annotazioni, ad esempio festività, eventi esterni, problemi di tracciamento, ecc. |
   | [!UICONTROL Scope] | (Facoltativo) Trascina le metriche che determinano l’attivazione dell’annotazione. Trascina quindi eventuali dimensioni o segmenti che fungano da filtri, per determinare quando l’annotazione sarà visibile. Se non specifichi un ambito, l’annotazione verrà applicata a tutti i dati.<ul><li>**[!UICONTROL Any of these metrics are present]**: trascina fino a 10 metriche per attivare la visualizzazione dell’annotazione.</li><li>**[!UICONTROL With all of these filters]**: trascina fino a 10 dimensioni o segmenti da usare come filtri, per determinare quando viene visualizzata l’annotazione.</li></ul><p>Casi d’uso: un eVar ha interrotto la raccolta dei dati per un particolare intervallo di date. Trascina l’eVar nella finestra di dialogo **[!UICONTROL Any of these metrics are present]**. Oppure: la metrica [!UICONTROL Visits] non riporta alcun dato; segui la stessa procedura.<p>**Nota:** un’annotazione applicata a un componente e quindi utilizzata come parte di una metrica calcolata o di una definizione di segmento NON eredita automaticamente l’annotazione. Per visualizzare l’annotazione, è necessario aggiungere alla sezione dell’ambito anche la metrica calcolata desiderata. Tuttavia, è necessario creare una nuova annotazione per ogni segmento a cui si desidera aggiungere le stesse informazioni.<p>Esempio: hai applicato un’annotazione a [!UICONTROL Orders] in un giorno specifico. Quindi utilizzi [!UICONTROL Orders] in una metrica calcolata per lo stesso intervallo di date. La nuova metrica calcolata non visualizza automaticamente l’annotazione per gli ordini; affinché venga visualizzata l’annotazione, la metrica calcolata deve essere aggiunta anche alla sezione ambito. |
   | [!UICONTROL Apply to all report suites] | Per impostazione predefinita, l’annotazione è applicabile alla suite di rapporti di origine. Selezionando questa casella, l’annotazione viene applicata a tutte le suite di rapporti dell’azienda. |
   | [!UICONTROL Apply to all projects] | Per impostazione predefinita, l’annotazione è applicabile al progetto corrente. Selezionando questa casella, l’annotazione viene applicata a tutti i tuoi progetti. Questa casella di controllo è disponibile solo quando si avvia il generatore di annotazioni dal Generatore di annotazioni? |

   {style=&quot;table-layout:auto&quot;}

1. Fai clic su **[!UICONTROL Save]**.
