---
title: Creazione di un intervallo di date
description: Crea un intervallo di date da utilizzare nel reporting.
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 8%

---

# Creazione di un intervallo di date

>[!NOTE]
>
>Stai visualizzando la documentazione per Analysis Workspace in Customer Journey Analytics. Le funzioni disponibili sono leggermente diverse da quelle di [Analysis Workspace in Adobe Analytics tradizionale](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Ulteriori informazioni...](/help/getting-started/cja-aa.md)

Puoi creare un intervallo di date personalizzato utilizzando uno dei due metodi seguenti:

* Direttamente in un progetto Workspace facendo clic sul pulsante &quot;`+`&quot; accanto all’elenco dei componenti dell’intervallo di date a sinistra
* Nel gestore dell&#39;intervallo di date

Per creare un intervallo di date nel gestore dell’intervallo di date:

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) utilizzando le tue credenziali AdobeID.
1. Passa a [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Fai clic sul pulsante [!UICONTROL Add] per aprire la finestra modale che crea un intervallo di date.

## Crea una finestra modale per l’intervallo di date

La finestra modale dispone di quattro campi che è possibile modificare:

* **Intervallo** di date: L’intervallo di date desiderato per questo componente.
* **Titolo**: Nome desiderato per questo componente. Il titolo viene utilizzato nei progetti Workspace.
* **Descrizione**: Descrizione del componente. La descrizione viene visualizzata quando fai clic sull&#39;icona ![i](../assets/i.png) .
* **Tag**: Utilizza i tag per organizzare gli intervalli di date. Un intervallo di date può appartenere a più tag.

## Selezione di un intervallo di date

Quando fai clic sull’intervallo di date nella finestra modale, puoi scegliere tra diverse opzioni:

* **Calendario**: Seleziona la data di inizio e di fine.
* **Utilizza date** continue: Selezionare questa casella se si desidera modificare l&#39;intervallo di date man mano che l&#39;ora continua. Non selezionare questa casella se desideri che l’intervallo di date rimanga statico.
* **Seleziona predefinito**: Utilizza questo elenco a discesa se desideri un intervallo di date personalizzato basato su un intervallo che Adobe offre per impostazione predefinita. Quando selezioni un predefinito, puoi personalizzare ulteriormente l’intervallo di date in base alle tue esigenze. Non influisce sul predefinito offerto da Adobe.

## Intervalli di date continui

Se desideri un intervallo di date continuo, puoi personalizzare quando viene eseguito il rollup. È possibile controllare quando le date di inizio e di fine si spostano in modo indipendente l’una dall’altra.

* **Quando inizia** la data: Scegliere se la data inizia all&#39;inizio di un periodo di tempo, alla fine di un periodo di tempo o utilizzare un giorno fisso.
* **Il periodo di tempo da utilizzare**: Scegli la frequenza con cui viene eseguito l’intervallo di date. Potete farlo rotolare ogni giorno, ogni settimana, ogni mese, ogni trimestre, o ogni anno.
* **Offset**: Scegliere l&#39;offset dell&#39;intervallo di date. È possibile aggiungere o sottrarre giorni, settimane, mesi, trimestri o anni.

## Esempi di date continue

Alcuni intervalli di date possono essere utili in alcuni rapporti.

Anno corrente:

```text
Start: Start of current year
End: End of current day
```

Giovedì scorso a questo giovedì:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Anno fiscale (ad esempio, se un anno fiscale inizia in dicembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
