---
title: Domini utilizzati da Customer Journey Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
TQID: https://experienceleague.adobe.com/d-nNfumskelDKrgCPQpyoZIagJrGcniXyQgACaHh5tA
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 3%

---

# Domini utilizzati da Customer Journey Analytics

Alcune configurazioni del firewall bloccano i domini su cui Customer Journey Analytics si basa per l’interfaccia di prodotto. È possibile utilizzare questo elenco di domini per modificare le impostazioni di rete dell&#39;organizzazione per consentire l&#39;accesso ai prodotti dall&#39;interno dell&#39;organizzazione. Per un’esperienza ottimale, Adobe consiglia di abilitare questi domini attraverso il firewall dell’organizzazione.

| Tecnologia | Dominio |
| --- | --- |
| Domini Customer Journey Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDark | `app.launchdarkly.com` |
| Archiviazione BLOB Microsoft® Azure | `awaascicdprodva7.blob.core.windows.net` |
| CDN MICROSOFT® AZURE | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Domini di Adobe Experience Cloud

Oltre ai domini di cui sopra, Adobe Experience Cloud si basa su diversi domini per la raccolta dei dati e l’esportazione dei rapporti. Vedere [Domini utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains) per questo elenco di domini.

>[!MORELIKETHIS]
>
>[Indirizzi IP utilizzati da Customer Journey Analytics](ip-addresses.md)
>
>[Domini utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
