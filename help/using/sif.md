---
title: SIF
description: Hjälpsida för Mönsteravkännarkod.
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---

# SIF {#sif}

## Bakgrund {#background}

SIF identifierar social användning som inte är kompatibel med AEM 6.5 LTS.

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## Möjliga lösningar {#solutions}

Hitta möjliga lösningar för de olika undertyperna nedan:

* `social.bundles.detected` - De här paketen avinstalleras under uppgraderingen
* `social.packages.detected` - De här paketen tas bort under uppgradering
* `social.packages.dependency` - Ta bort socialt paketberoende från anpassade paket
* `social.nodes.detected` - Uppdatera anpassad kod för att inte skapa sociala noder
* `social.configs.detected` - Använd inte egenskaper för social konfiguration i anpassad kod
* `social.users.detected` - Använd inte sociala användare i anpassad kod
* `social.overlays.detected` - Ta bort användning av sociala övertäckningar
* `social.paths.detected` - Ta bort sociala sökvägar efter att ha kontrollerat att de här sökvägarna inte används i AEM
* `social.resource.type.detected` - Ta bort användning av social resurstyp
* `social.usage` - Ta bort sociala API:er från anpassad kod.