---
title: Domini utilizzati dal Customer Journey Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
role: Admin
source-git-commit: 43bda939a5464c5f65b0a050ccfdb5ba17f7d34b
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 3%

---

# Domini utilizzati dal Customer Journey Analytics

Alcune configurazioni del firewall bloccano i domini su cui il Customer Journey Analytics si basa per l’interfaccia di prodotto. È possibile utilizzare questo elenco di domini per modificare le impostazioni di rete dell&#39;organizzazione per consentire l&#39;accesso ai prodotti dall&#39;interno dell&#39;organizzazione. L’Adobe consiglia di abilitare questi domini attraverso il firewall dell’organizzazione per un’esperienza ottimale.

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

Oltre ai domini di cui sopra, Adobe Experience Cloud si basa su diversi domini per la raccolta dei dati e l’esportazione dei rapporti. Consulta [Domini utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains) per questo elenco di domini.

>[!MORELIKETHIS]
>
>[Indirizzi IP utilizzati dal Customer Journey Analytics](ip-addresses.md)
>
>[Domini utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)