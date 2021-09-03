---
title: ASO
description: Hjälpsida för mönsteravkännarkod
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: dc9d6c94d5a724cf24890378ba6a8af7396760c6
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# ASO {#aso}

AEM - systemöversikt

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM - systemöversikt"
>abstract="ASO-koden identifierar allmän information om AEM. Varje sökning ger ett värde av en viss typ av systeminformation som kan vara till hjälp vid migreringsplanering och omfaktorisering."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM som Cloud Service - Versionsinformation"

`ASO` används för att identifiera allmän information om AEM. Varje sökning ger ett värde av en viss typ av systeminformation.

Undertyper används för att identifiera olika typer av information:

* `aem.version`: Den AEM versionen.
* `aem.product`: Upptäckt av användning av en AEM (handel, Forms osv.).
* `node.count`: Det ungefärliga antalet noder av en viss typ (Sida, Resurs osv.) och det totala antalet noder.
* `node.store`: Nodlagringens implementeringstyp (SegmentNodeStore, DocumentNodeStore) och dess storlek.
* `data.store`: Implementeringstypen för datalagret (FileDataStore, S3DataStore, AzureDataStore).
* `maintenance.task`: En underhållsuppgift.
* `slow.query`: En långsam fråga.

## Möjliga konsekvenser och risker {#implications-and-risks}

* AEM, nodantal samt implementeringstyper för nodarkiv och datalager tillhandahålls i informationssyfte.
* Det anpassade programmet kan förlita sig på produkter eller funktioner som inte finns i AEM som Cloud Service.
* Uppgradering med funktioner som inte stöds kan leda till en misslyckad uppgradering och ett icke-funktionellt program.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="Implementeringsvägledning"
>abstract="Information som visas via ASO-koden ger allmän information för din AEM, inklusive version, produkttillägg, information på systemnivå och denna bör granskas för alla produkter eller funktioner som inte stöds i AEM som en Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* AEM uppgraderingar med produkter eller funktioner som inte stöds rekommenderas inte och kanske inte stöds.
* Läs [versionsinformationen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html) om du vill veta mer om de senaste ändringarna i AEM som en Cloud Service.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
