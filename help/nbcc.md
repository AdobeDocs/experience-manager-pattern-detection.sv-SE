---
title: NBCC
description: Hjälpsida för mönsteravkännarkod
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---

# NBCC {#nbcc}

Icke-bakåtkompatibla ändringar

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="Icke-bakåtkompatibla ändringar"
>abstract="NBCC identifierar situationen där vissa JCR-noder eller paket ändras på ett icke-kompatibelt sätt. Kunden kanske inte känner till den här ändringen före en uppgradering."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="Betydande ändringar - AEM som en Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="Versionsinformation - AEM som Cloud Service"

`NBCC` identifierar den situation där vissa JCR-noder eller paket ändras på ett sätt som inte är kompatibelt. Kunden kanske inte känner till den här ändringen före en uppgradering.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Funktionen som är beroende av en komponent som använder icke-bakåtkompatibla ändringar kan brytas och kanske inte löses korrekt.
* Vissa funktioner i kundprogrammet eller vissa AEM kanske inte fungerar som de ska efter en uppgradering.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="Implementeringsvägledning"
>abstract="Det bästa sättet är att granska anpassad kod och se till att endast bakåtkompatibla Sling-komponenter överlappas eller refereras. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="Övertäckningar"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Överlägg eller referera endast bakåtkompatibla Sling-komponenter.
* Överväg att anpassa resurser som kommer från `/libs` eller paket efter en AEM uppgradering.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
