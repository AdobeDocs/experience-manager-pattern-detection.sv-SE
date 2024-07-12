---
title: DG
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# DG {#dg}

Utvecklarriktlinje

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="Riktlinjer för utvecklare"
>abstract="DG-kod identifierar avvikelser i valda utvecklingsriktlinjer för AEM 6.5 och AEM as a Cloud Service. Om du följer vedertagna standarder kan du förbättra systemets underhålls- och prestanda. Även om vissa av dessa avvikelser kanske inte är något problem i andra programsammanhang, inklusive i tidigare versioner av AEM, kan de orsaka problem när de används med AEM as a Cloud Service."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM - riktlinjer och bästa praxis"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service riktlinjer för utveckling"


`DG` Identifierar avvikelser från valda utvecklingsriktlinjer för [AEM 6.5](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices) och [AEM as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines). Om du följer vedertagna standarder kan du förbättra systemets underhålls- och prestanda. Även om vissa av dessa avvikelser kanske inte är något problem i andra programsammanhang, inklusive i tidigare versioner av AEM, kan de orsaka problem när de används med AEM as a Cloud Service.

Undertyper används för att identifiera olika typer av identifierade överträdelser:

* `java.io.inputstream`: Användning av `java.io.InputStream` i programkod.
* `maintenance.task.configuration`: Konfigurationen för en viss periodisk underhållsaktivitet.
* `sling.commons.scheduler`: Användning av API:t för Sling Commons Scheduler för en schemalagd aktivitet.
* `unsupported.asset.api`: Användning av Asset Manager-API:er som inte stöds i programkoden.
* `javax.jcr.observation.EventListener`: Användning av händelseavlyssnare i programkod.
* `custom.guava.cache`: Användning av Guava-cache i programkod.

## Möjliga konsekvenser och risker {#implications-and-risks}

* `java.io.inputstream`
   * Direktuppspelning av binära data med `java.io.InputStream` kan förbruka minnesresurser så att prestandan påverkas. Problemet beror på det begränsade minne som finns i behållare som används i AEM as a Cloud Service.

* `maintenance.task.configuration`
   * Vissa underhållsuppgifter som tidigare krävde explicit konfiguration konfigureras och hanteras nu automatiskt i AEM as a Cloud Service.
   * Konfiguration av underhållsaktiviteter i AEM as a Cloud Service måste flyttas till källkontroll.

* `sling.commons.scheduler`
   * Program som är beroende av bakgrundsuppgifter med [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) kanske inte fungerar som förväntat eftersom körningen inte kan garanteras i AEM as a Cloud Service.
   * Riktlinjer för [bakgrundsuppgifter och långvariga jobb](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#background-tasks-and-long-running-jobs) tyder på att koden som körs som en schemalagd aktivitet också måste anta att instansen som den körs på när som helst kan tas ned. Koden måste därför vara flexibel och återtagbar.

* `unsupported.asset.api`
   * Följande API:er för AssetManager har markerats som ej stöds i AEM as a Cloud Service.
      * createAssetForBinary
      * getAssetForBinary
      * removeAssetForBinary
      * createAsset

* `javax.jcr.observation.EventListener`
   * Program som är beroende av händelseavlyssnaren kanske inte fungerar som förväntat eftersom körningen inte kan garanteras.

* `custom.guava.cache`
   * Användning av Guava Cache kan orsaka prestandaproblem i AEM.


## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="Genomförande"
>abstract="Granska implementeringarna av användningen av Sling Commons Scheduler. Strukturera om dem till Sling Jobs, omstrukturera deras systemunderhållsuppgifter, granska direktuppspelning av binära data och omfaktorisera koden så att den överensstämmer med AEM as a Cloud Service."
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Försäljningsjobb"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/maintenance" text="Underhållsaktiviteter i AEM as a Cloud Service"

* `java.io.inputstream`
   * Använd en direkt binär överföringsmetod där binärfilen läggs till direkt i datalagret.
   * Exempel på resursanvändning finns i [aem-upload](https://github.com/adobe/aem-upload). För andra typer av binärfiler kan anpassad överföringslogik modelleras efter samma mönster.

* `maintenance.task.configuration`
   * Granska dokumentationen för AEM as a Cloud Service [underhållsaktivitet](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/maintenance).
   * Kontrollera att [konfigurationen för underhållsaktiviteten](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/overview#maintenance-tasks-configuration-in-source-control) finns i källkontrollen.

* `sling.commons.scheduler`
   * Ersätt [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) med [Sling Jobs](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing) som har en minst en körningsgaranti.
   * Långvariga jobb bör undvikas.

* `unsupported.asset.api`
   * I stället för att använda API:erna för Asset Manager som inte stöds läser du [aem-upload](https://github.com/adobe/aem-upload).

* `javax.jcr.observation.EventListener`
   * I stället för att använda händelseavlyssnaren rekommenderar vi att du omfaktoriserar händelsehanteringsmekanismen till [Sling Jobs](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing) eftersom den garanterar bearbetningen.

* `custom.guava.cache`
   * Om det behövs bör cacheminnen skapas utanför AEM. Extern cachningslösning kan övervägas.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
