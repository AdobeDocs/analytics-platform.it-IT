---
title: Indirizzi IP utilizzati dal Customer Journey Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
solution: Customer Journey Analytics
feature: Basics
exl-id: 5c52986c-7ff3-45b5-9039-2bfb6529238c
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Indirizzi IP utilizzati dal Customer Journey Analytics

Alcune configurazioni del firewall bloccano gli indirizzi IP provenienti dai server di raccolta dati di Adobe o dai server responsabili dell’accesso ai dati. Puoi utilizzare questo elenco di intervalli per modificare le impostazioni del firewall dell’organizzazione per consentire l’accesso e l’invio di dati dall’interno dell’organizzazione.

Questa pagina include gli indirizzi IP da aggiungere al inserisco nell&#39;elenco Consentiti di per il funzionamento dei sistemi in uscita, ad esempio [esportazione di dati in un provider cloud](/help/analysis-workspace/export/export-cloud.md).

>[!IMPORTANT]
>
>Adobe fa del suo meglio per mantenere aggiornato questo documento, ma non può garantire che l’elenco degli intervalli IP rimanga lo stesso. Tra i possibili cambiamenti vi sono la crescita e l&#39;espansione dell&#39;attività, un registro Internet richiede modifiche allo spazio di indirizzi IP di Adobe o un provider di servizi Internet smette di funzionare.

## VA7: clienti USA e America

| Blocco IP (notazione CIDR) |
| --- |
| `52.254.106.192/28` |
| `52.254.107.80/28` |
| `52.254.106.240/28` |
| `52.254.107.32/28` |
| `52.254.106.176/28` |
| `52.254.106.144/28` |
| `52.254.107.64/28` |
| `20.186.185.181` |
| `20.186.185.239` |
| `52.254.106.160/28` |
| `40.70.154.136/29` |
| `20.22.83.112` |
| `52.254.107.16/28` |
| `52.254.105.192/28` |
| `52.254.107.144/28` |
| `52.254.106.0/28` |
| `52.254.106.224/28` |
| `52.254.107.128/28` |
| `52.254.106.208/28` |
| `20.186.185.227` |
| `52.254.107.0/28` |

## NLD2: Europa

| Blocco IP (notazione CIDR) |
| --- |
| `40.74.6.128/28` |
| `51.144.184.248/29` |
| `40.74.7.192/28` |
| `40.74.7.128/28` |
| `40.74.7.176/28` |
| `20.50.23.153` |
| `40.74.6.80/28` |
| `40.74.6.144/28` |
| `40.74.5.128/28` |
| `51.105.144.1` |
| `51.105.144.81` |
| `40.74.4.176/28` |
| `52.142.236.87` |
| `40.74.4.144/28` |
| `20.101.246.9` |
| `40.74.4.160/28` |
| `40.74.7.160/28` |
| `40.74.7.144/28` |
| `40.74.3.176/28` |
| `51.124.70.4` |
| `40.74.6.96/28` |
| `40.74.7.208/28` |
| `40.74.6.112/28` |

## AUS5: Australia

| Blocco IP (notazione CIDR) |
| --- |
| `20.43.110.192/28` |
| `20.40.185.111` |
| `20.43.97.95` |
| `20.43.111.16/28` |
| `20.193.38.208/28` |
| `20.43.110.64/28` |
| `20.40.185.225` |
| `20.43.110.112/28` |
| `20.43.110.224/28` |
| `20.193.36.37` |
| `20.43.110.240/28` |
| `20.43.111.32/28` |
| `20.40.185.185` |
| `20.43.111.0/28` |
| `20.43.110.208/28` |
| `20.43.110.96/28` |
| `20.43.110.48/28` |
| `20.43.110.128/28` |
| `20.43.110.160/28` |
| `20.43.110.80/28` |
| `20.193.56.144/28` |
| `20.193.56.160/28` |
| `20.43.110.176/28` |
| `20.43.110.144/28` |
| `20.53.111.113` |
| `20.193.56.128/28` |
| `20.227.32.175` |

## CAN2: Canada

| Blocco IP (notazione CIDR) |
| --- |
| `20.116.159.80/28` |
| `20.116.159.224/28` |
| `20.116.159.192/28` |
| `20.116.159.64/28` |
| `20.151.241.173` |
| `20.116.159.128/28` |
| `20.116.159.208/28` |
| `20.116.159.48/28` |
| `20.151.240.247` |
| `20.116.159.0/28` |
| `20.220.243.238` |
| `20.116.175.240/28` |
| `20.116.155.128/28` |
| `20.116.248.0/28` |
| `20.151.241.138` |
| `20.116.159.144/28` |
| `20.116.175.224/28` |
| `20.116.248.16/28` |
| `20.151.241.124` |
| `20.116.159.160/28` |
| `20.116.159.96/28` |
| `20.104.5.248` |
| `20.116.159.112/28` |
| `20.116.159.176/28` |
| `20.116.159.32/28` |
| `20.116.158.240/28` |

>[!MORELIKETHIS]
>
>[Domini utilizzati dal Customer Journey Analytics](domains.md)
>
>[Indirizzi IP utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)