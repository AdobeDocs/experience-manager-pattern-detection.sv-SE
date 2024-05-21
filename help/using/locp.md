---
title: LOCP
description: Hjälpsida för Mönsteravkännarkod.
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# LOCP {#locp}

/libs Skriva över anpassade paket

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs Skriva över anpassade paket"
>abstract="LOCP identifierar identifieringen av ett anpassat paket som levererar innehåll till `/libs`, som är ett antimönster (förutom om det finns åtkomstkontrollistor)."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="Hållbara uppgraderingar"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Samla resurser"

`LOCP`  Identifierar identifieringen av ett anpassat paket som levererar innehåll till `/libs`, som är ett antimönster (utom ACL-listor).

## Möjliga konsekvenser och risker {#implications-and-risks}

* Kundkoden kan tas bort eller ersättas för alla CFP-, SP- eller större AEM-uppgraderingar.
* Ibland kanske det nya innehållet inte installeras korrekt.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="Genomförande"
>abstract="Kunderna bör granska sin egen kod och sina paket för att se om innehållet levereras till `/libs`. Om det behövs kan du ändra det så att det förlitar sig på övertäckning av innehållet under /apps och göra det kompatibelt med AEM as a Cloud Service. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Övertäckningar"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Kundpaket ska distribuera innehåll till `/apps` i stället för `/libs`.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) om ni behöver klargöranden eller frågor som behandlas.
