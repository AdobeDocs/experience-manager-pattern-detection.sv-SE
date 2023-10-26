---
title: CAV
description: Hjälpsida för mönsteravkännarkod
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# CAV {#cav}

Felaktigt innehållsområde

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="Felaktigt innehållsområde"
>abstract="CAV-koden identifierar mönstret där olika innehållsområden används på ett sätt som bryter mot reglerna i innehållsklassificeringen. Den här överträdelsen ger dig en översikt över övertäckningar, begränsat innehåll som kan behöva ändras när vi går över till AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Samla resurser"

`CAV` identifierar mönstret där olika innehållsområden används på ett sätt som bryter mot reglerna i innehållsklassificeringen.

Bearbetning av Sling-begäran definierar hur innehållet i en resurs, dess `sling:resourceType` egenskapen används särskilt för att avgöra vilket skript som ska användas för att återge innehållet. Se [Hitta skriptet](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script) för mer information. Sling tillhandahåller också tekniker för åtkomst och sammanslagning av resurser via&quot;Övertäckningar&quot; och&quot;Åsidosättningar&quot;. Dessa beskrivs som en del av [Samla resurser](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html) och in [Övertäckningar](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html).

För att göra det säkrare och enklare för kunderna att förstå vilka områden i `/libs` är säkra att använda och täcka över innehållet i `/libs` har klassificerats med &quot;mixin&quot;-egenskaper: Public, Abstract, Final och Internal. Varje klassificering innehåller regler om hur innehållet kan användas, ärvas eller överlagras. Se [Hållbara uppgraderingar](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html) om du vill ha en detaljerad beskrivning.

## Möjliga konsekvenser och risker {#implications-and-risks}

* En AEM uppgradering kan leda till sidåtergivningsproblem och andra oönskade beteenden.
* Säkerhetsuppdateringar gäller inte.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="Genomförande"
>abstract="Mönster som har identifierats med CAS där det finns olika brott mot innehållsområdet bör granskas. Klassificeringsområden för slutligt och internt innehåll bör undvikas. Kontakta Adobe Support för hjälp och förtydliganden."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="Hållbara uppgraderingar"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Minimera användningen av innehållsövertäckning till de fall där den behövs.
* Undvik framför allt överläggning av begränsat innehåll (slutlig och intern klassificering).
* Överväg att anpassa ändringar från `/libs` efter AEM uppgraderingar, ServicePack eller CumulativeFixPack.
* Kontakta oss [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
