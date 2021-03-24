---
title: CCOM
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---


# CCOM {#ccom}

Egen komponent

## Bakgrund {#background}

`CCOM` identifierar anpassade komponenter som har installerats på AEM. Denna information tillhandahålls för bedömning av bästa metoder.

En undertyp används med den här koden för att identifiera komponentkategorin:

* `custom.core`: En supertyp i komponentens kedja av supertyper innehåller &quot;core/wcm/components/&quot;, vilket anger att den ärver från en kärnkomponent.
* `custom.foundation`: En supertyp i komponentens kedja av supertyper innehåller &quot;core/wcm/components/&quot;, vilket anger att den ärver från en kärnkomponent.
* `custom.overlay.foundation`: Komponentsökvägen innehåller &quot;wcm/foundation/components/&quot; eller &quot;foundation/components/&quot;, vilket anger att den täcker en grundkomponent.
* `custom`: Den anpassade komponenten ärver eller täcker inte över en kärna- eller grundkomponent.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Bästa praxis är att minimera antalet anpassade komponenter, utnyttja kärnkomponenterna och använda huvudkomponenterna med Style System för att minska den tekniska skulden.

## Möjliga lösningar {#solutions}

* Mer information om kärnkomponenter finns i [Introduktion till kärnkomponenter](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html).
* Mer information om Style System finns på [Använda Style System](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring).
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
