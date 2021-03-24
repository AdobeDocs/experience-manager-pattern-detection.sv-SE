---
title: ecu
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---


# ecu {#ecu}

INAKTUELL: Ovidkommande innehållsanvändning (ersätts med CAV, felaktiga innehållsområden)

## Bakgrund {#background}

`ECU` identifierar mönstret där olika innehållsområden används på ett sätt som bryter mot reglerna i innehållsklassificeringen.

Hanteringen av Sling-begäranden definierar hur innehållet i en resurs, i synnerhet egenskapen `sling:resourceType`, används för att avgöra vilket skript som ska användas för att återge innehållet. (Mer information finns i [Leta reda på skriptet](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script).) Sling tillhandahåller också tekniker för åtkomst och sammanslagning av resurser via&quot;Övertäckningar&quot; och&quot;Åsidosättningar&quot;. Dessa beskrivs som en del av [Sling Resource Merger](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html) och i [Overlays](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html).

För att göra det säkrare och enklare för kunderna att förstå vilka områden i `/libs` som är säkra att använda och täcka över innehållet i `/libs` har klassificerats med &quot;mixin&quot;-egenskaper: Offentlig, Abstract, Final och Internal. Varje klassificering innehåller regler om hur innehållet kan användas, ärvas eller överlagras. Se [Hållbara uppgraderingar](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html) för en detaljerad beskrivning.

## Möjliga konsekvenser och risker {#implications-and-risks}

* En AEM uppgradering kan leda till sidåtergivningsproblem och andra oönskade beteenden.
* Säkerhetsuppdateringar gäller inte.

## Möjliga lösningar {#solutions}

* Minimera användningen av innehållsövertäckning till de fall där den behövs.
* Undvik framför allt överläggning av begränsat innehåll (slutlig och intern klassificering).
* Överväg att anpassa ändringar från `/libs` efter AEM uppgraderingar, ServicePack eller CumulativeFixPack.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
