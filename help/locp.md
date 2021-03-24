---
title: LOCP
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 0%

---


# LOCP {#locp}

/libs Skriva över anpassade paket

## Bakgrund {#background}

`LOCP` identifierar identifieringen av ett anpassat paket som levererar innehåll till  `/libs`, vilket är ett antimönster (förutom i fallet åtkomstkontrollistor).

## Möjliga konsekvenser och risker {#implications-and-risks}

* Kundkoden kan tas bort eller ersättas för alla uppgraderingar av CFP, SP eller större AEM.
* I vissa fall kanske det nya innehållet inte installeras korrekt.

## Möjliga lösningar {#solutions}

* Kundpaket ska distribuera innehåll till `/apps` i stället för `/libs`.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
