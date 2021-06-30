---
title: ACV
description: Hjälpsida för mönsteravkännarkod
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a5
source-git-commit: 57e33b97aba253bad62cf95dcca9ef6885d263e6
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# ACV {#acv}

Assets Content Validator

## Bakgrund {#background}

>[!INFO]
>id=&quot;aemcloud_bpa_acv_overview&quot;
>title=&quot;Assets Content Validator&quot;
>abstract=&quot;ACV identifierar de saknade obligatoriska noderna i resursinnehåll.&quot;
>additional-url=&quot;https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html&quot; text=&quot;Notable Changes - Experience Manager as a Cloud Service&quot;
>additional-url=&quot;https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html&quot; text=&quot;Experience Manager as a Cloud Service - Release Notes&quot;

`ACV`  Resursens innehållsvaliderare identifierar de saknade obligatoriska noderna i resursinnehållet. Detta kan leda till att vissa Assets-funktioner på Experience Manager inte fungerar som Cloud Service.

Undertyper används för att identifiera olika typer av information, t.ex.:

* `assets.sanity.missing.jcrcontent`: Identifiera mappar där obligatoriska noder saknas i databasen. Om du identifierar innehåll som saknas i databasen kan du förhindra att funktioner som inte fungerar fungerar eller att använda dem.

## Möjliga konsekvenser och risker {#implications-and-risks}

Detta kan leda till fel på vissa resursfunktioner som är beroende av ärvda egenskaper i Experience Manager som en Cloud Service.

## Möjliga lösningar {#solutions}

>[!INFO]
>id=&quot;aemcloud_bpa_acv_guidelines&quot;
>title=&quot;Implementeringsvägledning&quot;
>abstract=&quot;Adobe rekommenderar att innehållsstrukturen granskas för att förhindra att arbetsflöden som är beroende av ärvda egenskaper bryts. Kontakta kundtjänst om du behöver hjälp.&quot;
>additional-url=&quot;https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html&quot; text=&quot;Stöd för Experience Cloud&quot;

* Analysera en mapp om den saknar en underordnad nod. Skapa noderna manuellt om det går att hantera antalet mappar. Använd i annat fall ett skript.
* Kontakta vårt [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
