---
title: Déployer des Salles Microsoft Teams avec Microsoft 365 ou Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur le déploiement d’Salles Microsoft Teams avec Microsoft 365 ou Office 365, où Teams, Skype Entreprise et Exchange sont tous les deux en ligne.
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355643"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Déployer des Salles Microsoft Teams avec Microsoft 365 ou Office 365

Lisez cette rubrique pour plus d’informations sur la manière de déployer Salles Microsoft Teams avec Microsoft 365 ou Office 365, où les Microsoft Teams et Exchange sont tous les deux en ligne.

## <a name="requirements"></a>Conditions requises

Avant de déployer des Salles Microsoft Teams avec Microsoft 365 ou Office 365, assurez-vous que vous avez satisfait aux exigences. Pour plus d’informations, [voir Salles Microsoft Teams requise.](requirements.md)

### <a name="add-a-resource-account"></a>Ajouter un compte de ressource

1. Connecter à Exchange Online PowerShell. Pour obtenir des instructions à [ce Connecter, voir Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Dans Exchange Online PowerShell, créez une boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante. Par défaut, les boîtes aux lettres de salle n’ayant pas de comptes associés, vous devez ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier auprès d’Microsoft Teams.

   - Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

     - Compte : ConferenceRoom01@contoso.com
  
     - Nom : ConferenceRoom01

     - Alias : ConferenceRoom01

     - Mot de passe de compte : P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple active le compte de la boîte aux lettres de salle existante qui possède la valeur d’alias ConferenceRoom02 et définit le mot de passe sur 9898P@$$W 0rd. Notez que le compte sera ConferenceRoom02@contoso.com en raison de la valeur d’alias existante.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Pour plus d’informations sur la syntaxe et les paramètres, voir [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)

3. Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :

   - AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent directement la décision de réservation de salle sans intervention humaine).

   - AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)

   - DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)

   - SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)

   - RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion initiale reste tel que spécifié.)

   - AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - Réponse supplémentaire : « Il s’agit d’Microsoft Teams salle de réunion ! » (Texte supplémentaire à ajouter à la demande de réunion.

   Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommée ConferenceRoom01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Connecter sur MS Online PowerShell pour définir les paramètres Active Directory en exécutant `Connect-MsolService` le Cmdlet PowerShell. Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge.

5. Définissez le mot de passe pour qu’il n’expire jamais à l’aide de la syntaxe suivante :

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Cet exemple définit le mot de passe du ConferenceRoom01@contoso.onmicrosoft.com pour qu’il n’expire jamais.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > Si le mot de passe n’est pas réglé sur Jamais expirer, le compte ne se connecte plus sur l’appareil une fois la période d’expiration atteinte. Le mot de passe devra alors être modifié pour le compte et mis à jour localement le salles Teams. Les utilisateurs ne peuvent pas participer à des réunions le salles Teams l’expiration du mot de passe.

6. Le compte de ressource doit avoir une licence Microsoft 365 ou Office 365 valide, ou Exchange et Microsoft Teams ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte de ressource. Cela détermine les S SKD de licence disponibles pour votre compte. Vous pouvez utiliser `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer la liste des S SKUs disponibles pour Microsoft 365 ou Office 365 organisation comme suit :

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Ensuite, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Cet exemple ajoute la licence Salle de réunion compte :

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Pour obtenir des instructions détaillées, voir Attribuer des licences à des comptes [d’utilisateurs Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Vous pouvez également ajouter Système téléphonique fonctionnalités à ce compte, mais vous devez tout d’abord le configurer. Pour [plus d’Système téléphonique,](../what-is-phone-system-in-office-365.md) voir Qu’est-Système téléphonique ? Cet exemple ajoute le plan Appels nationaux et internationaux PSTN :

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>Validate

Pour validation, vous devez être en mesure d’utiliser n’importe Microsoft Teams client pour vous connectez au compte que vous avez créé.

## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Déployer les Salles Microsoft Teams](rooms-deploy.md)

[Configurer une console des salles Microsoft Teams](console.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Salles Microsoft Teams licences Salles Microsoft Teams licences](rooms-licensing.md)
