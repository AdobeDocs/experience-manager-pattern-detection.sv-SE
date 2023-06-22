---
title: ASO
description: Hjälpsida för mönsteravkännarkod
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: a899311c975efee180bc1d3bc3c7bca30d429a22
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# ASO {#aso}

AEM - systemöversikt

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM - systemöversikt"
>abstract="ASO-koden identifierar allmän information om AEM. Varje sökning ger ett värde av en viss typ av systeminformation som kan vara till hjälp vid migreringsplanering och omfaktorisering."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - versionsinformation"

`ASO` används för att identifiera allmän information om AEM. Varje sökning ger ett värde av en viss typ av systeminformation.

Undertyper används för att identifiera olika typer av information:

* `aem.version`: Den AEM versionen.
* `aem.product`: Upptäckt av användning av en AEM (handel, Forms osv.).
* `node.count`: Det ungefärliga antalet noder av en viss typ (Sida, Resurs osv.) och det totala antalet noder.
* `node.store`: Nodlagringens implementeringstyp (SegmentNodeStore, DocumentNodeStore) och dess storlek.
* `data.store`: Implementeringstypen för datalagret (FileDataStore, S3DataStore, AzureDataStore).
* `maintenance.task`: En underhållsuppgift.
* `slow.query`: En långsam fråga.
* `group.membership`: Antalet användare och undergrupper (endast direkta/deklarerade medlemmar) i en grupp.
* `cqtag.count`: Antalet CQ-taggade resurser.
* `smarttag.count`: Antalet resurser med smarta taggar.
* `ccom.version`: Versionen av Core Component-paketet.
* `instance.type`: AEM instanstyp (författare|publicera).
* `unprocessed.asset.count`: Antalet obearbetade resurser.
* `vanity.url.count`: Antal mål-URL:er.
* `index.size`: Total storlek på index för Lucene som kan migreras.
* `workflow.count`: Antal författararbetsflöden i körnings- och inkörningstillstånd.
* `jvm.arguments`: JVM-argumenten som läggs till på kommandoraden när AEM startas.

## Möjliga konsekvenser och risker {#implications-and-risks}

* AEM, antal noder, gruppmedlemskap, nodbutik, implementeringstyper för datalager, CQ-taggantal, antal smarta taggar, kärnkomponentversion, AEM instanstyp och antal obearbetade resurser tillhandahålls i informationssyfte.
* Det högre antalet tillfälliga URL:er (>1000) kan göra att Dispatcher och Publish-servrarna laddas med dyra frågor.
* Det anpassade programmet kan förlita sig på produkter eller funktioner som inte finns i AEM as a Cloud Service.
* Uppgradering med funktioner som inte stöds kan leda till en misslyckad uppgradering och ett icke-funktionellt program.
* Ett stort antal arbetsflöden för författare i kört eller inaktuellt tillstånd kan försämra prestanda.
* Långsamma frågor kan försämra systemets prestanda.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="Implementeringsvägledning"
>abstract="Information som visas via ASO-koden ger allmän information för din AEM, inklusive version, produkttillägg, information på systemnivå och denna bör granskas för alla produkter eller funktioner som inte stöds i AEM as a Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* AEM uppgraderingar med produkter eller funktioner som inte stöds rekommenderas inte och kanske inte stöds.
* De obearbetade resurserna måste bearbetas och egenskapen dam:assetState på noden jcr:content i resursen måste ställas in på&quot;bearbetad&quot; eller ta bort dessa resurser från migreringsuppsättningen innan de migreras till AEMaaCS.
* Vanity-URL:er kan ersättas med Apache Rewrites.
* Se [dokumentation](https://experienceleague.adobe.com/docs/experience-manager-65/developing/bestpractices/troubleshooting-slow-queries.html) för felsökning av långsamma frågor.
* Granska [versionsinformation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html) om du vill veta mer om de senaste förändringarna AEM as a Cloud Service.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
