---
title: Création de comptes de ressources de Microsoft teams pour les barres de collaboration de Microsoft teams à l’aide de PowerShell
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
description: Consultez cette rubrique pour plus d’informations sur le déploiement de barres de collaboration pour Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268028"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Créer un compte de ressources Microsoft 365 à l’aide de PowerShell

Consultez cette rubrique pour plus d’informations sur la création de comptes de ressources pour les barres de collaboration de Microsoft teams à l’aide de PowerShell.

Pour créer un compte de ressources, le plus simple consiste à utiliser le centre d’administration Microsoft 365. [Pour plus d’informations, consultez cet article](resource-account-ui.md).

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Configuration requise

Avant de déployer des salles Microsoft teams avec Office 365, assurez-vous que vous remplissez les conditions requises. Pour plus d’informations, reportez-vous à la section [déploiement de barres de collaboration pour Microsoft teams](collab-bar-deploy.md).

- Si vous avez besoin des fonctionnalités RTC pour la barre de collaboration, vous aurez besoin d’une licence de système téléphonique.

- Vos comptes de ressources doivent avoir des boîtes aux lettres Exchange. Étant donné qu’il s’agit de comptes de ressources, aucune licence Exchange n’est requise. Nous vous recommandons d’utiliser la licence de salles de réunion pour les comptes de ressources.


### <a name="add-a-resource-account"></a>Ajouter un compte de ressource

1. Connectez-vous à Exchange Online PowerShell. Pour obtenir des instructions, voir [se connecter à Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. Dans Exchange Online PowerShell, créez une nouvelle boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante.

   - Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

     - Nom : Huddle-salle-01

     - Alias : HuddleRoom01

     - Compte : huddleroom01@contoso.onmicrosoft.com

     - Mot de passe du compte : P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Dans cet exemple, le compte de la boîte aux lettres de salle existante possède la valeur alias HuddleRoom02 et le mot de passe est défini sur 808P@ $ $W 0rd. Notez que le compte sera HuddleRoom02@contoso.onmicrosoft.com en raison de la valeur de l’alias existant.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Pour plus d’informations sur les paramètres de syntaxe et de paramètre, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’interface utilisateur :

   - AutomateProcessing : l’acceptation automatique (les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine : gratuit = accepter ; occupé = refuser.)

   - AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté au sujet de la demande de réunion.)

   - DeleteComments : $false (conservez le texte dans le corps des demandes de réunion entrantes).

   - DeleteSubject : $false (conserver le sujet des demandes de réunion entrantes).

   - RemovePrivateProperty : $false (vérifie que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste indiqué.)

   - AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - AdditionalResponse : « cette salle possède une barre de collaboration pour Microsoft teams ! » (Le texte supplémentaire à ajouter à la demande de réunion.)

   Cet exemple configure ces paramètres sur la boîte aux lettres de salle nommée Huddle-salle-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Connectez-vous à MS Online PowerShell pour créer des paramètres Active Directory en exécutant l’applet de contrôle `Connect-MsolService -Credential $cred` PowerShell.   Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge. 

5. Définissez le mot de passe pour huddleroom01@contoso.onmicrosoft.com pour qu’il n’expire pas en utilisant la syntaxe suivante :

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. Le compte de ressource doit disposer d’une licence Office 365 valide, de préférence du SKU de la salle de réunion. Vous devez également attribuer un emplacement d’utilisation à votre compte d’appareil : cela détermine les références SKU de licence disponibles pour votre compte. Vous pouvez utiliser `Get-MsolAccountSku` pour récupérer la liste des références SKU disponibles pour votre client Office 365.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Vous pouvez attribuer la licence à l’aide de Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Pour obtenir des instructions détaillées, voir [attribuer des licences à des comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).




[Configurer les comptes pour les barres de collaboration de Microsoft teams à l’aide de PowerShell](resource-account-ps.md)

[Déploiement de barres de collaboration pour Microsoft teams](collab-bar-deploy.md)

[Barres de collaboration pour la gestion des licences Microsoft teams](../rooms/rooms-licensing.md)


