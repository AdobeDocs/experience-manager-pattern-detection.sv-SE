---
title: LUI
description: Hjälpsida för mönsteravkännarkod
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 1dbb239f23986f11c0dd6bfa883d8ab9124c0b52
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 1%

---

# LUI {#lui}

Äldre användargränssnitt

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="Äldre användargränssnitt"
>abstract="LUI identifierar användning av inaktuella element i användargränssnittet som inte rekommenderas eller inte stöds i senare versioner av AEM och i AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="Betydande ändringar - AEM as a Cloud Service"

`LUI` identifierar användningen av inaktuella element i användargränssnittet som inte rekommenderas eller inte stöds i senare versioner av AEM och i AEM as a Cloud Service.

Undertyper används för att identifiera olika typer av element i användargränssnittet som ska eller måste uppgraderas:

* `legacy.dialog.classic`: Klassiska användargränssnittsdialogrutor som baseras på ExtJS måste ändras till Coral.
   * Detta upptäcks när dialogrutans namn är &quot;dialog&quot; eller &quot;design_dialog&quot; och när `jcr:primaryType` egenskapsvärdet eller `xtype` egenskapsvärdet är &quot;cq:Dialog&quot;.
* `legacy.dialog.coral2`: Dialogrutorna för koral 2 bör uppdateras till att använda Coral 3.
   * Detta upptäcks när dialogrutan och dess underordnade innehållsnodnamn är &quot;cq:dialog/content&quot;, &quot;cq:design_dialog/content&quot;, &quot;cq:dialog.coral2/content&quot; eller &quot;cq:design_dialog.coral2/content&quot; och `sling:resourceType` egenskapsvärdet innehåller inte &quot;granite/ui/components/coral/Foundation&quot;.
* `legacy.custom.component`: Komponenter som ärver från `foundation/components` bör uppdateras för att använda kärnkomponenter.
   * Detta upptäcks när `jcr:primaryType` egenskapsvärdet är &quot;cq:Component&quot; och
      `sling:resourceSuperType` egenskapsvärdet innehåller &quot;grund/komponenter&quot; eller någon av
      `sling:resourceSuperType` egenskapsvärden för kedjan med supertypskomponenter innehåller &quot;grund/komponenter&quot;.
* `legacy.static.template`: Statiska mallar ska uppgraderas till redigerbara mallar.
   * Detta upptäcks när `jcr:primaryType` egenskapsvärdet är &quot;cq:Template&quot;.
* `content.fragment.template`: Mallar för innehållsfragment bör skapa fragmentmodeller som ersätter fragmentmallarna.
   * Mallar för innehållsfragment finns på följande platser:
      * Innehållsfragmentmallar som ligger utanför ramarna lagras i `/libs/settings/dam/cfm/templates`
      * De kan överlappas av  `/apps/settings/dam/cfm/templates`  eller  `/conf/.../settings/dam/cfm/templates`(... = global eller &quot;tenant&quot;)

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="Implementeringsvägledning"
>abstract="Det klassiska användargränssnittet är inte längre tillgängligt i AEM as a Cloud Service och standardgränssnittet för redigering är det användargränssnitt som har stöd för pekfunktioner. Bästa praxis är att flytta alla gränssnitt som inte stöds och länkade anpassningar bör omarbetas till nyare funktioner som är kompatibla med AEM as a Cloud Service. Kunderna kan utnyttja det befintliga AEM Moderniseringssviten för att minska den ansträngning som krävs för att modernisera AEM Sites implementeringar."
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM Modernization Tools"

* Det klassiska användargränssnittet är inte längre tillgängligt på AEM as a Cloud Service. Standardgränssnittet för redigering är det pekaktiverade gränssnittet.
* Om du förlitar dig på äldre anpassade komponenter kan underhållskostnaderna öka med tiden.
* Mallar för innehållsfragment ersattes av innehållsfragmentmodeller i AEM 6.3. Om du migrerar innehållsfragment som är baserade på äldre mallar till AEM as a Cloud Service bevaras dessa fragment som funktionella, men det går inte att skapa nya fragment som är baserade på den äldre mallen. Det går inte heller att leverera dessa fragment med AEM GraphQL, som kräver innehållsfragmentmodeller som scheman.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="Verktyg och resurser"
>abstract="Med hjälp av AEM Modernization Suite kan kunderna konvertera klassiska (ExtJS) dialogrutor till koralldialogrutor. Avsikten är att hjälpa kunderna att gå över från funktioner som inte stöds eller äldre till robusta, moderna AEM. De här verktygen är konfigurerbara, konfigureringsmedvetna och utökningsbara. Utforska även att ersätta anpassade komponenter med en uppsättning standardkomponenter för att snabba upp utvecklingstiden och minska underhållskostnaderna för dina program."
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/component.html" text="Komponentkonverterare"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="Kärnkomponenter"

* Utnyttja [AEM Moderniseringsverktyg](https://opensource.adobe.com/aem-modernize-tools/) för att minska den ansträngning som krävs för att modernisera era AEM Sites-implementeringar. Bland dessa verktyg finns konvertering av:
   * Klassiska (ExtJS) dialogrutor till koralldialogrutor
   * Foundation-komponenter till Core-komponenter
   * Statiska mallar och kolumnkontroll till redigerbara mallar och responsivt rutnät
   * Designa och utforma dialogrutor till redigerbara mallprofiler
* Granska projektets anpassade komponentbibliotek och överför om möjligt till uppsättningen standardiserade [Kärnkomponenter](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html) för att snabba upp utvecklingstiden och minska underhållskostnaderna för dina program.
* Vi rekommenderar att du skapar innehållsfragmentmodeller med funktioner som är likvärdiga med de gamla mallarna och använder dessa modeller för att skapa innehållsfragment som går framåt.Mer information finns i [Modeller för innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=en) för mer information.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
