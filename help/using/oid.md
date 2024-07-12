---
title: OID
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# OID {#oid}

Oak Index Definition

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak Index Definition"
>abstract="OID identifierar problem relaterade till Oak indexdefinitioner. Här identifieras ändringar som har gjorts i Oak standardindexdefinitioner. Den identifierar också anpassade indexdefinitioner för Oak som är inkompatibla med AEM as a Cloud Service. Meddelandet för varje OID-sökning identifierar indexet och ger ytterligare information."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing#how-to-use" text="Riktlinjer för innehållsindexering"

`OID` Identifierar problem relaterade till Oak indexdefinitioner. Här identifieras ändringar som har gjorts i Oak standardindexdefinitioner. Den identifierar också anpassade indexdefinitioner för Oak som är inkompatibla med AEM as a Cloud Service. Meddelandet för varje `OID`-sökning identifierar indexet och ger ytterligare information.

Undertyper används för att identifiera olika typer av information:

* `index.rule.violation`: Ett anpassat Oak-index är inkompatibelt med AEM as a Cloud Service
* `standard.index.modification`: En ändring av ett Oak-standardindex.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="Genomförande"
>abstract="Det bästa sättet är att granska alla anpassade index och omstrukturera enligt riktlinjerna för innehållsindexering. Använd indexkonverteraren för att migrera befintliga anpassade Oak-indexdefinitioner till AEM as a Cloud Service-kompatibla anpassade Oak-indexdefinitioner"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#oak-indexes" text="Riktlinjer för paketering"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools" text="Indexkonverterare"

* Ändringar av Oak standardindexdefinitioner kan gå förlorade under en AEM uppgradering.
* Oak-definitioner är oföränderliga, ska paketeras med kundens projektkod och ska bara distribueras med Cloud Manager.
* Alla indexdefinitioner för Oak ska följa namnkonventionen och andra regler för Oak-index i AEM as a Cloud Service. Annars kan det orsaka oönskat beteende.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="Verktyg och resurser"
>abstract="Granska ett WKND-gammalt projekt för att förstå hur OID-överträdelser kan lösas i ditt projekt. Granska även exemplet på OID-överträdelse på GitHub. Det kan hjälpa dig att förstå hur gamla index kan konverteras med verktyget Indexkonverterare och göras kompatibla med AEM as a Cloud Service."
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="Exempel på OID-överträdelse - GitHub"

* Åtgärda de indexregelfel som identifieras i meddelandet.
* Om du vill distribuera nya eller anpassade Oak-indexdefinitioner följer du AEM as a Cloud Service [packningsriktlinjer](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure).
* Anpassade AEM standardindex och nya anpassade Oak-indexdefinitioner bör följa [riktlinjerna för innehållsindexering](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing#preparing-the-new-index-definition) för AEM as a Cloud Service.
* Granska [WKD-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)-projekt och förstå hur [OID-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid) kan korrigeras och göras kompatibla med AEM as a Cloud Service.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
* Använd [Indexkonverteraren](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools) för att migrera befintliga anpassade Oak-indexdefinitioner till AEM as a Cloud Service-kompatibla anpassade Oak-indexdefinitioner.
