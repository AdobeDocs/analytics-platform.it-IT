---
title: Utilizzare l’oggetto di personalizzazione da usare con Adobe Journey Optimizer
description: Scopri come utilizzare l’oggetto di personalizzazione da usare con Adobe Journey Optimizer
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5086ac6e-5bee-4f0f-b7e5-a3d9bd8a1332
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '132'
ht-degree: 100%

---

# Utilizzare l’oggetto di personalizzazione da usare con Adobe Journey Optimizer {#upgrade-personalization}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-personalization"
>title="Utilizzare l’oggetto di personalizzazione per Adobe Journey Optimizer"
>abstract="Sfruttando le tecnologie all’avanguardia di machine learning e di deep learning controllati, l’ottimizzazione personalizzata consente a un utente aziendale (marketer) di definire gli obiettivi aziendali e utilizza i dati della relativa clientela per addestrare modelli orientati al business che offrano proposte personalizzate e ottimizzano i KPI."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Sfruttando le tecnologie all’avanguardia di machine learning e di deep learning controllati, l’ottimizzazione personalizzata consente a un utente aziendale (marketer) di definire gli obiettivi aziendali e utilizza i dati della relativa clientela per addestrare modelli orientati al business che offrano proposte personalizzate e ottimizzano i KPI.

1. Segui le informazioni disponibili in [Modello di ottimizzazione personalizzato](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/personalized-optimization-model) nella Guida di Journey Optimizer.

{{upgrade-final-step}}

<!--

The result of the personalization object ends up in a dataset. The result of experimentation. When a customer has used AA with Target, that ends up in a complete different space than when they're migrating to CJA and they're going to use CJA with Adobe Target. 

Target was the old way of setting up an A/B test or experimentation. Then ensuring the results of those tests in Target ended up in AA for reporting. Now if you're using Target, instead of saying that you want the data in Target, you can now select CJA as your reporting source for an Adobe Target activity. So if a customer is doing this in AA and they want to move to CJA, ...

If a customer has AJO, and is using Offers in AJO, then they can set up offers, and that also creates datasets in Platform... But that's not relevant with upgrade, exactly.



Questions we need to answer:

1. How do we determine the personalization criteria (Red for user A and blue for User B)

1. What do we implement on the site to determine the red / blue object?


2 ways we can do it:

Manually rendering content or Automatically rendering content. 


## Manual implementation of the Web SDK


## Mobile SDK implementation 





## Tags

-->
