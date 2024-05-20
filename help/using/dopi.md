---
title: DOPI
description: Hjälpsida för Mönsteravkännarkod.
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# DOPI {#dopi}

Inaktuellt sorterat egenskapsindex

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="Inaktuellt sorterat egenskapsindex"
>abstract="DOPI-kod identifierar användningen av ordnade egenskapsindexdefinitioner (`primaryType=oak:QueryIndexDefinition` AND type=&quot;ordered&quot;), som har ersatts sedan 6.1 och tagits bort i 6.2."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#the-ordered-index" text="Beställt index - inaktuellt"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing" text="Indexering - AEM as a Cloud Service"

`DOPI`  Identifierar användningen av indexdefinitioner för ordnade egenskaper (`primaryType=oak:QueryIndexDefinition` OCH `type="ordered"`), som har tagits bort sedan AEM 6.1 och tagits bort i AEM 6.2.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="Genomförande"
>abstract="Bästa praxis är att granska alla inaktuella sorterade index och flytta dem till den form av Lucene-index som stöds för att undvika betydande prestandaproblem eller icke-funktionella kundkrav."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/practices/best-practices-for-queries-and-indexing" text="God praxis - frågor och indexering"

* Vissa frågor kanske inte svarar.
* Kundens funktionalitet kanske inte fungerar som den ska.
* Genomför varningar eller till och med fel och betydande prestandapåföljder eftersom de inaktuella indexen inte har någon effekt.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="Verktyg och resurser"
>abstract="Granska WKND-äldre projekt för att förstå hur DOPI-överträdelser kan göras kompatibla med AEM Cloud Service. Granska också Exempel på DOPI-överträdelse i GitHub för att förstå hur äldre sorterade index kan konverteras till Lucene-baserade index som stöds i AEM as a Cloud Service."
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI-överträdelse - GitHub"

* Redigera indexdefinitionen så att den blir - eller ersätter indexet med - en indexdefinition som stöds. (Se [Fråga och indexering](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing)).
* Granska [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi) projekt och förstå hur [DOPI-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi) kan korrigeras och göras kompatibelt med AEM as a Cloud Service.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
