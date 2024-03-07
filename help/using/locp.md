---
title: LOCP
description: Hjälpsida för mönsteravkännarkod
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '175'
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

`LOCP` identifierar identifieringen av ett anpassat paket som levererar innehåll till `/libs`, som är ett antimönster (utom ACL-listor).

## Möjliga konsekvenser och risker {#implications-and-risks}

* Kundkoden kan tas bort eller ersättas för alla uppgraderingar av CFP, SP eller större AEM.
* I vissa fall kanske det nya innehållet inte installeras korrekt.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="Genomförande"
>abstract="Kunderna bör granska sin egen kod och sina paket för att identifiera om innehåll levereras till /libs och omfaktorisera det för att förlita sig på att innehållet under /apps överlappar och gör det kompatibelt med AEM as a Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="Övertäckningar"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Kundpaket ska distribuera innehåll till `/apps` i stället för `/libs`.
* Kontakta oss [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
