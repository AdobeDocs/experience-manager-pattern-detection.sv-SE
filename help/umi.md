---
title: UMI
description: Hjälpsida för mönsteravkännarkod
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
translation-type: tm+mt
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---

# UMI {#umi}

Fel vid felkonfiguration av uppgradering

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="Fel vid felkonfiguration av uppgradering"
>abstract="UMI identifierar ändringar i vissa OSGi-konfigurationer som kan orsaka problem vid uppgradering, inklusive en misslyckad uppgradering eller reducerad funktionalitet."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="Betydande ändringar - AEM som en Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM som Cloud Service - Versionsinformation"

`UMI` identifierar ändringar i vissa OSGi-konfigurationer som kan orsaka problem vid uppgradering, inklusive en misslyckad uppgradering eller reducerad funktionalitet.

Följande konfigurationer kontrolleras för ändring:
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`

## Möjliga konsekvenser och risker {#implications-and-risks}

* Om du ändrar eller tar bort konfigurationer kan det orsaka följande problem:
   * Uppgraderingen kan fastna (t.ex. `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` saknades men fanns i `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`).
   * Behörighetsproblem kan uppstå efter uppgradering (`org.apache.sling.engine.impl.auth.SlingAuthenticator`).
   * Vissa funktioner kanske inte fungerar som de ska. Om du till exempel ändrar `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` kan det leda till att vissa JSP-filer inte kompileras, vilket i slutänden leder till funktionsförlust.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="Implementeringsvägledning"
>abstract="Bästa praxis är att granska dina aktuella konfigurationer och återställa ändringar som gjorts i de angivna konfigurationerna för att undvika framtida uppgraderingsproblem. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Ändra inte eller ta bort de fyra konfigurationer som nämns ovan.
* Om konfigurationerna har ändrats bör de återställas till sina förväntade värden. Dessa värden anges i `UMI`-meddelandena.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
