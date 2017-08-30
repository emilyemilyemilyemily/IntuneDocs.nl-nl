---
title: Multi-Factor Authentication voor Intune-apparaatinschrijving
titleSuffix: Intune on Azure
description: Hoe u in Azure AD Multi-Factor Authentication vereist voor apparaatregistratie.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: 4789f94d06f61219dea3faa64a4ed0c59afcd56b
ms.sourcegitcommit: af013af8d9a63c9aa16e5e9eddf38ad9c5a77898
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Meervoudige verificatie voor apparaatinschrijvingen in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune kan Multi-Factor Authentication (MFA) in Azure Active Directory (AD) gebruiken voor apparaatregistraties om u te helpen uw zakelijke resources te beveiligen.

MFA vereist twee of meer van de volgende verificatiemethoden:

- Iets dat u weet (doorgaans een wachtwoord of pincode).
- Iets dat u hebt (een vertrouwd apparaat dat moeilijk kan worden gedupliceerd, zoals een telefoon).
- Iets van u (biometrisch, zoals een vingerafdruk).

MFA wordt ondersteund voor apparaten met iOS, Android, Windows 8.1 of hoger, Windows Phone 8.1 of hoger en Windows 10 Mobile of hoger.

Als u MFA inschakelt, moeten eindgebruikers twee soorten referenties opgegeven om een apparaat te registreren.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune configureren zodat Multi-Factor Authentication wordt vereist bij het registreren van apparaten

Voer de volgende stappen uit om MFA te vereisen wanneer een apparaat wordt geregistreerd:

>[!Important]
>Configureer geen **op het apparaat gebaseerde toegangsregels** voor Microsoft Intune-registratie.

1. Meld u met uw referenties aan bij uw [Microsoft Azure Portal](https://portal.azure.com).
2. Kies in de portal **Azure Active Directory**.
2. Kies in **Azure Active Directory** **Beheren** > **Bedrijfstoepassingen**.
3. Kies in **Bedrijfstoepassingen** **Beheren** > **Alle toepassingen**. U ziet een overzicht van alle Azure-apps die u beheert.
3. Kies **Microsoft Intune-inschrijving** in de lijst.
4. Kies onder **Microsoft Intune-inschrijving** **Beveiliging** > **Voorwaardelijke toegang**.
5. Kies **Nieuw beleid**.
6. Typ onder **Nieuw** beleid een beschrijvende naam voor het beleid.
7. Kies in de sectie **Toewijzingen** **Gebruikers en groepen**.
8. Kies onder **Gebruikers en groepen** de gebruikers of groepen waarop dit beleid van toepassing is en kies vervolgens **Gereed**.
9. Kies **Cloud-apps** in de sectie **Toewijzingen**.
10. Kies op het tabblad **Opnemen** onder **Cloud-apps** de optie **Apps selecteren** en kies vervolgens **Selecteren** > **Microsoft Intune-inschrijving**. Klik ten slotte op **Gereed**.
11. Kies in de sectie **Toewijzingen** de optie **Voorwaarden**.
12. U hoeft onder **Voorwaarden** geen instellingen voor MFA te configureren.
13. Kies in de sectie **Besturingselementen voor toegang** de optie **Verlenen**.
14. Kies onder **Verlenen** **Toegang verlenen** en selecteer vervolgens **Meervoudige verificatie vereisen**.
    Selecteer niet **Vereisen dat het apparaat moet worden gemarkeerd als compatibel**, omdat de compatibiliteit van het apparaat niet kan worden gecontroleerd totdat het is ingeschreven.
15. Kies **Selecteren**.
16. Kies onder **Nieuw beleid** **Beleid inschakelen** > **Aan** en kies vervolgens **Maken**.



## <a name="next-steps"></a>Volgende stappen

Als eindgebruikers hun apparaat inschrijven, moeten ze zich nu met een tweede vorm van identificatie, zoals een pincode, een telefoonnummer of biometrische gegevens, verifiëren.