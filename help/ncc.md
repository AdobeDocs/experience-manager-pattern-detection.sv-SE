---
title: NCC
description: Hjälpsida för mönsteravkännarkod
source-git-commit: fdc3e8bdef27de971743a9ecb04d3912cf8e60ad
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# NCC {#ncc}

Ej kompatibla ändringar

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_overview"
>title="Ej kompatibla ändringar"
>abstract="NCC identifierar situationen där vissa JCR-noder eller paket ändras på ett icke-kompatibelt sätt. Kunden kanske inte känner till den här ändringen före en uppgradering."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="Betydande ändringar - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="Versionsinformation - AEM as a Cloud Service"

`NCC` identifierar den situation där vissa JCR-noder eller paket ändras på ett sätt som inte är kompatibelt. Kunden kanske inte känner till den här ändringen före en uppgradering.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Funktionen som är beroende av en komponent som använder icke-kompatibla ändringar kan brytas och kanske inte löses korrekt.
* Vissa funktioner i kundprogrammet eller vissa AEM kanske inte fungerar som de ska efter en uppgradering.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_guidance"
>title="Implementeringsvägledning"
>abstract="Det bästa sättet är att granska anpassad kod och se till att endast kompatibla Sling-komponenter överlappas eller refereras. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="Övertäckningar"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Överlägg eller referera endast kompatibla Sling-komponenter.
* Överväg att anpassa resurser som kommer från `/libs` eller paket efter en AEM uppgradering.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
