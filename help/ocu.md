---
title: OCU
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# OCU {#ocu}

Inaktuell kodanvändning

## Bakgrund {#background}

`OCU` identifierar den situation där vissa JCR-noder, som Sling- eller AEM-komponenter eller API OSGi-exporter, ändras eller tas bort på ett icke-kompatibelt sätt. Kunden kanske inte känner till den här ändringen före en uppgradering. De kan uppgraderas till en version som inte är kompatibel eller inte vara tillgängliga alls.

Eftersom de gamla versionerna inte installeras som standard kanske kundapplikationen inte fungerar som den ska.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Funktionen som är beroende av komponenter som använder inaktuella komponenter eller API:er kan brytas och kanske inte kan matchas korrekt efter en uppgradering.
* Vissa funktioner i kundprogrammet eller vissa AEM kanske inte fungerar som de ska eller kanske inte är aktiva efter en uppgradering.

## Möjliga lösningar {#solutions}

* Kortfristig: Installation av kompatibilitetspaket kan vara till hjälp.
* Långsiktigt: Anpassa kundkoden till den senaste versionen av AEM eller API:er.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
