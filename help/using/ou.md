---
title: OU
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 6ec96fab-dd6e-46af-864f-05dad387cbb6
source-git-commit: b77a168fc8c075e8e41149a38df4d83fd2504a14
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# OU {#ou}

Inaktuell användning

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ou_overview"
>title="Inaktuell användning"
>abstract="OU identifierar den situation där vissa JCR-noder, som Sling- eller AEM-komponenter eller API OSGi-exporter, ändras eller tas bort på ett icke-kompatibelt sätt. Kunden kanske inte känner till denna förändring innan uppgraderingen. De kan uppgraderas till en version som inte är kompatibel eller inte vara tillgängliga alls."
>additional-url="https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="Betydande ändringar - AEM as a Cloud Service"

`OU` Identifierar situationen där vissa JCR-noder, som Sling- eller AEM-komponenter eller API OSGi-exporter, ändras eller tas bort på ett icke-kompatibelt sätt. Kunden kanske inte känner till denna förändring innan uppgraderingen. De kan uppgraderas till en version som inte är kompatibel eller inte vara tillgängliga alls.

Eftersom de gamla versionerna inte installeras som standard kanske kundapplikationen inte fungerar som den ska.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Funktionen som är beroende av komponenter som använder inaktuella komponenter eller API:er kan brytas och kanske inte kan matchas korrekt efter en uppgradering.
* Vissa funktioner i kundprogrammet eller vissa AEM kanske inte fungerar som de ska eller kanske inte är aktiva efter en uppgradering.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ou_guidance"
>title="Genomförande"
>abstract="Det bästa sättet är att granska och anpassa kundkoden så att den använder den senaste versionen av AEM eller API:er. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience Manager SDK API"
>additional-url="https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Kortsiktig: Installation av ett kompatibilitetspaket kan vara till hjälp.
* Långsiktigt: Anpassa kundkoden så att den använder den senaste versionen av AEM eller API:er.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
