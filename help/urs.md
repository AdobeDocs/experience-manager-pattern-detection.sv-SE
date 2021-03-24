---
title: URS
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 5a83dd8d08da974a5d775032b8dbea2593be9d15
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 0%

---


# URS {#urs}

Databasstrukturen stöds inte

## Bakgrund {#background}

`URS` används för att identifiera fall där databasstrukturen inte stöds. Från och med AEM 6.4 finns det riktlinjer för omstrukturering av databasinnehåll. Genom att tydligt definiera hierarkier för AEM produktkod och kundkod och undvika konflikter mellan dem, struktureras innehållet om från `/etc` till andra mappar i databasen, enligt följande högnivåregler:

* AEM produktkod placeras alltid i `/libs`, som inte får skrivas över av anpassad kod. Anpassad kod ska placeras i `/apps`, `/content` och `/conf`.
* Vi rekommenderar starkt att dessa riktlinjer följs för AEM som Cloud Service.

Undertyper används för att identifiera specifika typer av databasproblem som ska åtgärdas:
* `clientlibs.location`: Ett klientbibliotek som refererar  `/etc` via sökväg.
* `file.location`: En fil under  `/etc` som har ändrats sedan installationen.
* `node.location`: En nod under  `/etc` som har ändrats sedan installationen.
* `workflow.location`: En arbetsflödesmodell eller startfunktion under  `/etc/workflow`.
* `package.structure`: Ett paket som innehåller både ändringsbart och oföränderligt innehåll.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Anpassad kod som är beroende av äldre sökvägar kan orsaka oönskat beteende och påverka produktens funktion.
* Paket som innehåller både muterbart och oföränderligt innehåll orsakar troligen problem under distributionen.

## Möjliga lösningar {#solutions}

* Se [Databasomstrukturering](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html) för vägledning om hur du förbereder dig för AEM som Cloud Service.
* Se även [AEM projektstruktur](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) för mer information om ändringsbara och oföränderliga områden i databasen.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
* Dra nytta av [Repository Modernizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools) för att strukturera om befintliga projektpaket genom att separera innehåll och kod i diskreta paket som är kompatibla med den projektstruktur som har definierats för Adobe Experience Manager som en Cloud Service.