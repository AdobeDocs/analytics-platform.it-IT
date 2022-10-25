---
title: Chiavi gestite dal cliente
description: Scopri come configurare le chiavi gestite dal cliente per CJA.
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# Chiavi gestite dal cliente

>[!NOTE]
>
>Questa funzionalità sarà disponibile a novembre 2022.

Customer Journey Analytics (CJA) offre l’opzione per [Scudo sanitario](https://www.adobe.com/trust/compliance/hipaa-ready.html) e i clienti Privacy &amp; Security Shield per utilizzare una chiave gestita dal cliente di Azure (CMK) da applicare ai dati CJA.  Tieni presente che questo processo è separato da [Configurazione Adobe Experience Platform CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>Le chiavi gestite dal cliente sono attualmente disponibili solo per le organizzazioni che hanno acquistato il [Scudo sanitario o scudo per la privacy e la sicurezza](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) offerta aggiuntiva.

Per impostare CMK per CJA, effettua le seguenti operazioni:

1. Assicurati di avere diritto a CMK controllando con il team dell&#39;account Adobe.
1. Crea un nuovo archivio chiavi di Azure da utilizzare solo con CJA.
1. Lega il valore chiave di Azure all’app CMK di Azure CJA (collegamento da seguire).
1. Crea un ticket di Adobe dell’Assistenza clienti per richiedere la configurazione CMK. Includi l’URI di Azure nel ticket.
1. L’Assistenza clienti Adobe conferma il completamento dell’applicazione CMK sui dati CJA.
