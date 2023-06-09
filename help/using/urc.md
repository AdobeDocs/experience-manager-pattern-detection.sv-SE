---
title: URC
description: Hjälpsida för mönsteravkännarkod
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# URC {#urc}

Runmode-konfigurationen stöds inte

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="Runmode-konfigurationen stöds inte"
>abstract="URC identifierar användningen av konfigurationer som är baserade på ett körningslägesnamn som inte stöds i AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes" text="Körningslägen som stöds"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes" text="Runmodes"

`URC` identifierar användningen av konfigurationer som är baserade på ett körningslägesnamn som inte stöds i AEM as a Cloud Service.

## Möjliga konsekvenser och risker {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="Implementeringsvägledning"
>abstract="Bästa praxis är att granska om alla runmodes som används i programmet stöds och kontrollera att de följer riktlinjerna för upplösning i runmode"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#deploying" text="Riktlinjer för upplösning i körläge"

* Den uppsättning namn som kan användas för körningslägen i AEM as a Cloud Service är begränsad.
* Konfigurationer som baseras på runmode-namn som inte stöds har ingen effekt när de distribueras till AEM as a Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="Verktyg och resurser"
>abstract="Granska WKND-äldre projekt för att förstå hur URC-överträdelser kan göras kompatibla med AEM Cloud Service. Granska också URC-överträdelseexemplet på Github för att förstå hur anpassade runmode-baserade OSGi-konfigurationer kan uppdateras för att följa AEM as a Cloud Service."
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="Exempel på URC-överträdelse - Github"

* Granska användningen av den här konfigurationen för att avgöra om det är nödvändigt.
* Byt namn på konfigurationen så att den använder något av de alternativ som stöds [namn på runmode](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes) och följ [riktlinjer för upplösning av körningsläge](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution).
* Granska [wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc) projekt och förstå hur [URC-överträdelser](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc) kan korrigeras och göras kompatibelt med AEM as a Cloud Service.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
