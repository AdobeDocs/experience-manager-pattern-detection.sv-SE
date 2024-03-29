---
title: REP
description: Hjälpsida för mönsteravkännarkod
exl-id: e788deba-a301-404f-8e90-51f721409e69
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# [!DNL REP] {#rep}

Replikeringsagent

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="Replikeringsagent"
>abstract="REP identifierar aktiverade replikeringsagenter. Dessa rapporteras på grund av risken för problem som bör åtgärdas vid uppgradering till AEM as a Cloud Service. AEM as a Cloud Service använder Sling Content Distribution för att distribuera innehåll från författare till publiceringsmiljöer. Detta görs utanför AEM med hjälp av pipelinetjänsten i Adobe I/O. Detta konfigureras automatiskt i den AEM as a Cloud Service miljön."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents" text="Betydande ändringar - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents" text="Utvecklingsriktlinjer"

`REP` identifierar aktiverade replikeringsagenter. Dessa rapporteras på grund av risken för problem som bör åtgärdas vid uppgradering till AEM as a Cloud Service.

Undertyper används för att identifiera olika typer av information:

* `forward.replication`: Identifiera aktiverade agenter för framåtriktad replikering.
* `reverse.replication`: Identifiera aktiverade agenter för omvänd replikering.
* `standard.replication.agent.modification`: Identifiera de aktiverade standardreplikeringsagenter som har ändrats.
* `custom.replication.agent.detection`: Identifiera aktiverade anpassade replikeringsagenter.

AEM as a Cloud Service användningsområden [Distribution av säljinnehåll](https://sling.apache.org/documentation/bundles/content-distribution.html) för att distribuera innehåll från författare till publiceringsmiljöer. Detta görs utanför AEM med hjälp av pipelinetjänsten i Adobe I/O. Detta konfigureras automatiskt i den AEM as a Cloud Service miljön.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Replikeringskonfigurationen har ändrats med AEM as a Cloud Service. Alla aktuella replikeringsagenter bör granskas för att se vilka som ersätts av standardfunktioner, vilka konfigurationer som måste flyttas till kod och vilka som inte stöds.
* All användning av replikeringsagenter i anpassad kod eller arbetsflöden bör granskas vid uppgradering till AEM as a Cloud Service.
* Omvänd replikering stöds inte från början i AEM as a Cloud Service.
* Du behöver inte konfigurera en separat utgivarrensningsagent. Detta konfigureras automatiskt i den AEM as a Cloud Service miljön.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="Genomförande"
>abstract="Bästa praxis är att granska, omforma och optimera anpassade funktioner direkt beroende på replikeringsagenter och göra dem kompatibla med AEM as a Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication" text="Replikering - AEM as a Cloud Service"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Se AEM as a Cloud Service [Utvecklingsriktlinjer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents) och versionsinformation för [replikeringsagenter](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents).
* Granska, omforma och optimera funktioner som är direkt beroende av replikeringsagenter för att utföra affärsuppgifter.
* Se hur [replikering](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication) påverkas av distributionen på AEM as a Cloud Service.
* Kontakta oss [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
