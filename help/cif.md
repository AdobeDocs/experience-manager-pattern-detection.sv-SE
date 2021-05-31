---
title: CIF
description: Hjälpsida för mönsteravkännarkod
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 84aea5b24e51ce5672826bad4ec126074bf24a09
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# CIF {#cif}

Commerce Integration Framework Classic

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF identifierar den klassiska versionen av Commerce Integration Framework-användningen som är inkompatibel med AEM som en Cloud Service."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/introduction.html" text=" Innehåll och handel"

`CIF` CIF identifierar den klassiska versionen av Commerce Integration Framework-användningen som är inkompatibel med AEM som en Cloud Service. Meddelandet för varje `CIF`-sökning identifierar användningen och ger ytterligare information.

Undertyper används för att identifiera olika typer av information:

* `commerce.integration.framework.detected`: En klassisk version av Commerce Integration Framework är inte kompatibel med AEM som Cloud Service.


## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="Implementeringsvägledning"
>abstract="Bästa praxis är att granska alla klassiska versioner av Commerce Integration Framework-användning."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/changes.html" text="Betydande ändringar i CIF"

* Den klassiska versionen av Commerce Integration Framework stöds inte längre som Cloud Service på AEM. Det skulle blockera uppgraderingen till AEM som en Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="Verktyg och resurser"
>abstract="Den här guiden hjälper dig att identifiera de områden du behöver uppdatera för migrering av Experience Manager Cloud Service."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/migration.html" text="Migreringsguide för CIF"

* För Experience Manager som Cloud Service är CIF-tillägget den enda handelslösningen som stöds för Adobe Commerce och e-handelslösningar från tredje part. CIF-tillägget distribueras automatiskt till kunder på Experience Manager som Cloud Service, och ingen manuell driftsättning behövs. Se [Komma igång med AEM Commerce som en Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/storefront/getting-started.html).
* För att stödja projekt som distribuerar CIF Adobe tillhandahåller [AEM CIF Core Components](https://github.com/adobe/aem-core-cif-components).
* CIF-tillägg är tillgängligt för AEM 6.5 och via [portalen för programvarudistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). Den är kompatibel och har samma funktioner som CIF-tillägget för Experience Manager som en Cloud Service - inga justeringar krävs.
* Klassisk CIF med sina beroenden är inte längre tillgänglig. Kod som är beroende av den här CIF-versionen med com.adobe.cq.commerce.api Java API:er måste justeras till CIF-tillägget och dess principer.
