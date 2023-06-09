---
title: CTEM
description: Hjälpsida för mönsteravkännarkod
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 3%

---

# CTEM {#ctem}

Egen mall

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_overview"
>title="Egen mall"
>abstract="CTEM identifierar anpassade komponenter som har installerats på AEM. Denna information tillhandahålls i syfte att bedöma bästa praxis"

`CTEM` identifierar anpassade mallar som har installerats på AEM. Denna information tillhandahålls för bedömning av bästa metoder.

Mallar identifieras av ett primärt typvärde för &quot;cq:Template&quot;. En undertyp används med den här koden för att identifiera mallkategorin:

* `custom.editable.template`: Mallens sökväg börjar inte med &quot;/apps&quot;.
* `custom.static.template`: Mallens sökväg börjar med &quot;/apps&quot;.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="Implementeringsvägledning"
>abstract="Det bästa sättet är att flytta alla statiska mallar till redigerbara mallar. Kunderna kan använda befintliga AEM för att migrera statiska mallar till redigerbara mallar."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html" text="Redigerbara mallar"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM Modernization Tools"

* Det bästa sättet är att flytta alla statiska mallar till redigerbara mallar.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="Verktyg och resurser"
>abstract="Med hjälp av AEM Modernization Suite kan kunderna ändra strukturen på en sida från en statisk definition till en redigerbar mall. Avsikten är att hjälpa kunderna att gå över från de begränsade funktionerna i de gamla funktionerna till de robusta, moderna AEM. Dessa verktyg är konfigurerbara, konfigureringsmedvetna och utökningsbara. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/structure/about.html" text="Sidstrukturkonverterare"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Utnyttja [AEM](https://opensource.adobe.com/aem-modernize-tools/) för att migrera statiska mallar till redigerbara mallar.
* Mer information om redigerbara mallar finns på [Mallar](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
