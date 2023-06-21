---
title: DG
description: Hjälpsida för mönsteravkännarkod
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 1%

---

# DG {#dg}

Utvecklarriktlinje

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="Riktlinjer för utvecklare"
>abstract="DG-kod identifierar avvikelser från valda utvecklingsriktlinjer för AEM 6.5 och AEM as a Cloud Service. Om du följer vedertagna standarder kan du förbättra systemets underhålls- och prestanda. Även om vissa av dessa avvikelser kanske inte är något problem i andra programsammanhang, inklusive i tidigare versioner av AEM, kan de orsaka problem när de används med AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM - riktlinjer och bästa praxis"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="Utvecklingsriktlinjer för AEM as a Cloud Service"


`DG` identifierar avvikelser i valda utvecklingsriktlinjer för [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html) och [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html). Om du följer vedertagna standarder kan du förbättra systemets underhålls- och prestanda. Även om vissa av dessa avvikelser kanske inte är något problem i andra programsammanhang, inklusive i tidigare versioner av AEM, kan de orsaka problem när de används med AEM as a Cloud Service.

Undertyper används för att identifiera olika typer av identifierade överträdelser:

* `java.io.inputstream`: Användning av `java.io.InputStream` i programkod.
* `maintenance.task.configuration`: Konfigurationen av en viss periodisk underhållsaktivitet.
* `sling.commons.scheduler`: Användning av API:t för Sling Commons Scheduler för en schemalagd aktivitet.
* `unsupported.asset.api`: Användning av Asset Manager-API:er som inte stöds i programkoden.
* `javax.jcr.observation.EventListener`: Användning av händelseavlyssnare i programkod.

## Möjliga konsekvenser och risker {#implications-and-risks}

* `java.io.inputstream`
   * Direktuppspelning av binära data med `java.io.InputStream` kan förbruka minnesresurser så att prestandan påverkas. Detta beror särskilt på det begränsade minne som finns i behållare som används i AEM as a Cloud Service.

* `maintenance.task.configuration`
   * Vissa underhållsuppgifter som tidigare krävde explicit konfiguration konfigureras och hanteras nu automatiskt inom AEM as a Cloud Service.
   * Konfiguration av underhållsaktiviteter i AEM as a Cloud Service måste flyttas till källkontrollen.

* `sling.commons.scheduler`
   * Program som är beroende av bakgrundsuppgifter som använder [Schemaläggare för Sling Commons](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) kanske inte fungerar som väntat eftersom körningen inte kan garanteras på AEM as a Cloud Service.
   * AEM riktlinjer för as a Cloud Service utveckling för [bakgrundsuppgifter och tidskrävande jobb](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs) föreslå att koden som körs som en schemalagd aktivitet måste anta att instansen som den körs på när som helst kan tas ned. Därför måste koden vara flexibel och återanvändbar.

* `unsupported.asset.api`
   * Följande API:er för AssetManager har markerats som ej stöds på AEM as a Cloud Service.
      * createAssetForBinary
      * getAssetForBinary
      * removeAssetForBinary
      * createAsset

* `javax.jcr.observation.EventListener`
   * Program som är beroende av händelseavlyssnaren kanske inte fungerar som förväntat eftersom körningen inte kan garanteras.


## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="Implementeringsvägledning"
>abstract="I enlighet AEM utvecklingsriktlinjer och bästa praxis bör kunderna granska sina implementeringar av användningen av Sling Commons Scheduler och strukturera om dem till Sling Jobs, omstrukturera sina systemunderhållsuppgifter, granska strömning av binära data och omfaktorisera koden så att den överensstämmer med AEM as a Cloud Service."
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Försäljningsjobb"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html" text="Underhållsaktiviteter på AEM as a Cloud Service"

* `java.io.inputstream`
   * Använd en direkt binär överföringsmetod där binärfilen läggs till direkt i datalagret.
   * Användningsexempel: [aem-upload](https://github.com/adobe/aem-upload). För andra typer av binärfiler kan anpassad överföringslogik modelleras efter samma mönster.

* `maintenance.task.configuration`
   * Granska AEM as a Cloud Service [Underhållsaktivitet](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html) dokumentation.
   * Se till att [Konfiguration av underhållsaktivitet](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control) är i källkontrollen.

* `sling.commons.scheduler`
   * Ersätt användningen av [Schemaläggare för Sling Commons](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) med [Försäljningsjobb](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)som har en minst en exekveringsgaranti.
   * Långa jobb bör om möjligt undvikas.

* `unsupported.asset.api`
   * Använd inte de API:er för Asset Manager som inte stöds [aem-upload](https://github.com/adobe/aem-upload).

* `javax.jcr.observation.EventListener`
   * I stället för att använda händelseavlyssnaren bör du ändra händelsehanteringsmekanismen till [Försäljningsjobb](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing) eftersom det garanterar behandlingen.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.