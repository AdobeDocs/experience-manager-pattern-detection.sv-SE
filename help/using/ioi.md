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

Intern Oak-import

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="Intern Oak-import"
>abstract="IOI-koden identifierar kundernas användning av interna Oak-paket och importerar dem med OSGi. De exporteras utan någon särskild version. Oak programpaket eller tjänster på låg nivå AEM endast konsumera dem."

`IOI` Identifierar kundens användning av interna Oak-paket och importerar dem via OSGi. De exporteras utan någon särskild version. Oak programpaket eller tjänster på låg nivå AEM endast konsumera dem.
Vissa av dessa områden används av `com.adobe.granite.repository`, som konfigurerar en databas för AEM under start. Ett annat exempel är Adobe-paketet `com.adobe.granite.maintenance.oak` som omsluter och tillhandahåller underhållsåtgärder för Oak.

## Möjliga konsekvenser och risker {#implications-and-risks}

* I en senare AEM kan intern export tas bort, vilket kan orsaka brutna beroenden och inaktiva paket beroende direkt på Oak.
* API:n för intern export kan komma att ändras.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="Genomförande"
>abstract="Kunderna bör granska sin egen kod för att identifiera användningen av sådana API:er och göra dem kompatibla med AEM as a Cloud Service. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Använd Sling Resource API (eller JCR API) i stället för åtkomst på låg nivå.
* Undvik beroende på interna paket som inte är en del av något offentligt API eller SPI.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
