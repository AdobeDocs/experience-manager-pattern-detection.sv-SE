---
title: CTEM
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 2%

---


# CTEM {#ctem}

Egen mall

## Bakgrund {#background}

`CTEM` identifierar anpassade mallar som har installerats på AEM. Denna information tillhandahålls för bedömning av bästa metoder.

Mallar identifieras av ett primärt typvärde för &quot;cq:Template&quot;. En undertyp används med den här koden för att identifiera mallkategorin:

* `custom.editable.template`: Mallens sökväg börjar inte med &quot;/apps&quot;.
* `custom.static.template`: Mallens sökväg börjar med &quot;/apps&quot;.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Det bästa sättet är att flytta alla statiska mallar till redigerbara mallar.

## Möjliga lösningar {#solutions}

* Utnyttja [AEM Moderniseringsverktyg](https://opensource.adobe.com/aem-modernize-tools/) för att migrera statiska mallar till redigerbara mallar.
* Mer information om redigerbara mallar finns i [Mallar](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
