---
# required metadata

title: Mobiele apparaten inschrijven en een app installeren | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mobiele apparaten inschrijven en een app installeren
Als u het beheer van mobiele apparaten met Intune wilt instellen, moet u eerst de instantie voor het beheer van mobiele apparaten instellen, beheer voor apparaatplatforms inschakelen en vervolgens uw apparaten registreren met de bedrijfsportal-app. Vervolgens kunt u de Microsoft Skype-toepassing implementeren die u in stap 6 hebt gepubliceerd.

## Apparaatbeheer inschakelen en apparaten inschrijven

1.  **Intune als de  instantie voor het beheer van mobiele apparaten instellen**
    Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Beheerder** > **Beheer van mobiele apparaten** en klik onder **Taken** op **MDM-instantie instellen**.  Klik in het dialoogvenster MDM-instantie op **Ja**.
    ![Beheerconsole. MDM instellen op Intune](./media/mdmAuthority.png)

2.  **MDM inschakelen voor uw apparaatplatform**
    Schakel beheer van mobiele apparaten in voor het apparaatplatform dat u wilt beheren. Afhankelijk van uw platform zijn er andere vereisten van toepassing:

    -   **iOS en Mac OS X**: zie [iOS- en Mac-beheer instellen met Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone**: zie [Windows Phone-beheer instellen met Microsoft Intune](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **Android**: op mobiele apparaten met Android kunnen gebruikers zich inschrijven via de bedrijfsportal-app, die beschikbaar is via [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider). Er is geen aanvullende configuratie in Intune vereist.

3.  **Apparaten inschrijven**:

    -   **Android** installeer de app **Intune-bedrijfsportal** van Microsoft Corporation via [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) en meld u aan met de Intune-gebruikersreferenties die hierboven staan vermeld.

    -   **iOS en Mac OS X**: installeer de app **Microsoft Intune-bedrijfsportal** van Microsoft Corporation via de App Store en meld u aan met de Intune-gebruikersreferenties die hierboven staan vermeld. Geef **Ingeschreven apparaten** weer om uw apparaat toe te voegen.

    -   **Windows Phone 8.1**: gebruikers installeren de app **Bedrijfsportal** van Microsoft Corporation via de Windows Phone Store en melden zich aan met de Intune-gebruikersreferenties die hierboven staan vermeld.  Geef **Ingeschreven apparaten** weer om uw apparaat toe te voegen.

    -   **Windows Phone 8.0**: gebruikers kiezen **Systeeminstellingen** &gt; **Bedrijfsapps** en melden zich aan met de Intune-gebruikersreferenties die hierboven staan vermeld. De app Bedrijfsportal wordt op uw telefoon geïmplementeerd.

    Als u wordt gevraagd om een **serveradres**op te geven, voert u ‘manage.microsoft.com’ in.

## Een app installeren op een ingeschreven apparaat
In [stap 6](start-with-a-paid-subscription-to-microsoft-intune-step-6.md) van deze snelstartgids hebt u de Skype-app gepubliceerd naar uw aangepaste Intune-gebruikersgroep. Nu gaat u die app installeren op een apparaat dat zojuist is ingeschreven.

Open de bedrijfsportal op het ingeschreven mobiele apparaat, kies **Apps** en installeer **Microsoft Skype**.

Zie [Voorbereidingen voor het inschrijven van apparaten bij Microsoft Intune](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) voor meer informatie over het beheer van mobiele apparaten met [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]..


### Volgende stappen
Gefeliciteerd. U hebt zojuist de laatste stap van de *Snelstartgids voor Intune* voltooid. Nu de eerste configuratie is voltooid, kunt u overwegen om aanvullende MDM-functionaliteit in te schakelen.

>[!div class="step-by-step"]

>[&larr; **Apparaten inschrijven**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Taken na configuratie** &rarr;](.\post-configuration-tasks.md)  


<!--HONumber=May16_HO1-->

