---
title: intresseanmälning
description: Hjälpsida för Mönsteravkännarkod.
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# intresseanmälning {#ioi}

Import av intern Oak

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="Import av intern Oak"
>abstract="IOI-koden identifierar kundernas användning av interna Oak-paket, som importeras med OSGi. De exporteras utan någon särskild version. Eak bundles eller lågnivåtjänster AEM bara konsumera dem."

`IOI`  Identifierar kundens användning av interna Oak-paket, som importeras via OSGi. De exporteras utan någon särskild version. Eak bundles eller lågnivåtjänster AEM bara konsumera dem.
Vissa av dessa områden används av `com.adobe.granite.repository`, som konfigurerar en databas för AEM vid start. Ett annat exempel är `com.adobe.granite.maintenance.oak` Adobe bundle, som omsluter och tillhandahåller ekunderhåll.

## Möjliga konsekvenser och risker {#implications-and-risks}

* I en senare AEM kan intern export tas bort, vilket orsakar brutna beroenden och inaktiva paket som är direkt beroende av Oak.
* API:n för intern export kan komma att ändras.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="Genomförande"
>abstract="Kunderna bör granska sin egen kod för att identifiera användningen av sådana API:er och omvärdera dem så att de är kompatibla med AEM as a Cloud Service. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Använd Sling Resource API (eller JCR API) i stället för åtkomst på låg nivå.
* Undvik beroende på interna paket som inte är en del av något offentligt API eller SPI.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
