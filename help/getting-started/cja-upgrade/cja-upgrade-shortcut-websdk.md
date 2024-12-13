---
title: Collegamento per l’aggiornamento Migrare un’implementazione di AppMeasurement o estensione Analytics per utilizzare il Web SDK
description: Scopri il percorso consigliato per l’aggiornamento da Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 46%

---

# Collegamento per l’aggiornamento: esegui la migrazione di un’implementazione di AppMeasurement o estensione Analytics per utilizzare Web SDK {#shortcut-migrate-websdk}

>[!NOTE]
>
>Questa documentazione deve essere utilizzata come parte del [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Migrare l’implementazione di Analytics per utilizzare il Web SDK"
>abstract="Invece di inviare dati tramite un oggetto XDM, puoi inviare tutte le variabili in formato AppMeasurement tramite l’oggetto dati. Questa scelta rapida ti consente di continuare a utilizzare la logica di AppMeasurement per inviare dati a Platform."

<!-- markdownlint-enable MD034 -->

Durante l&#39;aggiornamento al Customer Journey Analytics, l&#39;Adobe [consiglia una nuova implementazione del SDK Web Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). Tuttavia, a seconda di diversi fattori, come la timeline e i vincoli delle risorse, i passaggi di aggiornamento consigliati potrebbero non essere pratici per la tua organizzazione.

Se l’implementazione di Adobe Analytics è AppMeasurement o l’estensione Analytics, è disponibile un collegamento per l’aggiornamento che consente di migrare l’implementazione di Adobe Analytics in modo da utilizzare Adobe Experience Platform Web SDK per iniziare a inviare dati ad Edge Network e Adobe Analytics prima di inviarli al Customer Journey Analytics.

## Vantaggi e svantaggi

Considera i seguenti vantaggi e svantaggi del collegamento per l’aggiornamento per migrare l’implementazione dell’AppMeasurement o dell’estensione Analytics per utilizzare Web SDK:

| Vantaggi | Svantaggi |
|----------|---------|
| <ul><li>**Offre tutti i vantaggi dei dati di hosting in Experience Edge Network**: <p>Questi vantaggi includono:</p><ul><li>Ottime prestazioni per reporting e disponibilità dei dati, perché Adobe Experience Platform è progettato per alimentare [casi d’uso di personalizzazione in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=it)</li><li>Consolidare l’implementazione per la raccolta dati di Adobe Experience Cloud tra altri prodotti Experience Cloud (AJO, RTCDP e così via)</li><li>Non si basa sulla nomenclatura di Adobe Analytics (prop, eVar, evento, ecc.)</li></ul><li>**Utilizza l’implementazione esistente**: sebbene questo approccio richieda alcune modifiche all’implementazione, non richiede un’implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti apportando modifiche minime alla logica di implementazione senza influire sulla reportistica di Adobe Analytics esistente.</li><li>**Fornisce la flessibilità necessaria per creare uno schema XDM per l’organizzazione in un secondo momento**: puoi eseguire la migrazione dell’implementazione esistente di Adobe Analytics per utilizzare Web SDK e verificare che tutto funzioni in Adobe Analytics, quindi creare lo schema XDM. Questa flessibilità consente un aggiornamento più metodico e attento al Customer Journey Analytics.</li></ul> | <ul><li>**Richiede la mappatura per inviare i dati a Platform**: quando l’organizzazione è pronta per utilizzare Customer Journey Analytics, devi inviare i dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell’oggetto dati sia una voce nello strumento di mappatura del flusso di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita solo una volta per questo flusso di lavoro e non implica l’apportazione di modifiche all’implementazione. Tuttavia, si tratta di un passaggio aggiuntivo non richiesto quando si inviano dati in un oggetto XDM.</li><li>**Debito tecnico**: poiché questo approccio utilizza una forma modificata dell’implementazione esistente, può essere più difficile tenere traccia della logica di implementazione ed eseguire modifiche in futuro quando necessario. </li></ul> |

{style="table-layout:auto"}

## Passaggi di base

Se decidi di prendere il collegamento per l&#39;aggiornamento per migrare l&#39;implementazione dell&#39;AppMeasurement o dell&#39;estensione Analytics per utilizzare Web SDK, viene aggiunto un nuovo passaggio ai passaggi generati dinamicamente per l&#39;organizzazione nel [questionario di aggiornamento da Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

I passaggi di base per la migrazione di un’implementazione di AppMeasurement o di estensione Analytics per utilizzare Web SDK sono i seguenti:

1. Inizia a inviare dati a Platform.

   Se invii già dati a Platform con la tua implementazione di Adobe Analytics, questo passaggio non è necessario. È sufficiente creare una connessione tra i set di dati di Platform e il Customer Journey Analytics, come descritto più avanti in questa procedura.

1. (Facoltativo) Crea uno schema XDM per l’organizzazione non appena hai tempo.

1. (Condizionale) Se hai creato uno schema XDM, utilizza la mappatura dello stream di dati per mappare tutti i campi nell’oggetto dati sullo schema XDM.
