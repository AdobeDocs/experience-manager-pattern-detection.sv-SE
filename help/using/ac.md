---
title: AC
description: Hjälpsida för Mönsteravkännarkod.
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%

---

# AC {#ac}

## Bakgrund {#background}

AC identifierar Assets-paketanvändning som inte är kompatibel med AEM 6.5 LTS

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## Möjliga lösningar {#solutions}

Hitta möjliga lösningar för de olika undertyperna nedan:

* `asset.bundles.detected` - Det här paketet avinstalleras under uppgraderingen.
* `asset.usage` - Ta bort alla komponentberoenden för tillgångsklassificering och tillgångskatalog från anpassad kod. Ändra koden om tillämpligt så att den använder det nya API:t `List<Scene7ConfigSetting>` `com.day.cq.dam.scene7.api.model.Scene7ViewerConfig#getSettingsList()`.
* `asset.overlays.detected` - Övertäckningar som skapats i Assets-komponenter för klassificering och katalog måste tas bort.
* `asset.resource.type.detected` - Ta bort all användning av resurstypen för Assets-klassificeringskomponenten i din anpassade kod.
* `asset.paths.detected` - Flytta allt kundinnehåll som finns under dessa sökvägar och ta bort dessa sökvägar efter att ha kontrollerat att de inte används i AEM.