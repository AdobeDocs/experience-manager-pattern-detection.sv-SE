---
title: URS
description: Hjälpsida för mönsteravkännarkod
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: d2ba93866c8f2b50c36ba6f5e9c5dc0313731c3b
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# URS {#urs}

Databasstrukturen stöds inte

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="Databasstrukturen stöds inte"
>abstract="URS identifierar fall av databasstruktur och nodegenskaper som inte stöds. Den här informationen används för att undvika konflikter mellan AEM produktkod och kundkod, och innehållet struktureras om från /etc till andra mappar i databasen med mera."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html" text="Omstrukturering av lager"

## Bakgrund {#background}

`URS` identifierar fall av databasstruktur och nodegenskaper som inte stöds. Från och med AEM 6.4 finns det riktlinjer för omstrukturering av databasinnehåll. Genom att tydligt definiera hierarkier för AEM produktkod och kundkod och undvika konflikter mellan dem struktureras innehållet om från `/etc` till andra mappar i databasen enligt följande högnivåregler:

* AEM produktkod placeras alltid i `/libs`, som inte får skrivas över av anpassad kod.
* Anpassad kod ska placeras i `/apps`, `/content` och `/conf`.
* Vi rekommenderar starkt att dessa riktlinjer följs AEM as a Cloud Service.

Undertyper används för att identifiera specifika typer av databasproblem som ska åtgärdas:
* `clientlibs.location`: Ett klientbibliotek som refererar `/etc` efter bana.
* `file.location`: En fil under `/etc` som har ändrats sedan installationen.
* `node.location`: En nod under `/etc` som har ändrats sedan installationen.
* `workflow.location`: En arbetsflödesmodell eller startfunktion under `/etc/workflow`.
* `package.structure`: Ett paket som innehåller både ändringsbart och oföränderligt innehåll.
* `node.size`: En nod med en storlek som inte stöds.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Anpassad kod som är beroende av äldre sökvägar kan orsaka oönskat beteende och påverka produktens funktion.
* Paket som innehåller både muterbart och oföränderligt innehåll orsakar troligen problem under distributionen.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="Implementeringsvägledning"
>abstract="Det bästa sättet är att granska kodprojektet och se till att det följer riktlinjerna för AEM projektstruktur och undvika att koden förlitar sig på äldre/databassökvägar som inte stöds, vilket kan orsaka oönskat beteende i AEM as a Cloud Service. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html" text="AEM riktlinjer för projektstruktur"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Se [Omstrukturering av lager](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html) för att ta fram riktlinjer för AEM as a Cloud Service.
* Se även [AEM projektstruktur](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) om du vill veta mer om ändringsbara och oföränderliga områden i databasen.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
* Utnyttja [Databasmodernisering](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools) att strukturera om befintliga projektpaket genom att separera innehåll och kod i separata paket som är kompatibla med projektstrukturen som definierats för Adobe Experience Manager as a Cloud Service.
