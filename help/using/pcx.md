---
title: PCX
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
source-git-commit: b77a168fc8c075e8e41149a38df4d83fd2504a14
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# PCX {#pcx}

Sidkomplexitet

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="Sidkomplexitet"
>abstract="PCX identifierar sidor som innehåller ett stort antal noder i sin struktur."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="Betydande ändringar - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - versionsinformation"

`PCX`  Identifierar sidor som innehåller många noder i sin struktur.

Undertyper används för att identifiera olika typer av information:

* `page.complexity.medium`: En sida innehåller ett måttligt stort antal noder som kan påverka återgivningsprestanda.
* `page.complexity.high`: En sida innehåller ett stort antal noder som troligen påverkar återgivningsprestanda.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Många noder på en sida kan påverka återgivningsprestanda.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="Genomförande"
>abstract="Det bästa sättet är att granska innehållsstrukturen för att minska sidans komplexitet. Det kan i sin tur förbättra sidåtergivningsprestanda. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Minska det totala antalet noder på en sida genom att utföra följande åtgärd:
   * Kontrollera att det inte finns några onödiga behållare.
   * Testa om samma layout kan användas med färre behållare.
   * Förenkla sidinnehållet.
   * Minska djupet i nodstrukturen.
   * Spärra eventuella medföljande upplevelsefragment för enkelhet.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
