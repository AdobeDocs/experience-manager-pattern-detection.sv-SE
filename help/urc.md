---
title: URC
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---


# URC {#urc}

Runmode-konfigurationen stöds inte

## Bakgrund {#background}

`URC` används för att identifiera användningen av konfigurationer som är baserade på ett körningslägesnamn som inte stöds som Cloud Service i AEM.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Den uppsättning namn som kan användas för runmodes i AEM som en Cloud Service är begränsad.
* Konfigurationer som baseras på runmode-namn som inte stöds har ingen effekt när de distribueras till AEM som en Cloud Service.

## Möjliga lösningar {#solutions}

* Granska användningen av den här konfigurationen för att avgöra om det är nödvändigt.
* Byt namn på konfigurationen så att den använder ett av de [namn på körningsläge som stöds](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes) och följ [riktlinjerna för upplösning i körningsläge](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution).
* Granska [wk-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)-projekt och förstå hur [URC-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc) kan korrigeras och göras kompatibla med AEM som en Cloud Service.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
