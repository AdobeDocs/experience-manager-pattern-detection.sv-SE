---
title: LUI
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---


# LUI {#lui}

Äldre användargränssnitt

## Bakgrund {#background}

`LUI` används för att använda inaktuella användargränssnittselement som inte rekommenderas eller som inte stöds i senare versioner av AEM och AEM som Cloud Service.

Undertyper används för att identifiera olika typer av element i användargränssnittet som ska eller måste uppgraderas:

* `legacy.dialog.classic`: Klassiska användargränssnittsdialogrutor som baseras på ExtJS måste ändras till Coral.
   * Detta upptäcks när dialogrutans namn är &quot;dialog&quot; eller &quot;design_dialog&quot; och när
egenskapsvärdet `jcr:primaryType` eller `xtype`-egenskapsvärdet är &quot;cq:Dialog&quot;.
* `legacy.dialog.coral2`: Dialogrutorna för koral 2 ska uppdateras till att använda Coral 3.
   * Detta upptäcks när dialogrutan och dess underordnade innehållsnodnamn är &quot;cq:dialog/content&quot;,
&quot;cq:design_dialog/content&quot;, &quot;cq:dialog.coral2/content&quot; eller &quot;cq:design_dialog.coral2/content&quot;
och egenskapsvärdet `sling:resourceType` inte innehåller
&quot;granite/ui/components/coral/Foundation&quot;.
* `legacy.custom.component`: Komponenter som ärver från  `foundation/components`bör uppdateras till att använda kärnkomponenter.
   * Detta upptäcks när egenskapsvärdet `jcr:primaryType` är &quot;cq:Component&quot; och
      `sling:resourceSuperType` egenskapsvärdet innehåller &quot;grund/komponenter&quot; eller någon av
      `sling:resourceSuperType` egenskapsvärden för kedjan med supertypskomponenter innehåller &quot;grund/komponenter&quot;.
* `legacy.static.template`: Statiska mallar bör uppgraderas till Redigerbara mallar.
   * Detta upptäcks när egenskapsvärdet `jcr:primaryType` är &quot;cq:Template&quot;.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Det klassiska användargränssnittet är inte längre tillgängligt i AEM som Cloud Service. Standardgränssnittet för redigering är det pekaktiverade gränssnittet.
* Om du förlitar dig på äldre anpassade komponenter kan underhållskostnaderna öka med tiden.

## Möjliga lösningar {#solutions}

* Använd [AEM Moderniseringsverktyg](https://opensource.adobe.com/aem-modernize-tools/) för att minska den ansträngning som krävs för att modernisera AEM Sites-implementeringarna. Bland dessa verktyg finns konvertering av:
   * Klassiska (ExtJS) dialogrutor till koralldialogrutor
   * Foundation-komponenter till Core-komponenter
   * Statiska mallar och kolumnkontroll till redigerbara mallar och responsivt rutnät
   * Designa och utforma dialogrutor till redigerbara mallprofiler
* Granska projektets bibliotek med anpassade komponenter och gå om möjligt över till en uppsättning standardiserade [kärnkomponenter](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html) för att snabba upp utvecklingstiden och minska underhållskostnaderna för dina program.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
