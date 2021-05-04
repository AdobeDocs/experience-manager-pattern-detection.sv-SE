---
title: intresseanmälning
description: Hjälpsida för mönsteravkännarkod
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# IOI {#ioi}

Import av intern Oak

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="Import av intern Oak"
>abstract="IOI-koden identifierar kundernas användning av interna Oak-paket, som importerar dem via OSGi. De exporteras vanligtvis utan någon särskild version och är avsedda endast för konsumtion av andra ekpaket eller AEM på låg nivå."

`IOI` identifierar kundernas användning av interna Oak-paket, och importerar dem via OSGi. De exporteras vanligtvis utan någon särskild version och är avsedda endast för konsumtion av andra ekpaket eller AEM på låg nivå.

Vissa av dessa används av `com.adobe.granite.repository`, som konfigurerar en databas för AEM vid start. Ett annat exempel är paketet `com.adobe.granite.maintenance.oak` Adobe, som omsluter och tillhandahåller Oak-underhållsåtgärder.

## Möjliga konsekvenser och risker {#implications-and-risks}

* I en senare AEM kan intern export tas bort, vilket kan orsaka brutna beroenden och inaktiva paket som är direkt beroende av Oak.
* API:n för intern export kan ändras.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="Implementeringsvägledning"
>abstract="Kunderna bör granska sin egen kod för att identifiera användningen av sådana API:er och omvärdera dem så att de är kompatibla med AEM som en Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Använd Sling Resource API (eller JCR API) i stället för åtkomst på låg nivå.
* Undvik beroende på interna paket som inte är en del av något offentligt API eller SPI.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
