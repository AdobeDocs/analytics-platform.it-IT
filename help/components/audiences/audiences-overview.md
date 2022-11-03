---
title: Panoramica sulla pubblicazione di tipi di pubblico di CJA
description: Scopri il concetto di pubblicazione di tipi di pubblico in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: eba2eb71ca434e0306c018b80209caf52266ee15
workflow-type: ht
source-wordcount: '424'
ht-degree: 100%

---

# Panoramica sulla pubblicazione di tipi di pubblico di CJA

Ora puoi creare e pubblicare i tipi di pubblico rilevati in Customer Journey Analytics (CJA) su [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) (RTCP) in Adobe Experience Platform per la personalizzazione e il targeting dei clienti.

La pubblicazione di tipi di pubblico offre un modo chiaro di attivarsi e di agire sulle informazioni presenti all’interno di CJA. Tali azioni possono includere:

* Utilizzo del pubblico per un percorso in Adobe Journey Optimizer.
* Esportazione del pubblico a terzi tramite una destinazione di Experience Platform.
* Arricchimento di Real-time Customer Profile con attributi utili derivati dai dati basati su eventi in CJA.
* Latenza minima dopo la pubblicazione del pubblico (un paio di minuti).
* Pubblicazione di tipi di pubblico una tantum o ricorrenti.

## Terminologia chiave

**Pubblico**: un insieme o un elenco di identità con uno spazio dei nomi e un ID specifico correlati a tale spazio dei nomi. I tipi di pubblico sono trasportabili da Adobe Experience Platform e dalle applicazioni che lo compongono (come CJA). I tipi di pubblico possono contenere spazi dei nomi misti.

**Filtro**: un insieme di regole che, se valutate in un insieme di dati per un periodo di tempo, produce un sottoinsieme di dati. Un filtro può essere utilizzato nel processo di creazione di un pubblico quando è associato ad altri servizi di supporto. I filtri sono definiti e mantenuti in CJA.

**Filtri** e **Segmenti**: CJA non utilizza il concetto “di segmenti”, ma utilizza i “filtri”. Sebbene siano entrambi un insieme di regole che possono contenere una logica simile, producono output diversi. Un filtro viene utilizzato per limitare un set di dati a scopo di analisi. Un segmento viene utilizzato per generare un elenco di identità che possono essere utilizzate per l’attivazione. I segmenti producono tipi di pubblico in Real-time Customer Profile, mentre i filtri (da soli) no. La pubblicazione di tipi di pubblico di CJA è il processo tramite il quale utilizziamo un filtro di CJA per creare un pubblico che può essere utilizzato da Real-time Customer Profile.

## Autorizzazioni

* Gli amministratori ricevono automaticamente l’autorizzazione **[!UICONTROL Audience Publishing]** in Adobe Admin Console.

* Gli amministratori possono concedere questa autorizzazione a singoli utenti.

* Gli amministratori richiedono inoltre l’autorizzazione **[!UICONTROL Manage Profiles]** in Adobe Experience Platform.

## Governance dei dati e consenso

Quando pubblichi un pubblico in CJA, vengono registrate le etichette e i criteri di governance dei dati allegati ai campi utilizzati nel pubblico.  Quando il pubblico viene attivato in una qualsiasi app di Adobe Experience, tutte le etichette e i criteri di governance dei dati associati sono disponibili per quel pubblico e possono essere applicati gli opportuni provvedimenti di implementazione. [Ulteriori informazioni sul consenso](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=it#consent-policy).

## Passaggi successivi

* [Creare e pubblicare tipi di pubblico](/help/components/audiences/publish.md)
* [Gestire i tipi di pubblico](/help/components/audiences/manage.md)
