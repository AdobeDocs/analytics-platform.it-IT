---
title: Creare annotazioni
description: Come creare le annotazioni in Workspace.
role: User, Admin
feature: Components
exl-id: 3cf9a0fd-11c9-4375-8bbe-9551ba86f86d
source-git-commit: 7164c90fe50434a07db8154de173c3c7d8e5cb14
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 88%

---

# Creare annotazioni

1. Per creare le annotazioni, è possibile iniziare in diversi modi:

| Metodo di creazione | Dettagli |
| --- | --- |
| **Vai a [!UICONTROL Components] > [!UICONTROL Annotation].** | Viene visualizzata la pagina di gestione Annotazioni. Fai clic su [!UICONTROL Create New Annotation] per aprire [!UICONTROL Annotation builder]. |
| **Fai clic con il pulsante destro del mouse su un punto di una tabella.** | Verrà visualizzato [!UICONTROL The Annotation builder]. Per impostazione predefinita, le annotazioni create in questo modo sono visibili solo nel progetto in cui sono state create. Tuttavia puoi renderle disponibili in tutti i progetti. Nota inoltre che le date, le metriche e altri dati sono già stati popolati.<p>![](assets/annotate-table.png) |
| **Fai clic con il pulsante destro del mouse su un punto in un grafico a [!UICONTROL Line].** | Verrà visualizzato [!UICONTROL Annotation builder]. Per impostazione predefinita, le annotazioni create in questo modo sono visibili solo nel progetto in cui sono state create. Tuttavia puoi renderle disponibili in tutti i progetti. Nota inoltre che le date, le metriche e altri dati sono già stati popolati.<p>![](assets/annotate-line.png) |
| **In Workspace, vai a [!UICONTROL Components] > [!UICONTROL Create annotation].** | Verrà visualizzato [!UICONTROL Annotation builder]. |
| **Usa questo tasto di scelta rapida** per aprire il generatore Annotazioni: (PC) `ctrl` `shift` + o, (Mac) `shift` + `command` + o | Tieni presente che utilizzando il tasto di scelta rapida per creare un’annotazione, puoi creare un’annotazione per un singolo giorno per la data corrente, senza alcun ambito preselezionato (metriche o dimensioni). |
| **Utilizza la [API per le annotazioni CJA](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | Le API delle annotazioni CJA consentono di creare, aggiornare o recuperare le annotazioni a livello di programmazione tramite Adobe Developer. Queste API utilizzano gli stessi dati e metodi utilizzati da Adobe all&#39;interno dell&#39;interfaccia utente del prodotto. |

1. Compila gli elementi di [!UICONTROL Annotation builder].

   ![](assets/ann-builder.png)

   | Elemento | Descrizione |
   | --- | --- |
   | [!UICONTROL Title] | Assegna un nome all’annotazione, ad esempio “giorno della memoria” |
   | [!UICONTROL Description] | (Facoltativo) Aggiungi una descrizione dell’annotazione, ad esempio “festa nazionale degli Stati Uniti d’America”. |
   | [!UICONTROL Tags] | (Facoltativo) Organizza le annotazioni creando o applicando un tag. |
   | [!UICONTROL Applied date] | Seleziona la data o l’intervallo di date che è necessario riportare per rendere visibile l’annotazione. |
   | [!UICONTROL Color] | Applica un colore all’annotazione. L’annotazione viene visualizzata nel progetto con il colore selezionato. Il colore può essere utilizzato per classificare le annotazioni, ad esempio festività pubbliche, eventi esterni, problemi di tracciamento e così via. |
   | [!UICONTROL Scope] | (Facoltativo) Trascina le metriche che attivano l’annotazione. Trascina quindi eventuali dimensioni o segmenti che agiscono da filtri (ad esempio, con cui sarà visibile l’annotazione). Se non specifichi alcun ambito, l’annotazione verrà applicata a tutti i dati.<ul><li>**[!UICONTROL Any of these metrics are present]**: trascina fino a 10 metriche per attivare l’annotazione da mostrare.</li><li>**[!UICONTROL With all of these filters]**: trascina fino a 10 dimensioni o segmenti per filtrare quando viene visualizzata l’annotazione.</li></ul><p>Casi d’uso: un eVar ha interrotto la raccolta dei dati per un intervallo di date specifico. Trascina l’eVar nella finestra di dialogo **[!UICONTROL Any of these metrics are present]**. O nel caso in cui la metrica [!UICONTROL Visits] non riporti alcun dato, segui la stessa procedura.<p>**Nota:** qualsiasi annotazione applicata a un componente che viene in seguito utilizzata come parte di una metrica calcolata o di una definizione di segmento, NON eredita automaticamente l’annotazione. Per visualizzare l’annotazione è necessario aggiungere alla sezione dell’ambito anche la metrica calcolata desiderata. È tuttavia necessario creare una nuova annotazione per qualsiasi segmento a cui desideri aggiungere le stesse informazioni.<p>Esempio: hai applicato un’annotazione a [!UICONTROL Orders] in un giorno specifico. In seguito utilizzi [!UICONTROL Orders] in una metrica calcolata per lo stesso intervallo di date. La nuova metrica calcolata non visualizza automaticamente l’annotazione per gli ordini; per consentirne la visualizzazione, la metrica calcolata deve essere aggiunta anche alla sezione ambito. |
   | [!UICONTROL Apply to all report suites] | Per impostazione predefinita, l’annotazione si applica alla suite di rapporti di origine. Selezionando questa casella, puoi applicare l’annotazione a tutte le suite di rapporti dell’azienda. |
   | [!UICONTROL Apply to all projects] | Per impostazione predefinita, l’annotazione si applica al progetto corrente. Selezionando questa casella, puoi applicare l’annotazione a tutti i progetti di tua proprietà. Questa casella di controllo viene visualizzata solo quando si avvia il Generatore di annotazioni dal Generatore di annotazioni? |

   {style=&quot;table-layout:auto&quot;}

1. Fai clic su **[!UICONTROL Save]**.
