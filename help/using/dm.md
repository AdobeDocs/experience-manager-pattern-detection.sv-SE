---
title: DM
description: Lär dig mer om hur koden för Mönsteravkännare identifierar användningen av AEM Assets - Dynamic Media.
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# DM {#dm}

Dynamic Media

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM-koden identifierar användningen av AEM Assets Dynamic Media i den aktuella implementeringen. Körningsläget identifierar Dynamic Media-läget."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM - riktlinjer och bästa praxis"
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service riktlinjer för utveckling"

`DM` (Dynamic Media) Identifierar användning av AEM Assets Dynamic Media. Körningsläget identifierar Dynamic Media-läget.

En undertyp används med den här koden:

* `dynamic.media.runmode`: Det associerade värdet för den här undertypen, om den anges, är antingen:
   * `dynamicmedia`: Dynamic Media - hybridläge
   * `dynamicmedia_scene7`: Dynamic Media - Scene7

## Möjliga konsekvenser och risker {#implications-and-risks}

* `dynamic.media.runmode`
   * Det kan finnas uppgraderingsproblem som gäller Dynamic Media.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="Genomförande"
>abstract="AEM as a Cloud Service stöder endast körningsläget dynamicmedia_scene7. Granska de aktuella inställningarna och kontakta Adobe Support Team för hjälp och förtydliganden."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media" text="Konfigurera Dynamic Media"
>additional-url="https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"


* `dynamic.media.runmode`
   * Mer information finns i [Konfigurera Dynamic Media](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media).

* Kontakta [AEM supportteamet](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) om du behöver klargöranden eller frågor som har åtgärdats.
