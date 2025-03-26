---
title: Raccolta degli ID sessione della metrica quantistica in Customer Journey Analytics
description: Modifica l’implementazione per includere gli ID sessione in modo da poterli analizzare in Customer Journey Analytics.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: ae88ab16e85bd1274990f8c4d04771398293fe09
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Raccolta degli ID sessione della metrica quantistica in Customer Journey Analytics

Alcuni casi d&#39;uso, come [l&#39;associazione delle riproduzioni delle sessioni della metrica quantistica](tie-session-replays.md) o [l&#39;utilizzo delle mappe di calore della metrica quantistica](heatmap.md) richiedono la modifica dell&#39;implementazione per raccogliere l&#39;ID della sessione della metrica quantistica. Questa pagina illustra il processo per inserire correttamente tali dati nell’implementazione esistente.

## Prerequisiti:

Questi passaggi presuppongono l’utilizzo di tag in Raccolta dati di Adobe Experience Platform. Puoi adattare questi metodi di raccolta dati a un’implementazione manuale di Web SDK se la tua organizzazione non utilizza i tag.

Per ulteriori informazioni, consulta la documentazione dell&#39;estensione tag [Quantum Metric](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric).

## Passaggio 1: acquisire l’ID della sessione della metrica quantistica utilizzando l’estensione dei tag della metrica quantistica

Segui questi passaggi per aggiungere l’ID sessione della metrica quantistica ai dati inviati a Adobe Experience Platform.

1. Utilizza l’estensione Quantum Metric nell’interfaccia utente dei tag per inviare dati a Quantum Metric.
1. Crea quattro elementi dati:
   1. Uno che acquisisce l&#39;ID sessione della metrica quantistica dal cookie della metrica quantistica denominato `QuantumMetricSessionID`
   1. Estrae l&#39;ID sessione della metrica quantistica da `localStorage`. A volte questo elemento dati viene caricato più rapidamente del cookie impostato nell’altro elemento dati.
   1. Utilizzare l&#39;Assistente agli elementi dati o il JavaScript personalizzato per estrarre il nodo `s` dall&#39;elemento dati `localStorage`.
   1. Uno che utilizza la logica per cercare prima l’elemento dati del cookie e, se trovato, restituirlo a un percorso oggetto XDM. Se non è definito, provare a cercare nell&#39;elemento dati dell&#39;oggetto `localStorage` estratto.
1. Invia l’elemento dati ID sessione della metrica quantistica finale all’oggetto XDM inviato in ogni evento.

>[!NOTE]
>A volte il Web SDK viene eseguito più rapidamente del codice della metrica quantistica. In questi casi, l’ID sessione viene inviato all’hit successivo. Se un visitatore non viene recapitato, l’ID sessione non viene raccolto in queste istanze.

## Passaggio 2: confermare i campi del set di dati inclusi

Verifica che i set di dati nella connessione abbiano ora l’ID sessione della metrica quantistica nel set di dati desiderato.

## Passaggio 3: aggiungere l’ID sessione della metrica quantistica come dimensione disponibile

Modifica la visualizzazione dati esistente per aggiungere l’ID sessione come dimensione disponibile in Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com).
1. Passare a Customer Journey Analytics e selezionare **[!UICONTROL Data views]** nel menu principale.
1. Seleziona la visualizzazione dati esistente desiderata.
1. Individuate l&#39;elenco del campo ID sessione della metrica quantistica a sinistra e trascinatelo nell&#39;area delle dimensioni al centro.
1. Nel riquadro di destra, impostare l&#39;impostazione [persistenza](/help/data-views/component-settings/persistence.md) su &#39;Sessione&#39;.
1. Fai clic su **[!UICONTROL Save]**.


