---
title: CIF
description: Hjälpsida för Mönsteravkännarkod.
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# CIF {#cif}

Commerce integration framework Classic

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce integration framework Classic"
>abstract="CIF identifierar den klassiska versionen av Commerce integration framework som inte är kompatibel med AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/content-and-commerce/introduction" text=" Innehåll och Commerce"

`CIF` Identifierar den klassiska versionen av Commerce integration framework som inte är kompatibel med AEM as a Cloud Service. Meddelandet för varje `CIF`-sökning identifierar användningen och ger ytterligare information.

Undertyper används för att identifiera olika typer av information:

* `commerce.integration.framework.detected`: En klassisk version av Commerce integration framework är inkompatibel med AEM as a Cloud Service.


## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="Genomförande"
>abstract="Bästa praxis är att granska alla klassiska versioner av Commerce integration framework användning."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/content-and-commerce/changes" text="Betydande förändringar av CIF"

* Den klassiska versionen av Commerce integration framework stöds inte längre på AEM as a Cloud Service. Det skulle blockera uppgraderingen till AEM as a Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="Verktyg och resurser"
>abstract="Den här guiden hjälper dig att identifiera de områden som du måste uppdatera för migreringen av Experience Manager Cloud Service."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/content-and-commerce/migration" text="Migreringsguide för CIF"

* För Experience Manager as a Cloud Service är CIF-tillägget den enda e-handelslösningen som stöds för Adobe Commerce och e-handelslösningar från tredje part. CIF-tillägget distribueras automatiskt till kunder med Experience Manager as a Cloud Service, och ingen manuell driftsättning behövs. Se [Komma igång med AEM Commerce as a Cloud Service](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/content-and-commerce/storefront/getting-started).
* Adobe tillhandahåller [AEM CIF Core Components](https://github.com/adobe/aem-core-cif-components) som stöd för projekt som distribuerar CIF.
* CIF-tillägg är tillgängligt för AEM 6.5 och via [portalen för programvarudistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). Den är kompatibel och innehåller samma funktioner som CIF-tillägget för Experience Manager as a Cloud Service - inga justeringar krävs.
* Klassisk CIF med sina beroenden är inte längre tillgänglig. Kod som bygger på den här CIF-versionen med com.adobe.cq.commerce.api Java™-API:er måste justeras efter CIF-tillägget och dess principer.

Du kan även hitta lösningar för de olika undertyperna nedan:

* `commerce.bundles.detected` - De här paketen avinstalleras under uppgraderingen
* `commerce.packages.detected` - De här paketen tas bort under uppgradering
* `commerce.packages.dependency` - Ta bort alla beroenden av Commerce från anpassade paket
* `commerce.nodes.detected` - Uppdatera anpassad kod för att inte skapa Commerce-noder i CQ
* `commerce.configs.detected` - Använd inte CQ Commerce-konfigurationsegenskaper i anpassad kod
* `commerce.users.detected` - Använd inte CQ Commerce-tjänstanvändare i anpassad kod
* `commerce.overlays.detected` - Ta bort CQ Commerce-övertäckningsanvändning
* `commerce.paths.detected` - Ta bort affärssökvägar när du har kontrollerat att sökvägarna inte används i AEM
* `commerce.resource.type.detected` - Ta bort användning av affärsresurstyp
* `commerce.usage` - Ta bort Commerce-API:er för CQ i din anpassade kod.
