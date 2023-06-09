---
title: OAUI
description: Hjälpsida för mönsteravkännarkod
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# OAUI {#oaui}

OAuth-användarinstans

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth-användarinstans"
>abstract="OAUI-kod identifierar mönstret där det finns minst en OAuth-relaterad konfigurerad användare som kräver korrekt migrering. OAuth är konfigurerad för användare när det finns en undernod med namnet oauth direkt under en rep:AuthorizableId-nod i formatet /home/user-path/user-node/oauth"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - versionsinformation"

`OAUI` identifierar mönstret där det finns minst en OAuth-relaterad konfigurerad användare som kräver korrekt migrering.

OAuth är konfigurerad för användare när det finns en undernod med namnet `oauth` direkt under `rep:AuthorizableId` nod i form av `/home/user-path/user-node/oauth`.

Ett exempel är: `/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Externa användare som konfigurerats med OAuth kan inte logga in på författare-/publiceringsinstanser förrän de har konfigurerats om enligt proceduren nedan.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="Implementeringsvägledning"
>abstract="Externa användare som konfigurerats med OAuth kan inte logga in på författare-/publiceringsinstanser förrän de har konfigurerats om så att de är kompatibla med AEM as a Cloud Service. AEM as a Cloud Service har endast stöd för IMS-autentisering för författare, administratörer och utvecklare samt SAML-baserad integration för publiceringsmiljöerna. Kontakta Adobe Support för hjälp och förtydliganden"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/ims-support.html" text="IMS-stöd - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/personalization/user-and-group-sync-for-publish-tier.html?lang=en#integration-with-an-idp" text="SAML-integrering - publicera"

* Kontakta din Adobe-representant för att diskutera olika alternativ för migrering av användare.
* Kontakta [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller ta itu med frågor.
