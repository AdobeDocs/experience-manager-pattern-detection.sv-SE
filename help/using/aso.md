---
title: ASO
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# ASO {#aso}

AEM - systemöversikt

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM - systemöversikt"
>abstract="ASO-koden identifierar allmän information om AEM. Varje sökning ger ett värde av en viss typ av systeminformation som kan vara till hjälp vid migreringsplanering och omfaktorisering."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - Versionsinformation"

`ASO` Identifierar allmän information om AEM. Varje sökning ger ett värde av en viss typ av systeminformation.

Undertyper används för att identifiera olika typer av information:

* `aem.version`: AEM.
* `aem.product`: Identifiering av användning av en AEM (Commerce, Forms osv.).
* `node.count`: Det ungefärliga antalet noder av en viss typ (Sida, Resurs och så vidare) och det totala antalet noder.
* `node.store`: Nodlagringens implementeringstyp (SegmentNodeStore, DocumentNodeStore) och dess storlek.
* `data.store`: Implementeringstypen för datalagret (FileDataStore, S3DataStore, AzureDataStore).
* `maintenance.task`: En underhållsaktivitet.
* `slow.query`: En långsam fråga.
* `group.membership`: Antalet användare och undergrupper (endast direkta/deklarerade medlemmar) i en grupp.
* `cqtag.count`: Antalet CQ-taggade resurser.
* `smarttag.count`: Antalet resurser med smarta taggar.
* `ccom.version`: Versionen av Core Component-paketet.
* `instance.type`: AEM instanstyp (författare|publicera).
* `unprocessed.asset.count`: Antalet obearbetade resurser.
* `vanity.url.count`: Antalet mål-URL:er.
* `index.size`: Total storlek på index för Lucene som kan migreras.
* `workflow.count`: Antalet arbetsflöden för författare som körs och är inaktuella.
* `jvm.arguments`: JVM-argumenten lades till på kommandoraden när AEM startades.

## Möjliga konsekvenser och risker {#implications-and-risks}

* AEM, antal noder, gruppmedlemskap, nodbutik, implementeringstyper för datalager, CQ-taggantal, antal smarta taggar, kärnkomponentversion, AEM instanstyp och antal obearbetade resurser tillhandahålls i informationssyfte.
* Det högre antalet tillfälliga URL:er (>1000) kan belasta Dispatcher- och Publish-servrarna med dyra frågor.
* Det anpassade programmet kan förlita sig på produkter eller funktioner som inte finns i AEM as a Cloud Service.
* Uppgradering med funktioner som inte stöds kan leda till en misslyckad uppgradering och ett icke-funktionellt program.
* Ett stort antal arbetsflöden för författare i ett öppet eller inaktuellt tillstånd kan försämra prestanda.
* Långsamma frågor kan försämra systemets prestanda.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="Genomförande"
>abstract="Information som exponeras via ASO-kod ger allmän information för din AEM, inklusive version, produkttillägg och information på systemnivå. Se om det finns några produkter eller funktioner som inte stöds i AEM as a Cloud Service. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* AEM uppgraderingar med produkter eller funktioner som inte stöds rekommenderas inte och kanske inte stöds.
* De obearbetade resurserna måste bearbetas och egenskapen `dam:assetState` på noden `jcr:content` i resursen måste anges till&quot;bearbetad&quot;. Du kan också ta bort dessa resurser från migreringsuppsättningen innan du migrerar till AEMaaCS.
* Vanity-URL:er kan ersättas med Apache Rewrites.
* Se [dokumentation](https://experienceleague.adobe.com/sv/docs/experience-manager-65/content/implementing/developing/bestpractices/troubleshooting-slow-queries) för felsökning av långsamma frågor.
* Se [versionsinformationen](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current) om du vill veta mer om de senaste ändringarna i AEM as a Cloud Service.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
