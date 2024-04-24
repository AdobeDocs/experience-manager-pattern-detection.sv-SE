---
title: INS
description: Hjälpsida för Mönsteravkännarkod.
exl-id: d89e1589-3195-4b2d-98f4-136bedaecb0b
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---

# INS {#ins}

Ogiltigt namnutrymme

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_overview"
>title="Ogiltigt namnutrymme"
>abstract="INS identifierar namnutrymmesproblem AEM instansen"

`INS`  (Ogiltigt namnutrymme) Identifierar namnutrymmesproblem i AEM.

Undertyper används för att identifiera olika typer av information, som:

* `uri`: Identifiera den ogiltiga namnområdes-URI:n i AEM.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Det går inte att replikera innehåll (över hela nivån) eller kopiera innehåll (över hela nivån) `env`, genom `/crx/packMgr`, eller innehållskopia).

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_guidance"
>title="Genomförande"
>abstract="Kontakta kundtjänst om du behöver hjälp."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Korrigera namnutrymmesdefinitioner enligt [JCR-specifikation](https://developer.adobe.com/experience-manager/reference-materials/spec/jcr/1.0/4.5_Namespaces.html). Följ de här stegen [här](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/how-can-i-delete-a-namespace-created-in-crx/td-p/225163)
* Kontakta [Experience Manager kundtjänstteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för klargöranden eller för att bemöta farhågor.
