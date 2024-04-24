---
title: CCOM
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# CCOM {#ccom}

Egen komponent

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="Egen komponent"
>abstract="CCOM identifierar anpassade komponenter som har installerats på AEM. Denna information tillhandahålls i syfte att bedöma bästa praxis"

`CCOM` Identifierar anpassade komponenter som har installerats på AEM. Denna information tillhandahålls för bedömning av bästa metoder.

En undertyp används med den här koden för att identifiera komponentkategorin:

* `custom.core`: En supertyp i komponentens kedja av supertyper innehåller&quot;core/wcm/components/&quot;, vilket anger att den ärver från en kärnkomponent.
* `custom.foundation`: En supertyp i komponentens kedja av supertyper innehåller&quot;core/wcm/components/&quot;, vilket anger att den ärver från en kärnkomponent.
* `custom.overlay.foundation`: Komponentsökvägen innehåller &quot;wcm/foundation/components/&quot; eller &quot;foundation/components/&quot;, vilket anger att den täcker en grundkomponent.
* `custom`: Den anpassade komponenten ärver eller täcker inte över en kärna- eller grundkomponent.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Bästa praxis är att minimera antalet anpassade komponenter, använda kärnkomponenter och använda kärnkomponenter med Style System för att minska den tekniska skulden.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="Genomförande"
>abstract="Bästa praxis är att minimera antalet anpassade komponenter, använda kärnkomponenter och använda kärnkomponenter med Style System för att minska den tekniska skulden."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction" text="Kärnkomponenter"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring" text="Formatsystem"

* Mer information om kärnkomponenter finns på [Introduktion till kärnkomponenter](https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction).
* Mer information om Style System finns på [Använda formatsystemet](https://experienceleague.adobe.com/en/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring).
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
