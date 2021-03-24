---
title: Forms
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: a6ba6e93c89644160650882ecbf17028bec35068
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 0%

---


# [!DNL FORMS] {#forms}

[!DNL Adobe Experience Manager Forms]

## Bakgrund {#background}

`FORMS` identifierar potentiella problem med migrering från Adobe Experience Manager Forms till Adobe Experience Manager Forms som Cloud Service. Åtgärda dessa problem innan du migrerar till Cloud Servicen.

Följande undertyper hjälper dig att identifiera olika typer av problem:

* `modified.feature`: Dessa funktioner, resurser och API:er har uppdaterats eller ändrats för Cloud Service. Innan du migrerar till Cloud Servicen kör du migreringsverktyget för att göra dessa funktioner och resurser kompatibla med Cloud Servicen.
* `unavailable.feature`: Miljön innehåller funktioner och resurser som inte är tillgängliga eller har tagits bort från Cloud Servicen. Migrera inte sådana funktioner eller resurser till en Cloud Service-miljö.
* `unsupported.feature`: I din miljö används vissa funktioner som inte stöds på Cloud Servicen. Migrera inte sådana funktioner eller resurser till en Cloud Service-miljö. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga.
* `unsupported.api`: Miljön har vissa API:er som inte stöds på Cloud Servicen. Inaktivera, ersätt eller ta bort dessa API:er från koden innan du migrerar till Cloud Servicen. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga.

Se avsnitten [Möjliga konsekvenser och risker](#implications-and-risks) och [Möjliga lösningar](#solutions) för information om ersättningar och andra åtgärder som krävs för att göra vissa funktioner och API:er kompatibla med Cloud Servicen

## Möjliga konsekvenser och risker {#implications-and-risks}

Åtgärda följande problem innan du migrerar till Adobe Experience Manager Forms som Cloud Service. När de nedan angivna konsekvenserna och riskerna inte åtgärdas fungerar vissa funktioner inte som förväntat i Cloud Servicen.

* Kodredigerarfunktionen för regelredigeraren är inte tillgänglig. (CODE_EDITOR)

* Stöd för e-post (SMTP-port) är inaktiverat som standard. (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL Email PDF]**-sändningsåtgärden är inte tillgänglig.(EMAIL_PDF_SUBMIT_ACTION)

* XDP-baserade adaptiva formulär stöds ännu inte. (XDP_BASED_FORM)

* En Skicka-åtgärd anropas omedelbart när formuläret skickas in i stället för att alla signerare ska slutföra signeringen. Det adaptiva signaturdokumentet (Adobe Sign Agreement PDF som skickas till signerare) är därför inte tillgängligt för att skicka åtgärder som ska användas eller bearbetas. (FORM_SIGN_INTEGRATION)

* Underskriftssteget är inte tillgängligt. (SIGNATURE_STEP)

* Verifieringssteget är inte tillgängligt. (VERIFY_STEP)

* Forms Portal-funktionen och **[!UICONTROL Forms Portal submit action]** är inte tillgängliga. Du kan inte använda Forms Portal för att lista formulär, spara utkast eller visa skickade formulär. Du kan inte skicka (använda **[!UICONTROL Forms Portal submit action]**) data som har skickats till ett anpassat formulär till en Forms-portal. [!UICONTROL Save as draft] och  [!UICONTROL Auto Save] en adaptiv formulärfunktion stöds inte för närvarande. (FORMS_PORTAL_SUBMISSION, FORMS_PORTAL, DRAFT_AUTO_SAVE, DRAFT_SAVE)

* **[!UICONTROL Submit to Forms workflow]**-sändningsåtgärden är inte tillgänglig. I AEM 6.5 Forms och tidigare användes inskickningsåtgärden för att skicka adaptiva formulärdata till äldre AEM Forms om JEE-arbetsflöden och LiveCycle Workflow. (LC_WORKFLOW_SUBMISSION)

* Funktionen Interactive Communications är inte tillgänglig.  (FP_PROFILE_INTERACTIVE_COMMUNICATIONS).

* **[!UICONTROL Save as draft]** och  **[!UICONTROL Auto Save]** en adaptiv formulärfunktion stöds inte för närvarande. (DRAFT_AUTO_SAVE, DRAFT_SAVE)

* Metadatadragspelspanelen är inte tillgänglig. (METADATA_ACCORDION_FORM_CONTAINER)

* CAPTCHA-komponenten använder nu Google reCAPTCHA-tjänsten som standard för att validera CAPTCHA. Alternativet att använda Adobe Experience Manager för att validera CAPTCHA är inte tillgängligt. (FORMS_CAPTCHA)

## Möjliga lösningar {#solutions}

* Använd migreringsverktyget för att konvertera alla regelskript i miljön till återanvändbara funktioner. Du kan använda de återanvändbara funktionerna med redigeraren för visuell regel för att fortsätta hämta resultat som erhållits med regelskript. (CODE_EDITOR)

* Kontakta supportteamet för att aktivera e-postfunktioner (öppna SMTP-porten) för din miljö. Endast utgående HTTP- och HTTPS-anslutningar är aktiverade som standard. (EMAIL_SERVICE_CONFIGURATION)

* Använd åtgärden **[!UICONTROL Email]** skicka i stället för **[!UICONTROL Email PDF]**. **[!UICONTROL Email]**-sändningsåtgärden innehåller alternativ för att skicka bilagor och bifoga DoR-filer (Document of Record) med e-post. (EMAIL_PDF_SUBMIT_ACTION)

* Migrera inte XDP-baserade adaptiva formulär till en Cloud Service-miljö. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga. (XDP_BASED_FORM)

* Skickade data innehåller ID för signeringsavtal. Du kan vid behov använda signeringsavtals-ID för att hämta en PDF-fil för signeringsavtal.  (FORM_SIGN_INTEGRATION)

* Ersätt signatursteget i dina anpassade formulär med alternativet att signera ett anpassat formulär efter att det skickats in, i samma fönster. Det hjälper dig att fortsätta tillhandahålla en [signeringsupplevelse i webbläsaren](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684). (SIGNATURE_STEP)

* Ta bort verifieringssteget från dina befintliga adaptiva formulär innan du flyttar sådana formulär till en Cloud Service-miljö. (VERIFY_STEP)

* Det finns inget alternativ till **[!UICONTROL Forms Portal submit action]**. Du kan använda den här skicka-åtgärden när Forms Portal-funktionen har släppts för Cloud Servicen. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga. (FORMS_PORTAL_SUBMISSION, FORMS_PORTAL)

* Det finns ingen alternativ åtgärd för att skicka till **[!UICONTROL Submit to Forms workflow]**-åtgärder. Du kan utveckla en anpassad skicka-åtgärd för att skicka data, bilagor eller DoR-filer (Document of Record) till en LiveCycle-process. (LC_WORKFLOW_SUBMISSION)

* Migrera inte dina interaktiva dokument, brev och relaterade ordlistor till en Cloud Service-miljö. (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* Inaktivera alternativet **[!UICONTROL Save as draft]** och **[!UICONTROL Enable Auto Save]** i dina adaptiva formulär innan du migrerar dem till Cloud Servicen. Du kan aktivera dessa alternativ när funktionen Forms Portal släpps för Cloud Servicen. Håll ett öga på månadsversionsinformationen om vilka funktioner som är tillgängliga. (DRAFT_AUTO_SAVE, DRAFT_SAVE)

* Det finns ingen ersättning för metadatadragspelspanelen. Ta bort det från formulären innan du migrerar dem till Cloud Servicen.(METADATA_ACCORDION_FORM_CONTAINER)

* Använd Google reCaptcha i stället för den CAPTCHA-tjänst som tillhandahålls av Adobe Experience Manager. (FORMS_CAPTCHA)

Gå till [Adobe Support](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
