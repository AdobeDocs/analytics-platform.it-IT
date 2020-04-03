---
title: Creazione di un intervallo di date
description: Crea un intervallo di date da utilizzare nei rapporti.
translation-type: tm+mt
source-git-commit: 2452490cc2f147cfd87540a68be2d0c219d8744f

---


# Creazione di un intervallo di date

Puoi creare un intervallo di date personalizzato utilizzando uno dei due metodi seguenti:

* Direttamente in un progetto dell&#39;area di lavoro facendo clic sul pulsante &#39;`+`&#39; accanto all&#39;elenco dei componenti dell&#39;intervallo di date a sinistra
* In Gestione intervalli di date

Per creare un intervallo di date nel gestore intervalli di date:

1. Accedete ad [analytics.adobe.com](https://analytics.adobe.com) utilizzando le credenziali AdobeID.
1. Passa a [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Fare clic sul [!UICONTROL Add] pulsante per aprire la finestra modale che crea un intervallo di date.

## Creazione di una finestra modale per l&#39;intervallo di date

Nella finestra modale sono disponibili quattro campi:

* **Intervallo** di date: L&#39;intervallo di date desiderato per questo componente.
* **Titolo**: Nome del componente desiderato. Il titolo viene utilizzato nei progetti dell’area di lavoro.
* **Descrizione**: Descrizione del componente. La descrizione viene visualizzata quando si fa clic sull&#39;icona ![i](../assets/i.png) .
* **Tag**: Utilizza i tag per organizzare gli intervalli di date. Un intervallo di date può appartenere a più tag.

## Selezione di un intervallo di date

Quando fai clic sull’intervallo di date nella finestra modale, hai diverse opzioni:

* **Calendario**: Selezionare la data di inizio e di fine.
* **Usa date** continue: Selezionare questa casella se si desidera che l&#39;intervallo di date cambi man mano che l&#39;ora continua. Non selezionare questa casella se si desidera che l&#39;intervallo di date rimanga statico.
* **Selezionate il predefinito**: Utilizzate questo menu a discesa se desiderate un intervallo di date personalizzato basato su un intervallo offerto da Adobe per impostazione predefinita. Quando selezionate un predefinito, potete personalizzare ulteriormente l’intervallo di date in base alle vostre esigenze. Non influenza il predefinito offerto da Adobe.

## Intervalli di date

Se si desidera un intervallo di date continuo, è possibile personalizzare il momento del suo scorrimento. È possibile controllare il momento in cui le date di inizio e di fine scorrono indipendentemente l&#39;una dall&#39;altra.

* **Data di inizio**: Scegliere se la data inizia all&#39;inizio di un periodo di tempo, alla fine di un periodo di tempo, oppure utilizzare un giorno fisso.
* **Periodo di tempo da utilizzare**: Scegliere la frequenza con cui l&#39;intervallo di date viene eseguito. Potete farlo rotolare ogni giorno, ogni settimana, ogni mese, ogni trimestre, o ogni anno.
* **Offset**: Scegliere l&#39;offset dell&#39;intervallo di date. Potete aggiungere o sottrarre giorni, settimane, mesi, trimestri o anni.

## Esempi di date continue

Alcuni intervalli di date possono essere utili in alcuni rapporti.

Anno in corso:

```text
Start: Start of current year
End: End of current day
```

Da giovedì scorso a giovedì:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Anno fiscale (ad esempio, se un anno fiscale inizia in dicembre)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
