---
title: DM
description: Hjälpsida för mönsteravkännarkod
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 0%

---

# DM {#dm}

Dynamic Media

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM-koden identifierar användningen av AEM Assets Dynamic Media i den aktuella implementeringen. Dynamic Media-läget identifieras av körningsläget."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM - riktlinjer och bästa praxis"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM riktlinjer för as a Cloud Service utveckling"

`DM` använder AEM Assets Dynamic Media. Dynamic Media-läget identifieras av körningsläget.

En undertyp används med den här koden:

* `dynamic.media.runmode`: Det associerade värdet för den här undertypen, om den anges, är antingen:
   * `dynamicmedia`: Dynamic Media - Hybrid-läge
   * `dynamicmedia_scene7`: Dynamic Media - Scen 7-läge

## Möjliga konsekvenser och risker {#implications-and-risks}

* `dynamic.media.runmode`
   * Det kan finnas uppgraderingsproblem som gäller Dynamic Media.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="Genomförande"
>abstract="AEM as a Cloud Service stöder bara körningsläget dynamicmedia_scene7. Granska de aktuella inställningarna och kontakta Adobe Support Team för hjälp och förtydliganden."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html" text="Konfigurera Dynamic Media"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"


* `dynamic.media.runmode`
   * Mer information finns på [Konfigurera Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html).

* Kontakta oss [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
