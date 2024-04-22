---
title: ARRK
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# ARRK {#wrk}

Arbetsflöde

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="Arbetsflöde"
>abstract="WRK-kod identifierar en sökning som är relaterad till en arbetsflödesmodell eller startprogram. Dessa rapporteras eftersom anpassade arbetsflödesmodeller för resurser måste migreras när de uppgraderas till AEM as a Cloud Service. Med AEM as a Cloud Service utförs nu bearbetning av mediefiler av mikrotjänster."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="Asset Microservices"

`WRK` identifierar en sökning som är relaterad till en arbetsflödesmodell eller startprogram. Dessa rapporteras eftersom anpassade arbetsflödesmodeller för resurser måste migreras när de uppgraderas till AEM as a Cloud Service.

En undertyp används för att identifiera den typ av arbetsflödesproblem som för närvarande upptäcks.

* `custom.asset.workflow`: Identifiering av en anpassad arbetsflödesmodell eller startfunktion för resurs.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="Genomförande"
>abstract="Eftersom standardarbetsflöden för resurser automatiskt stöds av mina tillgångsmikrotjänster är bästa praxis att granska alla anpassade arbetsflödesmodeller eller startfunktioner för att se om de behövs när vi väl har övergått till AEM as a Cloud Service. Anpassningar av arbetsflöden för resurser kräver migrering för att kunna arbeta med AEM as a Cloud Service med hjälp av verktyget för migrering av arbetsflöden för resurser"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="Komma igång - Asset Microservices"

* Resursbearbetning har traditionellt utförts med resursarbetsflöden som körs på AEM författarinstans. Med AEM as a Cloud Service utförs nu bearbetning av mediefiler av mikrotjänster. Se [asset microservices overview](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html) för mer information.
* Standardarbetsflöden för resurser stöds automatiskt av mina tillgångsmikrotjänster.
* Anpassningar av arbetsflöden för resurser kräver migrering för att fungera med AEM as a Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="Verktyg och resurser"
>abstract="Granska och planera för att köra verktyget för resursarbetsflödesmigrering när en anpassad arbetsflödesmodell eller startfunktion för resurser har identifierats. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="Verktyg för resursarbetsflödesmigrering"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Om en anpassad arbetsflödesmodell eller startfunktion för en resurs identifieras, ska du köra [Migreringsverktyg för arbetsflöde för resurs](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html).
* Granska [Komma igång med att använda objektmikrotjänster](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html) för mer information.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
