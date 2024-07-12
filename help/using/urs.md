---
title: URS
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: b77a168fc8c075e8e41149a38df4d83fd2504a14
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---

# URS {#urs}

Databasstrukturen stöds inte

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="Databasstrukturen stöds inte"
>abstract="URS identifierar fall av URS (Databasstruktur som inte stöds) och nodegenskaper. Den här ytinformationen undviker konflikter mellan AEM produktkod och kundkod, och innehållet struktureras om från `/etc` till andra mappar i databasen med mera."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/restructuring/repository-restructuring" text="Omstrukturering av lager"

## Bakgrund {#background}

`URS` Identifierar fall av URS (Databasstruktur som inte stöds) och nodegenskaper. Från och med AEM 6.4 finns det riktlinjer för omstrukturering av databasinnehåll. Genom att tydligt definiera hierarkier för AEM produktkod och kundkod, och undvika konflikter mellan dem alla, omstruktureras innehållet från `/etc` till andra mappar i databasen. Följ då följande högnivåregler:

* AEM produktkod placeras alltid i `/libs` som den anpassade koden inte får skriva över.
* Anpassad kod ska placeras i `/apps`, `/content` och `/conf`.
* Vi rekommenderar starkt att dessa riktlinjer följs för AEM as a Cloud Service.

Undertyper används för att identifiera specifika typer av databasproblem som ska åtgärdas:

* `clientlibs.location`: Ett klientbibliotek som refererar till `/etc` via sökväg.
* `file.location`: En fil under `/etc` som har ändrats sedan installationen.
* `node.location`: En nod under `/etc` som har ändrats sedan installationen.
* `workflow.location`: En arbetsflödesmodell eller startfunktion under `/etc/workflow`.
* `package.structure`: Ett paket som innehåller både muterbart och oföränderligt innehåll.
* `node.size`: En nod med en storlek som inte stöds.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Anpassad kod som är beroende av äldre sökvägar kan orsaka oönskat beteende och påverka produktens funktion.
* Paket som innehåller både muterbart och oföränderligt innehåll kan förmodligen orsaka problem under distributionen.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="Genomförande"
>abstract="Det bästa är att granska kodprojektet. Se till att den följer riktlinjerna för AEM projektstruktur och undvik att kod förlitar sig på äldre eller ostödda databassökvägar som kan orsaka oönskat beteende i AEM as a Cloud Service. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure" text="AEM riktlinjer för projektstruktur"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Mer information om hur du förbereder dig för AEM as a Cloud Service finns i [Databasomstrukturering](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/restructuring/repository-restructuring).
* Se även [AEM Projektstruktur](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure) om du vill veta mer om ändringsbara och oföränderliga områden i databasen.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
* Använd [Databasmodernisering](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/repo-modernizer#refactoring-tools) för att strukturera om befintliga projektpaket genom att separera innehåll och kod i diskreta paket så att de blir kompatibla med den projektstruktur som har definierats för Adobe Experience Manager as a Cloud Service.
