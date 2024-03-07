---
title: FORMULÄR
description: Hjälpsida för mönsteravkännarkod
exl-id: ac28760b-b0ab-4082-b7ce-730cddc4ad83
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 0%

---

# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_overview"
>title="FORMS"
>abstract="FORMS kod identifierar potentiella problem med migrering från Adobe Experience Manager Forms till Adobe Experience Manager Forms as a Cloud Service. Granska eventuella konsekvenser och risker som är förknippade med detta och åtgärda dessa problem innan du migrerar till Cloud Servicen."
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-pattern-detection/table-of-contents/forms.html#implications-and-risks" text="Möjliga konsekvenser och risker"

`FORMS` Identifierar potentiella problem relaterade till migrering från [!DNL Adobe Experience Manager Forms] till [!DNL Adobe Experience Manager Form]som [!DNL Cloud Service]. Åtgärda problemen innan du migrerar till [!DNL Cloud Service].

Följande undertyper hjälper dig att identifiera olika typer av problem:

* `modified.feature`: Dessa funktioner, resurser och API:er har uppdaterats eller ändrats för Cloud Service. Innan du migrerar till Cloud Servicen kör du migreringsverktyget för att göra dessa funktioner och resurser kompatibla med Cloud Servicen.
* `unavailable.feature`: Din miljö har funktioner och resurser som inte är tillgängliga eller har tagits bort från Cloud Servicen. Migrera inte sådana funktioner eller resurser till en Cloud Service-miljö.
* `unsupported.feature`: Din miljö använder vissa funktioner som inte stöds på Cloud Servicen. Migrera inte sådana funktioner eller resurser till en Cloud Service-miljö. Om du vill ha information om vilka funktioner som är tillgängliga läser du i månadsversionsinformationen.
* `unsupported.api`: Din miljö har vissa API:er som inte stöds på Cloud Servicen. Inaktivera, ersätt eller ta bort dessa API:er från koden innan du migrerar till Cloud Servicen. Om du vill ha information om vilka funktioner som är tillgängliga läser du i månadsversionsinformationen.

Se [Möjliga konsekvenser och risker](#implications-and-risks) och [Möjliga lösningar](#solutions) för information om ersättningar och andra åtgärder som krävs för att göra vissa funktioner och API:er kompatibla med Cloud Servicen

## Möjliga konsekvenser och risker {#implications-and-risks}

Åtgärda följande problem innan du migrerar till [!DNL Adobe Experience Manager Forms as a Cloud Service]. När de nedan angivna konsekvenserna och riskerna inte åtgärdas fungerar vissa funktioner inte som förväntat i Cloud Servicen.

* Kodredigerarfunktionen för regelredigeraren är inte tillgänglig. (CODE_EDITOR)

* Stöd för e-post (SMTP-port) är inaktiverat som standard. (EMAIL_SERVICE_CONFIGURATION)

* The **[!UICONTROL Email PDF]** Åtgärden Skicka är inte tillgänglig.(EMAIL_PDF_SUBMIT_ACTION)

* XFA-baserad Adaptiv Forms stöds inte ännu. (XFA_BASED_FORM, XDP_BASED_FORM)

* En Skicka-åtgärd anropas omedelbart när formuläret skickas in i stället för att alla signerare ska slutföra signeringen. Det Adobe Sign-avtal PDF som skickas till signerare är därför inte tillgängligt för Skicka åtgärder att använda eller bearbeta. (FORM_SIGN_INTEGRATION)

* Underskriftssteget är inte tillgängligt. (SIGNATURE_STEP)

* Verifieringssteget är inte tillgängligt. (VERIFY_STEP)

* The **[!UICONTROL Submit to Forms Workflow]** Åtgärden Skicka är inte tillgänglig. I AEM 6.5 Forms och tidigare användes åtgärden Skicka för att skicka data med anpassningsbara formulär till äldre AEM Forms i JEE-arbetsflöden och -LiveCyclen Workflow. (LC_WORKFLOW_SUBMISSION)

* Funktionen Interactive Communications är inte tillgänglig.  (FP_PROFILE_INTERACTIVE_COMMUNICATIONS).

* Metadatadragspelspanelen är inte tillgänglig. (METADATA_ACCORDION_FORM_CONTAINER)

* CAPTCHA-komponenten använder nu Google reCAPTCHA-tjänsten som standard för att validera CAPTCHA. Alternativet att använda Adobe Experience Manager för att validera CAPTCHA är föråldrat. (FORMS_CAPTCHA)

* [!DNL AEM Forms] app är inte tillgänglig för [!DNL Cloud Services]. (AEM_FORMS_APP)

* [Dokumenttjänster](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=en#deployment-topology) steg är inte tillgängliga i AEM arbetsflöden. (WORKFLOW_DOCSERVICES)

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_guidance"
>title="Genomförande"
>abstract="Information som visas via FORMS-kod kan ge vägledning om ersättningar och andra åtgärder som krävs för att göra vissa funktioner och API:er kompatibla med Cloud Servicen. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Stöd för Experience Cloud"

* Använd migreringsverktyget för att konvertera alla regelskript i miljön till återanvändbara funktioner. Du kan använda de återanvändbara funktionerna med redigeraren för visuell regel för att fortsätta hämta resultat som erhållits med regelskript. (CODE_EDITOR)

* Kontakta supportteamet för att aktivera e-postfunktioner (öppna SMTP-porten) för din miljö. Endast utgående HTTP- och HTTPS-anslutningar är aktiverade som standard. (EMAIL_SERVICE_CONFIGURATION, e-poststeg)

* Använd **[!UICONTROL Email]** Skicka åtgärd i stället för **[!UICONTROL Email PDF]**. The **[!UICONTROL Email]** Skicka åtgärd innehåller alternativ för att skicka bilagor och bifoga DoR (Document of Record) med e-post. (EMAIL_PDF_SUBMIT_ACTION)

* Skickade data innehåller Adobe Sign Agreement ID. Du kan använda Sign Agreement ID för att hämta ett Sign-avtal PDF, om det behövs.  (FORM_SIGN_INTEGRATION)

* Ta bort signatursteget från ett befintligt anpassat formulär. Konfigurera ditt adaptiva formulär att använda [signeringsupplevelse i webbläsaren](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684). Här visas Adobe Sign-avtal som signerar avtalet i webbläsaren när ett anpassat formulär skickas. Signering i webbläsaren ger en snabbare signeringsupplevelse och sparar tid åt signeraren. (SIGNATURE_STEP)

* Ta bort verifieringssteget från din befintliga adaptiva Forms innan du flyttar sådana formulär till en [!DNL Cloud Service] miljö. (VERIFY_STEP)

* Ändra dina befintliga anpassningsbara formulär så att de kan användas [Skicka till REST-slutpunkt](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint), [Skicka e-post](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email), [Skicka med formulärdatamodell](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model)och [Anropa ett AEM](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow) Skicka åtgärder.

* Du kan utveckla ett AEM arbetsflöde och ändra befintliga anpassningsbara formulär så att de kan användas [AEM](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow) Skicka åtgärd för att skicka data till ett AEM arbetsflöde i stället för att använda **[!UICONTROL Submit to Forms Workflow]** Skicka åtgärd. Du kan utveckla en anpassad Skicka-åtgärd för att skicka data, bilagor eller DoR-filer (Document of Record) till en LiveCycle-process i stället för att använda [!UICONTROL Submit to Forms Workflow]. (LC_WORKFLOW_SUBMISSION)

* Information om tillgängligheten av funktionen Interaktiv kommunikation finns i månadsversionsinformationen. Migrera inte dina interaktiva Cloud Service, brev och relaterade ordlistor till en textmiljö förrän funktionen inte är tillgänglig. (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* Det finns ingen ersättning för metadatadragspelspanelen. Ta bort det från formulären innan du migrerar dem till Cloud Servicen.(METADATA_ACCORDION_FORM_CONTAINER)

* Använd Google reCaptcha i stället för den CAPTCHA-tjänst som tillhandahålls av Adobe Experience Manager. (FORMS_CAPTCHA)

* Migrera inte en AEM arbetsflödesmodell som använder ett Document Services-arbetsflödessteg. Migrera inte och uppdatera inte heller Adaptive Forms som skickar användardata till en arbetsflödesmodell som använder Document Services-arbetsflödessteg, eller ändra Skicka-åtgärden till en [stöds en](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html) innan formuläret migreras. (WORKFLOW_DOCSERVICES)

* Adaptiv Forms har en responsiv design. Dessa formulär ändrar utseende, design och interaktivitet baserat på den underliggande enheten. Du kan fortsätta använda Adaptiv Forms på en mobil enhet. Leta efter månadsversionsinformation för information om tillgängligheten för [!DNL AEM Forms] app. (AEM_FORMS_APP)

* Stöd för XFA-baserad Adaptive Forms finns inte direkt tillgängligt. Om du tänker använda XFA-baserad Adaptive Forms kontaktar du Adobe Support med information om ditt användningsfall och specifika krav.(XFA_BASED_FORM, XDP_BASED_FORM)

Nå ut till [Stöd för Adobe](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
