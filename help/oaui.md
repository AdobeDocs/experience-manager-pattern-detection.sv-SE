---
title: OAUI
description: Hjälpsida för mönsteravkännarkod
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# OAUI {#oaui}

OAuth-användarinstans

## Bakgrund {#background}

`OAUI` identifierar mönstret där det finns minst en OAuth-relaterad konfigurerad användare som kräver korrekt migrering.

OAuth är konfigurerad för användare när det finns en undernod med namnet `oauth` direkt under en `rep:AuthorizableId`-nod i formatet `/home/user-path/user-node/oauth`.

Ett exempel är: `/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`.

## Möjliga konsekvenser och risker {#implications-and-risks}

* Externa användare som konfigurerats med OAuth kan inte logga in på författare-/publiceringsinstanser förrän de har konfigurerats om enligt proceduren nedan.

## Möjliga lösningar {#solutions}

* Kontakta din Adobe-representant för att diskutera olika alternativ för migrering av användare.
* Kontakta vårt [AEM supportteam](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) för att få klargöranden eller för att ta itu med frågor.
