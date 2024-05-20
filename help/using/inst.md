---
title: INST
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---

# INST {#inst}

Installerad artefakt

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="Installerad artefakt"
>abstract="INST identifierar anpassade paket och paket från tredje part som kunden har installerat i AEM. Dessa rapporteras för att bidra till att karakterisera systemets tillstånd i den allmänna omfattningen av en uppgraderingsinsats. Alla tredjepartspaket måste följa riktlinjerna för AEM as a Cloud Service utveckling och paketering."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="Utvecklingsriktlinjer - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package" text="Riktlinjer för paketering - AEM as a Cloud Service"

`INST`  Identifierar anpassade paket och paket från tredje part som kunden har installerat i AEM. Dessa rapporteras för att bidra till att karakterisera systemets tillstånd i den allmänna omfattningen av en uppgraderingsinsats.

När flera versioner av ett paket har installerats rapporteras endast den senaste versionen.

Paket och paket som identifieras har inte nödvändigtvis optimerats för AEM as a Cloud Service. Alla tredjepartspaket bör verifieras med den som skapat dem eller Adobe för kompatibilitet med AEM as a Cloud Service.

Undertyper används för att identifiera olika typer av information:

* `custom.bundle`: Ett paket som har installerats i AEM.
* `custom.package`: Ett paket som har installerats i AEM.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="Genomförande"
>abstract="Kunder kan inte längre installera tredjepartspaket med CRX Package Manager. Kunderna bör granska dessa installerade artefakter som måste struktureras och optimera dem för att fungera med AEM as a Cloud Service. Verifiera alla tredjepartspaket med antingen dess skapare eller med Adobe för kompatibilitet med AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embeddeds" text="Bädda in delpaket i behållarpaketet"


* Det går inte att installera tredjepartspaket med CRX Package Manager på AEM as a Cloud Service.
* Program som är beroende av tredjepartspaket kanske inte fungerar som förväntat förrän de distribueras korrekt för att fungera med AEM as a Cloud Service.
* Om leverantörspaket från tredje part inte är optimerade för AEM som en molntjänst kan det leda till oönskat beteende.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="Verktyg och resurser"
>abstract="Läs om hur INST-överträdelser kan göras kompatibla med AEM Cloud Service. Granska också INST-överträdelse-exemplet på GitHub för att förstå hur detta kan korrigeras och distribueras på AEM as a Cloud Service."
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="Exempel på INST-överträdelse - GitHub"

* Tredjepartspaket ska distribueras till AEM som en del av projektet med Cloud Manager [distributionsprocess](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/deploy-code#deployment-process).
* Granska hur [bädda in tredjepartspaket](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embedding-3rd-party-packages) i ditt projekt för AEM as a Cloud Service.
* Tredjepartspaket måste följa AEM as a Cloud Service [utveckling](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines) och [packning](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package) riktlinjer.
* Granska [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst) projekt och förstå hur [INST-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst) kan korrigeras och göras kompatibelt med AEM as a Cloud Service.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
