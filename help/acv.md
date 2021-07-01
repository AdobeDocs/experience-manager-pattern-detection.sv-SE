---
title: ACV
description: Hjälpsida för mönsteravkännarkod
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a5
source-git-commit: d61fbb28fdf91fd9b356654d5cd2d50b156398c4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# ACV {#acv}

Assets Content Validator

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets Content Validator"
>abstract="ACV identifierar de saknade obligatoriska noderna i resursinnehållet."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html" text="Betydande ändringar - Experience Manager som Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="Experience Manager som Cloud Service - Versionsinformation"

`ACV`  Resursens innehållsvaliderare identifierar de saknade obligatoriska noderna i resursinnehållet. Detta kan leda till att vissa Assets-funktioner på Experience Manager inte fungerar som Cloud Service.

Undertyper används för att identifiera olika typer av information, t.ex.:

* `assets.sanity.missing.jcrcontent`: Identifiera mappar där obligatoriska noder saknas i databasen. Om du identifierar innehåll som saknas i databasen kan du förhindra att funktioner som inte fungerar fungerar eller att använda dem.

## Möjliga konsekvenser och risker {#implications-and-risks}

Detta kan leda till fel på vissa resursfunktioner som är beroende av ärvda egenskaper i Experience Manager som en Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="Implementeringsvägledning"
>abstract="Adobe rekommenderar att du granskar innehållsstrukturen för att förhindra att arbetsflöden som är beroende av ärvda egenskaper bryts. Kontakta kundtjänst om du behöver hjälp.&quot;
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Analysera en mapp om den saknar en underordnad nod. Skapa noderna manuellt om det går att hantera antalet mappar. Använd i annat fall ett skript.
* Kontakta vårt [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
