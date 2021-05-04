---
title: DG
description: Hjälpsida för mönsteravkännarkod
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 1%

---

# DG {#dg}

Utvecklarriktlinje

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="Riktlinjer för utvecklare"
>abstract="DG-kod identifierar avvikelser från valda utvecklingsriktlinjer för AEM 6.5 och AEM som en Cloud Service. Om du följer vedertagna standarder kan du förbättra systemets underhålls- och prestanda. Även om vissa av dessa avvikelser kanske inte är något problem i andra programsammanhang, inklusive i tidigare versioner av AEM, kan de orsaka problem när de används med AEM som Cloud Service."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM - riktlinjer och bästa praxis"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="Utvecklingsriktlinjer för AEM as a Cloud Service"


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

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="Implementeringsvägledning"
>abstract="I enlighet AEM utvecklingsriktlinjer och bästa praxis bör kunderna granska sina implementeringar av användningen av Sling Commons Scheduler och strukturera om dem till Sling Jobs, omstrukturera sina systemunderhållsuppgifter, granska strömning av binära data och omfaktorisera koden så att den uppfyller AEM som en Cloud Service."
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Försäljningsjobb"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html" text="Underhållsaktiviteter i AEM som en Cloud Service"

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
