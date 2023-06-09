---
title: ecu
description: Hjälpsida för mönsteravkännarkod
exl-id: fd061001-b00e-44ae-bd31-71bd2fa733cd
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# ecu {#ecu}

INAKTUELL: Ovidkommande innehållsanvändning (ersätts med CAV, felaktiga innehållsområden)

## Bakgrund {#background}

`ECU` identifierar mönstret där olika innehållsområden används på ett sätt som bryter mot reglerna i innehållsklassificeringen.

Bearbetning av Sling-begäran definierar hur innehållet i en resurs, dess `sling:resourceType` egenskapen används särskilt för att avgöra vilket skript som ska användas för att återge innehållet. (Se [Hitta skriptet](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script) för mer information.) Sling tillhandahåller också tekniker för åtkomst och sammanslagning av resurser via&quot;Övertäckningar&quot; och&quot;Åsidosättningar&quot;. Dessa beskrivs som en del av [Samla resurser](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html) och in [Övertäckningar](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html).

För att göra det säkrare och enklare för kunderna att förstå vilka områden i `/libs` är säkra att använda och täcka över innehållet i `/libs` har klassificerats med &quot;mixin&quot;-egenskaper: Offentlig, Abstract, Final och Internal. Varje klassificering innehåller regler om hur innehållet kan användas, ärvas eller överlagras. Se [Hållbara uppgraderingar](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html) om du vill ha en detaljerad beskrivning.

## Möjliga konsekvenser och risker {#implications-and-risks}

* En AEM uppgradering kan leda till sidåtergivningsproblem och andra oönskade beteenden.
* Säkerhetsuppdateringar gäller inte.

## Möjliga lösningar {#solutions}

* Minimera användningen av innehållsövertäckning till de fall där den behövs.
* Undvik framför allt överläggning av begränsat innehåll (slutlig och intern klassificering).
* Överväg att anpassa ändringar från `/libs` efter AEM uppgraderingar, installationer av ServicePack eller CumulativeFixPack.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
