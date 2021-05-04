---
title: PCX
description: Hjälpsida för mönsteravkännarkod
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---

# PCX {#pcx}

Sidkomplexitet

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="Sidkomplexitet"
>abstract="PCX identifierar sidor som innehåller ett stort antal noder i sin struktur."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="Betydande ändringar - AEM som en Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM som Cloud Service - Versionsinformation"

`PCX` identifierar sidor som innehåller ett stort antal noder i sin struktur.

Undertyper används för att identifiera olika typer av information:

* `page.complexity.medium`: En sida innehåller ett måttligt stort antal noder som kan påverka återgivningsprestanda.
* `page.complexity.high`: En sida innehåller ett mycket stort antal noder som troligen kommer att påverka återgivningsprestanda.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Ett stort antal noder på en sida kan påverka återgivningsprestanda.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="Implementeringsvägledning"
>abstract="Det bästa sättet är att granska innehållsstrukturen för att minska sidkomplexiteten, vilket resulterar i bättre sidåtergivningsprestanda. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Minska det totala antalet noder på en sida genom att utföra följande steg:
   * Kontrollera att det inte finns några onödiga behållare.
   * Testa om samma layout kan användas med färre behållare.
   * Förenkla sidinnehållet.
   * Minska djupet i nodstrukturen.
   * Spärra eventuella medföljande upplevelsefragment för enkelhetens skull.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
