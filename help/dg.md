---
title: DG
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# DG {#dg}

Utvecklarriktlinje

## Bakgrund {#background}

`DG` identifierar avvikelser från valda utvecklingsriktlinjer för  [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html) och  [AEM som en Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html). Om du följer vedertagna standarder kan du förbättra systemets underhålls- och prestanda. Även om vissa av dessa avvikelser kanske inte är något problem i andra programsammanhang, inklusive i tidigare versioner av AEM, kan de orsaka problem när de används med AEM som Cloud Service.

Undertyper används för att identifiera olika typer av identifierade överträdelser:

* `java.io.inputstream`: Användning av  `java.io.InputStream` i programkod.
* `maintenance.task.configuration`: Konfigurationen av en viss periodisk underhållsaktivitet.
* `sling.commons.scheduler`: Användning av API:t för Sling Commons Scheduler för en schemalagd aktivitet.

## Möjliga konsekvenser och risker {#implications-and-risks}

* `java.io.inputstream`
   * Direktuppspelning av binära data med `java.io.InputStream` kan förbruka minnesresurser så att prestandan påverkas. Detta beror särskilt på det begränsade minne som finns i behållare som används i AEM som Cloud Service.

* `maintenance.task.configuration`
   * Vissa underhållsåtgärder som tidigare krävde explicit konfiguration konfigureras och hanteras automatiskt i AEM som en Cloud Service.
   * Konfiguration av underhållsaktiviteter i AEM som en Cloud Service måste flyttas till källkontrollen.

* `sling.commons.scheduler`
   * Program som är beroende av bakgrundsuppgifter som använder [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) kanske inte fungerar som förväntat eftersom körningen inte kan garanteras i AEM som en Cloud Service.
   * AEM som riktlinjer för utveckling av Cloud Service för [bakgrundsuppgifter och tidskrävande jobb](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs) tyder på att koden som körs som en schemalagd aktivitet måste anta att instansen som den körs på när som helst kan tas bort. Därför måste koden vara flexibel och återanvändbar.

## Möjliga lösningar {#solutions}

* `java.io.inputstream`
   * Använd en direkt binär överföringsmetod där binärfilen läggs till direkt i datalagret.
   * Använd [aem-upload](https://github.com/adobe/aem-upload) för användningsfall för resurser. För andra typer av binärfiler kan anpassad överföringslogik modelleras efter samma mönster.

* `maintenance.task.configuration`
   * Granska AEM som Cloud Service [Underhållsaktivitet](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html) dokumentation.
   * Kontrollera att [konfigurationen av underhållsaktiviteten](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control) är i källkontrollen.

* `sling.commons.scheduler`
   * Ersätt [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) med [Sling Jobs](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing), som har en minst en körningsgaranti.
   * Långa jobb bör om möjligt undvikas.

* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
