---
title: ASO
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# ASO {#aso}

AEM - systemöversikt

## Bakgrund {#background}

`ASO` används för att identifiera allmän information om AEM. Varje sökning ger ett värde av en viss typ av systeminformation.

Undertyper används för att identifiera olika typer av information:

* `aem.version`: Den AEM versionen.
* `aem.product`: Upptäckt av användning av en AEM (handel, Forms osv.).
* `node.count`: Det ungefärliga antalet noder av en viss typ (Sida, Resurs osv.).
* `node.store`: Nodlagringens implementeringstyp (SegmentNodeStore, DocumentNodeStore).
* `data.store`: Implementeringstypen för datalagret (FileDataStore, S3DataStore, AzureDataStore).
* `maintenance.task`: En underhållsuppgift.
* `slow.query`: En långsam fråga.

## Möjliga konsekvenser och risker {#implications-and-risks}

* AEM, nodantal samt implementeringstyper för nodarkiv och datalager tillhandahålls i informationssyfte.
* Det anpassade programmet kan förlita sig på produkter eller funktioner som inte finns i AEM som Cloud Service.
* Uppgradering med funktioner som inte stöds kan leda till en misslyckad uppgradering och ett icke-funktionellt program.

## Möjliga lösningar {#solutions}

* AEM uppgraderingar med produkter eller funktioner som inte stöds rekommenderas inte och kanske inte stöds.
* Läs [versionsinformationen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html) om du vill veta mer om de senaste ändringarna i AEM som en Cloud Service.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
