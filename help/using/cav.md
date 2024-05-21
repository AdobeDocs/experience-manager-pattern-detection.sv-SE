---
title: CAV
description: Hjälpsida för Mönsteravkännarkod.
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---

# CAV {#cav}

Felaktigt innehållsområde

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="Felaktigt innehållsområde"
>abstract="CAV-koden identifierar mönstret där olika innehållsområden används på ett sätt som bryter mot reglerna i innehållsklassificeringen. Överträdelsen ger dig en översikt över övertäckningar, begränsat innehåll som kan behöva ändras efter att det har flyttats till AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Samla resurser"

`CAV` Identifierar mönstret där olika innehållsområden används på ett sätt som bryter mot reglerna i innehållsklassificeringen.

Bearbetning av Sling-begäran definierar hur innehållet i en resurs, dess `sling:resourceType` egenskapen används särskilt för att avgöra vilket skript som används för att återge innehållet. Se [Hitta skriptet](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script) för mer information. Sling innehåller även tekniker för att komma åt och sammanfoga resurser via övertäckningar och åsidosättningar. Dessa tekniker beskrivs som en del av [Samla resurser](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger) och in [Övertäckningar](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/overlays).

För att göra det säkrare och enklare för kunderna att förstå vilka delar av `/libs` är säkra att använda och täcka över, `/libs` klassificeras med &quot;mixin&quot;-egenskaper:

* Offentlig
* Abstrakt
* Slutlig
* Intern

Varje klassificering innehåller regler om hur innehållet kan användas, ärvas eller överlagras. Se [Hållbara uppgraderingar](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades) om du vill ha en detaljerad beskrivning.

## Möjliga konsekvenser och risker {#implications-and-risks}

* En AEM uppgradering kan leda till sidåtergivningsproblem och andra oönskade beteenden.
* Säkerhetsuppdateringar gäller inte.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="Genomförande"
>abstract="Mönster som identifieras med CAS där olika innehållsområdets överträdelser förekommer bör granskas. Klassificeringsområden för slutligt och internt innehåll bör undvikas. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="Hållbara uppgraderingar"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Minimera användningen av innehållsövertäckning till de fall där den behövs.
* Undvik framför allt överläggning av begränsat innehåll (slutlig och intern klassificering).
* Överväg att anpassa ändringar från `/libs` efter AEM uppgraderingar, Service Pack eller Cumulative Fix Pack.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
