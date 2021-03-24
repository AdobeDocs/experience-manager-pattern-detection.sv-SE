---
title: ARRK
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---


# WRK {#wrk}

Arbetsflöde

## Bakgrund {#background}

`WRK` identifierar en sökning som är relaterad till en arbetsflödesmodell eller startprogram. Dessa rapporteras eftersom anpassade arbetsflödesmodeller för resurser måste migreras när de uppgraderas till AEM som en Cloud Service.

En undertyp används för att identifiera den typ av arbetsflödesproblem som för närvarande upptäcks.

* `custom.asset.workflow`: Identifiering av en anpassad arbetsflödesmodell eller startfunktion för resurser.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Resursbearbetning har traditionellt utförts med arbetsflöden för resurser som körs på AEM Author-instansen. Med AEM som Cloud Service utförs nu tillgångsbearbetning av tillgångsmikrotjänster. (Mer information finns i översikten [över mikrotjänster för resurser](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html).
* Standardarbetsflöden för resurser stöds automatiskt av mina tillgångsmikrotjänster.
* Anpassningar av arbetsflöden för resurser kräver migrering för att fungera med AEM som Cloud Service.

## Möjliga lösningar {#solutions}

* Om en anpassad arbetsflödesmodell eller startfunktion för en resurs identifieras ska du köra [verktyget för migrering av arbetsflöde för resurs](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html).
* Mer information finns i [Komma igång med att använda resursmikrotjänster](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html).
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
