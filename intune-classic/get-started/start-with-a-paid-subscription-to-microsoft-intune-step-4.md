---
title: Intune-licenties toewijzen | Microsoft Docs
description: Licenties toewijzen aan gebruikers voor uw Intune-abonnement
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 03/28/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 793df9f3734b84c74ecac9b8192d0b06306607e8
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="assign-intune-licenses-to-your-user-accounts"></a>Intune-licenties toewijzen aan uw gebruikersaccounts

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U moet eerst aan elke gebruiker een Intune-licentie toewijzen voordat gebruikers hun apparaten bij Intune kunnen inschrijven, ongeacht of u handmatig gebruikers toevoegt of deze synchroniseert vanuit uw on-premises Active Directory.

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Een Intune-licentie toewijzen in het Office 365-beheercentrum

U kunt de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) gebruiken om handmatig cloudgebruikers toe te voegen en licenties toe te wijzen aan zowel cloudgebruikersaccounts als accounts die vanuit uw on-premises Active Directory zijn gesynchroniseerd met Azure AD.

1.  Meld u bij de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) aan met uw tenantbeheerdersreferenties en selecteer vervolgens **Gebruikers** > **Actieve gebruikers**.

2.  Selecteer het gebruikersaccount waaraan u een Intune-gebruikerslicentie wilt toewijzen en selecteer vervolgens **Productlicenties** > **Bewerken**.

3.  Zet **Intune** of **Enterprise Mobility + Security** op **Aan** en selecteer **Opslaan**.

4. Het gebruikersaccount beschikt nu over de benodigde machtigingen om de service te gebruiken en apparaten in te schrijven bij het beheer.

> [!NOTE]
> Gebruikers worden pas weergegeven in de beheerconsole nadat zij een apparaat hebben ingeschreven. U kunt ook een groep gebruikers in één keer bewerken door de optie voor het toevoegen of vervangen van een licentie voor alle geselecteerde gebruikers te selecteren.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Schoolgegevens synchroniseren gebruiken om licenties toe te wijzen aan gebruikers met Intune for Education
Als uw organisatie een onderwijsinstelling is, kunt u met Schoolgegevens synchroniseren(SDS) licenties voor Intune for Education toewijzen aan gesynchroniseerde gebruikers. Kies het selectievakje Intune for Education tijdens het instellen van uw SDS-profiel.  

![Afbeelding van het instellen van het SDS-profiel](./media/i4e-sds-profile-setup-setting.png)

Als u een licentie voor Intune for Education toewijst, zorg er dan voor dat er ook een Intune A Direct-licentie wordt toegewezen.

![Afbeelding van het instellen van de productlicentie](./media/i4e-set-licenses.png)

Zie [Overzicht van Schoolgegevens synchroniseren](https://support.office.com/en-us/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US) voor meer informatie over SDS.

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>PowerShell gebruiken om EMS-gebruikerslicenties selectief te beheren
In organisaties die gebruikmaken van Enterprise Mobility + Security (voorheen Enterprise Mobility Suite) van Microsoft, werken mogelijk gebruikers die alleen Azure Active Directory Premium of Intune-services in het EMS-pakket nodig hebben. Met [Azure Active Directory PowerShell-cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) kunt u één service of een subset van services toewijzen.

Als u selectief gebruikerslicenties voor EMS-services wilt toewijzen, opent u PowerShell als beheerder op een computer waarop de [Azure Active Directory-module voor Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) is geïnstalleerd. U kunt PowerShell installeren op een lokale computer of op de ADFS-server.

U moet een nieuwe licentie-SKU-definitie maken die alleen van toepassing is op de gewenste serviceplannen. Daarvoor schakelt u de plannen uit die u niet wilt toepassen. U kunt bijvoorbeeld een licentie-SKU-definitie maken waarmee geen licentie voor Intune wordt toegewezen. Typ het volgende om een lijst met beschikbare services weer te geven:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

U kunt de volgende opdracht uitvoeren om het Intune-serviceplan uit te sluiten. Met dezelfde methode kunt u een complete beveiligingsgroep uitbreiden. U kunt echter ook gedetailleerdere filters gebruiken.

**Voorbeeld 1**<br>
Maak een nieuwe gebruiker via de opdrachtregel en wijs een EMS-licentie toe zonder het Intune-gedeelte van de licentie in te schakelen:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Controleer met:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Voorbeeld 2**<br>
Schakel het Intune-gedeelte van de EMS-licentie uit voor een gebruiker aan wie al een licentie is toegewezen:

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Controleer met:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

>[!div class="step-by-step"]

>[&larr; **Gebruikers synchroniseren met Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gebruikers en apparaten organiseren** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  
