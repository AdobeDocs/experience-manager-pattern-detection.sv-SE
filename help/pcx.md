---
title: PCX
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# PCX {#pcx}

Sidkomplexitet

## Bakgrund {#background}

`PCX` identifierar sidor som innehåller ett stort antal noder i sin struktur.

Undertyper används för att identifiera olika typer av information:

* `page.complexity.medium`: En sida innehåller ett måttligt stort antal noder som kan påverka återgivningsprestanda.
* `page.complexity.high`: En sida innehåller ett mycket stort antal noder som troligen kommer att påverka återgivningsprestanda.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Ett stort antal noder på en sida kan påverka återgivningsprestanda.

## Möjliga lösningar {#solutions}

* Minska det totala antalet noder på en sida genom att utföra följande steg:
   * Kontrollera att det inte finns några onödiga behållare.
   * Testa om samma layout kan användas med färre behållare.
   * Förenkla sidinnehållet.
   * Minska djupet i nodstrukturen.
   * Spärra eventuella medföljande upplevelsefragment för enkelhetens skull.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
