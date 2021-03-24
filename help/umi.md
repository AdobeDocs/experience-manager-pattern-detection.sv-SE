---
title: UMI
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# UMI {#umi}

Fel vid felkonfiguration av uppgradering

## Bakgrund {#background}

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

* Ändra inte eller ta bort de fyra konfigurationer som nämns ovan.
* Om konfigurationerna har ändrats bör de återställas till sina förväntade värden. Dessa värden anges i `UMI`-meddelandena.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
