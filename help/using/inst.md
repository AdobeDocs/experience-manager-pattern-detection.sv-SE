---
title: INST
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# INST {#inst}

Installerad artefakt

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="Installerad artefakt"
>abstract="INST identifierar anpassade paket och paket från tredje part som kunden har installerat i AEM. Sådana paket och paket rapporteras för att hjälpa till att beskriva systemets status och det allmänna tillämpningsområdet för en uppgraderingsinsats. Alla tredjepartspaket måste följa AEM as a Cloud Service riktlinjer för utveckling och paketering."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="Utvecklingsriktlinjer - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package" text="Riktlinjer för paketering - AEM as a Cloud Service"

`INST` Identifierar anpassade paket och paket från tredje part som kunden har installerat i AEM. Sådana paket och paket rapporteras för att hjälpa till att beskriva systemets status och det allmänna tillämpningsområdet för en uppgraderingsinsats.

När flera versioner av ett paket har installerats rapporteras endast den senaste versionen.

Paket och paket som identifieras har inte nödvändigtvis optimerats för AEM as a Cloud Service. Alla tredjepartspaket bör verifieras med den som skapat dem eller Adobe för kompatibilitet med AEM as a Cloud Service.

Undertyper används för att identifiera olika typer av information:

* `custom.bundle`: Ett paket som har installerats i AEM.
* `custom.package`: Ett paket som har installerats i AEM.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="Genomförande"
>abstract="Kunder kan inte längre installera paket från tredje part med CRX Package Manager. Kunderna bör granska dessa installerade artefakter som måste struktureras och optimera dem för att arbeta med AEM as a Cloud Service. Verifiera alla tredjepartspaket med antingen dess skapare eller med Adobe för kompatibilitet med AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embeddeds" text="Bädda in delpaket i behållarpaketet"


* Det går inte att installera tredjepartspaket med CRX Package Manager i AEM as a Cloud Service.
* Program som är beroende av tredjepartspaket kanske inte fungerar som förväntat förrän de distribueras korrekt för att fungera med AEM as a Cloud Service.
* Om leverantörspaket från tredje part inte är optimerade för AEM som en molntjänst kan det leda till oönskat beteende.

Tänk också på följande deltyper:

* `guava.bundle` - Guava stöds inte direkt i AEM 6.5 LTS och paketet är inte tillgängligt efter uppgraderingen.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="Verktyg och resurser"
>abstract="Granska ett WKND-gammalt projekt för att förstå hur INST-överträdelser kan göras kompatibla med AEM Cloud-tjänsten. Granska även exemplet på INST-överträdelse på GitHub för att förstå hur problemet kan åtgärdas och distribueras i AEM as a Cloud Service."
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="Exempel på INST-överträdelse - GitHub"

* Tredjepartspaket ska distribueras till AEM som en del av projektet med Cloud Manager [distributionsprocess](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/deploy-code#deployment-process).
* Granska hur du [bäddar in tredjepartspaket](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embedding-3rd-party-packages) i ditt projekt för AEM as a Cloud Service.
* Tredjepartspaket måste följa riktlinjerna för AEM as a Cloud Service [utveckling](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines) och [paketering](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package).
* Granska [projekt som är äldre än ](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst) och förstå hur [INST-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst) kan korrigeras och göras kompatibla med AEM as a Cloud Service.
* Kontakta [AEM Support Team](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
* För undertypen `guava.bundle` måste du antingen installera Guava eller ta bort användningen om Guava används i din egen kod.
