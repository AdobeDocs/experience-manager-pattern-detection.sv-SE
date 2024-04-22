---
title: MI
description: Hjälpsida för Mönsteravkännarkod.
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# MI {#mi}

Felkonfigurationsproblem

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="Felkonfigurationsproblem"
>abstract="MI identifierar konfigurationsproblem AEM instansen"

Felkonfigurationsproblem i felkommunikation identifierar konfigurationsproblem i AEM.

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
   * Adobe rekommenderar att du anger värdet till 0,5 för att utnyttja hälften av de tillgängliga processorerna.
* `missing.maintenance.configuration`
   * Rensa revision: Se [Rensa version](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup). Den viktiga delen som rör konfigurationen är här: [Revision Cleanup - Configure Tail and Full compaction](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup).
   * Lucene Binaries Cleanup: Se [Operations Dashboard - Lucene Binaries Cleanup](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-dashboard#lucene-binaries-cleanup).
   * Skräpinsamling för datalager: Se [Skräpinsamling för datalager](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/data-store-garbage-collection).
   * Rensa arbetsflöde: Se [Vanlig tömning av arbetsflödesinstanser](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/workflows-administering#regular-purging-of-workflow-instances).
   * Underhållsaktivitet för granskningslogg: Se [Underhåll av granskningslogg](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-audit-log).
* Kontakta [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för klargöranden eller för att bemöta farhågor.
