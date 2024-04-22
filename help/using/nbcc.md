---
title: NBCC
description: Hjälpsida för Mönsteravkännarkod.
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# NBCC {#nbcc}

UTTRYCKT: Icke-bakåtkompatibla ändringar (ersätts av NCC, icke-kompatibla ändringar)

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="Icke-bakåtkompatibla ändringar"
>abstract="NBCC identifierar situationen där vissa JCR-noder eller paket ändras på ett icke-kompatibelt sätt. Kunden kanske inte känner till den här ändringen före en uppgradering."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="Betydande ändringar - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="Versionsinformation - AEM as a Cloud Service"

`NBCC` identifierar den situation där vissa JCR-noder eller paket ändras på ett sätt som inte är kompatibelt. Kunden kanske inte känner till den här ändringen före en uppgradering.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Funktionen som är beroende av en komponent som använder icke-bakåtkompatibla ändringar kan brytas och kanske inte löses korrekt.
* Vissa funktioner i kundprogrammet eller vissa AEM kanske inte fungerar som de ska efter en uppgradering.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="Genomförande"
>abstract="Det bästa sättet är att granska anpassad kod och se till att endast bakåtkompatibla Sling-komponenter överlappas eller refereras. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="Övertäckningar"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Överlägg eller referera endast bakåtkompatibla Sling-komponenter.
* Överväg att anpassa resurser som kommer från `/libs` eller paket efter en AEM uppgradering.
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
