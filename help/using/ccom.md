---
title: CCOM
description: Hjälpsida för mönsteravkännarkod
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# CCOM {#ccom}

Egen komponent

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="Egen komponent"
>abstract="CCOM identifierar anpassade komponenter som har installerats på AEM. Denna information tillhandahålls i syfte att bedöma bästa praxis"

`CCOM` identifierar anpassade komponenter som har installerats på AEM. Denna information tillhandahålls för bedömning av bästa metoder.

En undertyp används med den här koden för att identifiera komponentkategorin:

* `custom.core`: En supertyp i komponentens kedja av supertyper innehåller &quot;core/wcm/components/&quot;, vilket anger att den ärver från en kärnkomponent.
* `custom.foundation`: En supertyp i komponentens kedja av supertyper innehåller &quot;core/wcm/components/&quot;, vilket anger att den ärver från en kärnkomponent.
* `custom.overlay.foundation`: Komponentsökvägen innehåller &quot;wcm/foundation/components/&quot; eller &quot;foundation/components/&quot;, vilket anger att den täcker en grundkomponent.
* `custom`: Den anpassade komponenten ärver eller täcker inte över en kärna- eller grundkomponent.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Bästa praxis är att minimera antalet anpassade komponenter, utnyttja kärnkomponenterna och använda huvudkomponenterna med Style System för att minska den tekniska skulden.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="Implementeringsvägledning"
>abstract="Bästa praxis är att minimera antalet anpassade komponenter, utnyttja kärnkomponenterna och använda huvudkomponenterna med Style System för att minska den tekniska skulden."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="Kärnkomponenter"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring" text="Formatsystem"

* Mer information om kärnkomponenter finns på [Introduktion till kärnkomponenter](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html).
* Mer information om Style System finns på [Använda formatsystemet](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring).
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
