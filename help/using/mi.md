---
title: MI
description: Hjälpsida för mönsteravkännarkod
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: efb06dc7e00f91d4c080553df3153deb90b093f2
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# MI {#mi}

Felkonfigurationsproblem

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="Felkonfigurationsproblem"
>abstract="MI identifierar konfigurationsproblem AEM instansen"

`MI`  Felkonfigurationsproblem identifierar konfigurationsproblem på AEM.

Undertyper används för att identifiera olika typer av information, som:

* `sling.job.max.parallel`: Identifiera snedstreck där den maximala parallella konfigurationen är -1.
* `missing.maintenance.configuration`: Identifiera saknade konfigurationer av underhållsaktiviteter.

## Möjliga konsekvenser och risker {#implications-and-risks}

* `sling.job.max.parallel`
   * Värdet -1 ersätts med antalet tillgängliga processorer. Detta kan orsaka prestandaproblem AEM instansen.
* `missing.maintenance.configuration`
   * Konfigurationer för underhållsaktiviteter som saknas kan orsaka prestandaförluster eller instansfel.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="Genomförande"
>abstract="Kontakta kundtjänst om du behöver hjälp."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* `sling.job.max.parallel`
   * Värdet bör anges till 0,5 för att hälften av de tillgängliga processorerna ska kunna användas.
* `missing.maintenance.configuration`
   * Revision Clean Up: Please refer [Rensa version](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html). Den viktiga delen som rör konfigurationen är här: [Revision Cleanup - Configure Tail and Full compaction](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html#how-to-configure-full-and-tail-compaction).
   * Lucene Binaries Cleanup: Se [Operations Dashboard - Lucene Binaries Cleanup](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-dashboard.html#lucene-binaries-cleanup).
   * Skräpinsamling för datalager: se [Skräpinsamling för datalager](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/data-store-garbage-collection.html).
   * Töm arbetsflöde: se [Vanlig tömning av arbetsflödesinstanser](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/workflows-administering.html#regular-purging-of-workflow-instances).
   * Underhållsaktivitet för granskningslogg: se [Underhåll av granskningslogg](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-audit-log.html).
* Nå ut till [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
