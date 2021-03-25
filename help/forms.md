---
title: FORMULÄR
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: aa44c3ce87496f412191000f1980a7ebbde386cd
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---


# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## Bakgrund {#background}

`FORMS` Identifierar potentiella problem relaterade till migrering från  [!DNL Adobe Experience Manager Forms] till  [!DNL Adobe Experience Manager Form]som en  [!DNL Cloud Service]fil. Åtgärda problemen innan du migrerar till [!DNL Cloud Service].

Följande undertyper hjälper dig att identifiera olika typer av problem:

* `modified.feature`: Dessa funktioner, resurser och API:er har uppdaterats eller ändrats för Cloud Service. Innan du migrerar till Cloud Servicen kör du migreringsverktyget för att göra dessa funktioner och resurser kompatibla med Cloud Servicen.
* `unavailable.feature`: Miljön innehåller funktioner och resurser som inte är tillgängliga eller har tagits bort från Cloud Servicen. Migrera inte sådana funktioner eller resurser till en Cloud Service-miljö.
* `unsupported.feature`: I din miljö används vissa funktioner som inte stöds på Cloud Servicen. Migrera inte sådana funktioner eller resurser till en Cloud Service-miljö. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga.
* `unsupported.api`: Miljön har vissa API:er som inte stöds på Cloud Servicen. Inaktivera, ersätt eller ta bort dessa API:er från koden innan du migrerar till Cloud Servicen. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga.

Se avsnitten [Möjliga konsekvenser och risker](#implications-and-risks) och [Möjliga lösningar](#solutions) för information om ersättningar och andra åtgärder som krävs för att göra vissa funktioner och API:er kompatibla med Cloud Servicen

## Möjliga konsekvenser och risker {#implications-and-risks}

Åtgärda följande problem innan du migrerar till [!DNL Adobe Experience Manager Forms as a Cloud Service]. När de nedan angivna konsekvenserna och riskerna inte åtgärdas fungerar vissa funktioner inte som förväntat i Cloud Servicen.

* Kodredigerarfunktionen för regelredigeraren är inte tillgänglig. (CODE_EDITOR)

* Stöd för e-post (SMTP-port) är inaktiverat som standard. (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL Email PDF]**-åtgärden Skicka är inte tillgänglig.(EMAIL_PDF_SUBMIT_ACTION)

* XFA-baserad Adaptiv Forms stöds inte ännu. (XFA_BASED_FORM, XDP_BASED_FORM)

* En Skicka-åtgärd anropas omedelbart när formuläret skickas in i stället för att alla signerare ska slutföra signeringen. Det Adobe Sign-avtals-PDF som skickas till signerare är därför inte tillgängligt för Skicka åtgärder att använda eller bearbeta. (FORM_SIGN_INTEGRATION)

* Underskriftssteget är inte tillgängligt. (SIGNATURE_STEP)

* Verifieringssteget är inte tillgängligt. (VERIFY_STEP)

* Forms Portal-funktionen och **[!UICONTROL Forms Portal Submit Action]** är inte tillgängliga än. (FORMS_PORTAL_SUBMISSION, FORMS_PORTAL, DRAFT_AUTO_SAVE, DRAFT_SAVE)

* **[!UICONTROL Submit to Forms Workflow]**-åtgärden Skicka är inte tillgänglig. På [!DNL AEM 6.5 Forms] och tidigare versioner användes åtgärden Skicka för att skicka adaptiva formulärdata till äldre [!DNL AEM Forms on JEE]-arbetsflöden och LiveCycle Workflow. (LC_WORKFLOW_SUBMISSION)

* Funktionen Interactive Communications är inte tillgänglig.  (FP_PROFILE_INTERACTIVE_COMMUNICATIONS).

* **[!UICONTROL Save as draft]** och  **[!UICONTROL Auto Save]** en adaptiv formulärfunktion stöds inte för närvarande. (DRAFT_AUTO_SAVE, DRAFT_SAVE)

* Metadatadragspelspanelen är inte tillgänglig. (METADATA_ACCORDION_FORM_CONTAINER)

* CAPTCHA-komponenten använder nu Google reCAPTCHA-tjänsten som standard för att validera CAPTCHA. Alternativet att använda Adobe Experience Manager för att validera CAPTCHA är föråldrat. (FORMS_CAPTCHA)

* [!DNL AEM Forms] är inte tillgängligt för  [!DNL Cloud Services]. (AEM_FORMS_APP)

* [Dokumenttjänststeg är inte ](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=en#deployment-topology) tillgängliga i AEM arbetsflöden. (WORKFLOW_DOCSERVICES)

## Möjliga lösningar {#solutions}

* Använd migreringsverktyget för att konvertera alla regelskript i miljön till återanvändbara funktioner. Du kan använda de återanvändbara funktionerna med redigeraren för visuell regel för att fortsätta hämta resultat som erhållits med regelskript. (CODE_EDITOR)

* Kontakta supportteamet för att aktivera e-postfunktioner (öppna SMTP-porten) för din miljö. Endast utgående HTTP- och HTTPS-anslutningar är aktiverade som standard. (EMAIL_SERVICE_CONFIGURATION, e-poststeg)

* Använd **[!UICONTROL Email]** Skicka åtgärd i stället för **[!UICONTROL Email PDF]**. **[!UICONTROL Email]**-åtgärden Skicka innehåller alternativ för att skicka bilagor och bifoga DoR (Document of Record) med e-post. (EMAIL_PDF_SUBMIT_ACTION)

* Skickade data innehåller Adobe Sign Agreement ID. Du kan vid behov använda signeringsavtals-ID för att hämta en PDF-fil för signeringsavtal.  (FORM_SIGN_INTEGRATION)

* Ta bort signatursteget från ett befintligt anpassat formulär. Konfigurera ditt adaptiva formulär så att du kan använda [signering i webbläsaren](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684). Här visas Adobe Sign-avtal som signerar avtalet i webbläsaren när ett anpassat formulär skickas. Signering i webbläsaren ger en snabbare signeringsupplevelse och sparar tid åt signeraren. (SIGNATURE_STEP)

* Ta bort verifieringssteget från din befintliga adaptiva Forms innan du flyttar sådana formulär till en [!DNL Cloud Service]-miljö. (VERIFY_STEP)

* Ändra dina befintliga adaptiva formulär så att de använder [Skicka till REST-slutpunkt](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint), [Skicka e-post](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email), [Skicka med formulärdatamodell](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model) och [Anropa ett AEM arbetsflöde](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow) Skicka-åtgärder. Forms Portal och Forms Portal Submit Action är inte tillgängliga än. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga. (FORMS_PORTAL_SUBMISSION, FORMS_PORTAL)

* Du kan utveckla ett AEM arbetsflöde och ändra dina befintliga adaptiva formulär så att du kan använda [AEM arbetsflöde](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow) Skicka åtgärd för att skicka data till ett AEM arbetsflöde i stället för att använda åtgärden Skicka. **[!UICONTROL Submit to Forms Workflow]** Du kan utveckla en anpassad Skicka-åtgärd för att skicka data, bilagor eller DoR-filer (Document of Record) till en LiveCycle-process i stället för att använda [!UICONTROL Submit to Forms Workflow]. (LC_WORKFLOW_SUBMISSION)

* Håll ett öga på månadsversionsinformationen om tillgängligheten av funktionen Interaktiv kommunikation. Migrera inte dina interaktiva Cloud Service, brev och relaterade ordlistor till en textmiljö förrän funktionen inte är tillgänglig. (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* Inaktivera alternativen **[!UICONTROL Save as draft]** och **[!UICONTROL Enable Auto Save]** i din adaptiva Forms innan du migrerar dem till Cloud Servicen. Du kan aktivera dessa alternativ när funktionen Forms Portal släpps för Cloud Servicen. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga. (DRAFT_AUTO_SAVE, DRAFT_SAVE)

* Det finns ingen ersättning för metadatadragspelspanelen. Ta bort det från formulären innan du migrerar dem till Cloud Servicen.(METADATA_ACCORDION_FORM_CONTAINER)

* Använd Google reCaptcha i stället för den CAPTCHA-tjänst som tillhandahålls av Adobe Experience Manager. (FORMS_CAPTCHA)

* Adaptiv Forms har en responsiv design. Dessa formulär ändrar utseende, design och interaktivitet baserat på den underliggande enheten. Du kan fortsätta att använda Adaptiv Forms på en mobil enhet samtidigt som du håller ett öga på månadsversionsinformationen för tillgängligheten för [!DNL AEM Forms]-appen. (AEM_FORMS_APP)

* Migrera inte en AEM arbetsflödesmodell som använder ett Document Services-arbetsflödessteg. Migrera inte heller Adaptive Forms som skickar användardata till en arbetsflödesmodell som använder Document Services-arbetsflödessteg eller ändra Skicka-åtgärden till en [som stöds](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html) innan du migrerar formuläret. (WORKFLOW_DOCSERVICES)

* Stöd för XFA-baserad Adaptive Forms finns inte direkt tillgängligt. Om du tänker använda XFA-baserad Adaptive Forms kontaktar du Adobe Support med information om ditt användningsfall och specifika krav.(XFA_BASED_FORM, XDP_BASED_FORM)

Gå till [Adobe Support](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
