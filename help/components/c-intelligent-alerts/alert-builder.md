---
description: Scopri come creare avvisi in Analysis Workspace.
title: Creare avvisi
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 67%

---

# Creare avvisi {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularità temporale"
>abstract="Per granularità temporale si intende la frequenza con cui viene controllato l’avviso."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>L’utilizzo degli avvisi con rilevamento delle anomalie (noti anche come _avvisi intelligenti_) è disponibile solo per le organizzazioni con un pacchetto Customer Journey Analytics Prime o Ultimate.

Gli avvisi in Customer Journey Analytics ti consentono di ricevere notifiche in base a percentuali di modifica o a punti dati specifici. A seconda del pacchetto di Customer Journey Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie.

Per informazioni più dettagliate sugli avvisi, vedere [Panoramica avvisi](/help/components/c-intelligent-alerts/intelligent-alerts.md).

Per creare un avviso:

<!-- Note that there are difference in how alerts are created in CJA vs AA. In AA you can create alerts from the Workspace menu and using a shortcut; these are not possible in CJA... -->

1. In Customer Journey Analytics, selezionare **[!UICONTROL Components]** > **[!UICONTROL Alerts]**. In [Gestione avvisi](alert-manager.md), seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** per creare un nuovo avviso oppure seleziona uno degli avvisi elencati per modificarne uno esistente.

   Viene visualizzata l’interfaccia del [Generatore di avvisi](#alert-builder).

1. Seleziona **[!UICONTROL Save]** per salvare l’avviso. Seleziona **[!UICONTROL Save as]** per salvare una copia dell’avviso.


## Generatore di avvisi

L’interfaccia del Generatore di avvisi è familiare a quella utilizzata per creare segmenti o metriche calcolate in Customer Journey Analytics:

![Interfaccia generatore di avvisi](assets/alert-builder.png)

Specifica i seguenti dettagli nel generatore di avvisi per un avviso:

| Elemento | Descrizione |
|---------|----------|
| **[!UICONTROL Title]** | Inserisci un nome per l’avviso. Il nome può contenere il nome del rapporto o la soglia di metrica. |
| **[!UICONTROL Description (optional)]** | Inserisci una descrizione per l’avviso. |
| **[!UICONTROL Time granularity]** | Specifica quanto spesso desideri che la metrica sia controllata: ogni giorno, settimana o mese.<p><b>Nota</b>: per le visualizzazioni dati con un [calendario personalizzato](/help/data-views/create-dataview.md#calendar), la granularità mensile non è supportata nel generatore di avvisi.<!--true?--></p> |
| **[!UICONTROL Recipients]** | Specifica a chi deve essere inviato l’avviso. Può essere inviato a un utente o un gruppo di Analytics, a un indirizzo e-mail o a un numero telefonico.<p><b>Importante</b>: il numero di telefono deve essere preceduto da un `+` e da un [codice paese](https://countrycode.org/).</p><p>L’e-mail che un utente riceve dopo un avviso:</p><p>![E-mail avviso](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Expiration date]** | Imposta la data e l’ora di scadenza dell’avviso. |
| **[!UICONTROL Delay]** | Il tempo necessario prima che i dati siano completi e disponibili per essere inseriti in Customer Journey Analytics varia a seconda dell’organizzazione, in genere da 3 a 9 ore dopo l’ora dell’evento dati. Affinché gli avvisi siano precisi, i dati evento per un determinato intervallo di eventi devono essere completi, il che significa che Adobe non riceve più i dati evento per l’intervallo di eventi specificato.<p>Per tenere conto di questo ritardo nel tempo di acquisizione, gli avvisi hanno un ritardo predefinito di 9 ore prima di essere inviati.</p><p>Puoi impostare il ritardo predefinito di 9 ore su qualsiasi valore compreso tra 0 e 24 ore. Tuttavia, la riduzione del ritardo al di sotto di 9 ore può significare che stai eseguendo un rapporto con dati incompleti, il che si traduce in informazioni di avviso imprecise.</p><p>Quando configuri la riduzione del ritardo, tieni presente quanto segue:</p><ul><li>**Comprendere la disponibilità dei dati rispetto alla completezza dei dati**: i dati batch vengono acquisiti in un set di dati Experience Platform solo dopo un periodo di 3-9 ore. Affinché gli avvisi siano precisi, l’acquisizione dei dati deve essere completa, con tutti i dati batch disponibili nel set di dati.</li><li>**Determina il tempo necessario per il completamento e la disponibilità dei dati nel set di dati**: i tempi di acquisizione dei dati variano a seconda dell’organizzazione. Verifica che il ritardo scelto per la consegna degli avvisi sia lo stesso o meno frequente del tempo necessario per rendere disponibili i dati batch nel set di dati di Platform<!--add link? -->.</li><p>**Suggerimento:** Il modo più accurato per conoscere il tempo necessario per il completamento e l&#39;acquisizione di tutti i dati batch nel set di dati di Experience Platform consiste nel consultare i data engineer della tua organizzazione.</p><p>In alternativa, puoi avere un’idea generale di quanto tempo ci vuole affinché la consegna batch nell’organizzazione sia disponibile nel set di dati di Platform. Crea la seguente tabella a forma libera in Analysis Workspace:</p><ol><li>In una tabella a forma libera in Analysis Workspace, aggiungi una metrica [!UICONTROL **Eventi**] e una dimensione [!UICONTROL **Giorno**].</li><li>Suddividi la dimensione [!UICONTROL **Giorno**] utilizzando una dimensione [!UICONTROL **Ore**].<p>Le ore senza dati vengono visualizzate come 0.</p></li></ol><li>**Conto degli errori nei calcoli**: se riduci il ritardo predefinito, configura il ritardo per almeno un&#39;ora in più rispetto al tempo necessario all&#39;organizzazione per completare l&#39;acquisizione dei dati. Ad esempio, in caso di ritardo di 3 ore prima del completamento dell’acquisizione dei dati, imposta il ritardo su 4 ore.</li></ul><p>Per ulteriori informazioni, consulta [Tempi di acquisizione dati in Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) nell’articolo [Confronto delle funzionalità degli avvisi: Customer Journey Analytics e Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Send an alert when]** | [!UICONTROL **Uno di questi trigger di metriche**]: trascina le metriche (comprese le metriche calcolate) qui per creare trigger per l’avviso.<p>Se non tutte le metriche, dimensioni o segmenti nell’avviso sono compatibili con la visualizzazione dati selezionata, compare un messaggio **“componenti non compatibili”**.</p><p>Determina la soglia che dovrà essere superata affinché venga attivato l’avviso. Puoi impostare questo valore su una soglia e quindi su una delle seguenti condizioni:</p><ul><li>anomaly exists (l’anomalia esiste)</li><li>anomaly is above expected (l’anomalia supera il valore previsto)</li><li>anomaly is below expected (l’anomalia è inferiore al valore previsto)</li><li>is above or equals (è superiore o uguale a)</li><li>is below or equals (è inferiore o uguale a)</li><li>changes by (cambia di)</li><li>Puoi impostare una soglia di 90%, 95%, 99%, 99,75% o 99,9%.</li></ul><p>[!UICONTROL **Con tutti questi filtri**]: trascina segmenti o dimensioni per aggiungere filtri all&#39;avviso. Ad esempio, l&#39;aggiunta di un segmento *Solo dispositivi mobili* implica che la regola viene attivata solo per i dispositivi mobili. Puoi aggiungere altri filtri utilizzando un’istruzione AND. Per aggiungere una regola AND o OR, fai clic sull’icona a forma di ingranaggio.</p><p>Vedi [Avvisi - Casi d&#39;uso](/help/components/c-intelligent-alerts/alerts-use-cases.md).</p> |
| **[!UICONTROL Preview]** | L’anteprima interattiva degli avvisi mostra la frequenza con cui, approssimativamente, un avviso viene attivato in base all’esperienza passata.<p>Ad esempio, se imposti la granularità su Ogni giorno, l’anteprima indicherà che l’avviso è stato attivato x volte per una specifica metrica negli ultimi 30 o 31 giorni.</p><p>Se vengono attivati troppi avvisi, è possibile regolare la soglia in [Gestisci avvisi](/help/components/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |
