---
title: Déployer des Salles Microsoft Teams avec Office 365 ProPlus
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer des Salles Microsoft Teams avec Office 365.
ms.openlocfilehash: f54e7f7e201127b0a61c99f09fee2084378dbbd9
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503711"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Déployer des Salles Microsoft Teams avec Office 365 ProPlus

Lisez cette rubrique pour plus d’informations sur la façon de déployer des Salles Microsoft Teams avec Office 365.

## <a name="requirements"></a>Conditions requises

Avant de déployer Salles Microsoft Teams avec Office 365, assurez-vous que vous avez satisfait à la exigences. Pour plus d’informations, [voir la Salles Microsoft Teams requise](requirements.md).

### <a name="add-a-resource-account"></a>Ajouter un compte de ressource

1. Connecter à Exchange Online PowerShell. Pour obtenir des instructions à [ce Connecter, voir Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. Dans Exchange Online PowerShell, créez une boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante. Par défaut, les boîtes aux lettres de salle n’ont pas de comptes associés. Vous devrez ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier.

   - Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

     - Nom : Salle de conférence 01

     - Alias : ConferenceRoom01

     - Compte : ConferenceRoom01@contoso.com

     - Mot de passe de compte : P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple active le compte de la boîte aux lettres de salle existante qui possède la valeur d’alias ConferenceRoom02 et définit le mot de passe sur 9898P@$$W 0rd.

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Pour plus d’informations sur la syntaxe et les paramètres, voir [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :

   - AutomateProcessing : autoaccept (la boîte aux lettres effectue automatiquement une décision de réservation de salle directement sans intervention humaine).

   - AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)

   - DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)

   - SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)

   - RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion initiale reste tel que spécifié.)

   - AddAdditionalResponse : $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - Réponse supplémentaire : « Il s’agit d’Microsoft Teams salle de réunion ! » (Texte supplémentaire à ajouter à la demande de réunion.

   Cet exemple configure ces paramètres sur la boîte aux lettres de salle Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).
   
4. Connecter sur MS Online PowerShell définissez les valeurs Active Directory en exécutant l'$cred powershell « Connecter-MsolService -Credential $cred ». Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge. 

5. Nous vous encourageons vivement à désactiver l’expiration des mots de passe salles Teams comptes. Voici un exemple de la désactivation de l’expiration du mot de passe pour le compte ConferenceRoom01 :

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. Le compte de ressource doit avoir une licence Office 365 valide pour se connecter à Microsoft Teams. Vous devez également affecter un emplacement d’utilisation à votre compte d’appareil, ce qui détermine les S SKD de licence disponibles pour votre compte. Vous pouvez l’utiliser `Get-MsolAccountSku` pour récupérer la liste des S SKUs disponibles pour votre Office 365 client. Vous pouvez ajouter une licence à l’aide de l’cmdlet `Set-MsolUserLicense` .

   Cet exemple affecte la licence Salle de réunion utilisateur à un utilisateur basé aux États-Unis.

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   Pour obtenir des instructions détaillées, voir [Attribuer des licences à des comptes d’utilisateurs Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).


## <a name="validate"></a>Validate

Pour validation, vous devez être en mesure d’utiliser n’importe quel client Microsoft Teams pour vous connectez au compte que vous avez créé.

## <a name="see-also"></a>Voir aussi
[Mettre à jour les boîtes aux lettres de salle avec des métadonnées supplémentaires pour fournir une meilleure expérience de recherche et de suggestion de salle](/powershell/module/exchange/set-place)

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Déployer les Salles Microsoft Teams](rooms-deploy.md)

[Configurer une console des salles Microsoft Teams](console.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Salles Microsoft Teams licences](rooms-licensing.md)
