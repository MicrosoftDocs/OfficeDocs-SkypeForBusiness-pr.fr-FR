---
title: Déployer des salles Microsoft Teams avec Exchange Online
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
description: Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams avec Exchange Online et Skype Entreprise Server sur site.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662309"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Déployer des salles Microsoft Teams avec Exchange Online

Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams avec Exchange Online et Skype Entreprise Server sur site.
  
Si votre organisation dispose d’un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne, votre configuration dépend de l’endroit où chaque service est hébergé. Cette rubrique traite des déploiements hybrides de salles Microsoft Teams avec Exchange hébergé en ligne. Ce type de déploiement étant très différent, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre eux. Le processus suivant fonctionne pour de nombreuses configurations. Si le processus n’est pas configuré pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final que celui documenté ici, ainsi que pour d’autres options de déploiement.

La manière la plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de la Windows PowerShell. Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer de nouveaux comptes d’utilisateurs, ou à valider les comptes de ressources existants que vous avez afin de vous aider à les transformer en comptes d’utilisateurs de salles Microsoft Teams compatibles. Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer des comptes que votre appareil Microsoft Teams Rooms utilisera.

## <a name="requirements"></a>Conditions requises

Avant de déployer des salles Microsoft Teams avec Exchange Online, assurez-vous que vous disposez de la version requise. Pour plus d’informations, consultez [la conditions requises pour les salles Microsoft Teams.](requirements.md)
  
Pour déployer des salles Microsoft Teams avec Exchange Online, suivez les étapes ci-dessous. Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées. 

   > [!NOTE]
   >  Le [module Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) pour les applets de commande Windows PowerShell dans cette section (par exemple, Set-MsolUser) a été testé dans le cadre de la configuration de comptes pour les appareils Microsoft Teams Rooms. Il est possible que d’autres cmdlets fonctionnent, toutefois, elles n’ont pas été testées dans ce scénario particulier.

Si vous avez déployé les services AD FS (Active Directory Federation Services), vous deront peut-être convertir le compte d’utilisateur en utilisateur géré avant de suivre ces étapes, puis convertir l’utilisateur en utilisateur fédéré une fois ces étapes terminées.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Création d’un compte et définition des propriétés Exchange

1. Démarrez une session Windows PowerShell session distante sur un PC et connectez-vous à Exchange Online comme suit :

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Après avoir établi une session, vous allez créer une boîte aux lettres et l’activer en tant que compte RoomMailboxAccount, ou modifier les paramètres d’une boîte aux lettres de salle existante. Cela permet au compte de s’authentifier dans Salles Microsoft Teams.

   Si vous modifiez une boîte aux lettres de ressource :

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si vous créez une boîte aux lettres de ressources :

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Pour améliorer l’expérience de réunion, vous devez définir les propriétés Exchange sur le compte d’utilisateur comme suit :

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Ajout d’une adresse e-mail pour votre compte de domaine sur site

1. Dans l’outil Utilisateurs et ordinateurs **Active Directory AD,** cliquez avec le bouton droit sur le conteneur ou l’unité organisationnelle dans qui vos comptes Salles Microsoft Teams seront créés, cliquez sur **Nouveau,** puis sur **Utilisateur.**
2. Tapez le nom d’affichage (- Identité) de l’cmdlet  précédente (Set-Mailbox ou  New-Mailbox) dans la zone Nom complet et l’alias dans la zone Nom de l’utilisateur. Cliquez sur **Suivant**.
3. Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.

    > [!NOTE]
    > La sélection **du mot de passe n’expire** jamais est obligatoire pour Skype Entreprise Server sur les salles Microsoft Teams. Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe. Si c’est le cas, vous devez créer une exception pour chaque compte d’utilisateur Salles Microsoft Teams.
  
4. Cliquez sur **Terminer** pour créer le compte.
5. Après avoir créé le compte, exécutez une synchronisation d’annuaires. Cela peut être réalisé à l’aide de la configuration [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) dans PowerShell. Une fois cette procédure terminée, allez à la page Utilisateurs et vérifiez que les deux comptes créés lors des étapes précédentes ont été fusionnés.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Attribuer une licence Microsoft 365 ou Office 365

1. Tout d’abord, connectez-vous à Azure AD pour appliquer certains paramètres de compte. Pour vous connecter, vous pouvez exécuter l’applet de commande suivante. Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 n’est](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. Le compte d’utilisateur doit avoir une licence Microsoft 365 ou Office 365 valide pour s’assurer qu’Exchange et Skype Entreprise Server fonctionnent. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous devez effectuer le devoir dans une étape suivante.
3. Ensuite, utilisez `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> pour récupérer la liste des S SKUs disponibles pour votre organisation Microsoft 365 ou Office 365.
4. Une fois les S SKUs répertoriées, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK). 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Activer le compte d’utilisateur avec Skype Entreprise Server

1. Créez une session Windows PowerShell distance à partir d’un PC comme suit :

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.
>
> Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Pour activer votre compte Salles Microsoft Teams pour Skype Entreprise Server, exécutez la commande ci-après :

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur auprès d’un utilisateur existant de Skype Entreprise Server à l’aide de cette commande.

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Affecter une licence Skype Entreprise Server à votre compte Salles Microsoft Teams

1. Connectez-vous en tant qu’administrateur client, ouvrez le Centre d’administration Microsoft 365, puis cliquez sur l’application Administrateur.
2. Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.
3. Cliquez sur le compte Salles Microsoft Teams, puis sur l’icône de stylet pour modifier les informations sur le compte.
4. Cliquez sur **Licences**.
5. Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise. Vous devez utiliser une licence Plan 3 si vous souhaitez utiliser Voix Entreprise salles Microsoft Teams.
6. Cliquez sur **Enregistrer**.

Pour validation, vous pouvez utiliser n’importe quel client Skype Entreprise pour vous connecter à ce compte.

> [!NOTE]
> Si vous utilisez actuellement les références E1, E3, E4 ou E5 avec Skype Entreprise Plan 2 avec Audioconférence ou Phone System et un plan d’appels, celles-ci continueront de fonctionner. Toutefois, vous devez envisager de passer à un modèle de licence plus simple, comme décrit dans la mise à jour des licences de salle de réunion [Teams,](rooms-licensing.md)une fois les licences actuelles expirées.

> [!IMPORTANT]
> Si vous utilisez Le plan 2 de Skype Entreprise, vous ne pouvez utiliser que les salles Microsoft Teams en mode Skype Entreprise, ce qui signifie que toutes vos réunions seront des réunions Skype Entreprise. Pour activer votre salle de réunion pour les réunions Microsoft Teams, nous vous recommandons d’acheter la licence Salle de réunion.
  
## <a name="related-topics"></a>Sujets associés

[Configurer des comptes pour les salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)
