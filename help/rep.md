---
title: REP
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 7d05067fc624571e6fe520e2a1addd5dff8acbd8
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 1%

---


# [!DNL REP] {#rep}

Replikeringsagent

## Bakgrund {#background}

`REP` identifierar aktiverade replikeringsagenter. Dessa rapporteras på grund av risken för problem som bör åtgärdas vid uppgradering till AEM som Cloud Service.

AEM som Cloud Service använder [Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html) för att distribuera innehåll från författare till publiceringsmiljöer. Detta görs utanför AEM med hjälp av pipelinetjänsten i Adobe I/O. Detta konfigureras automatiskt som en Cloud Service i den tilldelade AEM.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Replikeringskonfigurationen har ändrats med AEM som Cloud Service. Alla aktuella replikeringsagenter bör granskas för att se vilka som ersätts av standardfunktioner, vilka konfigurationer som måste flyttas till kod och vilka som inte stöds.
* All användning av replikeringsagenter i anpassad kod eller arbetsflöden bör granskas vid uppgradering till AEM som Cloud Service.
* Omvänd replikering stöds inte från början i AEM som en Cloud Service.
* Du behöver inte konfigurera en separat utgivarrensningsagent. Detta konfigureras automatiskt som en Cloud Service i AEM.

## Möjliga lösningar {#solutions}

* Se AEM som en Cloud Service [Utvecklingsriktlinjer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents) och versionsinformation för [replikeringsagenter](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents).
* Granska, omforma och optimera funktioner som är direkt beroende av replikeringsagenter för att utföra affärsuppgifter.
* Se hur [replikering](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication) påverkas av distribution i AEM som en Cloud Service.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
