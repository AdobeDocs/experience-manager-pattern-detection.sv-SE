---
title: MI
description: Hjälpsida för Mönsteravkännarkod.
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# MI {#mi}

Felkonfigurationsproblem

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="Felkonfigurationsproblem"
>abstract="MI identifierar konfigurationsproblem AEM instansen"

`MI` (Misconfiguration Issue) Identifierar konfigurationsproblem i AEM.

Undertyper används för att identifiera olika typer av information, som:

* `sling.job.max.parallel`: Identifiera snedställningsjobben där den maximala parallella konfigurationen är inställd på -1.
* `missing.maintenance.configuration`: Identifiera saknade underhållsuppgiftskonfigurationer.

## Möjliga konsekvenser och risker {#implications-and-risks}

* `sling.job.max.parallel`
   * Värdet -1 ersätts med antalet tillgängliga processorer. Det kan därför orsaka prestandaproblem i en AEM.
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
   * Rensa version: Se [Rensa version](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup). Den viktiga delen av konfigurationen är här: [Revision Cleanup - Configure Tail och Full compaction](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup).
   * Lucene-binärrensning: Se [Operations Dashboard - Lucene Binaries Cleanup](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-dashboard#lucene-binaries-cleanup).
   * Skräpinsamling för datalager: Se [Skräpinsamling för datalager](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/data-store-garbage-collection).
   * Rensa arbetsflöde: Se [Regelbunden tömning av arbetsflödesinstanser](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/workflows-administering#regular-purging-of-workflow-instances).
   * Underhållsaktivitet för granskningslogg: Se [Underhåll av granskningslogg](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-audit-log).
* Kontakta [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
