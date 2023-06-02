---
title: Creare un intervallo di date
description: Crea un intervallo di date da utilizzare nel reporting.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: be49bcbbc9d1b7d3989e15a30114da8cbc5e4851
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 5%

---

# Creare un intervallo di date

Puoi creare un intervallo di date utilizzando uno dei due metodi seguenti:

* Direttamente in un progetto Workspace facendo clic su &quot;`+`Pulsante &#39; accanto all&#39;elenco dei componenti dell&#39;intervallo di date a sinistra
* Nel gestore degli intervalli di date

Per creare un intervallo di date nel gestore degli intervalli di date:

1. Accedi a [analytics.adobe.com](https://analytics.adobe.com) utilizzando le credenziali Adobe ID.
1. Passa a [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Fai clic su [!UICONTROL Add] per aprire la finestra modale che crea un intervallo di date.

## Creare una finestra modale di intervallo di date

La finestra modale dispone di quattro campi che è possibile modificare:

* **Intervallo di date**: intervallo di date desiderato per questo componente.
* **Titolo**: nome desiderato per questo componente. Il titolo viene utilizzato nei progetti Workspace.
* **Descrizione**: descrizione desiderata per questo componente. La descrizione viene visualizzata quando si fa clic su ![i](../assets/i.png) icona.
* **Tag**: utilizza i tag per organizzare gli intervalli di date. Un intervallo di date può appartenere a più tag.

## Selezione di un intervallo di date

Quando fai clic sull’intervallo di date nella finestra modale, puoi scegliere tra diverse opzioni:

* **Calendario**: seleziona la data di inizio e di fine.
* **Utilizzare date continue**: seleziona questa casella se desideri che l’intervallo di date cambi con il passare del tempo. Non selezionare questa casella se si desidera che l’intervallo di date rimanga statico.
* **Seleziona predefinito**: utilizza questa selezione a discesa se desideri un intervallo di date personalizzato basato su un intervallo che Adobe offre per impostazione predefinita. Quando selezioni un predefinito, puoi personalizzare ulteriormente l’intervallo di date in base alle tue esigenze. Non influisce sul predefinito offerto da Adobe.

## Intervalli di date continui

Se desideri un intervallo di date continuo, puoi personalizzarlo durante il rollup. È possibile controllare quando le date di inizio e di fine vengono riportate indipendentemente l&#39;una dall&#39;altra.

* **Quando inizia la data**: scegli se la data inizia all’inizio di un periodo di tempo, alla fine di un periodo di tempo o utilizza un giorno fisso.
* **Periodo di tempo da utilizzare**: scegli la frequenza con cui viene eseguito l’intervallo di date. Puoi farla rotolare ogni giorno, ogni settimana, ogni mese, ogni trimestre, o ogni anno.
* **Offset**: scegli l’offset dell’intervallo di date. È possibile aggiungere o sottrarre giorni, settimane, mesi, trimestri o anni.

## Esempi di date continue

Alcuni intervalli di date possono essere utili in alcuni rapporti.

Progressivo anno:

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
