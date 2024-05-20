---
title: ARRK
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# ARRK {#wrk}

Arbetsflöde

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="Arbetsflöde"
>abstract="WRK-kod identifierar en sökning som är relaterad till en arbetsflödesmodell eller startprogram. Dessa identifieringar rapporteras eftersom anpassade arbetsflödesmodeller för resurser måste migreras när de uppgraderas till AEM as a Cloud Service. Med AEM as a Cloud Service utför tillgångsmikrotjänsterna materialbearbetningen."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview" text="Asset Microservices"

`WRK`  Identifierar en sökning som är relaterad till en arbetsflödesmodell eller startprogram. Dessa identifieringar rapporteras eftersom anpassade arbetsflödesmodeller för resurser måste migreras när de uppgraderas till AEM as a Cloud Service.

En undertyp används för att identifiera den typ av arbetsflödesproblem som för närvarande upptäcks.

* `custom.asset.workflow`: Identifiering av en anpassad arbetsflödesmodell eller startfunktion för resurs.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="Genomförande"
>abstract="Standardarbetsflöden för resurser stöds automatiskt av mina tillgångsmikrotjänster. Bästa praxis är därför att granska alla anpassade arbetsflödesmodeller för resurser eller Launcher. När du granskar kan du se om de behövs efter övergången till AEM as a Cloud Service. Anpassningar av arbetsflöden kräver migrering för att fungera med AEM as a Cloud Service med hjälp av verktyget för resursarbetsflödesmigrering"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use" text="Komma igång - Asset Microservices"

* Resursbearbetning har traditionellt utförts med resursarbetsflöden som körs på AEM författarinstans. Med AEM as a Cloud Service utför tillgångsmikrotjänsterna materialbearbetningen. Se [asset microservices overview](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview) för mer information.
* Standardarbetsflöden för resurser stöds automatiskt av mina tillgångsmikrotjänster.
* Anpassningar av arbetsflöden för resurser kräver migrering för att fungera med AEM as a Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="Verktyg och resurser"
>abstract="Granska och planera körningen av verktyget för resursarbetsflödesmigrering när en anpassad arbetsflödesmodell eller startfunktion för en resurs har identifierats. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool" text="Verktyg för resursarbetsflödesmigrering"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Om en anpassad arbetsflödesmodell eller startfunktion för en resurs identifieras, ska du köra [Migreringsverktyg för arbetsflöde för resurs](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool).
* Granska [Komma igång med att använda objektmikrotjänster](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use) för mer information.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
