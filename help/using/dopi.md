---
title: DOPI
description: Hjälpsida för mönsteravkännarkod
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# DOPI {#dopi}

Inaktuellt sorterat egenskapsindex

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="Inaktuellt sorterat egenskapsindex"
>abstract="DOPI-kod identifierar användningen av ordnade egenskapsindexdefinitioner (primärType=oak:QueryIndexDefinition AND type=&quot;ordered&quot;), som har tagits bort sedan 6.1 och tagits bort i 6.2."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=en#the-ordered-index" text="Beställt index - inaktuellt"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html" text="Indexering - AEM as a Cloud Service"

`DOPI` identifierar användningen av ordnade egenskapsindexdefinitioner (`primaryType=oak:QueryIndexDefinition` OCH `type="ordered"`), som har tagits bort sedan 6.1 och tagits bort i 6.2.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="Genomförande"
>abstract="Bästa praxis är att granska alla inaktuella sorterade index och flytta dem till en typ av lucenindex som stöds för att undvika betydande prestandaproblem eller icke-funktionella kundkrav."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/practices/best-practices-for-queries-and-indexing.html" text="God praxis - frågor och indexering"

* Vissa frågor kanske inte svarar.
* Kundens funktionalitet kanske inte fungerar som den ska.
* Genomför varningar eller till och med fel och betydande prestandapåföljder eftersom de inaktuella indexen inte har någon effekt.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="Verktyg och resurser"
>abstract="Granska WKND-äldre projekt för att förstå hur DOPI-överträdelser kan göras kompatibla med AEM Cloud Service. Granska också Exempel på DOPI-överträdelse på Github för att förstå hur äldre sorterade index kan konverteras till Lucene-baserade index som stöds i AEM as a Cloud Service."
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="Exempel på DOPI-överträdelse - Github"

* Ändra indexdefinitionen så att den blir, eller ersätter indexet med, en indexdefinition som stöds. (Se [Fråga och indexering](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html)).
* Granska [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi) projekt och förstå hur [DOPI-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi) kan korrigeras och göras kompatibelt med AEM as a Cloud Service.
* Kontakta oss [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
