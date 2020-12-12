---
title: Déploiement de salles de Microsoft teams avec Exchange Online
ms.author: dstrome
author: dstrome
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Consultez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft teams avec Exchange Online et Skype entreprise Server en local.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662309"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Déploiement de salles de Microsoft teams avec Exchange Online

Consultez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft teams avec Exchange Online et Skype entreprise Server en local.
  
Si votre organisation dispose d’une combinaison de services, avec une partie hébergée en local et une partie hébergée en ligne, votre configuration dépend de l’emplacement d’hébergement de chaque service. Cette rubrique traite des déploiements hybrides pour les salles Microsoft teams avec Exchange hébergé en ligne. Dans la mesure où ce type de déploiement comporte autant de variations différentes, il n’est pas possible de fournir des instructions détaillées pour chacune d’elles. Le processus suivant fonctionne pour de nombreuses configurations. Si le processus ne vous convient pas, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final qu’indiqué ici, et pour d’autres options de déploiement.

Le moyen le plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de Windows PowerShell distant. Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script permettant de créer de nouveaux comptes d’utilisateurs, ou de valider des comptes de ressources existants dont vous avez besoin afin de vous aider à les convertir en comptes d’utilisateurs de salles Microsoft teams compatibles. Si vous le souhaitez, vous pouvez suivre les étapes ci-dessous afin de configurer des comptes que votre appareil de salle Microsoft teams utilisera.

## <a name="requirements"></a>Configuration requise

Avant de déployer des salles Microsoft teams avec Exchange Online, assurez-vous que vous remplissez les conditions requises. Pour plus d’informations, voir la [Configuration requise pour Microsoft teams salles](requirements.md).
  
Pour déployer des salles Microsoft teams avec Exchange Online, suivez les étapes ci-dessous. Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées. 

   > [!NOTE]
   >  Le [module Azure Active Directory pour les applets de contrôle Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) de cette section (par exemple, Set-MsolUser) a été testé dans la configuration de comptes pour les appareils Microsoft Teams. Il est possible que d’autres cmdlets puissent fonctionner, mais qui n’ont pas été testées dans ce scénario spécifique.

Si vous avez déployé les services AD FS (Active Directory Federation Services), il est possible que vous deviez convertir le compte d’utilisateur en utilisateur géré avant de suivre ces étapes, puis de reconvertir l’utilisateur en utilisateur fédéré une fois ces étapes terminées.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Création d’un compte et définition des propriétés Exchange

1. Démarrez une session Windows PowerShell distante sur un PC et connectez-vous à Exchange Online en procédant comme suit :

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Après avoir établi une session, vous pouvez créer une nouvelle boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou changer les paramètres d’une boîte aux lettres de salle existante. Cela permettra au compte d’s’authentifier dans les salles de Microsoft Teams.

   Si vous modifiez une boîte aux lettres de ressource :

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si vous créez une nouvelle boîte aux lettres de ressources :

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Pour améliorer l’utilisation de la réunion, vous devez définir les propriétés Exchange sur le compte d’utilisateur comme suit :

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Ajout d’une adresse e-mail pour votre compte de domaine sur site

1. Dans l’outil d' **annonce utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur le conteneur ou l’unité d’organisation dans lequel vos comptes Microsoft teams seront créés, cliquez sur **nouveau**, puis sur **utilisateur**.
2. Entrez le nom d’affichage (-identité) à partir de l’applet de connexion précédente (Set-Mailbox ou New-Mailbox) dans la zone **nom complet** et l’alias dans la zone nom **d’utilisateur** de l’utilisateur. Cliquez sur **Suivant**.
3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > Le fait de sélectionner un **mot de passe n’expire jamais** est requis pour Skype entreprise Server sur les salles de Microsoft Teams. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Si tel est le cas, vous devez créer une exception pour chaque compte d’utilisateur de Microsoft Teams.
  
4. Cliquez sur **Terminer** pour créer le compte.
5. Une fois le compte créé, effectuez une synchronisation d’annuaires. Pour ce faire, vous pouvez utiliser [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) dans PowerShell. Lorsque vous avez terminé, accédez à la page utilisateurs et vérifiez que les deux comptes créés aux étapes précédentes ont été fusionnés.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Attribution d’une licence Microsoft 365 ou Office 365

1. Tout d’abord, connectez-vous à Azure AD pour appliquer des paramètres de compte. Pour vous connecter, vous pouvez exécuter l’applet de commande suivante. Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. Le compte d’utilisateur doit avoir une licence Microsoft 365 ou Office 365 valide pour garantir le bon fonctionnement d’Exchange et de Skype entreprise Server. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous devez créer le devoir à l’étape suivante.
3. Utilisez ensuite `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> pour récupérer la liste des références SKU disponibles pour votre organisation Microsoft 365 ou Office 365.
4. Une fois que vous avez répertorié les références (SKU), vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> applet. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK). 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Activer le compte utilisateur avec Skype entreprise Server

1. Créez une session Windows PowerShell distante à partir d’un PC comme suit :

> [!NOTE]
> Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.
>
> Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Pour activer votre compte Microsoft teams pour Skype entreprise Server, exécutez la commande suivante :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si vous n’êtes pas sûr de la valeur à utiliser pour le paramètre RegistrarPool de votre environnement, vous pouvez obtenir la valeur d’un utilisateur Skype entreprise Server existant à l’aide de la commande suivante

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Affectation d’une licence Skype entreprise Server à votre compte Microsoft teams

1. Connectez-vous en tant qu’administrateur client, ouvrez le centre d’administration Microsoft 365, puis cliquez sur l’application Administration.
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
3. Cliquez sur le compte Microsoft Teams, puis cliquez sur l’icône représentant un crayon pour modifier les informations de compte.
4. Cliquez sur **Licences**.
5. Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise. Vous devez utiliser une licence de plan 3 Si vous souhaitez utiliser Enterprise Voice sur les salles de Microsoft Teams.
6. Cliquez sur **Enregistrer**.

Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client Skype entreprise pour vous connecter à ce compte.

> [!NOTE]
> Si vous utilisez actuellement E1, E3, E4 ou E5 avec Skype entreprise plan 2 avec audioconférence ou avec un système téléphonique et un plan d’appels, ces références continuent de fonctionner. Néanmoins, vous devez envisager de migrer vers un modèle de licence plus simple, comme décrit dans la rubrique mise à jour de la gestion des licences de la [salle de réunion teams](rooms-licensing.md), après l’expiration des licences actuelles.

> [!IMPORTANT]
> Si vous utilisez le plan 2 de Skype entreprise, vous ne pouvez utiliser que le mode Skype entreprise uniquement en mode Skype entreprise, ce qui signifie que toutes vos réunions seront des réunions Skype entreprise. Pour pouvoir activer la salle de réunion pour les réunions Microsoft Teams, nous vous recommandons d’acheter la licence de salle de réunion.
  
## <a name="related-topics"></a>Sujets associés

[Configurer des comptes pour les salles de Microsoft teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)
