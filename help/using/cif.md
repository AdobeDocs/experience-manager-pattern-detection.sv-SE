---
title: CIF
description: Hjälpsida för Mönsteravkännarkod.
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# CIF {#cif}

Commerce integration framework Classic

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce integration framework Classic"
>abstract="CIF identifierar den klassiska versionen av Commerce integrationa frameworkens användning som är inkompatibel med AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/introduction" text=" Innehåll och handel"

`CIF`  Identifierar den klassiska versionen av Commerce integrationa frameworkens användning som är inkompatibel med AEM as a Cloud Service. Meddelandet för varje `CIF` identifierar användningen och ger ytterligare information.

Undertyper används för att identifiera olika typer av information:

* `commerce.integration.framework.detected`: En klassisk version av Commerce integration framework som inte är kompatibel med AEM as a Cloud Service.


## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="Genomförande"
>abstract="Det bästa sättet är att granska all klassisk Commerce integration framework."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/changes" text="Betydande ändringar i CIF"

* Den klassiska versionen av Commerce integrationa frameworken stöds inte längre på AEM as a Cloud Service. Det skulle blockera uppgraderingen till AEM as a Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="Verktyg och resurser"
>abstract="Den här guiden hjälper dig att identifiera de områden som du måste uppdatera för migrering av Experience Manager Cloud Service."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/migration" text="Migreringsguide för CIF"

* För Experience Manager as a Cloud Service är CIF-tillägget den enda e-handelslösningen som stöds för Adobe Commerce och e-handelslösningar från tredje part. Tillägget CIF driftsätts automatiskt för kunder på Experience Manager as a Cloud Service; ingen manuell driftsättning behövs. Se [Komma igång med AEM Commerce as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/storefront/getting-started).
* För att stödja projekt som distribuerar CIF tillhandahåller Adobe [AEM CIF kärnkomponenter](https://github.com/adobe/aem-core-cif-components).
* CIF är också tillgängligt för AEM 6.5 genom [Programdistributionsportal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). Den är kompatibel och innehåller samma funktioner som CIF för Experience Manager as a Cloud Service - inga justeringar krävs.
* Klassisk CIF med sina beroenden är inte längre tillgänglig. Kod som bygger på den här CIF versionen med com.adobe.cq.commerce.api Java™ API:er måste justeras till CIF och dess principer.
