---
title: Avvertenze
description: Avvertenze per l’estensione BI in vari strumenti BI in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Avvertenze


Ciascuno degli strumenti BI supportati ha alcune avvertenze sull’utilizzo dell’estensione Customer Journey Analytics BI.

+++ Strumenti BI

>[!BEGINTABS]

>[!TAB Desktop Power BI]

* Il filtro dell&#39;intervallo di date avanzato di Power BI Desktop è esclusivo.  Per la data di fine, devi selezionarne una oltre il giorno per il quale desideri generare il rapporto. Ad esempio, **[!UICONTROL è uguale o successivo a]** `1/1/2023` **[!UICONTROL e precedente a]** `1/2/2023`.
* Power BI Desktop viene impostato automaticamente su **[!UICONTROL Importa]** quando si crea una connessione. Assicurati di utilizzare **[!UICONTROL Direct Query]**.
* Power BI Desktop espone le trasformazioni dei dati tramite Power Query.  Power Query funziona principalmente con connessioni di tipo Importa, pertanto molte trasformazioni applicate come funzioni di data o di stringa generano un errore che indica che è necessario passare a una connessione di tipo Importa.  Se devi trasformare i dati in fase di query, utilizza dimensioni e metriche derivate in modo che Power BI non debba eseguire le trasformazioni stesse.
* Power BI Desktop non è in grado di gestire le colonne di tipo data-ora. Le dimensioni **[!UICONTROL daterange *X *]**, ad esempio**[!UICONTROL daterangehour ]**e**[!UICONTROL daterangeminute ]**, non sono pertanto supportate.
* Per impostazione predefinita, Power BI Desktop tenta di effettuare più connessioni utilizzando un numero maggiore di sessioni di Query Service.  Accedi alle impostazioni di Power BI per il progetto e disabilita le query parallele.
* Power BI Desktop esegue tutte le operazioni di ordinamento e limitazione sul lato client. Power BI Desktop ha anche una semantica diversa per il filtro *X* superiore che include valori associati. Pertanto, non puoi creare lo stesso ordinamento e le stesse limitazioni disponibili in Analysis Workspace.
* Le versioni precedenti di Power BI Desktop, nell’ottobre 2024, hanno interrotto le origini dati PostgreSQL. Assicurati di utilizzare la versione indicata in questo articolo.

>[!TAB Desktop Tableau]

* L’intervallo di date del desktop Tableau è esclusivo. Per la data di fine, devi selezionarne una oltre il giorno per il quale desideri generare il rapporto.
* Per impostazione predefinita, quando si aggiunge una dimensione data o data-ora come **[!UICONTROL Daterangemonth]** alle righe di un foglio, Tableau Desktop racchiude il campo in una funzione **[!UICONTROL YEAR()]**.  Per ottenere ciò che desideri, devi selezionare tale dimensione e dal menu a discesa selezionare la funzione data che desideri utilizzare.  Ad esempio, cambia da **[!UICONTROL Anno]** a **[!UICONTROL Mese]** quando tenti di utilizzare **[!UICONTROL Mese_Daterangente]**.
* Limitare i risultati al primo *X* non è ovvio in Tableau Desktop. È possibile limitare i risultati in modo esplicito o utilizzando un campo calcolato e la funzione **[!UICONTROL INDEX()]**.  L&#39;aggiunta di un filtro *X* principale a una dimensione genera istruzioni SQL complesse utilizzando un inner join non supportato.

>[!TAB Ricerca]

* Il Looker dispone di un numero massimo di connessioni per nodo che devono essere comprese tra 5 e 100.  Impossibile impostare questo valore su 1.  Questa impostazione implica che una connessione Looker utilizzi sempre almeno 5 delle sessioni disponibili di Query Service.
* Looker consente di creare un progetto con una visualizzazione basata su una visualizzazione dati di Customer Journey Analytics. Looker crea quindi un modello basato sulle dimensioni e sulle metriche, disponibili nella visualizzazione Dati, utilizzando LookerML.  Questa vista Progetto non si aggiorna automaticamente per corrispondere all&#39;origine.  Se apporti modifiche o aggiunte a dimensioni, metriche, metriche calcolate o segmenti della visualizzazione dati di CJA, tali modifiche non vengono visualizzate automaticamente in Looker.  È necessario aggiornare manualmente la visualizzazione Progetto o creare un nuovo progetto.
* L&#39;esperienza utente di Looker in campi di data o data e ora come **[!UICONTROL Daterange Date]** o **[!UICONTROL Daterangeday Date]** è fonte di confusione.
* L’intervallo di date del ricercatore è esclusivo invece di inclusivo.  **[!UICONTROL fino a (prima di)]** è in grigio, quindi questo aspetto potrebbe mancare.  Per il giorno di fine, devi selezionarne uno oltre il giorno per il quale desideri generare il rapporto.
* Looker non tratta automaticamente le metriche come metriche.  Quando selezioni una metrica, per impostazione predefinita Looker tenta di trattare la metrica come una dimensione nella query.  Per trattare una metrica come una metrica, devi creare un campo personalizzato come illustrato in precedenza. Come collegamento è possibile selezionare **[!UICONTROL ⋮]**, selezionare **[!UICONTROL Aggrega]**, quindi selezionare **[!UICONTROL Somma]**.

>[!TAB Blocco appunti Jupyter]

* L’avvertenza principale per Jupyter Notebook è che lo strumento non ha un’interfaccia utente drag-and-drop come altri strumenti di business intelligence. Puoi creare buoni effetti visivi, ma devi scrivere del codice per farlo.

>[!TAB StudioRS]

* R dplyr funziona con uno schema piatto ed è quindi necessaria l&#39;opzione **[!UICONTROL FLATTEN]**.
* L&#39;avvertenza principale per RSudio è che lo strumento non è un&#39;interfaccia utente di trascinamento come gli altri strumenti di business intelligence. Puoi creare buoni effetti visivi, ma devi scrivere del codice per farlo.

>[!ENDTABS]

+++
