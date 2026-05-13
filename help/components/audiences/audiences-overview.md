---
title: Scopri la panoramica sulla pubblicazione di tipi di pubblico in Customer Journey Analytics
description: Scopri il concetto di pubblicazione di tipi di pubblico in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
TQID: https://experienceleague.adobe.com/x64-Q7kfdcy4pAPrOb-TfliMFMNSTafJILEaxR3qbrs
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 553
ht-degree: 73%

---

# Panoramica sulla pubblicazione del pubblico

>[!NOTE]
>
>Comprendere la differenza tra analisi del pubblico e pubblicazione del pubblico:
>
>* **Analisi del pubblico**: consente di acquisire i dati di appartenenza al pubblico dai set di dati del profilo di Experience Platform in una connessione Customer Journey Analytics. Per informazioni sull&#39;analisi del pubblico, vedere [Panoramica dell&#39;analisi del pubblico](/help/connections/audience-analysis/audience-analysis-overview.md).
>* **Pubblicazione del pubblico**: ti consente di creare e pubblicare su Adobe Experience Platform i tipi di pubblico rilevati in Customer Journey Analytics per la personalizzazione e il targeting dei clienti.

Puoi creare e pubblicare i tipi di pubblico rilevati in Customer Journey Analytics su [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) in Adobe Experience Platform per la personalizzazione e il targeting dei clienti. (Per informazioni sull&#39;acquisizione dei dati di appartenenza al pubblico dai set di dati del profilo di Experience Platform in una connessione Customer Journey Analytics, consulta [Panoramica dell&#39;analisi del pubblico](/help/connections/audience-analysis/audience-analysis-overview.md).)

La pubblicazione di tipi di pubblico offre un modo chiaro di attivarsi e di agire sulle informazioni presenti all’interno di Customer Journey Analytics. Tali azioni possono includere:

* Utilizzo del pubblico per un percorso in Adobe Journey Optimizer.
Per ulteriori informazioni sull’utilizzo dei tipi di pubblico che sono stati pubblicati in Experience Platform, consulta [Introduzione ai tipi di pubblico](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences) nella documentazione di Journey Optimizer.
* Esportazione del pubblico a terzi tramite una destinazione di Experience Platform.
* Arricchimento del profilo cliente in tempo reale con attributi utili derivati dai dati basati su eventi in Customer Journey Analytics.
* Tutto questo con una latenza minima dopo la pubblicazione del pubblico.
Per ulteriori informazioni, consulta [Considerazioni sulla latenza](/help/components/audiences/publish.md#latency-considerations) in [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md).
* Pubblicazione di tipi di pubblico una tantum o ricorrenti

I tipi di pubblico creati in Customer Journey Analytics non devono necessariamente essere basati su set di dati abilitati per il profilo. Puoi acquisire dati storici in Experience Platform senza abilitare set di dati e schemi associati per il profilo. Quindi utilizza questi set di dati per scoprire tipi di pubblico rilevanti in Customer Journey Analytics e pubblicarli in Real-time Customer Profile in Experience Platform a scopo di attivazione.

## Terminologia chiave

**Pubblico**: un insieme o un elenco di identità con uno spazio dei nomi e un ID specifico correlati a tale spazio dei nomi. I tipi di pubblico sono trasportabili da Adobe Experience Platform e dalle applicazioni che lo compongono (come Customer Journey Analytics). I tipi di pubblico possono contenere spazi dei nomi misti.

**Segmento**: un set di regole che, se valutate su un insieme di dati per un periodo di tempo, crea un sottoinsieme di dati. Un segmento può essere utilizzato nel processo di creazione di un pubblico quando è unito ad altri servizi di supporto. I filtri sono definiti e mantenuti in Customer Journey Analytics.

## Autorizzazioni

* Gli amministratori ricevono automaticamente l&#39;autorizzazione **[!UICONTROL Pubblicazione dei tipi di pubblico]** in Adobe Admin Console.

* Gli amministratori e gli amministratori dei profili di prodotto possono concedere l&#39;autorizzazione **[!UICONTROL Creazione pubblico]** e **[!UICONTROL Visualizzazione pubblico]** ai singoli utenti. Per ulteriori informazioni, consulta [Controllo dell’accesso a livello di utente](/help/technotes/access-control.md#user-level-access).

* Gli amministratori devono inoltre disporre dell&#39;autorizzazione **[!UICONTROL Gestione profili]** in Adobe Experience Platform.

## Governance dei dati e consenso

Quando pubblichi un pubblico in Customer Journey Analytics, vengono registrate le etichette e i criteri di governance dei dati allegati ai campi utilizzati nel pubblico.  Quando il pubblico viene attivato in una qualsiasi app di Adobe Experience, tutte le etichette e i criteri di governance dei dati associati sono disponibili per quel pubblico e possono essere applicati gli opportuni provvedimenti di implementazione. [Ulteriori informazioni sul consenso](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=it#consent-policy).

## Passaggi successivi

* [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md)
* [Gestire i tipi di pubblico](/help/components/audiences/manage.md)
