---
title: intresseanmälning
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---


# IOI {#ioi}

Import av intern Oak

## Bakgrund {#background}

`IOI` identifierar kundernas användning av interna Oak-paket, och importerar dem via OSGi. De exporteras vanligtvis utan någon särskild version och är avsedda endast för konsumtion av andra ekpaket eller AEM på låg nivå.

Vissa av dessa används av `com.adobe.granite.repository`, som konfigurerar en databas för AEM vid start. Ett annat exempel är paketet `com.adobe.granite.maintenance.oak` Adobe, som omsluter och tillhandahåller Oak-underhållsåtgärder.

## Möjliga konsekvenser och risker {#implications-and-risks}

* I en senare AEM kan intern export tas bort, vilket kan orsaka brutna beroenden och inaktiva paket som är direkt beroende av Oak.
* API:n för intern export kan ändras.

## Möjliga lösningar {#solutions}

* Använd Sling Resource API (eller JCR API) i stället för åtkomst på låg nivå.
* Undvik beroende på interna paket som inte är en del av något offentligt API eller SPI.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.