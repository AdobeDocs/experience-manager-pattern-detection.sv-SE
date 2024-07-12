---
title: CCOM
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# CCOM {#ccom}

Egen komponent

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="Egen komponent"
>abstract="CCOM identifierar anpassade komponenter som är installerade på AEM. Denna information tillhandahålls i syfte att bedöma bästa praxis"

`CCOM` Identifierar anpassade komponenter som är installerade på AEM. Denna information tillhandahålls för bedömning av bästa metoder.

En undertyp används med den här koden för att identifiera komponentkategorin:

* `custom.core`: En supertyp i komponentens kedja av supertyper innehåller `core/wcm/components/`, vilket anger att den ärver från en kärnkomponent.
* `custom.foundation`: En supertyp i komponentens kedja av supertyper innehåller `core/wcm/components/`, vilket anger att den ärver från en kärnkomponent.
* `custom.overlay.foundation`: Komponentsökvägen innehåller `wcm/foundation/components/` eller `foundation/components/`, vilket anger att den täcker en grundkomponent.
* `custom`: Den anpassade komponenten ärver eller täcker inte över en kärna- eller grundkomponent.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Bästa sättet är att minimera antalet anpassade komponenter, använda kärnkomponenter och använda kärnkomponenter med Style System så att du kan minska den tekniska skulden.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="Genomförande"
>abstract="Bästa praxis är att minimera antalet anpassade komponenter, använda kärnkomponenter och använda kärnkomponenter med Style System för att minska den tekniska skulden."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction" text="Kärnkomponenter"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring" text="Formatsystem"

* Mer information om kärnkomponenter finns i [Introduktion till kärnkomponenter](https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction).
* Mer information om Style System finns på [Använda Style System](https://experienceleague.adobe.com/en/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring).
* Kontakta [AEM supportteamet](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
