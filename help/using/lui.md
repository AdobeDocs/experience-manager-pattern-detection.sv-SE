---
title: LUI
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# LUI {#lui}

Äldre användargränssnitt

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="Äldre användargränssnitt"
>abstract="LUI identifierar användningen av inaktuella användargränssnittselement. Dessa element som inte rekommenderas eller inte stöds i senare versioner av AEM och i AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="Betydande ändringar - AEM as a Cloud Service"

`LUI`  Identifierar användningen av inaktuella användargränssnittselement. Dessa element rekommenderas inte eller stöds inte i senare versioner av AEM och i AEM as a Cloud Service.

Undertyper används för att identifiera olika typer av element i användargränssnittet som ska eller måste uppgraderas:

* `legacy.dialog.classic`: Dialogrutor för klassiskt användargränssnitt som baseras på ExtJS måste ändras till Koral.
   * Den här undertypen identifieras när dialogrutans namn är `dialog` eller `design_dialog` och när `jcr:primaryType` egenskapsvärdet eller `xtype` egenskapsvärdet är `cq:Dialog`.
* `legacy.dialog.coral2`: `Coral 2` ska dialogrutorna uppdateras för att användas `Coral 3`.
   * Den här undertypen identifieras när dialogrutan och dess nodnamn för underordnat innehåll är
      * `cq:dialog/content`,
      * `cq:design_dialog/content`,
      * `cq:dialog.coral2/content`,
      * eller `cq:design_dialog.coral2/content`
och `sling:resourceType` egenskapsvärdet innehåller inte `granite/ui/components/coral/foundation`.
* `legacy.custom.component`: Komponenter som ärver från `foundation/components` bör uppdateras för att använda kärnkomponenter.
   * Den här undertypen identifieras när `jcr:primaryType` egenskapsvärdet är `cq:Component` och
     `sling:resourceSuperType` egenskapsvärdet innehåller&quot;grund/komponenter&quot;. Eller någon av
     `sling:resourceSuperType` egenskapsvärden för kedjan med supertypskomponenter innehåller &quot;grund/komponenter&quot;.
* `legacy.static.template`: Statiska mallar ska uppgraderas till redigerbara mallar.
   * Den här undertypen identifieras när `jcr:primaryType` egenskapsvärdet är `cq:Template`.
* `content.fragment.template`: Mallar för innehållsfragment bör skapa fragmentmodeller som ersätter fragmentmallarna.
   * Mallar för innehållsfragment finns på följande platser:
      * Innehållsfragmentmallar som ligger utanför ramarna lagras i `/libs/settings/dam/cfm/templates`
      * De kan överlappas av  `/apps/settings/dam/cfm/templates`  eller  `/conf/.../settings/dam/cfm/templates`(... = global eller &quot;tenant&quot;)
* `translation.dictionary`: `I18n` lexikon som finns under `/apps`.
   * `/apps` är oföränderlig vid körning och translator.html är inte längre tillgänglig i AEM som en molntjänst.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="Genomförande"
>abstract="Det klassiska användargränssnittet är inte längre tillgängligt i AEM as a Cloud Service och standardgränssnittet för redigering är det användargränssnitt som har stöd för pekfunktioner. Det bästa sättet är att flytta alla gränssnitt som inte stöds och länkade anpassningar bör anpassas till nyare funktioner som är kompatibla med AEM as a Cloud Service. Kunderna kan använda den befintliga AEM Moderniseringssviten för att minska den ansträngning som krävs för att modernisera AEM Sites implementeringar."
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM Modernization Tools"

* Det klassiska användargränssnittet är inte längre tillgängligt på AEM as a Cloud Service. Standardgränssnittet för redigering är det pekaktiverade gränssnittet.
* Om du förlitar dig på äldre anpassade komponenter kan underhållskostnaderna öka med tiden.
* Mallar för innehållsfragment ersätter modeller för innehållsfragment i AEM 6.3. När du migrerar innehållsfragment som är baserade på äldre mallar till AEM as a Cloud Service bevaras dessa fragment som funktionella, men det går inte att skapa fragment som är baserade på den äldre mallen. Det går inte heller att leverera dessa fragment med AEM GraphQL, som kräver Content Fragment-modeller som scheman.
* /apps är oföränderlig vid körning och translator.html är inte längre tillgänglig i AEM som en molntjänst. Således `I18n` Ordlistor måste komma från Git via CI/CD-flödet.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="Verktyg och resurser"
>abstract="Med hjälp av AEM Modernization Suite kan kunderna konvertera klassiska (ExtJS) dialogrutor till koralldialogrutor. Avsikten är att hjälpa kunderna att gå över från funktioner som inte stöds eller äldre till robusta, moderna AEM. Dessa verktyg är konfigurerbara, konfigureringsmedvetna och utökningsbara. Utforska även att ersätta anpassade komponenter med en uppsättning standardkomponenter för att snabba upp utvecklingstiden och minska underhållskostnaderna för dina program."
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="Komponentkonverterare"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction" text="Kärnkomponenter"

* Om du vill minska ansträngningarna för att modernisera dina AEM Sites-implementeringar använder du [AEM Moderniseringsverktyg](https://opensource.adobe.com/aem-modernize-tools/). Bland dessa verktyg finns konvertering av:
   * Klassiska (ExtJS) dialogrutor till koralldialogrutor
   * Foundation-komponenter till Core-komponenter
   * Statiska mallar och kolumnkontroll till redigerbara mallar och responsivt rutnät
   * Designa och utforma dialogrutor till redigerbara mallprofiler
* Granska projektets anpassade komponentbibliotek och överför om möjligt till uppsättningen standardiserade [Kärnkomponenter](https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction) för att snabba upp utvecklingstiden och minska underhållskostnaderna för dina program.
* Skapa Content Fragment-modeller med funktioner som motsvarar de gamla mallarna och använd dessa modeller för att skapa innehållsfragment i framtiden. Se [Modeller för innehållsfragment](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/content-fragments/content-fragments-models) för mer information.
* `I18n` Ordlistor måste komma från Git via CI/CD-flödet. [Dokumentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#apps-libs-immutable)
* Kontakta [AEM](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för förtydliganden eller för att ta itu med frågor.
