---
title: INST
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---


# INST {#inst}

Installerad artefakt

## Bakgrund {#background}

`INST` identifierar anpassade paket och paket från tredje part som kunden har installerat i AEM. Dessa rapporteras för att bidra till att karakterisera systemets tillstånd i den allmänna omfattningen av en uppgraderingsinsats.

När flera versioner av ett paket har installerats rapporteras endast den senaste versionen.

Paket och paket som identifieras har inte nödvändigtvis optimerats för AEM som en Cloud Service. Alla tredjepartspaket bör verifieras med den som skapat dem eller Adobe för kompatibilitet med AEM som Cloud Service.

Undertyper används för att identifiera olika typer av information:

* `custom.bundle`: Ett paket som har installerats i AEM.
* `custom.package`: Ett paket som har installerats i AEM.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Det går inte att installera tredjepartspaket med CRX Package Manager i AEM som Cloud Service.
* Program som är beroende av tredjepartspaket kanske inte fungerar som förväntat förrän de distribueras korrekt för att fungera med AEM som en Cloud Service.
* Om leverantörspaket från tredje part inte är optimerade för AEM som en molntjänst kan det leda till oönskat beteende.

## Möjliga lösningar {#solutions}

* Tredjepartspaket ska distribueras till AEM som en del av projektet med Cloud Manager [distributionsprocessen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html#deployment-process).
* Granska hur du [bäddar in tredjepartspaket](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embedding-3rd-party-packages) i ditt projekt för AEM som en Cloud Service.
* Tredjepartspaket måste följa AEM som en Cloud Service [utveckling](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html) och [paketering](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html).
* Granska [wk-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)-projekt och förstå hur [INST-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst) kan korrigeras och göras kompatibla med AEM som en Cloud Service.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
