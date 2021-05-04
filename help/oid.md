---
title: OID
description: Hjälpsida för mönsteravkännarkod
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# OID {#oid}

Oak Index-definition

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak Index-definition"
>abstract="OID identifierar problem som är relaterade till indexdefinitioner för Oak. Den identifierar ändringar som har gjorts i standardindexdefinitionerna för ekak. Den identifierar också anpassade Oak-indexdefinitioner som är inkompatibla med AEM som en Cloud Service. Meddelandet för varje OID-sökning identifierar indexet och ger ytterligare information."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#how-to-use" text="Riktlinjer för innehållsindexering"

`OID` identifierar problem som är relaterade till indexdefinitioner för läckage. Den identifierar ändringar som har gjorts i standardindexdefinitionerna för ekak. Den identifierar också anpassade Oak-indexdefinitioner som är inkompatibla med AEM som en Cloud Service. Meddelandet för varje `OID`-sökning identifierar indexet och ger ytterligare information.

Undertyper används för att identifiera olika typer av information:

* `custom.index.violation`: Ett anpassat Oak-index är inkompatibelt med AEM som en Cloud Service.
* `standard.index.modification`: En ändring av ett standardekindexvärde.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="Implementeringsvägledning"
>abstract="Det bästa sättet är att granska alla anpassade index och strukturerade enligt riktlinjerna för innehållsindexering. Utnyttja indexkonverteraren för att migrera befintliga anpassade indexdefinitioner för eko till AEM som en Cloud Service-kompatibel indexdefinition för eko"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#oak-indexes" text="Riktlinjer för paketering"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools" text="Indexkonverterare"

* Ändringar av standardindexdefinitioner för ekv kan gå förlorade under en AEM uppgradering.
* Oak-definitioner är oföränderliga, ska paketeras med kundens projektkod och ska bara distribueras med Cloud Manager.
* Alla Oak-indexdefinitioner ska följa namnkonventionen och andra regler för Oak-index i AEM som Cloud Service. De som inte gör det kan orsaka oönskat beteende.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="Verktyg och resurser"
>abstract="Granska ett WKND-gammalt projekt för att förstå hur OID-överträdelser kan lösas i ditt projekt. Granska också Exempel på OID-överträdelse på Github för att förstå hur äldre index kan konverteras med verktyget Indexkonverterare och göras kompatibla med AEM som en Cloud Service."
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="Exempel på OID-överträdelse - Github"

* Åtgärda de indexregelfel som identifieras i meddelandet.
* Följ AEM som en Cloud Service [paketeringsriktlinjer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) för att distribuera nya eller anpassade Oak-indexdefinitioner.
* Anpassade AEM standardindex och nya anpassade Oak-indexdefinitioner ska följa [riktlinjerna för innehållsindexering](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#preparing-the-new-index-definition) för AEM som Cloud Service.
* Granska [wk-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)-projekt och förstå hur [OID-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid) kan korrigeras och göras kompatibla med AEM som en Cloud Service.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
* Använd [indexkonverteraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools) för att migrera befintliga anpassade indexdefinitioner för eko till AEM som en Cloud Service-kompatibel indexdefinition för ekon.
