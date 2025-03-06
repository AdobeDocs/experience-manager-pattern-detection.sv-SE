---
title: SCR
description: Hjälpsida för Mönsteravkännarkod.
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%

---

# SCR {#scr}

## Bakgrund {#background}

SIF identifierar att AEM Screens inte är kompatibelt med AEM 6.5 LTS.

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## Möjliga lösningar {#solutions}

Hitta möjliga lösningar för de olika undertyperna nedan:

* `screens.bundles.detected` - De här paketen avinstalleras under uppgraderingen.
* `screens.packages.detected` - De här paketen tas bort under uppgraderingen.
* `screens.packages.dependency` - Ta bort alla beroenden av Screens från dina anpassade paket.
* `screens.configs.detected` - Kontrollera att du inte använder några Screens-konfigurationsegenskaper i din anpassade kod.
* `screens.users.detected` - Kontrollera att du inte använder Screens-tjänstanvändare i anpassad kod.
* `screens.paths.detected` - Ta bort Screens-sökvägar efter att ha kontrollerat att de inte används i AEM.
* `screens.resource.type.detected` - Ta bort användning av Screens-resurstyp.
* `screens.usage` - Ta bort Screens API:er från din anpassade kod.