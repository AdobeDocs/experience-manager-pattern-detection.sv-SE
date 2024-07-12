---
title: INS
description: Hjälpsida för Mönsteravkännarkod.
exl-id: d89e1589-3195-4b2d-98f4-136bedaecb0b
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%

---

# INS {#ins}

Ogiltigt namnutrymme

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_overview"
>title="Ogiltigt namnutrymme"
>abstract="INS identifierar namnutrymmesproblem AEM instansen"

`INS` (ogiltigt namnområde) Identifierar namnområdesproblem i AEM.

Undertyper används för att identifiera olika typer av information, som:

* `uri`: Identifiera den ogiltiga namnområdes-URI:n i AEM.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Det går inte att replikera innehåll (över skiktet) eller kopiera innehåll (över `env`, via `/crx/packMgr` eller innehållskopia).

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_guidance"
>title="Genomförande"
>abstract="Kontakta kundtjänst om du behöver hjälp."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Åtgärda namnutrymmesdefinitionerna enligt [JCR-specifikationen](https://developer.adobe.com/experience-manager/reference-materials/spec/jcr/1.0/4.5_Namespaces.html). Följ stegen som anges [här](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/how-can-i-delete-a-namespace-created-in-crx/td-p/225163)
* Kontakta [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
