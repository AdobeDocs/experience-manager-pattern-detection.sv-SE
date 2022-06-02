---
title: CDW
description: Hjälpsida för mönsteravkännarkod
source-git-commit: 04709ba74eedad903669aae589c605542e1e3b09
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# CDW {#cdw}

Widget för anpassad dialogruta

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_overview"
>title="Widget för anpassad dialogruta"
>abstract="CDW identifierar widgetar för anpassade dialogrutor som bör uppdateras för att vara kompatibla med AEM as a Cloud Service."

`CDW`  Anpassade dialogrutewidgetar identifierar anpassade CoralUI- och Classic-dialogrutewidgetar. Dessa bör uppdateras för att vara kompatibla med AEM as a Cloud Service.

Undertyper används för att identifiera olika typer av information, t.ex.:

* `custom.coral.widget`: Identifiera widgetar för anpassade dialogrutor baserat på CoralUI 2 eller CoralUI 3.
* `custom.classic.widget`: Identifiera widgetar för anpassade dialogrutor baserat på ExtJs.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Det klassiska användargränssnittet är inte längre tillgängligt på AEM as a Cloud Service. Standardgränssnittet för redigering är det pekaktiverade gränssnittet.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_guidance"
>title="Implementeringsvägledning"
>abstract="Kontakta kundtjänst om du behöver hjälp."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Anpassade widgetar för klassisk dialogruta ska konverteras från ExtJS till [CoralUI](https://developer.adobe.com/experience-manager/reference-materials/6-5/coral-ui/coralui3/getting-started.html).
* Anpassade widgetar för Coral Dialog bör utvärderas för uppdatering till CoralUI 3.
* Nå ut till [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
