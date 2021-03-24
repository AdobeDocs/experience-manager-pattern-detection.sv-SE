---
title: DOPI
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# DOPI {#dopi}

Inaktuellt sorterat egenskapsindex

## Bakgrund {#background}

`DOPI` identifierar användningen av ordnade egenskapsindexdefinitioner (`primaryType=oak:QueryIndexDefinition` AND  `type="ordered"`) som har tagits bort sedan 6.1 och tagits bort i 6.2.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Vissa frågor kanske inte svarar.
* Kundens funktionalitet kanske inte fungerar som den ska.
* Genomför varningar eller till och med fel och betydande prestandapåföljder eftersom de inaktuella indexen inte har någon effekt.

## Möjliga lösningar {#solutions}

* Ändra indexdefinitionen så att den blir, eller ersätter indexet med, en indexdefinition som stöds. (Se [Fråga och indexera](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html)).
* Granska [wk-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)-projekt och förstå hur [DOPI-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi) kan korrigeras och göras kompatibla med AEM som en Cloud Service.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
