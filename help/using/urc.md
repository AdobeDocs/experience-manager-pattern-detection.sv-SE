---
title: URC
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# URC {#urc}

Körningsläget stöds inte

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="Körningsläget stöds inte"
>abstract="URC identifierar användningen av konfigurationer som är baserade på ett körningslägesnamn som inte stöds i AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes" text="Körningslägen som stöds"
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/deploying/overview#runmodes" text="Körningslägen"

`URC` Identifierar användningen av konfigurationer som är baserade på ett körningslägesnamn som inte stöds i AEM as a Cloud Service.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="Genomförande"
>abstract="Bästa praxis är att granska om alla körningslägen som används i programmet stöds. Och se till att de följer riktlinjerna för upplösning i körningsläge"
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#deploying" text="Riktlinjer för upplösning i körläge"

* Namnuppsättningen som kan användas för att köra olika lägen i AEM as a Cloud Service är begränsad.
* Konfigurationer som baseras på körlägesnamn som inte stöds har ingen effekt när de distribueras till AEM as a Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="Verktyg och resurser"
>abstract="Granska WKND-äldre projekt för att förstå hur URC-överträdelser kan göras kompatibla med AEM Cloud Service. Granska också URC-överträdelseexemplet på GitHub för att förstå hur anpassade körlägesbaserade OSGi-konfigurationer kan uppdateras för att följa AEM as a Cloud Service."
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="Exempel på URC-överträdelse - GitHub"

* Granska användningen av den här konfigurationen så att du kan avgöra om det är nödvändigt.
* Byt namn på konfigurationen med något av de [namn på körningsläge](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes) som stöds och följ [riktlinjerna för körningsupplösning](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#runmode-resolution).
* Granska [gammaldags](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)-projekt och förstå hur [URC-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc) kan korrigeras och göras kompatibla med AEM as a Cloud Service.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
