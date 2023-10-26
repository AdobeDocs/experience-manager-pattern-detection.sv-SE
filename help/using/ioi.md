---
title: intresseanmälning
description: Hjälpsida för mönsteravkännarkod
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# intresseanmälning {#ioi}

Import av intern Oak

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="Import av intern Oak"
>abstract="IOI-koden identifierar kundernas användning av interna Oak-paket, som importerar dem via OSGi. De exporteras vanligtvis utan någon särskild version och är avsedda endast för konsumtion av andra ekpaket eller AEM på låg nivå."

`IOI` identifierar kundernas användning av interna Oak-paket, och importerar dem via OSGi. De exporteras vanligtvis utan någon särskild version och är avsedda endast för konsumtion av andra ekpaket eller AEM på låg nivå.

Vissa av dessa används av `com.adobe.granite.repository`, som konfigurerar en databas för AEM vid start. Ett annat exempel är `com.adobe.granite.maintenance.oak` Adobe bundle, som omsluter och tillhandahåller ekunderhåll.

## Möjliga konsekvenser och risker {#implications-and-risks}

* I en senare AEM kan intern export tas bort, vilket kan orsaka brutna beroenden och inaktiva paket som är direkt beroende av Oak.
* API:n för intern export kan komma att ändras.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="Genomförande"
>abstract="Kunderna bör granska sin egen kod för att identifiera användningen av sådana API:er och omvärdera dem så att de är kompatibla med AEM as a Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Använd Sling Resource API (eller JCR API) i stället för åtkomst på låg nivå.
* Undvik beroende på interna paket som inte är en del av något offentligt API eller SPI.
* Kontakta oss [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
