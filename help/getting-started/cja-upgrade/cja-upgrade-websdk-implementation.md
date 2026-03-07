---
title: Informazioni sulle opzioni di implementazione di Web SDK durante l’aggiornamento a Customer Journey Analytics
description: Scopri le opzioni di implementazione di Web SDK durante l’aggiornamento a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 100%

---

# Informazioni sulle opzioni di implementazione di Web SDK durante l’aggiornamento a Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Libreria JavaScript di Web SDK (alloy.js)"
>abstract="Includi la libreria Web SDK (alloy.js) in ogni pagina del sito."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Estensione tag Web SDK"
>abstract="(Consigliato) Se non utilizzi ancora i tag, installa il caricamento di tag sul sito. Se utilizzi già i tag, puoi aggiungere l’estensione Web SDK alla proprietà tag. Questa opzione include implementazioni utilizzando i tag all’interno della raccolta dati di Adobe Experience Platform e i sistemi di gestione dei tag di terze parti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="Pacchetto NPM"
>abstract="Utilizza l’API di raccolta dati per inviare i dati direttamente a uno stream di dati. Sono supportati sia i tipi non autenticati (da client a server) che autenticati (da server a server)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="Implementare Web SDK per la proprietà specificata"
>abstract="Per istruzioni più dettagliate, seleziona il tipo di implementazione desiderato nella guida all’aggiornamento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Aggiungere la libreria Web SDK al sistema di gestione dei tag di terze parti"
>abstract="Per aggiungere la libreria Web SDK al sito, collabora con l’amministratore del sistema sulla gestione dei tag.<br><br>Il tempo di completamento di questa attività dipende in larga misura dalla capacità di risposta del singolo responsabile del sistema di gestione dei tag. L’aggiunta della libreria Web SDK potrebbe essere inclusa nella logica di implementazione associata e distribuita durante i cicli di rilascio standard dell’organizzazione."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Il processo consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics è una nuova implementazione di Experience Platform Web SDK, che è il metodo di raccolta dati preferito per Customer Journey Analytics.

Sono disponibili tre metodi supportati per utilizzare Adobe Experience Platform Web SDK:

* [Estensione tag Web SDK](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/install/extension): Adobe consiglia di utilizzare questo metodo. Installa un tag loader sul sito, quindi utilizza l’interfaccia utente di Adobe Experience Platform Data Collection per configurare la tua implementazione.

* [Libreria JavaScript di Web SDK](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/install/library): fai riferimento a un file di libreria ospitato su CDN o ospita il file di libreria utilizzando la tua infrastruttura. Effettua chiamate alla libreria dall’interno del codice sul tuo sito.

* [NPM](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/install/npm): installa Web SDK nel sito utilizzando gestore di pacchetti NPM.

Per ulteriori informazioni, consulta [Panoramica sull’installazione di Web SDK](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/install/overview) nella Guida di Experience Platform Web SDK.
