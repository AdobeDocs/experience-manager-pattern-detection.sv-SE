---
title: OAUI
description: Hjälpsida för Mönsteravkännarkod.
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: b77a168fc8c075e8e41149a38df4d83fd2504a14
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---

# OAUI {#oaui}

OAuth-användarinstans

## Bakgrund {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth-användarinstans"
>abstract="OAUI-kod identifierar mönstret där det finns minst en OAuth-relaterad konfigurerad användare som kräver korrekt migrering. OAuth är konfigurerad för användare när det finns en undernod med namnet OAuth direkt under en rep:AuthorizableId-nod i formatet /home/user-path/user-node/oauth"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - Versionsinformation"

`OAUI` Identifierar mönstret där det finns minst en OAuth-relaterad konfigurerad användare som kräver korrekt migrering.

OAuth är konfigurerad för användare när det finns en undernod med namnet `oauth` direkt under en `rep:AuthorizableId`-nod i formatet `/home/user-path/user-node/oauth`.

Ett exempel är: `/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Externa användare som konfigurerats med OAuth kan inte logga in på författare-/publiceringsinstanser förrän de har konfigurerats om enligt proceduren nedan.

## Möjliga lösningar {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="Genomförande"
>abstract="Externa användare som konfigurerats med OAuth kan inte logga in på författare-/publiceringsinstanser förrän de har konfigurerats om så att de är kompatibla med AEM as a Cloud Service. AEM as a Cloud Service har endast stöd för IMS-autentisering för författare-, Admin- och Dev-användare och SAML-baserad integration för publiceringsmiljöerna. Kontakta Adobe Support för hjälp eller klargöranden."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/security/ims-support" text="IMS-stöd - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/personalization/user-and-group-sync-for-publish-tier#integration-with-an-idp" text="SAML-integrering - Publish"

* Kontakta din Adobe-representant om du måste diskutera olika alternativ för migrering av användare.
* Kontakta [AEM supportteamet](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller frågor.
