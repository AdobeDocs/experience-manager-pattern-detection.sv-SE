---
title: ACV
description: Hjälpsida för mönsteravkännarkod
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
source-git-commit: e7096efc1d9da7f5aad5a5b353ba622c879cc4a5
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# ACV {#acv}

Assets Content Validator

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets Content Validator"
>abstract="ACV identifierar de saknade obligatoriska noderna i resursinnehållet."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html" text="Betydande ändringar - Experience Manager as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="Experience Manager as a Cloud Service - versionsinformation"

`ACV`  Resursens innehållsvaliderare identifierar de saknade obligatoriska noderna och felen i resursinnehållet. Detta kan leda till fel på vissa Assets-funktioner på Experience Manager as a Cloud Service.

Undertyper används för att identifiera olika typer av information, t.ex.:

* `missing.jcrcontent`: Identifiera mappar där obligatoriska noder saknas i databasen. Om du identifierar innehåll som saknas i databasen kan du förhindra att funktioner som inte fungerar fungerar eller att använda dem.
* `missing.original.rendition`: Identifiera resurserna med en obligatorisk ursprunglig återgivning som saknas i databasen. Observera att det inte krävs någon generering av underresurser i AEMaaCS för att förhandsgranska PDF-sidor. Därför ignoreras rapportering av underresurser som saknar ursprunglig återgivning för PDF-resurser.
* `metadata.descendants.violation`: Identifiera resurserna med fler än 100 underordnade under objektets metadatanod i databasen.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Detta kan leda till fel på vissa resursfunktioner som är beroende av ärvda egenskaper i Experience Manager as a Cloud Service.
* AEM Assets är beroende av den ursprungliga återgivningen. Resursbearbetningen i Cloud Servicen kommer att hamna i en slinga om den ursprungliga återgivningen saknas. Generering av delresurser stöds inte i AEMaaCS.
* Ett stort antal underordnade under metadatanoden kan göra inläsningen av mappar som består av resurser som bryter mot detta kan gå långsammare.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="Implementeringsvägledning"
>abstract="Adobe rekommenderar att du granskar innehållsstrukturen för att förhindra att arbetsflöden som är beroende av ärvda egenskaper bryts. Kontakta kundtjänst om du behöver hjälp."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Analysera en mapp om den saknar en underordnad nod. Skapa noderna manuellt om det går att hantera antalet mappar. Använd i annat fall ett skript.
* För resurser som saknar den ursprungliga återgivningen kan du antingen överföra resurserna igen eller ta bort dem innan du migrerar.
* Ingen åtgärd krävs för den ursprungliga återgivningen av underresurser som saknas.
* Nå ut till [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
