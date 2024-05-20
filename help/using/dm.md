---
title: DM
description: Lär dig mer om hur koden för Mönsteravkännare identifierar användningen av AEM Assets - Dynamic Media.
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# DM {#dm}

Dynamic Media

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM-koden identifierar användningen av AEM Assets Dynamic Media i den aktuella implementeringen. Dynamic Media-läget identifieras av körningsläget."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM - riktlinjer och bästa praxis"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM riktlinjer för as a Cloud Service utveckling"

`DM` (Dynamic Media) Identifierar användningen av AEM Assets Dynamic Media. Dynamic Media-läget identifieras av körningsläget.

En undertyp används med den här koden:

* `dynamic.media.runmode`: Det associerade värdet för den här undertypen, om den anges, är antingen:
   * `dynamicmedia`: Dynamic Media - Hybrid-läge
   * `dynamicmedia_scene7`: DYNAMIC MEDIA - SCENE7

## Möjliga konsekvenser och risker {#implications-and-risks}

* `dynamic.media.runmode`
   * Det kan finnas uppgraderingsproblem som gäller Dynamic Media.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="Genomförande"
>abstract="AEM as a Cloud Service stöder endast körningsläget dynamicmedia_scene7. Granska de aktuella inställningarna och kontakta Adobe Support Team för hjälp och förtydliganden."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media" text="Konfigurera Dynamic Media"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"


* `dynamic.media.runmode`
   * Mer information finns på [Konfigurera Dynamic Media](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media).

* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) om ni behöver klargöranden eller frågor som behandlas.
