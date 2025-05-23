---
title: NBCC
description: Hjälpsida för Mönsteravkännarkod.
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# NBCC {#nbcc}

UTTRYCKT: Icke-bakåtkompatibla ändringar (ersätts av NCC, icke-kompatibla ändringar)

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="Icke-bakåtkompatibla ändringar"
>abstract="NBCC identifierar den situation där vissa JCR-noder eller paket ändras på ett icke-kompatibelt sätt. Kunden kanske inte känner till denna förändring innan uppgraderingen."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="Betydande ändringar - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="Versionsinformation - AEM as a Cloud Service"

`NBCC` Identifierar situationen där vissa JCR-noder eller paket ändras på ett icke-kompatibelt sätt. Kunden kanske inte känner till denna förändring innan uppgraderingen.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Funktionen som är beroende av en komponent som använder icke-bakåtkompatibla ändringar kan brytas och kanske inte löses korrekt.
* Vissa funktioner i kundprogrammet eller vissa AEM kanske inte fungerar som de ska efter en uppgradering.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="Genomförande"
>abstract="Det bästa sättet är att granska anpassad kod och se till att endast bakåtkompatibla Sling-komponenter överlappas eller refereras. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-65/content/implementing/developing/platform/overlays#platform" text="Övertäckningar"
>additional-url="https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Överlägg eller referera endast bakåtkompatibla Sling-komponenter.
* Överväg att anpassa resurser som kommer från `/libs` eller paket efter en AEM uppgradering.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
