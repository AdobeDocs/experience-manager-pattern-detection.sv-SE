---
title: UMI
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# UMI {#umi}

Fel vid felkonfiguration av uppgradering

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="Fel vid felkonfiguration av uppgradering"
>abstract="UMI identifierar ändringar i vissa OSGi-konfigurationer som orsakar problem vid uppgradering, inklusive en misslyckad uppgradering eller reducerad funktionalitet."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="Betydande ändringar - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - Versionsinformation"

`UMI` Identifierar ändringar i vissa OSGi-konfigurationer som orsakar problem vid uppgradering, inklusive en misslyckad uppgradering eller reducerad funktionalitet.

Följande konfigurationer kontrolleras för ändring:

* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`
* `org.apache.sling.commons.log.LogManager.factory.config` : Identifiera om egenskapen `org.apache.sling.commons.log.file` för de anpassade loggarna pekar på något annat än `logs/error.log`-filen.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Om du ändrar eller tar bort konfigurationer kan det orsaka följande problem:
   * Uppgraderingen kan fastna (till exempel saknas `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` men finns i `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`).
   * Behörighetsproblem kan uppstå efter uppgradering (`org.apache.sling.engine.impl.auth.SlingAuthenticator`).
   * Vissa funktioner kanske inte fungerar som de ska. Om du till exempel ändrar `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` kan det leda till att vissa JSP-filer inte kompileras, vilket i slutänden leder till funktionsförlust.
   * Värdena för Externalizer-konfigurationen `com.day.cq.commons.impl.ExternalizerImpl` anges med miljövariabler för molnhanteraren i AEM as a Cloud Service.
   * AEM som en Cloud Service stöder inte anpassade loggfiler. Loggar som skrivits till loggar med egna namn är inte tillgängliga från AEM as a Cloud Service.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="Genomförande"
>abstract="Det bästa sättet är att granska dina aktuella konfigurationer och återställa ändringar som gjorts i de angivna konfigurationerna för att undvika framtida uppgraderingsproblem. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Ändra inte eller ta bort de fyra konfigurationer som nämns ovan.
   * Om följande överträdelse inträffar:\
     &quot;Nödvändiga egenskaper för OSGi-konfigurationen `xyz-configuration` saknas: [property-1,property-2...].&quot;\
     Bekräfta om dessa borttagningar är berättigade eller inte eftersom OSGI-konfigurationerna är OTB och kanske aldrig har ändrats/sparats i OSGi Config Manager.
* Om konfigurationerna har ändrats bör de återställas till sina förväntade värden. Dessa värden anges i `UMI`-meddelandena.
* Information om `com.day.cq.commons.impl.ExternalizerImpl` finns i [dokumentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developer-tools/externalizer) om hur du ställer in Externalizer-konfigurationen med hjälp av miljövariabler för molnhanteraren i AEM as a Cloud Service.
* För `org.apache.sling.commons.log.LogManager.factory.config` ändrar du OSGI-konfigurationen så att den anpassade loggningsfunktionen skickas till filen `logs/error.log`. Se [dokumentation](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/logs) för att peka på filen `logs/error.log`.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
