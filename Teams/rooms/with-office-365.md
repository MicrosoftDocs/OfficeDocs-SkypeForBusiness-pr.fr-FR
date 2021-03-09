---
title: Déployer des salles Microsoft Teams avec Microsoft 365 ou Office 365
ms.author: v-cichur
author: cichur
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams avec Microsoft 365 ou Office 365, où Teams ou Skype Entreprise et Exchange sont tous deux en ligne.
ms.openlocfilehash: 7a25fb17e4b9fce4a51c6e2be5828ecafff59894
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569120"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Déployer des salles Microsoft Teams avec Microsoft 365 ou Office 365

Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams avec Microsoft 365 ou Office 365, où Microsoft Teams ou Skype Entreprise et Exchange sont tous deux en ligne.

La manière la plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de la Windows PowerShell. Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer de nouveaux comptes d’utilisateurs, ou à valider les comptes de ressources existants que vous avez afin de vous aider à les transformer en comptes d’utilisateurs de salles Microsoft Teams compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer des comptes que votre appareil Microsoft Teams Rooms utilisera.

## <a name="requirements"></a>Conditions requises

Avant de déployer salles Microsoft Teams avec Microsoft 365 ou Office 365, assurez-vous que vous avez la qualité requise. Pour plus d’informations, consultez [la conditions requises pour les salles Microsoft Teams.](requirements.md)

Pour activer Skype Entreprise, vous devez avoir les produits suivants :

- Skype Entreprise Online (plan 2, ou offre d’entreprise) ou version supérieure dans votre offre Microsoft 365 ou Office 365. Le plan doit autoriser les fonctionnalités de conférences téléphoniques.

- Si vous avez besoin de fonctionnalités de connexion à partir d’une réunion, vous avez besoin d’une licence Audioconférence et d’un système téléphonique.  Si vous avez besoin de fonctionnalités d’appel sortant pour une réunion, vous avez besoin d’une licence d’audioconférence.

- Vos utilisateurs clients doivent avoir une boîte aux lettres Exchange.

- Votre compte Salles Microsoft Teams requiert au minimum une licence Skype Entreprise Online (plan 2), mais pas une licence Exchange Online. Pour plus d’informations, consultez les [licences Salles Microsoft Teams.](rooms-licensing.md)

Pour plus d’informations sur les plans Skype Entreprise Online, consultez la [description du service Skype Entreprise Online.](https://technet.microsoft.com/library/jj822172.aspx)

### <a name="add-a-device-account"></a>Ajout d’un compte d’appareil

1. Connectez-vous à Exchange Online PowerShell. Pour obtenir des instructions, [voir Se connecter à Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. Dans Exchange Online PowerShell, créez une boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante. Par défaut, les boîtes aux lettres de salle n’ayant pas de comptes associés, vous devez ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier auprès des systèmes de salle Skype v2.

   - Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

     - Nom : Rigel-01

     - Alias : Rigel1

     - Compte : Rigel1@contoso.onmicrosoft.com

     - Mot de passe de compte : P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Cet exemple active le compte de la boîte aux lettres de salle existante qui possède la valeur d’alias Rigel2 et définit le mot de passe sur 9898P@$$W 0rd. Notez que le compte sera Rigel2@contoso.onmicrosoft.com en raison de la valeur d’alias existante.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Pour plus d’informations sur la syntaxe et les paramètres, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

3. Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de la salle pour améliorer l’expérience de réunion :

   - AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent la décision de réservation de salle directement sans intervention humaine : libre = accepter ; occupé = refus.)

   - AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)

   - DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)

   - SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)

   - RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion initiale reste tel que spécifié.)

   - AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - Réponse supplémentaire : « Il s’agit d’une salle de réunion Skype ! » (Le texte supplémentaire à ajouter à la demande de réunion.)

   Cet exemple configure ces paramètres sur la boîte aux lettres de salle rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Connectez-vous à MS Online PowerShell pour définir les paramètres Active Directory en exécutant `Connect-MsolService -Credential $cred` l’cmdlet PowerShell. Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge.

5. Si vous ne souhaitez pas que le mot de passe expire, utilisez la syntaxe suivante :

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Cet exemple définit le mot de passe du compte pour Rigel1@contoso.onmicrosoft.com à n’expirer jamais.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> Si le mot de passe n’est pas réglé sur Jamais expirer, le compte ne se connecte plus sur l’appareil une fois la période d’expiration atteinte. Le mot de passe devra alors être modifié pour le compte et mis à jour localement sur l’appareil MTR.

6. Le compte d’appareil doit avoir une licence Microsoft 365 ou Office 365 valide, ou exchange et Microsoft Teams ou Skype Entreprise ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer la liste des S SKUs disponibles pour votre organisation Microsoft 365 ou Office 365 comme suit :

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Ensuite, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Cet exemple ajoute la licence salle de réunion au compte :

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Pour obtenir des instructions détaillées, voir Attribuer des licences à des comptes d’utilisateurs [avec PowerShell Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Vous pouvez également ajouter des fonctionnalités Phone System à ce compte, mais vous devez tout d’abord la configurer. Pour [plus d’informations, voir Qu’est-ce que](../what-is-phone-system-in-office-365.md) le système téléphonique ? Cet exemple ajoute le plan Appels nationaux et internationaux PSTN :

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Ensuite, vous devez activer le compte d’appareil avec Skype Entreprise. Assurez-vous que votre environnement répond aux exigences définies dans la exigences des [salles Microsoft Teams.](requirements.md)

   Démarrez une [session Windows PowerShell distance](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) comme suit (n’oubliez pas d’installer les [composants PowerShell de Skype](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)Entreprise Online) :

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.
>
> Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   Obtenez les informations registrarPool à partir du nouveau compte d’utilisateur en cours de configuration, comme illustré dans l’exemple ci-après :

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Ensuite, activez votre compte Salles Microsoft Teams pour Skype Entreprise Server en exécutant l’cmdlet suivante :

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Il est possible que les nouveaux comptes d’utilisateurs ne soient pas créés dans le même pool de bureaux d’enregistrement que les comptes d’utilisateurs existants du client. La commande ci-dessus permet d’éviter les erreurs de configuration de compte en raison de cette situation.

## <a name="validate"></a>Validate

Pour validation, vous pouvez utiliser n’importe quel client Skype Entreprise pour vous connectez au compte que vous avez créé.

## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Déployer les Salles Microsoft Teams](rooms-deploy.md)

[Configurer une console des salles Microsoft Teams](console.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Licences de salles Microsoft Teams](rooms-licensing.md)
