---
title: Domini utilizzati da Customer Journey Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
autotag-review: '2026-05-19T09:27:11.172Z'
TQID: 'https://experienceleague.adobe.com/y3FgZsfqtozN8IaJlBvmfybUIH3s7fiiw2Rc4iNLyGI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 1%

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

## Domini aziendali CX

Oltre ai domini di cui sopra, CX Enterprise si basa su diversi domini per la raccolta dei dati e l&#39;esportazione dei report. Per l&#39;elenco dei domini, vedere [Domini utilizzati da CX Enterprise](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/domains).

>[!MORELIKETHIS]
>
>[Indirizzi IP utilizzati da Customer Journey Analytics](ip-addresses.md)
>
>[Domini utilizzati da CX Enterprise](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/domains)
