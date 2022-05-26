---
title: UMI
description: Hjälpsida för mönsteravkännarkod
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: b19818f3f043641328b68adfe37a9c9cb09d1143
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# UMI {#umi}

Fel vid felkonfiguration av uppgradering

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="Fel vid felkonfiguration av uppgradering"
>abstract="UMI identifierar ändringar i vissa OSGi-konfigurationer som kan orsaka problem vid uppgradering, inklusive en misslyckad uppgradering eller reducerad funktionalitet."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="Betydande ändringar - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - versionsinformation"

`UMI` identifierar ändringar i vissa OSGi-konfigurationer som kan orsaka problem vid uppgradering, inklusive en misslyckad uppgradering eller reducerad funktionalitet.

Följande konfigurationer kontrolleras för ändring:
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`

## Möjliga konsekvenser och risker {#implications-and-risks}

* Om du ändrar eller tar bort konfigurationer kan det orsaka följande problem:
   * Uppgraderingen kan fastna (till exempel `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` saknades men fanns i `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`).
   * Behörighetsproblem kan uppstå efter uppgradering (`org.apache.sling.engine.impl.auth.SlingAuthenticator`).
   * Vissa funktioner kanske inte fungerar som de ska. Till exempel ändra `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` kan leda till att vissa JSP-filer inte kompileras, vilket i slutänden leder till funktionsförlust.
   * Värdena för externaliserarkonfigurationen `com.day.cq.commons.impl.ExternalizerImpl` anges av miljövariabler i molnhanteraren i AEM as a Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="Implementeringsvägledning"
>abstract="Bästa praxis är att granska dina aktuella konfigurationer och återställa ändringar som gjorts i de angivna konfigurationerna för att undvika framtida uppgraderingsproblem. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Ändra inte eller ta bort de fyra konfigurationer som nämns ovan.
   * Vid följande överträdelse:\
      &quot;Nödvändiga egenskaper för OSGi-konfigurationen &#39;xyz-configuration&#39; saknas: &#39;[egenskap-1,egenskap-2...]&#39;.&quot;\
      Bekräfta om borttagningarna är giltiga eller inte eftersom OSGI-konfigurationerna är OTB och kanske aldrig har ändrats/sparats i OSGi Config Manager.
* Om konfigurationerna har ändrats bör de återställas till sina förväntade värden. Dessa värden anges i `UMI` meddelanden.
* För `com.day.cq.commons.impl.ExternalizerImpl`, se [dokumentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/externalizer.html?lang=en) för att ställa in extern konfigurering med hjälp av miljövariabler för molnhantering i AEM as a Cloud Service.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
