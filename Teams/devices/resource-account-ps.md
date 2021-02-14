---
title: Création de comptes de ressources Microsoft Teams pour les barres de collaboration pour Microsoft Teams à l’aide de PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur le déploiement des barres de collaboration pour Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268028"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Créer un compte de ressources Microsoft 365 à l’aide de PowerShell

Lisez cette rubrique pour plus d’informations sur la création de comptes de ressources pour les barres de collaboration pour Microsoft Teams à l’aide de PowerShell.

Pour créer un compte de ressource, le plus simple consiste à utiliser le Centre d’administration Microsoft 365. [Consultez cet article sur la façon de faire.](resource-account-ui.md)

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Conditions requises

Avant de déployer salles Microsoft Teams avec Office 365, assurez-vous que vous avez la qualité requise. Pour plus d’informations, voir [Les barres de collaboration de déploiement de Microsoft Teams.](collab-bar-deploy.md)

- Si vous avez besoin des fonctionnalités PSTN pour la barre de collaboration, vous aurez besoin d’une licence Phone System.

- Vos comptes de ressources doivent avoir des boîtes aux lettres Exchange. Comme il s’agit de comptes de ressources, aucune licence Exchange n’est requise. Nous vous recommandons d’utiliser la licence Salles de réunion pour les comptes de ressources.


### <a name="add-a-resource-account"></a>Ajouter un compte de ressource

1. Connectez-vous à Exchange Online PowerShell. Pour obtenir des instructions, [voir Se connecter à Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)

2. Dans Exchange Online PowerShell, créez une boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante.

   - Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

     - Nom : Bldle-Room-01

     - Alias : BldleRoom01

     - Compte : huddleroom01@contoso.onmicrosoft.com

     - Mot de passe de compte : P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple active le compte de la boîte aux lettres de salle existante qui a la valeur d’alias BldleRoom02 et définit le mot de passe sur 808P@$$W 0rd. Notez que le compte sera HuddleRoom02@contoso.onmicrosoft.com en raison de la valeur d’alias existante.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Pour plus d’informations sur la syntaxe et les paramètres, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)


3. Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de la salle pour améliorer l’expérience de réunion :

   - AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent directement la décision de réservation de salle sans intervention humaine : libre = accepter ; occupé = refus.)

   - AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)

   - DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)

   - SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)

   - RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste tel que spécifié.)

   - AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - Réponse supplémentaire : « Cette salle dispose d’une barre de collaboration pour Microsoft Teams ! » (Le texte supplémentaire à ajouter à la demande de réunion.)

   Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommée Bldle-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Connectez-vous à MS Online PowerShell pour définir les paramètres Active Directory en exécutant `Connect-MsolService -Credential $cred` l’cmdlet PowerShell.   Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge. 

5. Définissez le mot de passe huddleroom01@contoso.onmicrosoft.com ne pas expirer en utilisant la syntaxe suivante :

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. Le compte de ressource doit avoir une licence Office 365 valide, de préférence la référence SKU de salle de réunion. Vous devez également affecter un emplacement d’utilisation à votre compte d’appareil, ce qui détermine les S SKD de licence disponibles pour votre compte. Vous pouvez `Get-MsolAccountSku` l’utiliser pour récupérer la liste des SKT disponibles pour votre client Office 365.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Vous pouvez attribuer la licence à l’aide de Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Pour obtenir des instructions détaillées, voir Attribuer des licences à des comptes d’utilisateurs [avec PowerShell Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)




[Configurer des comptes pour les barres de collaboration pour Microsoft Teams à l’aide de PowerShell](resource-account-ps.md)

[Déployer des barres de collaboration pour Microsoft Teams](collab-bar-deploy.md)

[Barres de collaboration pour la gestion des licences Microsoft Teams](../rooms/rooms-licensing.md)


