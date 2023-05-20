---
title: DM
description: Hjälpsida för mönsteravkännarkod
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 7%

---

# DM {#dm}

Dynamic Media

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM-koden identifierar användningen av AEM Assets Dynamic Media i den aktuella implementeringen. Dynamic Media-läget identifieras av körningsläget."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM - riktlinjer och bästa praxis"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="Utvecklingsriktlinjer för AEM as a Cloud Service"

`DM` använder AEM Assets Dynamic Media. Dynamic Media-läget identifieras av körningsläget.

En undertyp används med den här koden:

* `dynamic.media.runmode`: Det associerade värdet för den här undertypen, om den anges, är antingen:
   * `dynamicmedia`: Dynamic Media - hybridläge
   * `dynamicmedia_scene7`: Dynamic Media - Scene 7-läge

## Möjliga konsekvenser och risker {#implications-and-risks}

* `dynamic.media.runmode`
   * Det kan finnas uppgraderingsproblem som gäller Dynamic Media.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="Implementeringsvägledning"
>abstract="AEM as a Cloud Service stöder bara körningsläget dynamicmedia_scene7. Granska de aktuella inställningarna och kontakta Adobe Support Team för hjälp och förtydliganden."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html" text="Installera Dynamic Media"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"


* `dynamic.media.runmode`
   * Mer information finns på [Konfigurera Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html).

* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
