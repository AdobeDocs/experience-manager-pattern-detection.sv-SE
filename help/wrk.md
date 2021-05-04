---
title: ARRK
description: Hjälpsida för mönsteravkännarkod
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# WRK {#wrk}

Arbetsflöde

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="Arbetsflöde"
>abstract="WRK-kod identifierar en sökning som är relaterad till en arbetsflödesmodell eller startprogram. Dessa rapporteras eftersom anpassade arbetsflödesmodeller för resurser måste migreras när de uppgraderas till AEM som en Cloud Service. Med AEM som Cloud Service utförs nu tillgångsbearbetning av tillgångsmikrotjänster."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="Asset Microservices"

`WRK` identifierar en sökning som är relaterad till en arbetsflödesmodell eller startprogram. Dessa rapporteras eftersom anpassade arbetsflödesmodeller för resurser måste migreras när de uppgraderas till AEM som en Cloud Service.

En undertyp används för att identifiera den typ av arbetsflödesproblem som för närvarande upptäcks.

* `custom.asset.workflow`: Identifiering av en anpassad arbetsflödesmodell eller startfunktion för resurser.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="Implementeringsvägledning"
>abstract="Eftersom standardarbetsflöden för resurser automatiskt stöds av mina tillgångsmikrotjänster är bästa praxis att granska alla anpassade arbetsflödesmodeller eller startfunktioner för att se om de behövs när vi väl har övergått till att AEM som en Cloud Service. Anpassningar av arbetsflöden för resurser kräver migrering för att kunna fungera med AEM som Cloud Service med hjälp av verktyget för migrering av arbetsflöden för tillgångar"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="Komma igång - Asset Microservices"

* Resursbearbetning har traditionellt utförts med arbetsflöden för resurser som körs på AEM Author-instansen. Med AEM som Cloud Service utförs nu tillgångsbearbetning av tillgångsmikrotjänster. (Mer information finns i översikten [över mikrotjänster för resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html).
* Standardarbetsflöden för resurser stöds automatiskt av mina tillgångsmikrotjänster.
* Anpassningar av arbetsflöden för resurser kräver migrering för att fungera med AEM som Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="Verktyg och resurser"
>abstract="Granska och planera för att köra verktyget för resursarbetsflödesmigrering när en anpassad arbetsflödesmodell eller startfunktion för resurser har identifierats. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="Verktyg för resursarbetsflödesmigrering"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Om en anpassad arbetsflödesmodell eller startfunktion för en resurs identifieras ska du köra [verktyget för migrering av arbetsflöde för resurs](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html).
* Mer information finns i [Komma igång med att använda resursmikrotjänster](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html).
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
