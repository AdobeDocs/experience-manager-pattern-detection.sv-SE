---
title: WRF
description: Hjälpsida för Mönsteravkännarkod.
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 0%

---

# WRF {#wrf}

## Bakgrund {#background}

WRF identifierar webbutiksanvändning som inte är kompatibel med AEM 6.5 LTS.

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## Möjliga lösningar {#solutions}

Hitta möjliga lösningar för de olika undertyperna nedan:

* `weretail.bundles.detected` - De här paketen avinstalleras under uppgraderingen
* `weretail.packages.detected` - De här paketen tas bort under uppgradering
* `weretail.configs.detected` - Använd inte konfilegenskaperna We.Retail i din anpassade kod
* `weretail.packages.dependency` - Ta bort beroendet för anpassade paket på We.Retail
* `weretail.paths.detected` - Dessa We.Retail-sökvägar kan tas bort efter att du har kontrollerat att du inte använder sociala medier
* `weretail.resource.type.detected` - Ta bort användning av resurstypen Vi.Retail
* `weretail.usage` - Ta bort API:er för webb.butik från din anpassade kod.