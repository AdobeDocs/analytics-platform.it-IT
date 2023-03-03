---
title: Creare e pubblicare tipi di pubblico in Real-time Customer Profile
description: Scopri come pubblicare tipi di pubblico da Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: 1bd07390b1e01c64f192994a6d9d41e7c9a88440
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Creare e pubblicare tipi di pubblico

Questo argomento illustra come creare e pubblicare i tipi di pubblico identificati in Customer Journey Analytics (CJA) su [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it) in Adobe Experience Platform per la personalizzazione e il targeting dei clienti.

Leggi questa [panoramica](/help/components/audiences/audiences-overview.md) per acquisire familiarità con il concetto di pubblico di CJA.

## Creare un pubblico {#create}

1. Per creare tipi di pubblico, puoi iniziare in diversi modi:

   | Metodo di creazione | Dettagli |
   | --- | --- |
   | Dal menu principale **[!UICONTROL Components]>[!UICONTROL Audiences]** | Viene visualizzata la pagina di gestione dei tipi di pubblico. Fai clic su **[!UICONTROL Create audience]**; viene aperto [!UICONTROL Audience builder]. |
   | Da una tabella a forma libera | Fai clic con il pulsante destro del mouse su un elemento in una tabella a forma libera e seleziona **[!UICONTROL Create an audience from selection]**. Usando questo metodo il filtro viene precompilato con la dimensione o l’elemento della dimensione selezionato nella tabella. |
   | Dall’interfaccia utente di creazione/modifica del filtro | Seleziona la casella che riporta **[!UICONTROL Create an audience from this filter]**. Usando questo metodo il filtro viene precompilato. |

   {style=&quot;table-layout:auto&quot;}

1. Crea il pubblico.

   Configura queste impostazioni prima di pubblicare il pubblico.

   ![](assets/create-audience.png)

   | Impostazione | Descrizione |
   | --- | --- |
   | [!UICONTROL Name] | Il nome del pubblico. |
   | [!UICONTROL Tags] | Qualsiasi tag che desideri assegnare al pubblico per motivi organizzativi. Puoi utilizzare un tag preesistente o inserirne uno nuovo. |
   | [!UICONTROL Description] | Aggiungi una buona descrizione del pubblico, per distinguerlo dagli altri. |
   | [!UICONTROL Refresh frequency] | La frequenza con cui desideri aggiornare il pubblico.<ul><li>Puoi scegliere di creare un pubblico una tantum (impostazione predefinita) che non necessita di aggiornamento. Ad esempio, potrebbe essere utile per campagne una tantum specifiche.</li><li>Puoi selezionare altri intervalli di aggiornamento. Per la frequenza di aggiornamento di 4 ore, esiste un limite di 75 o 150 tipi di aggiornamenti del pubblico, a seconda dell’adesione CJA.</li></ul> |
   | Data di scadenza | La data in cui il pubblico smetterà di aggiornarsi. Il valore predefinito è un anno dalla data di creazione. I tipi di pubblico in scadenza vengono trattati in modo simile ai rapporti pianificati in scadenza: l’amministratore riceve un’e-mail un mese prima della scadenza del pubblico. |
   | Finestra di lookback di aggiornamento | Specifica quanto indietro desideri andare nella finestra dei dati durante la creazione del pubblico. Il massimo è 90 giorni. |
   | [!UICONTROL One-time date range] | L’intervallo di date per la pubblicazione del pubblico una tantum. |
   | [!UICONTROL Filter] | I filtri sono l’input principale per il pubblico. Puoi aggiungere fino a 20 filtri. Questi filtri possono essere uniti con gli operatori `And` o `Or`. |
   | [!UICONTROL View sample IDs] | Un campione di ID in questo pubblico. Utilizza la barra di ricerca per cercare ID di esempio. |

   {style=&quot;table-layout:auto&quot;}

1. Interpreta l’anteprima dei dati.

   L’anteprima del pubblico viene visualizzata nella barra a destra. Consente di avere un’analisi sintetica del pubblico creato.

   ![](assets/data-preview.png)

   | Impostazione di anteprima | Descrizione |
   | --- | --- |
   | Finestra di [!UICONTROL Data preview] | L’intervallo di date per il pubblico. |
   | [!UICONTROL Total people] | Un numero di riepilogo del numero totale di persone presenti nel pubblico. Può arrivare fino a 20 milioni di persone. Se il pubblico supera i 20 milioni di persone, devi ridurne la dimensione prima di poterlo pubblicare. |
   | [!UICONTROL Audience size limit] | Mostra quanto è lontano il pubblico dal limite di 20 milioni. |
   | [!UICONTROL Estimated audience return] | Questa impostazione è utile per il retargeting dei clienti del pubblico che ritornano al tuo sito. In altre parole, che compaiono nuovamente in questo set di dati. <p>Qui puoi selezionare l’intervallo di tempo (i prossimi sette giorni, le prossime due settimane, il prossimo mese) per ottenere la stima del numero di clienti che potrebbero tornare. |
   | [!UICONTROL Estimated to return] | Questo numero fornisce una stima dei clienti fidelizzati nell’intervallo di tempo selezionato dall’elenco a discesa. Per prevedere questo numero usiamo il tasso storico di abbandono del pubblico. |
   | [!UICONTROL Preview metrics] | Questa impostazione ti consente di esaminare metriche specifiche per verificare se il pubblico contribuisce in misura sproporzionata a questa metrica, ad esempio “[!UICONTROL Revenue]” o “[!UICONTROL Average time on site]”. Ti fornisce il conteggio complessivo della metrica, così come la percentuale del totale che rappresenta. Puoi selezionare qualsiasi metrica disponibile nella visualizzazione dati. |
   | [!UICONTROL Namespaces included] | Gli spazi dei nomi specifici associati alle persone nel pubblico. Alcuni esempi includono ECID, ID CRM, indirizzi e-mail e così via. |
   | [!UICONTROL Sandbox] | La [sandbox di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) in cui risiede il pubblico. Quando pubblichi questo pubblico in Platform, puoi utilizzarlo solo entro i confini di questa sandbox. |

   {style=&quot;table-layout:auto&quot;}

1. Controlla nuovamente la configurazione del pubblico e fai clic su **[!UICONTROL Publish]**.

   Se tutto è andato correttamente, riceverai un messaggio di conferma della pubblicazione del pubblico. Ci vogliono solo pochi minuti perché questo pubblico venga visualizzato in Experience Platform. Anche per i tipi di pubblico con milioni di membri, dovrebbero essere necessari meno di 5 minuti.

1. Fai clic su **[!UICONTROL View audience in AEP]** all’interno dello stesso messaggio; ti porterà all’[interfaccia utente dei segmenti](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=it) in Adobe Experience Platform. Per ulteriori informazioni, vedi di seguito.

## Cosa succede dopo la creazione di un pubblico? {#after-audience-created}

Dopo aver creato un pubblico, Adobe crea un segmento Experience Platform in streaming per ogni nuovo pubblico CJA. Un segmento AEP in streaming verrà creato solo se l’organizzazione è configurata per la segmentazione in streaming.

* Il segmento AEP condivide lo stesso nome/descrizione del pubblico CJA, ma al nome verrà aggiunto l’ID del pubblico CJA per assicurarsi che sia univoco.
* Se il nome/descrizione del pubblico CJA viene modificato, anche il nome/descrizione del segmento AEP rispecchia tale modifica.
* Se un pubblico CJA viene eliminato da un utente, il segmento AEP non sarà eliminato. Questo perché l‘eliminazione del pubblico CJA può essere annullata in un momento successivo.

## Considerazioni sulla latenza {#latency}

In diversi intervalli precedenti, durante e dopo la pubblicazione del pubblico, possono verificarsi alcune latenze. Ecco una panoramica delle latenze che possono verificarsi.

![](assets/latency-diagram.png)

| # | Punto di latenza | Durata della latenza |
| --- | --- | --- |
| 1 | Acquisizione di dati nel Data Lake | Fino a 30 minuti |
| 2 | Acquisizione di dati da Experience Platform in CJA | Fino a 60 minuti |
| 3 | La pubblicazione dei tipi di pubblico sul Profilo cliente in tempo reale inclusa la creazione automatica del segmento in streaming e consentendo al segmento di essere pronto a ricevere i dati. | Circa 60 minuti |
| 4 | Frequenza di aggiornamento per tipi di pubblico | <ul><li>Aggiornamento singolo (latenza inferiore a 5 minuti)</li><li>Aggiornamento ogni 4 ore, ogni giorno, ogni settimana, ogni mese (la latenza va di pari passo con la frequenza di aggiornamento) |
| 5 | Creazione della destinazione in AEP: attivazione del nuovo segmento | 1-2 ore |

{style=&quot;table-layout:auto&quot;}

## Utilizzare i tipi di pubblico di CJA in Experience Platform {#audiences-aep}

CJA prende tutte le combinazioni di spazi dei nomi e ID dal pubblico pubblicato e le trasmette al Profilo cliente in tempo reale (RTCP). CJA invia il pubblico a Experience Platform con l’identità primaria impostata in base a ciò che è stato selezionato come [!UICONTROL Person ID] al momento della configurazione della connessione.

RTCP esamina quindi ogni combinazione di spazio dei nomi/ID e cerca un profilo di cui potrebbe far parte. Un profilo è fondamentalmente un cluster di spazi dei nomi, ID e dispositivi collegati. Se trova un profilo, aggiungerà lo spazio dei nomi e l’ID agli altri ID in questo profilo come attributo di appartenenza al segmento. Ora, ad esempio, “user@adobe.com” può essere impostato come destinatario su tutti i relativi dispositivi e canali. Se non viene trovato un profilo, ne viene creato uno nuovo.

Puoi visualizzare i tipi di pubblico di CJA in Platform andando su **[!UICONTROL Segments]** > **[!UICONTROL Create segments]** > scheda **[!UICONTROL Audiences]** > **[!UICONTROL CJA Audiences]**.

Puoi trascinare i tipi di pubblico di CJA nella definizione del segmento dei segmenti di AEP.

![](assets/audiences-aep.png)

## Domande frequenti {#faq}

Domande frequenti sulla pubblicazione dei tipi di pubblico.

+++**Cosa succede se un utente non fa più parte di un pubblico in CJA?**

In questo caso, viene inviato un evento di uscita a Experience Platform da CJA.

+++

+++**Cosa succede se elimini un pubblico in CJA?**

Quando un pubblico CJA viene eliminato, non viene più visualizzato nell’interfaccia utente di Experience Platform. Tuttavia, in Platform nessun profilo associato a quel pubblico viene effettivamente eliminato.

+++

+++**Se in RTCDP non esiste un profilo corrispondente, verrà creato un nuovo profilo?**

Sì.

+++

+++**CJA invia i dati del pubblico come eventi della pipeline o come un file flat che viene anche trasmesso anche al data lake?**

CJA trasmette i dati al RTCP tramite pipeline e questi dati vengono anche raccolti in un set di dati di sistema nel data lake.

+++

+++**Quali identità invia CJA?**

Qualsiasi coppia di identità/spazio dei nomi utilizzata nella [configurazione della connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=it#create-connection). Nello specifico, il passaggio in cui un utente seleziona il campo che desidera utilizzare come “ID persona”.

+++

+++**Quale ID è scelto come identità primaria?**

Vedi sopra. Inviamo una sola identità per “persona” CJA.

+++

+++**RTCP elabora anche i messaggi CJA? CJA può aggiungere identità a un grafico dell’identità di profilo tramite la condivisione del pubblico?**

No. Inviamo una sola identità per “persona”, quindi RTCP non avrebbe bordi del grafico da utilizzare.

+++

## Passaggi successivi

* Per gestire questo pubblico, vai all’[interfaccia utente di gestione](/help/components/audiences/manage.md).
