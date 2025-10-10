---
title: Domini utilizzati da Customer Journey Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
source-git-commit: 8ffbca5dd83987a90d7b744d236e0556314000dd
workflow-type: tm+mt
source-wordcount: '152'
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
| Archiviazione BLOB di Microsoft® Azure | `awaascicdprodva7.blob.core.windows.net` |
| CDN di Microsoft® Azure | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Domini di Adobe Experience Cloud

Oltre ai domini di cui sopra, Adobe Experience Cloud si basa su diversi domini per la raccolta dei dati e l’esportazione dei rapporti. Vedere [Domini utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/domains) per questo elenco di domini.

>[!MORELIKETHIS]
>
>[Indirizzi IP utilizzati da Customer Journey Analytics](ip-addresses.md)
>
>[Domini utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/domains)
