---
title: REP
description: Hjälpsida för mönsteravkännarkod
exl-id: e788deba-a301-404f-8e90-51f721409e69
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 1%

---

# [!DNL REP] {#rep}

Replikeringsagent

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="Replikeringsagent"
>abstract="REP identifierar aktiverade replikeringsagenter. Dessa rapporteras på grund av risken för problem som bör åtgärdas vid uppgradering till AEM som Cloud Service. AEM som Cloud Service använder Sling Content Distribution för att distribuera innehåll från författare till publiceringsmiljöer. Detta görs utanför AEM med hjälp av pipelinetjänsten i Adobe I/O. Detta konfigureras automatiskt som en Cloud Service i den tilldelade AEM."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents" text="Betydande ändringar - AEM som en Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents" text="Utvecklingsriktlinjer"

`REP` identifierar aktiverade replikeringsagenter. Dessa rapporteras på grund av risken för problem som bör åtgärdas vid uppgradering till AEM som Cloud Service.

AEM som Cloud Service använder [Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html) för att distribuera innehåll från författare till publiceringsmiljöer. Detta görs utanför AEM med hjälp av pipelinetjänsten i Adobe I/O. Detta konfigureras automatiskt som en Cloud Service i den tilldelade AEM.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Replikeringskonfigurationen har ändrats med AEM som Cloud Service. Alla aktuella replikeringsagenter bör granskas för att se vilka som ersätts av standardfunktioner, vilka konfigurationer som måste flyttas till kod och vilka som inte stöds.
* All användning av replikeringsagenter i anpassad kod eller arbetsflöden bör granskas vid uppgradering till AEM som Cloud Service.
* Omvänd replikering stöds inte från början i AEM som en Cloud Service.
* Du behöver inte konfigurera en separat utgivarrensningsagent. Detta konfigureras automatiskt som en Cloud Service i AEM.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="Implementeringsvägledning"
>abstract="Bästa praxis är att granska, omforma och optimera anpassade funktioner direkt beroende på replikeringsagenter och göra dem kompatibla med AEM som en Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication" text="Replikering - AEM som Cloud Service"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Se AEM som en Cloud Service [Utvecklingsriktlinjer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents) och versionsinformation för [replikeringsagenter](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents).
* Granska, omforma och optimera funktioner som är direkt beroende av replikeringsagenter för att utföra affärsuppgifter.
* Se hur [replikering](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication) påverkas av distribution i AEM som en Cloud Service.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
