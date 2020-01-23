---
title: Déploiement de salles de Microsoft teams avec Exchange en local
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Consultez cette rubrique pour plus d’informations sur le déploiement de salles de Microsoft teams dans un environnement hybride avec Exchange sur site.
ms.openlocfilehash: c8309f4d7007bcd249334c554d284e5be00bfa16
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268928"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Déploiement de salles de Microsoft teams avec Exchange en local

Pour plus d’informations sur le déploiement de salles de Microsoft teams dans un environnement hybride avec Exchange en local et Microsoft teams ou Skype entreprise Online, reportez-vous à cette rubrique.
  
Si votre organisation dispose d’une combinaison de services, avec une partie hébergée en local et une partie hébergée en ligne, votre configuration dépend de l’emplacement d’hébergement de chaque service. Cette rubrique traite des déploiements hybrides pour les salles de Microsoft teams sur lesquelles Exchange est hébergé sur site. Dans la mesure où ce type de déploiement comporte autant de variations différentes, il n’est pas possible de fournir des instructions détaillées pour chacune d’elles. Le processus suivant fonctionne pour de nombreuses configurations. Si le processus ne vous convient pas, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final qu’indiqué ici, et pour d’autres options de déploiement.

Microsoft fournit [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous permet de créer de nouveaux comptes d’utilisateur, ou de valider des comptes de ressources existants dont vous disposez pour vous aider à les convertir en comptes d’utilisateurs de salles Microsoft teams compatibles. Si vous le souhaitez, vous pouvez suivre les étapes ci-dessous afin de configurer des comptes que votre appareil de salle Microsoft teams utilisera.
  
## <a name="requirements"></a>Configuration requise

Avant de déployer des salles Microsoft teams avec Exchange en local, assurez-vous que vous remplissez les conditions requises. Pour plus d’informations, voir la [Configuration requise pour Microsoft teams salles](requirements.md).
  
Si vous déployez des salles Microsoft teams avec Exchange en local, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local. Ce compte sera synchronisé avec Office 365. Vous devrez réaliser les opérations suivantes :
  
- Création d’un compte et synchronisation avec Active Directory

- Activation de la boîte aux lettres distante et définition des propriétés

- Attribuez une licence Office 365.

- Activez le compte de l’appareil avec Skype entreprise Server. Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :

  - Vous devez disposer de Skype entreprise Online (plan 2) ou d’une version ultérieure dans votre plan Office 365. Le plan doit prendre en charge la fonctionnalité de conférence.
  
  - Si vous avez besoin d’une voix entreprise (RTC) avec des fournisseurs de service de téléphonie pour Microsoft Teams, vous avez besoin de Skype entreprise Online (plan 3).
  
  - Les utilisateurs de votre client doivent avoir des boîtes aux lettres Exchange.
  
  - Votre compte Microsoft teams Room nécessite une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3), mais elle ne nécessite pas de licence Exchange Online.

- Affectez une licence Skype entreprise Server à votre compte Microsoft teams Room.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Création d’un compte et synchronisation avec Active Directory

1. Dans l’outil **utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur le dossier ou l’unité d’organisation dans lequel les comptes de Microsoft teams seront créés, cliquez sur **nouveau**, puis sur **utilisateur**.

2. Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.

3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > Le fait de sélectionner un **mot de passe n’expire jamais** est requis pour Skype entreprise Server sur les salles de Microsoft Teams. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Si tel est le cas, vous devez créer une exception pour chaque compte d’appareil Microsoft Teams.
  
4. Une fois le compte créé, exécutez une synchronisation de répertoire. Lorsque vous avez terminé, accédez à la page utilisateurs du centre d’administration Microsoft 365 et vérifiez que le compte créé lors des étapes précédentes a été fusionné en ligne.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Activation de la boîte aux lettres distante et définition des propriétés

1. [Ouvrez Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [Connectez-vous à votre serveur Exchange à l’aide de Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. Dans Exchange PowerShell, en utilisant la commande suivante, la boîte aux lettres du compte (activée par boîte aux lettres) s’exécute à l’aide de la commande suivante :

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [activer-boîte aux lettres](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. Dans Exchange PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’interface utilisateur :

   - AutomateProcessing : l’acceptation automatique (les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine : gratuit = accepter ; occupé = refuser.)

   - AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté au sujet de la demande de réunion.)

   - DeleteComments : $false (conservez le texte dans le corps des demandes de réunion entrantes).

   - DeleteSubject : $false (conserver le sujet des demandes de réunion entrantes).

   - RemovePrivateProperty : $false (vérifie que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste indiqué.)

   - AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)

   - AdditionalResponse : « il s’agit d’une salle de réunion Skype ! » (Le texte supplémentaire à ajouter à la demande de réunion.)

   Cet exemple configure ces paramètres sur la boîte aux lettres de salle nommée Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Affectation d’une licence Office 365

1. Se connecter à Azure Active Directory. Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge. 

2. Le compte d’appareil doit avoir une licence Office 365 valide ou Exchange et Microsoft Teams ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> pour récupérer la liste des références SKU disponibles.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Vous pouvez ensuite ajouter une licence à l’aide du`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> applet. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Pour obtenir des instructions détaillées, voir [attribuer des licences à des comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Activer le compte de l’appareil

PowerShell Skype entreprise Online permet de gérer les services de Microsoft teams et de Skype entreprise online.

1. Créez une session Windows PowerShell distante à partir d’un PC comme suit :

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Obtenez l’adresse SIP du compte :

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Pour activer votre compte Microsoft teams Room, exécutez la commande suivante :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un utilisateur existant à l’aide de la commande suivante :

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Attribution d’une licence à votre compte Microsoft teams

1. Ouvrez une session en tant qu’administrateur client, ouvrez le portail d’administration Office 365, puis cliquez sur l’application Administration.
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
3. Cliquez sur le compte Microsoft Teams, puis cliquez sur l’icône représentant un crayon pour modifier les informations de compte.
4. Cliquez sur **Licences**.
5. Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise. Vous devez utiliser une licence de plan 3 Si vous souhaitez utiliser Enterprise Voice dans vos salles Microsoft Teams.
6. Cliquez sur **Enregistrer**.

Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client pour vous connecter à ce compte.
  
## <a name="see-also"></a>Voir aussi

[Configurer des comptes pour les salles de Microsoft teams](rooms-configure-accounts.md)

[Plan pour les salles de Microsoft teams](rooms-plan.md)
  
[Déploiement de salles de Microsoft teams](rooms-deploy.md)
  
[Configurer une console de salle Microsoft teams](console.md)
  
[Gérer Microsoft Teams Rooms](rooms-manage.md)
