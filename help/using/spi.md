---
title: SPI
description: Hjälpsida för Mönsteravkännarkod.
source-git-commit: e050b9190f67fd6ccfac31490c4bf2a60d47731f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# SPI {#spi}

## Bakgrund {#background}

SIF identifierar sökning och marknadsföring som inte är kompatibel med AEM 6.5 LTS.

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## Möjliga lösningar {#solutions}

Hitta möjliga lösningar för de olika undertyperna nedan:

* `searchpromote.bundles.detected` - Dessa paket avinstalleras under uppgraderingen
* `earchpromote.packages.detected` - De här paketen tas bort under uppgraderingen
* `searchpromote.packages.dependency` - Ta bort eventuell sökning och höj upp beroenden som dina anpassade paket kan ha
* `searchpromote.usage` - Ta bort API:er för sökning och marknadsföring från din anpassade kod
* `searchpromote.users.detected` - Använd inte tjänstanvändarna Search och Promote i anpassad kod
* `searchpromote.configs.detected` - Använd inte konfigurationsegenskaperna Sök och Befordra i din anpassade kod.