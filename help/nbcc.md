---
title: NBCC
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---


# NBCC {#nbcc}

Icke-bakåtkompatibla ändringar

## Bakgrund {#background}

`NBCC` identifierar den situation där vissa JCR-noder eller paket ändras på ett sätt som inte är kompatibelt. Kunden kanske inte känner till den här ändringen före en uppgradering.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Funktionen som är beroende av en komponent som använder icke-bakåtkompatibla ändringar kan brytas och kanske inte löses korrekt.
* Vissa funktioner i kundprogrammet eller vissa AEM kanske inte fungerar som de ska efter en uppgradering.

## Möjliga lösningar {#solutions}

* Överlägg eller referera endast bakåtkompatibla Sling-komponenter.
* Överväg att anpassa resurser som kommer från `/libs` eller paket efter en AEM uppgradering.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
