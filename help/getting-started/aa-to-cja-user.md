---
title: Guida utente di CJA per gli utenti di Adobe Analytics
description: Cosa considerare dal punto di vista di un utente quando l’azienda sposta i dati da Adobe Analytics al Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 30e02f8865daea5d0f6a669f84714abec25ecd76
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 5%

---

# Guida utente di CJA per gli utenti di Adobe Analytics

Se la tua organizzazione sta iniziando a utilizzare il Customer Journey Analytics , potresti notare alcune somiglianze e differenze tra Analytics tradizionale e CJA. Questa pagina ha lo scopo di spiegare queste differenze per aiutare ad adeguare la tua organizzazione al nuovo flusso di lavoro di implementazione e reporting. Questa pagina fornisce anche risorse aggiuntive sui nuovi concetti e ulteriori passaggi per rendere il percorso come analista più semplice e di successo.

Diverse funzioni della CJA sono state rinominate e riprogettate per essere in linea con gli standard di settore. Alcuni termini aggiornati includono segmenti, suite di rapporti virtuali, classificazioni, attributi cliente e nomi di contenitori. Le limitazioni di eVar e proprietà non esistono più, a favore di dimensioni e metriche personalizzate flessibili.

## Cosa non è cambiato

Gran parte di ciò che hai familiarità con il reporting non è cambiato.

* È comunque possibile utilizzare la potenza di [Analysis Workspace](/help/analysis-workspace/home.md) per analizzare i dati. Workspace funziona allo stesso modo di Adobe Analytics tradizionale.
* La stessa versione di [Dashboard di Adobe Analytics](/help/mobile-app/home.md) è disponibile e funziona in modo simile tra CJA e Analytics tradizionale.
* [Report Builder](/help/report-builder/report-buider-overview.md) dispone di una nuova interfaccia ed è in esecuzione su PC, Mac e la versione Web di Excel.

## Modifiche al reporting

Puoi accedere a molti più dati multicanale da analizzare. Ad esempio, puoi creare un progetto Workspace che analizza le prestazioni di più canali

![visualizzazioni multicanale](assets/cross-channel.png)

## Modifiche all’architettura dei dati {#architecture}

Il Customer Journey Analytics ottiene i suoi dati da Adobe Experience Platform. L’Experience Platform ti consente di centralizzare e standardizzare i dati e i contenuti dei clienti da qualsiasi sistema o canale e applica la scienza dei dati e l’apprendimento automatico per migliorare la progettazione e la distribuzione di esperienze personalizzate.

In Platform i dati del cliente vengono memorizzati come set di dati, costituiti da uno schema e da un batch di dati. Per ulteriori informazioni su Platform, consulta [Panoramica dell’architettura di Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=it).

L’amministratore CJA stabilisce [connessioni](/help/connections/create-connection.md) ai set di dati in Platform. Poi costruiscono [visualizzazioni dati](/help/data-views/data-views.md) utilizzando tali connessioni. Le visualizzazioni dati sono concettualmente simili alle suite di rapporti virtuali e sono la base del reporting in Customer Journey Analytics. Poiché Platform genera tutti i dati per il reporting, le suite di rapporti non esistono più come contenitore di dati.

Una connessione consente all’amministratore di Analytics di integrare i set di dati da [!DNL Adobe Experience Platform] in [!UICONTROL Customer Journey Analytics], incluso nel seguente video:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe offre diversi modi per inserire i dati in Adobe Experience Platform, inclusi i dati della suite di rapporti tramite il connettore origine Adobe Analytics o l’SDK per web. Le implementazioni esistenti da più suite di rapporti possono essere combinate in Platform. Le connessioni e le visualizzazioni dati basate su questi set di dati possono combinare i dati esistenti in precedenza in suite di rapporti separate.

## Modifiche al concetto di suite di rapporti virtuali {#data-views}

[!UICONTROL Data views] prendi il concetto di suite di rapporti virtuali così come sono oggi ed espandilo per [abilitare controlli aggiuntivi sui dati](/help/data-views/create-dataview.md) reso disponibile tramite connessioni. Queste modifiche rendono configurabili e retroattive le impostazioni generali come il fuso orario e gli intervalli di timeout della sessione. È inoltre possibile personalizzare a livello di report o di visualizzazione dati singole impostazioni di variabili, come l’attribuzione e la scadenza. Queste impostazioni sono anche non distruttive e retroattive.

Il selettore suite di rapporti in alto a destra ti consente di scegliere tra le visualizzazioni dati disponibili:

![data-view-selector](assets/data-views.png)

Vedi [Casi di utilizzo intorno alle visualizzazioni dati](/help/data-views/data-views-usecases.md) per ulteriori informazioni su questo concetto.

## Modifiche al concetto di eVar e proprietà

[!UICONTROL eVars], [!UICONTROL props]e [!UICONTROL events] in Adobe Analytics tradizionale non esiste più in [!UICONTROL Customer Journey Analytics]. Sono disponibili elementi schema illimitati, tra cui dimensioni, metriche e campi elenco. Tutte le impostazioni di attribuzione precedentemente applicate durante il processo di raccolta dati ora si applicano al momento della query.

## Modifiche al concetto di segmenti

Adobe ha rinominato il componente &quot;segmenti&quot; in &quot;filtri&quot; per allinearlo meglio agli standard di settore e fornire una migliore distinzione con i segmenti in Adobe Experience Platform.\

[!UICONTROL Customer Journey Analytics] non utilizza più eVar, prop o eventi, ma utilizza qualsiasi elemento dello schema di Platform. Ciò significa che nessuno dei segmenti esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. Per spostare su un Customer Journey Analytics i segmenti Adobe Analytics esistenti, guarda il video seguente:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

Non è ancora possibile condividere o pubblicare [!UICONTROL filters] ([!UICONTROL segments]) da [!DNL Customer Journey Analytics] ad Experience Platform Unified Profile, questa funzionalità è in fase di sviluppo.

Oltre al concetto di modifica dei segmenti, vengono aggiornati anche i contenitori di segmenti.

* **I contenitori Hit ora sono contenitori &quot;Evento&quot;**. La [!UICONTROL Person] Il contenitore include ogni sessione e evento per i visitatori entro l’intervallo di tempo specificato.
* **I contenitori delle visite ora sono contenitori &quot;Sessione&quot;**. La [!UICONTROL Session] Il contenitore ti consente di identificare le interazioni di pagina, le campagne o le conversioni per una sessione specifica.
* **I contenitori dei visitatori ora sono [!UICONTROL Person] contenitori**. La [!UICONTROL Person] Il contenitore include ogni sessione e evento per i visitatori entro l’intervallo di tempo specificato.

## Modifiche al concetto di metriche calcolate

Le metriche calcolate hanno un nome simile tra Analytics tradizionale e CJA. Tuttavia, [!UICONTROL Customer Journey Analytics] non utilizza più eVar, prop o eventi, ma utilizza qualsiasi elemento dello schema di Platform. Questa modifica fondamentale significa che nessuna delle metriche calcolate esistenti è compatibile con [!UICONTROL Customer Journey Analytics]. Per spostare le metriche calcolate di Adobe Analytics in un Customer Journey Analytics, guarda il video seguente:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Modifiche alle impostazioni di attribuzione e scadenza delle variabili

[!UICONTROL Customer Journey Analytics] applica tutte le impostazioni di variabile, inclusa l’attribuzione e la scadenza, al momento del rapporto. Queste impostazioni ora risiedono in [visualizzazioni dati](/help/data-views/component-settings/persistence.md), e alcune impostazioni di variabili (come l’attribuzione) possono essere modificate nei progetti Workspace.

È possibile avere più versioni della stessa variabile nella stessa visualizzazione dati. Ad esempio, puoi avere una dimensione Codice di tracciamento che scade dopo 30 giorni e un’altra che scade alla fine di una sessione. Entrambe queste dimensioni del codice di tracciamento utilizzano gli stessi dati di origine, ma utilizzano impostazioni di attribuzione diverse.

È inoltre possibile avere più visualizzazioni dati basate sulla stessa connessione. Ad esempio, puoi avere una visualizzazione dati con un timeout di sessione di 30 minuti e un&#39;altra con un timeout di sessione di 15 minuti. Entrambe le visualizzazioni dati vengono visualizzate nel selettore in alto a destra per consentire una transizione senza soluzione di continuità tra di esse.

## Modifiche al concetto di classificazioni

Le &quot;classificazioni&quot; sono ora note come &quot;Set di dati di ricerca&quot;. I set di dati di ricerca vengono utilizzati per cercare i valori o le chiavi presenti nei dati evento o profilo. Ad esempio, puoi caricare dati ricerca che mappano ID numerici nei dati evento ai nomi dei prodotti. Vedi [Aggiungere dati a livello di account come set di dati di ricerca](/help/use-cases/b2b.md) per un esempio di utilizzo.

## Modifiche al concetto di attributi del cliente

Gli &quot;attributi del cliente&quot; sono ora noti come &quot;set di dati di profilo&quot;. I set di dati del profilo contengono dati applicati a visitatori, utenti o clienti nella [!UICONTROL Event] dati. Ad esempio, ti consente di caricare dati CRM sui tuoi clienti. Puoi scegliere l’ID persona da includere. Ogni set di dati definito in [!DNL Experience Platform] ha un proprio set di uno o più ID persona definiti.

## Modifiche al modo in cui Adobe identifica i visitatori

CJA espande i concetti di identità oltre gli ECID per includere qualsiasi ID che desideri utilizzare, inclusi ID cliente, ID cookie, ID unione, ID utente, codice di tracciamento e così via. Utilizzo di un ID namespace comune nei set di dati o utilizzo di [Analisi cross-channel](/help/connections/cca/overview.md) aiuta a collegare le persone tra loro tra diversi set di dati. Qualsiasi utente che imposti un progetto Workspace in CJA deve comprendere gli ID utilizzati nei set di dati. Guarda il seguente video che evidenzia l&#39;uso delle identità nel Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Modifiche al concetto di elemento dimensione traffico ridotto

In Analytics tradizionale, una variabile che riceve troppi valori univoci inizia a bucket degli elementi dimensionali sotto `Low-Traffic`. Il Customer Journey Analytics ha molte limitazioni ai campi cardinali elevati. Le modifiche all’architettura di reporting consentono ad Analysis Workspace di creare rapporti su molti elementi dimensionali più unici. Vedi [Lunga coda](../analysis-workspace/workspace-faq/long-tail.md) per ulteriori informazioni su come CJA ottimizza il reporting per dimensioni con molti valori univoci.
