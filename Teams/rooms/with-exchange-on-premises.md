---
title: Déployer Salles Microsoft Teams déploiement Exchange local (hybride)
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Lisez cette rubrique pour plus d’informations sur le déploiement d Salles Microsoft Teams dans un environnement hybride avec des Exchange en local.
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767227"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Déployer Salles Microsoft Teams avec Exchange local (hybride)

Lisez cette rubrique pour plus d’informations sur le déploiement d Salles Microsoft Teams dans un environnement hybride avec des Exchange locaux et Microsoft Teams.
  
Si votre organisation dispose d’un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne, votre configuration dépend de l’endroit où chaque service est hébergé. Cette rubrique traite des déploiements hybrides Salles Microsoft Teams avec Exchange sur site. Ce type de déploiement étant très différent, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre eux. Le processus suivant fonctionne pour de nombreuses configurations. Si le processus n’est pas configuré pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final que celui documenté ici, ainsi que pour d’autres options de déploiement.
  
## <a name="requirements"></a>Conditions requises

Avant de déployer Salles Microsoft Teams avec Exchange local, assurez-vous que vous avez satisfait aux exigences. Pour plus d’informations, [voir Salles Microsoft Teams requise.](requirements.md)

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Activation de la boîte aux lettres distante et définition des propriétés

1. [Ouvrez Exchange Management Shell ou](/powershell/exchange/exchange-server/open-the-exchange-management-shell) connectez-vous à votre serveur Exchange à [l’aide de Remote PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. Dans Exchange PowerShell, créez une boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante. Par défaut, les boîtes aux lettres de salle n’ayant pas de comptes associés, vous devez ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier auprès d’Microsoft Teams.

   - Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

     - Compte : ConferenceRoom01@contoso.com
  
     - Nom : ConferenceRoom01

     - Alias : ConferenceRoom01

     - Mot de passe de compte : P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
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

3. Dans Exchange PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :

   - AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent les décisions de réservation de salle directement sans intervention humaine).

   - AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)

   - DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)

   - SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)

   - RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion initiale reste tel que spécifié.)

   - AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - Réponse supplémentaire : « Il s’agit d’Microsoft Teams salle de réunion ! » (Texte supplémentaire à ajouter à la demande de réunion.

   Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommée ConferenceRoom01.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="set-password-to-never-expire"></a>Définir un mot de passe pour qu’il n’expire jamais

1. Dans **l’outil Utilisateurs** et ordinateurs Active Directory, recherchez le compte de Salles Microsoft Teams, cliquez dessus avec le bouton droit, puis sélectionnez **Propriétés.**

2. Cochez la **case Mot de passe n’expire** jamais, puis cliquez sur **OK.**

   > [!NOTE]
   > La sélection **du mot de passe n’expire** jamais est une obligation pour Salles Microsoft Teams. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Si c’est le cas, vous devez créer une exception pour chaque Salles Microsoft Teams compte.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Affecter une licence Microsoft 365 licence Office 365 licence

1. Connecter à Azure Active Directory. Pour plus d’Azure Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge. 

2. Le compte de ressource doit avoir une licence Microsoft 365 ou Office 365 valide, ou Exchange et Microsoft Teams ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte de ressource. Cela détermine les S SKD de licence disponibles pour votre compte. Vous pouvez utiliser `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer la liste des S SKUs disponibles.

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. Ensuite, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Cet exemple ajoute la licence Salle de réunion compte :

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

Pour validation, vous pouvez utiliser n’importe quel client pour vous connecter à ce compte.
  
## <a name="related-topics"></a>Sujets associés

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)
