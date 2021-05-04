---
title: LOCP
description: Hjälpsida för mönsteravkännarkod
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# LOCP {#locp}

/libs Skriva över anpassade paket

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs Skriva över anpassade paket"
>abstract="LOCP identifierar identifieringen av ett anpassat paket som levererar innehåll till /libs, som är ett antimönsterpaket (förutom i ACL-listor)."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="Hållbara uppgraderingar"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Samla resurser"

`LOCP` identifierar identifieringen av ett anpassat paket som levererar innehåll till  `/libs`, vilket är ett antimönster (förutom i fallet åtkomstkontrollistor).

## Möjliga konsekvenser och risker {#implications-and-risks}

* Kundkoden kan tas bort eller ersättas för alla uppgraderingar av CFP, SP eller större AEM.
* I vissa fall kanske det nya innehållet inte installeras korrekt.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="Implementeringsvägledning"
>abstract="Kunderna bör granska sin egen kod och sina paket för att identifiera om innehåll levereras till /libs och omfaktorisera det för att förlita sig på att innehållet under /apps överlappas och göra det kompatibelt med AEM som en Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="Övertäckningar"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Kundpaket ska distribuera innehåll till `/apps` i stället för `/libs`.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
